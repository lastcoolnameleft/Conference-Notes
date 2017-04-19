* Welcome to day 2
* Logo - has checkered past
  * Moby has stayed the same from beginning.
  * Came from contest.  Someone from Indonesia won.
  * Have been getting complains from animal rights whale.
    * Exploit whale by making them carry containers
    * True story - PETA
  * Wait until 90 minute talk to find out new update
* Day 1:Dev + Operators
  * Highlights:
    * Docker for Devs
      * Desktop to Cloud integration
    * Docker for Ops
      * LinuxKit
      * Secure Orchestration
      * Project Moby
  * Docker is in the enterprise (lots of logos)
    * Service provider, Healthcare, Financial, Tech, Insurance, Public sector
  * ETR - Data analysis company.
    * Saw trends amoung 3k CIO/decision makers
    * What are you spending on in x?
      * Report to hedge funds
    * Docker is off the charts for microservices
    * Docker is rising in enterprise industry
      * "keep planes in air, monitor file alarms, cure diseases, power financial institutions, ecommerce"
  * Myth of Bi-Modal IT
    * You are either working on old, slow app or new, fast app/infrastructure
    * Only one mode that matters.  Fast
    * 1/2 of companies are starting on traditional apps
      * If you dockerize a traditional app w/o changing code, you can get 50%-5x infrastructure efficiency
      * Can take Win2003 Server and run on Win2016
      * Can take app from old DC to new DC or go directly to cloud
    * Once you dockerize your app, you can move to CI/CD
    * Once they do for a few apps, they see how they can pick apart monolithic apps
  * Exciting because Docker makes you Future + Past proof.
    * Reality is diverse
      * Win/Lin, Baremetal/Virtual, OnPRem/Cloud, Traditional/microservices.
* Swarmy Kocherlakota
  * Global head of infrsastructure and Ops - Visa
  * First off, thank you Visa customers.  You're in good hands.
  * Disclaimer:  Do you own research
  * Visa by the #'s
    * One of largest payment service providers
    * Reach
      * 3.1 B cards
      * 176 currences
    * Scale
  * Vision
    * Make electronic payments accessible to everyone and everywhere
    * Open our platform to drive innovation in digital payments
    * Deploy code to prod on 1st day as a dev
    * Build with JIT infrastruture
    * Global infrastructure w/ highest security and avail
    * "I love our developers, and want to empower you.  But I don't want to talk to you"
      * "Feeling is mutual"
  * Before - couple of years
    * Only one solution
    * Virtualize it.  
      * ! Like taking baremetal and doing space division multiplexing 
    * Lots more devs in infrastructure/automation than before
  * Meanwhile
    * Infrastructure footprint is growing
    * Maintenance windows are shrinking
  * ...with wasted efficiency
    * Infrastructure prov times - 12 mo
    * Procure/provision - 3 mo
    * Decommission - 3 mo
  * CloudPhysics - Less than 90% of infra is 5% utilized
    * Most of CPU is agents anyway
  * Break the pattern
    * Docker + Microservices
  * Perceived Opportunity
    * Dev Producitivy
    * Standard way to compose, package, deploy + manage
    * Time Division Multiplexing (was doing space, now doing tie)
  * Key Arch Decisions
    * Baremetal vs virtual
      * Civil war amoung architects
    * Ecosystem components - Service registration, Discovery, LB
    * Network Arch - should we wait for it to evolve?
  * Visa Today
    * Live in prod for 6 mo
    * 100k trans/day
    * 10x app scalability
    * multi clusters in multi-regions
  * After
    * Prov time = Seconds (not days for Virtual env)
    * Patching and Maint - Goodbye.  (can hang hats)
    * Tech Refresh - Invisible infra
    * Multi-tenance - Time + space division multiplex
  * Lessons learned
    * Granularity - 
    * Memory footprint - can do micrservices, but if heap size is big, then issue
      * Most apps are memory bound
    * Load balancing - wish there were more features, but happy
    * Operationalization - Supporting env
    * Expanding the blueprint for 5 more app groups
  * Visa Roadmap
    * Classic - baremetal virtual + container - Days
    * IaaS - BareMetal Virtual + cont - Hours
    * BYO Stack  - Hours
    * BYO Service - SEconds
  * Tetris like Infrastructure
    * Space + Time Div multiplexing
    * Speed - measured in seconds
    * Efficiency - containers / Business Value
    
