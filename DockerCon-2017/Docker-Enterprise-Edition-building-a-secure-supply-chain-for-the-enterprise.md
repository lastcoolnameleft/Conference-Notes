* Docker Enterprise Edition
  * CaaS enabled platform for modern s/w supply chain
  * Integrated orchestration, security and mgmt
  * predictable quarterly release with 1-yr of support and main
  * security patches and hotfixes backported to all supported versions
  * enterprise class support
  * Certified infrastructure, containers and plugins
* Enterprise and Community Edition
  * EE
    * Paid docker sub
    * includes support from docker
    * predictable quarterly release
    * certified partner ecosystem
    * Enterprise grade features
  * CE
    * Free "do it yourself" dev + ops
    * does not include support
    * Quarterly stable release for ops
    * Montly edge rel for devs
    
* Docker TRusted Registry - DTR
* Universal Control Plane - UCP
* EE components
 * Integrated security
   * Img mgmt
   * app & cluster mgmt
 * Docker engine
* EE Architer
  * Raft consensus group
    * Internal distribured store
    * Nodes
      * UCP mgr
      * separate mananger and workers
  * DTR replica worker
  
* Image promotion
  * "blessing" image from one repo to another one in same DTR
  * Repos each have own access control
  * e.g. Jenkins builds and pushed to DTR
  * Some criteria?
    * tag with certain version
    * Doesn't contain any vulnerability above threshold
    * package exists or is greater or less than a X size
    * > or < X size
    * license e.g. don't contain GPLv3
* Image scanning
  * Scan at binary level
    * not just package version
  * scan both win + lin
  * New vulnerabilities db released daily
* Mixed Win/Lin cluster
  * Linux managers
    * UCP controllers
    * DTR replicas
    * AuthN, Img scanning, notary and other shared services
  * Mixed workers
    * widnwso native containers on win nodes
    * Linux containers on Linux nodes
  * Cool that they run together, but can they talk together?  Yes
    * Inter-OS networking to be considered
* Secrets mgmt
  * e.g. db password - want only that container can see secret
  * Store inside internal distributed store and then injected into container
* App Mgmt
  * Control plane for app
  * Demo of secrets and adding service + secret
    * Will deny creating secret w/o proper permission
* Summary
  * Docker EE: Container mgmt
  * Try docker EE:  docker.com/trial
  * image scanning, secret mgmt
