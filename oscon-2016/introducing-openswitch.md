# Introducing OpenSwitch: The open source, open community enterprise-grade switch network operating system

## Details
*  http://conferences.oreilly.com/oscon/open-source-us/public/schedule/detail/51615
* Mark Atwood (Hewlett Packard Enterprise)

## Notes
*	White box networking talk
*	Mark Atwood - HP
* http://openswitch.net
* Network OS:  Sepcialized OS for network devices such as router, switch, firewall (l3 processing, routing, etc.)
*	OpenSwitch:  NOS, Linux, OpenSource, "Complete"
*	Why?  
  *	Too big: Others try to be google, azure, FB, OCP Projects
  *	not all there:  df.io
  *	too small:  DD-WRT
  *	just right:  openswitch
* Linux based
* License 
	*	Apache2 permissive 
	*	Apache CCLA for corp contrib
	*	Xocto
* OS Enablement
	*	git.openswitch.net & mirrored to Github
	*	gerrit reviews
	*	zuul & jenkins
* openswitch.net
	*	review.os.net, zuul.os.net, lists.os.net.  freenode #openswitch
* Governance
	*	Working to turn to Linux foundation
* Participating Companies
	*	P4, barefoot networks, broadcom, HP, linkedin
*	Everything talks to OVSDB server 
*	13 week release cadence
*	Q:  What is cli flavor?  
  * Looks like Cisco IOS, but more consistent 
*	Q: Hardware?  
  * Released on HP own hardware.  Don't have model 
	*	midrange aruba network
*	Q:  Can run on hypervisor?  
  * Yes.   You can give direct control of network interface, or run purely virtualized switch
*	Trying to get on Debian

## Other
* http://openswitch.net
* https://en.wikipedia.org/wiki/OpenFlow - h/w adoption not 100%
* Black box:  don't know what's going on underneath.  Can only run certain commands. 
* Grey box: open system (like what Arista provides) can build on top of system like Linux.  Manu combine s/w and h/w together.
* White box:  Just provide h/w, some compat. OS
