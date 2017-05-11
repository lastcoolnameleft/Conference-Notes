* What is container?
  * App packaging and deployment mechanism
  * When you package, a shared lib moves into the container itself
  * Shared lib with v1 and v2 can be deployed
  * Also a Package distribution mechanism
    * ACR
  * Image you know works -> Image to you know works everywhere
  * Clear boundary for your stuff
  * Runtime isolation
    * Can run prod web server + Intern's Minecraft
    * NOT a security boundary
    * Run apps at greater density
* Container orchestator?
  * Programs crash!
    * Standardize support services
      * Restart
      * Log rolling
  * Target CI/CD
  * You talk to container service
    * It creates Orchestraor for you.
    * After that, you talk to native API yourself
* Most incidents are self inflicted
  * Jack knife a trailer
  * If backing up, is complicated 
  * Want to decouple 
  * Decouple SRE
    * App SRE
    * Cluster SRE
    * Kernel/os sre - iaas virt 
    * H/w SRE - Azure does this
  * People talk about dev ops
    * Really dev ops own the app SRE side
    * Cluster SRE is also devops
* Preview of Draft 
  * Containers look too hard for devs to use
  * High conceptual overhead
  * "Draft create"
      * Detects python. 
      * "Draft up"
      * Ships source code from laptop and sends to K8s
* Gitlab demo
    * Deployed on Acs
    * Cloned simple ruby app
    * Running on K8S
    * Great, simple demo of gitlab pushing from repo, to stg to prod
    * Only had to modify one file of location of service
* Glympse of future
    * Distributed systems are becoming more modular
    * "Before they were crafts people, but not democratized. No one builds GUI anymore"
    * Kube Lego - pays attention to http service. Delivers and renews cert. 
    * demoed using kube Lego to add tls cert to live service
    * "Let's encrypt " is CA Root - Acme for assigning cert
* K8s - can manage between 5k and RPi
* MySQL not really scalable. But looked at Percona
* Acs engine was almost called "Acs labs" as it's for more experimental designs
* Draining/ "session draining" and "readiness" to prevent new conn before ready. 