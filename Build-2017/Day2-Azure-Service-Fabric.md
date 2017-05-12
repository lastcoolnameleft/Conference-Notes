* Main room full.  Had to go to overflow room.  So popular!
* Service Fabric has been a container orchestrator for years
* GA Windows Container orchestrator
* What does this mean?
  * Image deploy + activation
  * support for authN and priv registry
  * Env vars to provide inputs
  * Volume driver support
    * Mounting persistent volumes
  * Networking
    * Bridge Networking (mapping of container ports to dynamic ports on host machine)
    * Registration of container endpoints w/ Naming Service 
    * DNS server w/i cluster to resolve container endpoints
  * Resource governance
    * apply policy on containers for resource constrains
  * Windows containers w/ Hyper-V Isolation
  * PReview: Support for docker Compose
    * Can take lift-and-shift
    * Launch in SF
* Legacy app: Lift and Shift
  * Service Fabric Cluster
  * Contains
    * Docker Compose
    * FE/BE App
  * Live Demo.
* Partner Shoutout: Alaska Airlines 
*  Container networking: road ahead
  * Per app isolated network
    * Isolated network when comm. b/w multiple containers
    * Similar to overlay network
  * Fixed IP addr / container
    * When container fails over, it retains the same IP addr when activated on a new node
    * Contaienr can be addressed directly and use NSG and LB
    * Easy to use with DNS
  * Resource Governance
    * Preconfig capacity constraints (e.g. cpu, mem)
  * SF programming models inside contaienrs 
    * Reliable Services / Actors
  * Deeper VS integration
    * local debugging and visualization of containers in SF Explorer
  * Local storage volume driver
    * Mounting of persistent volumes to local disk storage 
* Demo
  * Docker Compose -> SF Cluster
  * Hosting ASP.NET Core in SF
    * WebHost is in own process
    * WebHost in Reliable Service
  * Gateway to your app: stateless service
    * Azure LB (Layer 4/IP LB)
* Announce: SF + Azure API Mgmt
  * Service discovery + routing
  * Partition resolution
  * Replica Selection
  * Resolve + retry policies
  * Not available yet.  Prob in a month.
* Cluster and App mgmt
  * Azure ARM PS module for cluster mgmt
  * single node cluster for dev/test purposes
  * Patching service integrated w/ Win Update service for automated VMSS patching
  * Integration with AppInsights and OMS for containers
    * Can put appInsights ID in cluster when creating new cluster
    * Use EventFlow to monitor 