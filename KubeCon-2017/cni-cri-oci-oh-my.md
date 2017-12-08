# CNI, CRI, and OCI, Oh My

* Who
  * Elise Philips
  * Paul Burt
* What is standard?  
  * ISO is well known:
  * Whatever the country, whatever the language, we are ISO
* You might have JS now, but you'd hate it even more if you had to write it for each different browser
* The same way JS enables multiple browsers to thrive, the standard does that
* In Container Space
  * Frakti - allow VM to plugin as Runtime
    * hypervisor based container
  * KataContainers - similar mindset
* What's a container?  TAR file (similar to zip file)
  * tar files + cgroups, chroot, unshare, nsenter, bind mounts 
  * Containers from Scratch - Eric Chiang
  * Best practices - Brian "redbeard"
* "Hell is someone else's dev environment"
* CNI - Container Network Interface
  * STarted by CoreOS
  * Only concerns itself only with n/w connectivity of containers by removing allocated resources when the container is deleted
  * CNI (coreos) vs CNM (docker) - Muhammad Ali vs Joe Fraiser
    * CNI pressured enough that CNM emerged
    * "CNM is designed to support the Docker runtime engine only"
  * adoped by CNCF
  * What is CNI plugin?
    * Just an executable?
    * creaes network namespace, and reads a JSOn config
    * runtime excx plugin by JSON name
    * plugin finds out what to do from JSON streams to stdin
    * plugin does its thing
    * If an error, runtime tells the plugin to delete (DEL)
    * Otherwise, the runtime cleans up (DEL) at end of lifecycle
  * Example config - plugin for bridge plugin
    * JSON: { name:myname, type:bridge, bridge: mynet0, isdefaultgw: true, forceaddress: false; ipmasq: true, hairpinmode: }
* notable developments this year:
  * IPv6
  * plugin chaining
  * port-forwarding
* hard NOT to use CNI now
  * Rapidly approaching 1.0
  * "All the cool plugins are using it"
* CRI - Container Runtime Interface
  * "Oh wow...I'm giving a book report on The Hobbit to JRR Tolken"
  * "Docker and rkt were integrated directly and deeply into kubelet source through internal and volatile interface"
  * CRI emerged as solution to that volatility
  * What does it look like?  Adapter
    * Added a wrapper around kubelet (gprc, protobuf)
    * Defines interface in consistent way
  * CRI timeline 
* "That's cool in a mom and dad got me socks for x-mas kind of way"
  * CRI-O - Minimal impl of runtime
  * OCI based impl of k8s container runtime interface
  * EASY to demo, but not enough time!
  * visit:  cri-o project on k8s incubator
  * Goal:  We don't need diff s/w ecosystem for every container format?  Thank goodness
* OCI
  * OCI is standard for each plug. 
    * e.g. we want to standardize both sides of equation
  * Docker - overloaded term
    * image format
    * container runtime
    * log collection daemon
    * init system + process babysitter
    * container image build system
    * remote mgmt API
* Timeline
  * Mid 2014
    * Docker was becoming popular
    * But image format was missing
  * Dec 2014
    * CoreOS created appc
    * image format + runtime env
    * appc has format image spec, image discovery 
  * April 2015
    * Docker image format progressed.  1st attempt at image spec
  * Two separate worlds.  media branded as "container wars"
    * Coreos was eager to work with Docker
    * Where OCI came in
  * What is OCI - Define what container is in an open way to everyone can impl it
  * What makes up the standard?
    * image-spec - what's in a container
      * video from "2017 what is a container" by Johnathan Boole
    * runtime spec  - how to run a container
      * On-disk layout of a container 
      * extracted root filesystem and config, easy to run
      * lifecycle verbs (start, etc.)
    * What happened to appc?
      * didnt make sense to exist
      * once it hit v1, deprecated it
  * OCI is 1st standard to hit 1.0
    * standardizes image format
    * Lots more to be done.
    * CSI - Container Storage Interface
      * Young standard, being worked on
* Standards will continue to evolve.  Will grow
  * lead to more optiosn for user
  * And that's somethign worth being passionate about
  * Check out Open Cloud Services on coreos.com/blog
* QnA
  * Are latest images by Docker OCI compat?  Yes.
    * can use Scopio to see how it works.  See index file which points to other manifests
