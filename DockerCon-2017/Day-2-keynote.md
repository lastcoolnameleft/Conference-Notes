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
* Your world is a diverse mix of app + infra
* Start with a secure base + containerize apps
* Build a supply chain (CaaS)
  * Secure image registry
  * control plane
  * No logos on dev side or 
  * IaaS is too low, Paas is too high, Caas is just right
  * PG13: IaaS is great, but make sure you don't get your aaS in a sling
* Secure Supply Chain from Dev to Build
  * Use digital signatures
* Demo Supply Chain
  * Docker Trusted Registry
    * Policies
      * Image has to meet polcity before promoted.
        * "Critical vunterabilities"
      * Docker image scanning checks each image
      * Use old version of alpine 
      * Fixed issue.  Did it get promoted to prod?
        * Yes.  Auto-promosted from dev->prod
  * UI: Resources, etc.
  * Need to add password.
    * Injest as compose file
    * Create secret, only available to container
  * Running on hybrid Windows+Linux cluster
    * Show MySQL SQL server on Win.  Payment gateway are Linux
* Leverage the Ecosystem in the Supply Chain
  * Major expansions
    * IBM - Linux for z System and Power Series
    * Every Major cloud - Alibaba cloud (Aspara stack agility), Google cloud Platform, 
      * Alibaba is one of largest users
        * Largest online retail in China
        * Single's Day in China dwarfs Black Friday - 60% happens through Alibaba
    * Broader Delivery Ecosystem
      * Accenture has built application platform for integrating docker
* Demo - Deploying 3rd party apps and traditional apps
  * Convert LAMP stack to container
    * image2docker - extract app from VMDK and creates Dockerfile
    * now build dockerfile and push
    * !! Converted VM into Container
  * Containerize Oracle DB
    * Oracle DB is alrady official app on store
      * Oracle DB in a container
      * Official Image from Oracle
      * FN2187 ?
    * Oracle has made decision to put apps like Oracle DB in store
* Mark Cavage - VP Product Dev, Oracle
  * Announcing Oracle on DockerStore
  * What does this mean?
    * We will support you running Oracle inside Docker
    * WE have a DB + language
  * We took heartstone, Oracle DB, Weblogid Server, Conherence and Java
  * All s/w is available inside docker store
  * Can use std docker run commands
  * Putting all s/w in Store, Free for Dev/Test
    * Call when you want PRod and/or Support
  * Why?
    * "If it's not in Docker, I don't download it..."
    * Developers drive decisions
    * Oracle s/w used by mijllions
  * Why should ISV's be in Docker Store?
    * Widely available - single marketplace for all s/w on any cloud
    * Trusted and Certified -
      * When we looked 80 version of WebLogic.  How do you know which one to use?
  * Going to see a lot more from us this year
* The Docker Modernize Traditional Apps PRogram
  * turnkey program - 5 apps and 5 days. 
    * Show how to migrate application to Docker
    * www.docker.com/MTA
    * Works for Traditional apps + .NET
* Aaron Ades - AVP Sol Eng MetLife
  * Wow, an INsurance company at DockerCon
  * Next year, Docker is turning 5.  MetLife is turning 150.
  * Sell Life insurance.  All insurance is a promise
  * A promise is a bit of information.  We've been in information bit for 150 years
  * timeline
    * 1920's 
    * 1950 - first company in industry to invest in computing.  Univac.
    * 1980's - first consolidated app.  shove in mainframe
      * There is code still running from 1982
    * Become a public company
  * Wrapp the app
    * just like bacon makes everything tastes better, wrap in microservices
  * Tap the data
    * modern data - arch ensures data flows freely.
  * Scrapp the app
    * Retire 
  * New levels for savings
    * consolidate VM's - up to 70% consolidation
    * Move workloads to Azure
    * Massive operational leverage
  * Formed "ModSquad" team
    * 1st foray into devops - "Go figure it out"
    * and they did it and other stuff too.
      * also did with chatops + bots
    * Changed culture at MetLife.
    * Got stuff done and had fun doing it
    * Won award from CIO - "antiboties to the old culture"
  * Even old elephants can dance
    * Took 5 months to go from concept to prouduction with Docker
    * "Docker 0 to 60 in 5 months: How a Traditional Fortune 40 Company Turns on a Dime"
