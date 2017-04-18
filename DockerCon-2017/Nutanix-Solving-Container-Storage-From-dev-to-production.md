* Container Persistence
  * Can use DAta Stores
  * Local Storage - DAS (Direct Attached Storage)
    * How do you back it up?  verify db's are not corrupted
  * 3-tier (remote storage)
    * Not flexible, might take months to install
  * Distributed Storage - SDS (Software defined service)
    * can add space/storage as you need them.
  * Can run in cloud
    * but might not want to run in cloud.  
* Nutanix
  * Sell Appliance model, but s/w defined
  * Your choice of hypervisor
  * Use docker plugin
    * Create volume and mounts disk
  * Using VG (volume group), you can do normal things on Nutanix
    * backup, DR, compression, dedupe
* Container "learning cliff" (dev vs prod)
  * security, code quality, container hosting, peer discovery, config changes, supervision, monitor, rolling deployment, 
* Can use from Docker DataCenter
* links
  * nutanix.com/testdrive
  * nutanix.com/contact
  * nutanix.com/docker
