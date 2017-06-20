* What?
    * Uses community version of MySQL
    * Making it easier for you to build faster
    * What do you get with Azure DB for PostGres MySQL
* Features
    * Built-in HA
        * do not need to build a replica, etc.
    * Scale on the fly w/o app downtime
    * Secured to prodct data out-of-the-box
        * Don't need to ask "do I need to encrypt my data?"
            * By default
            * Data on disk and in flight
    * Auto backups and storage for recovery to any point to 35 days
    * Use native tools, drivers and libs
        * By using community edition
        * Same drivers
    * Simple and inclusive pay-as-you-go pricings
* Service Fundamentals
    * DB -> Server |Azure DB for Postgres -> Resource Group -> Sub ->Acc't
    * Resource is logical server
        * Connection endpoint for Postgres SQL
        * Can create 1:N user db
        * Pinned to region
        * policy scope (e.g. firewall rules, recovery, monitoring and mgmt)
* Connect
    * Create via CLI, Portal, Customer Mgr apps
    * Talks via REST to ARM
    * Talks to Azure DB Mgmt Services
    * Creats Postgres server 
    * Can use pgadmin
* SEcurity built in
    * Identiy - Native authN
    * SSL + Server firewall rules
    * Built-in encryption for app data and backups
* Service tiers
    * 100 ~ 1 core
    * Basic - Small app with Vario IOPS
        * compute scaling: 50,100
        * Storage Scaling: 50GB->1TB
    * Std (throughput optimized)
        * Rec for apps with scalable compute
        * Compute scaling: 100,200,400,800,1600, 2000
        * Storage Scaling: 125GB->1TB
    * Premium (latency optimized)
        * Rec for ap p requiring scalible compute and lkow 
        * same as Std
        * Storage: 4TB
    * Native Postgres 9.5 and 9.6
* Customer Highlight
    * Higher Ed Profiles, CEO Higher ed profiles
    * Experienced wiiht Oracle/SAP
        * license is passed to clients
    * Portable (as our move frmo AWS to Azure demonstrated)
        * Moved w/o problems
    * arch
        * blob storage
        * Lin VM for Postgres
        * App service for NodeJS (1/client)
        * End User
    * FE/BE
        * Angular, Sails, Node
    * Challenges
        * Responsible for security patches on Linux/Postgres
        * Managing attached disks
        * NONE add value to customer
    * Migration
        * Create service using portal
        * Export existing db using pg_dump
        * create DB + users on Pgres
        * Import using psql 
        * 2.5GB dump file (for one db)
    * Test results
        * DB migration was actually simple
    * Why use Managed Service?
        * Small company, want to focus resources on impacts
        * Student data is protected by law
* Credo360
    * Profile
        * Reputation and P2P review platform
        * Not a marketplace
        * Check people's credibility
        * Conduct transactions buy/sell/hire
        * Rate/review people you deal with
        * Protect privacy and maintain anonymity
    * Tech stack
        * Same lang for BE and FE 
        * T?ype-safety to catch bugs early
        * REliable and scalable database
        * free soln' and tooling
        * Node + Socket.IO
        * Typescript + VSCode
        * Postgres (extensive use of JSONB)
    * Challenges
        * Tuning
            * No expertise to config db for best
            * dofficult to setup continuous perf
        * Scaling
            * Can't dynamically scale server resources
            * No exper/time to setup replcias
        * reliability
    * Now  
        * Eliminates last self-managed component
        * No need to manage OS, db server s/w
        * Easily plugs into existing infra
        * *More time to focus on apps*x
    * Demo
        * Scaling up
            * Paused connections while scaling up
        * CPU hit 40%.  Send out email on threshold
* Available
    * 11 regions 
    * goal: in all regions by GA
    * GH repo
        * Quickstart samples
        * https://github.com/Azure/azure-postgresql
* Q&A
    * HA - how?
        * Impl in DB platform services itself
        * DAta is already replciated on storage
        * If instance goes down, bring up new and redirect
        * Max of 60 sec
        * NOT hot/hot
    * Encryption at Rest
        * Can bring your own key?
        * Currently just system managed
        * Local data residency?
            * Repl is done via standard Azure geo-pair regions
    * In preview now
    * Avail:
        * US East, Japan East/West, North Euro, West Europe
        * Not in UK
    * Plan:  Want to integrate with DAta Lake, etc.
    * Waiting to hear what users/customers want to do.
    * compare and contract AWS/AZure migration
        * Was easy move since all OSS
        * Now landed on Azure
            * took advantage of managed services
            * Pleased with how turned out
            * transparent to Customers 
    * Mysql talk is same
        * MySQL 5.6, 5.7
            * Oracle produced MySQL CE
            * Only InnoDB engine
    * latency
        * Found connection estbalishing was slow
        * ~600ms via VM but ~1.2 sec on managed
            * Team worked hard to get it back down.  
            * USe connection pooling, so not an issue
