Containerize Legacy Apps
* Brandon Royal - Sol'n architect @ Docker
* Trying to help customer migrate their apps
* Imagine
  * Thought experiment:  You've created the perfect greenfield app in containers.  All is good in the wolrd.
  * Everything is good.  Right?  NO.
  * Legacy apps in need of innovation
    * Costly and lots of effort.
    * Could go back in past and tell them to use containers from day 1
  * Now it's your job to building containerized app
* Will talk about steps and success from customers
* What are benefits?  Why modernize traditional apps?
  * Portable (infra indepent apps), Secure (reduce risk & enforce new controls), Efficient (optimize capex and opex costs)
* get started
  * identify app
  * containerize
    * Image2Docker - for Lin and Win
  * config and secure
  * compose
  * deploy
* Identify App
  * existing initatives
  * framework compatability
  * Arch. fit
    * Look at 2-3 tiers and tackle those
  * impl
    * Go
      * persistent data externally or manage using volumes
      * build scripts, packages
      * registry hacks and phantom bins (don't be afraid of them)
        * will carry tech debt, but do that and put in docker file but can address later
    * Refactor
      * in-process session state
      * GUI dependencies (build/runtime)
      * Logging to disk
* Containerize App
  * Leverage Image2Docker to quickly detect app artifacts and create docker images
  * Win - Built on PowerShell
  * Demo: Image2Docker:  ASP.NET
    * Not perfect.  Won't catch all dependencies
* Config and Secure App
  * Exteranlize XML Config, move to env vars and secrets
* Compose and deploy app
  * Use dockerEE to compose and deploy stack
  * Images can be LARGE
    * In GB for Win.
    * Use DTR CAche - optimize pull/push performance
  * Secure deployments
    * Sign and scan images
* Rohit Tatachar - Sr Program Mgr - MSFT IT
  * MSFT IT
    * 2500 apps, 10BU, Azure cloud migrations
    * reduce infra & ops code while moving to Azure and modern app arch
  * Current Legacy app inits
    * ~90% Legacy apps in VM env
    * 25% Legacy apps approaching sunsetting in 2-4 yrs (no refactoring)
    * ~90% apps require trad or enter components
  * Docker + Win: Contaienrs to rescue
  * Journey to containers
    * Select initial apps - 
      * tech selection criteria - coordinate w/ app owners
    * Containerize 
      * Use Image2Docker (i2D) to create Docker images and deploy to Docker EE on Azure
    * Apply Enterprise Config - gMSA domain identies Win Auth Service Accts
  * Select 1st apps
    * Web and app tier
    * IIS 6.0+
    * .NET Framework 3.5+
    * WinServ2008+
    * No low level network or ident serv
    * No depend on h/w or driver access
    * NO desktop apps RDP, VDI
    * SQL Server containzerized for dev only
  * Legacy Patterns in Modern INfra
    * Docker Ent Edition: The Modern Hybrid App Platform
  * Wind Auth
    * gMSA - Globally Managed Service Acc't
    * Support via Docker EE
  * Intial Results
    * 10 apps
    * 4x app density
    * 1/3 infra cost
