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
  * Next Steps
    * Deploy at Scale
      * across DockerEE
      * Docker EE CI/CD Integration
    * Prod Ops
      * manage initial apps in prod
      * Integrate docker content trust and Docker security scanning into prod build process
    * Achieve Digital Transformation
      * Contribute to i2D to continue to addr use cases
      * VS2017
      * Integrated Azure deployment
* Rob Tanner - Div mgr, Enterprise Middlware serv - Northern Trust
  * About NT
    * Provider of Asset mgmt for instutions and families
    * Not oldest.  MetLife blew out of water.  One of oldest
    * Pride:  Best class services experience as possible
    * S/w defined DC strategy
      * Agility, Reliability, etc.
  * Greenfield microservice apps are great, but what do I do w/ the other remainer of my apps?
  * Our env
    * 400+
    * WebLogic Apps
    * .NET apps
    * Tomcat apps
    * Try to make as lift and shift as possible
  * Why traditional apps in Docker EE?
  * Infrastructure Efficiency
    * Old way
      * App specific infrastructure provis
      * Challenging dependency/middleware mgmt
      * per app isolation
    * Docker Way
      * Heterogenous pool of infrastructure resources avail to apps
      * dependencies middleware containe w/i app images
      * multi-tenant
    * Building Reliable Foundation for Hybrid Cloud
      * With Azure, create dev app in docker and deploy on Azure w/i a Day
      * Docker Declared Services
  * Improved Security
    * Limited attack surface
    * Understood and scanned app BoM
      * Heartbleed: How many people knew exactly how many impacted
    * Automated patching in build process
    * TLS signed images at every stage of build - Docker Notary
    * 3rd party IPS/IDS
  * Faster deployments w/ less infrastructure
    * w/o docker:  29 days
    * w/ Docker: 7 days (4x faster delpoyments)
  * Docker EE single pane of glass
    * Docker EE became the obvious choice since it's a single pane of glass for all workload...including Win/Lin stacks
    * spring boot front-end
    * asp.net web api
  * Future of Docker at NT
    * Docker EE is the standard for all legacy apps at NT...period
    * Containerize WebLogic.
      * Contain the WebLogic domain in container
* takeaway
  * identify your app
  * start small
  * keep it small
* docker.com/MTA
* 
