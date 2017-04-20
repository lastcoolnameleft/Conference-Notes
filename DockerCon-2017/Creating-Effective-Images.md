* Abby Fuller - Sr Tech Evangelist, AWS
* Before AWS was DevOps eng
* If you don't write images the smart way, you get paged at 2AM
* If you don't watch out, your images can be over a 1GB.  Giant
* Will cover
  * How layers word
  * basics for buidling minimal images
  * Best practices for Win Contaienrs
  * Dockerfile: good bad and bloated
  * docker security scan
  * Looking forward to future
* How do layers work?
  * Read-only layers (container base image, Ubuntu, those ro layers
  * Thin read-write layer (data, app code)
* Why do I cae how many layers?
  * More layers mean larger imge
    * larger image, longer build time, pull/push from reg
  * Smaller images mean faster builds, and faster deploys
    * Smaller attack surface
  * When moving to microservices, deploying more often
    * deploying image multiple times /week, be careful
* Ok, how can I reduce layers?
  * Sharing is caring
    * Limit data written to container layer
  * Chain RUN statements
* Building minimal inages: the basics
  * Dockerfile = series of instructiosn for building an image
* Cache rules everything around me
  * Wu-Tang - Cache rules everything around me.
  * anything you can re-use can save you time.
  * Not same for add/copy.  Looks at fingerprint of file
* Let's start with dockerfile
  * FROM ubuntu:latest; LABEL; RUN apt-get; COPY . /app; WORKDIR /app; RUN pip install; EXPOSE 5000; ENTRYPOINT ["python"]; CMD["app.py"]
  * Choose right base
    * ubuntu latest 458MB
    * python:2.7-alpine: 86.8MB
  * alpine latest: 3.9MB
* When do I want full base OS?
  * Do like it, but don't need it
  * Compliance
  * Security - someone else has gone through and verified
  * Ease of Dev - will have dev headers
    * Getting started, might care less about size
* Simple changes, big results
```FROM python:2.7-alpine```
# don't need apt-get
```
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
EXPOSE 5000
ENTRYPOINT ["python"]
CMD["app.py"]
```
* Fewer cache invalidations mean smaller images
```
COPY requirements.txt /app
* got app code?
ONBUILD ADD requirement.txt /app
ONBUILD RUN pip install -r /app/requirements.txt
ONBUILD COPY . /app
```
* Some high-level best practices
  * Port over existing VM workloads
  * Convert from existing win image
    * ConvertTo-Dockerfile
  * Convert from VHD
  ```
  ConverTo-Dockerfile -imagepath c:\vms\test.vhd -artifact IIS -artifactparam windows-container -Outputpath c:\windows-contaienrs
  ```
* Things to think about
  * Watch what you build
    * Building any of these patchs will be sad:
    * c: c:\ / /windows c:/windows
    * Might be removed to prevent building from those
 * Avoid installing packages with MSI
   * MSI installations are not space efficient.  This is no tthe same as linux distros; where you can add/use/rm the install files
   * Windows/Installer/<packager>.msi
   * Windows saves files for installs
* Dockerfiles - good, bad, bloated
```
from ubuntu
run apt-get update -y
run apt-get install -y python-pip python-dev build-essential
copy . /app
```
  * You think this is nice because you can comment each line
  * Optimize by running apt-get update and install on one line.
  * instead of invalidating cache, can chain run-commands 
  * Can do better
```
from python:2.7-alpne
```
    * removed apt-get 
  * Try custom base container
  ```FROM xxx.us-east1.amazon.com/dockercon-base:latest
  ```
    * Use shared base image
    * Use less space on ECS host
    * Build base for own language
  * Multi-base builds are even better
    * Recently announced
* use RUN statements effectiely
```
RUN apt-get update && apt-get install && rm -rf /var/lib/lists/*
```
* Switching USER adds layers
```
RUN groupAdd -r dockercon && ...
USER dockercon
```
  * If switching often, consider the fact that your dockerfile is handling too many things.
* Lots of distros will come with non-priv user already
  * Switch and dont' switch back.
* Avoid ADDing large files
  * BAD
  ```ADD http://...```
  * Best
  ```RUN mkdir -p curl \ 
  rm -rf x```
* Lang specific
  * Use 2 artifacts
    * One for artifact, one from base.
* goland
```from scratch
copy ./dockercon /dockercon
ENTRYPOINT ['/dockercon']
* Ruby
  * Official images for ruby are huge
  * every gem you have requires more gems
