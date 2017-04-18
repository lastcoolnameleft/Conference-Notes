
* Presentors:
  * Taylor Brown (@taylorb_msft)
  * Steve Lasker (@stevelasker) - program manager for Visual tools

* Slides
  * Slides: https://docs.com/taylorb
  * Demos: https://github.com/SteveLasker/Visitors
  
* Cloud has changed expectations
* Containers deliver speed, flexibility and savings
  * 62^ report redunction in MTTR
  * 10X cost reduction in maintaining existing apps
  * 13X more s/w releases:
    * "Some customers don't want to release faster
* MSFT + Docker - why?
  * Want any OS, Anywhere, Any app (Monolith, Microservice), Any Language
  * Linux Containers, 
  * We have some things Linux doesn't have.  But everyone is getting lifted because of it
  * Azure Stack - Allow you to use onPrem
* Containerized Workflow
  * Contaienrs are new binary of deployment
  * VSTS - .NET Windows + .NET
  * Azure KeyVault, Hashicorp Vault - OSS + Win
  * Puts power back into developers so that Ops people don't have to install WCF
* Demo - Visual Studio
  * Demo for adding docker-compose
  * !!! Running in Container + Breakpoint in VS
    * Clicked "Continue" and hit breakpoint in other container!
  * .NET core that targets Nano.  
    * Supports Linux today
  * SQL Server in Docker
    * Re-run test from same state each time
    * Great sweet spot for running DB in container
  * 1/12 the cost of Oracle
  * VSCode - we live in a polyglot world
    * Code editor, try not to use "Visuals"
  * Maintained Images by MSFT
    * Azure Container registry
    * store.docker.com
  * Image2Docker - great way to migrating WinVM
  * Using HyperV Isolation - use EXACT SAME CONTAINER
    * Windows Kernel and Windows Server Kernel are not the same
      * Can adjust between the two
    * Support for Linux container support
      * allow Linux contaienrs to run just with Windows containers
    * Showing work in OSS so people see in the open
    * Means you get to use best tool for job
    * Can now compare side-by-side, .NET on Lin an Win and see which runs better
  * Windows OS Envs
    * ServerCore - highly compat, traditional apps
    * Nano Server - Highly Optimized, Born-in-cloud-apps
  * Azure Container Service
    * Unique
    * Runs your choice of DC/OS, Swarm and K8S
    * All code to run is in OSS
    * Can run exact same onPrem as in Cloud
    * Why care?  Get support from MSFT.
  * Cloud Console
    * Right in portal, get Bash support
  * App Service - Container PaaS
    * Can package up container and run there.
    * Can now package deps in container if had issue where AppService didn't let you install necessary dep before
  * Service Fabric
    * Reliable Collections (Lin + Win support)
  * Operations Mgmt Suite
    * Can use to monitor containers AND onPrem 
    * Can run with conjunction of onPrem
    * Can see not just app having problem, but VM being hosted on
  * Azure Container Registry
    * Just GA'ed
  * Will discuss even more at //Build
  
  * Q&A:
    * What would not work in container that you need a VM?
      * If you have Kernel Mode Driver.  Rough spot.  Because kernel
      * UI Install script - Because headless services
    * Generating data in container. How do I get out?
      * Volumes allow you to have create state separation
    * Blog or list-serv?  
      * None yet, but will investigate
    * Can I run same container on Lin + Win?
      * Because they share the host kernel
      * HyperV allows for ...
    * How is Powershell being integrated?
      * We build PS module for docker.  Not seeing much activity.
      * If we see gain traction, will put more dev resources on it.
      * Are building PS image
    * SQL Server images
      * 2016 img for Win+Lin.
      * 2014 for Win.  
      * Based upon Dev issue
      * Preview of 2017.
    * Roadmap for Docker features
      * Add additional container primatives
      * e.g. cgroups.  Not equivalent in Win.
