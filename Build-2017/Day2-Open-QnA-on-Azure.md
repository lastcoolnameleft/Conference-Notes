* Open Q&A on Azure
    * Mark Russinovich
      * CTO of Azure 
    * Corey Sanders
      * Product Owner for: Compute, ServiceFabric
* Questions
  * ElasticDB for Azure SQL.  Similar feature (multi-tenant) for Azure Search?
    * No plans but interested.  ElasticDB has been great success.
    * Multi-tenant is great.  Need to see it to catchupa
  * Cloud heavily relied on operations.  What is SRE model?
    * Every team has to respond to issues.  (Even Program mgr)
    * SRE team is focused on core platform
    * Evolving model.  Devs building tooling and adding back to services
    * Follow the sun model.  8 hr shifts
  * CosmosDB.  Ate DocDB (and maybe Table?)  How should we think of CosmosDB going forward as architects?  And ServiceFabric.
    * Corey:  Loves CosmosDB.  Favorite service on all compute
    * ARM endpoint is built on SF. 
    * CosmosDB is built on SF
    * Using for internal services has been happening before we announced it
    * Built lots on top of SF.  Been in prod for 8 yrs.
    * VM Infrastructure on top of SF
    * Support for stateful uS.
      * Allow to focus on one-box exp.  Dev doesn't have to worry about failovers.  Have hot standby's
    * In addition to SF, see interest in partners.  OpenShift, PCF, K8S
    * Actor Model:  OO uS. SF takes care of name resolution
      * Halo Online is built on MSR Actor Model. LB is taken care of
  * For custom RBAC, can someone document the 10-zillion policies?
    * "Would like something like Netwatcher"
  * Future of Cloud Services?
    * CS: Original show of Azure
    * "Microservices v1"
    * Want to break apart to different layers.
    * Was hosted runtime + hosting env
    * Can't bring own host-OS.  Win only.  Unit of deployment was VM
    * Very coarse grained
    * Taking lessons learned, and integrating into VMSS
    * We will keep it going as long as you run on it.  But are not innovating on it
    * Instant metadata service.  
      * Good indication of where we're going.  Can see request for maint.
      * Want to expose same capabilities
    * Marketplace extension requires CS.  Shouldn't.  Will investigate
  * Connecting to onPrem data?
    * Have On Premesis Data Gateway which could assist.  
    * Could use Express route?
  * Azure Gov't.  Struggling.  Lag time for features.  what are you doing?
    * Don't know how long using Azure Gov't.  But gap has shrunk significantly
    * Teams now have unified rollout between two.  
    * Huge priority for us.
    * Q: App Insights are painpoint.  
    * We've improved back-end.
    * Existing services are on different path, so might lag.
  * Need special h/w.  Want to install crypto-card on Azure
    * No.  
    * Go to someone like Equinix.  
    * Q: We have 20 servers that need the crypto-card.
  * Security:  SQL Server is exposed publicly.  Express route to support?
    * Scenario:  Either VM or PaaS.  It's a public IP. Can we cut that public endpoint?
    * Getting lots of attention on this issue.
    * Not an issue for some customers.
    * Can see IP ACL's.  But those are fragile
  * FPG.  Where's biggest bang for buck in cloud?
    * Have 5:30 session on it.  Full hour talk
    * already using for Accelerated Networking.
  * Azure Stack. Lags behind.  Will resolved?
    * Definitely.
    * Some flex on update principles.
    * Once AS goes into GA.  Will keep up with public cloud.
    * Some optionality on when you take updates.
    * There will be lag, because we will release in batches 
    * Q: Currently 1 yr behind.
    * Won't be that long in future.
  * Azure AD is great.  But lacks machine objects (only user/usergroups)
    * There is work coming.  Will go to broader compute story.
    * will be able to give access like any identity
    * instance metadata service uses it
  * Private cloud is defined differently across cloud.  Infrastructure dedicated to specific customers.  
    * What is driving that requirement?
      * Security.
    * Azure is fundamentally a multi-tenant system.  
    * Don't see us making full stack of Azure dedicated to single customer
    * Don't have many customers asking for us.
      * DoD cloud is asking and example
    * Every service is built to be multi-tenant
    * Closest we get to it is:  Azure Stack
  * Will Azure Files support Encrypt at Rest?
    * On roadmap.
    * All data services, Encrypt at Rest is on roadmap
    * Seeing SQL Azure, see 2 sec of delay
    * With Cosmos, you can specify those consistency
  * Service Fabric Open Source?
    * Programming Model for SF is OSS
    * No plans to OSS full platform.
  * Don't trust data in US.  MSFT went far to keep trust.  Trusted DC in Germany. Don't have LUIS.  Feels like gov't cloud.  Lagging.
    * German DC would legally meet needs, but lagging
    * Answer for Germany is the same for all our soverign cloud.  
    * Only soverign cloud we have in Europe is Germany
  * Azure Marketplace needs some love.  Test Port (3389) is blocked by company.  Main UI is arcane.
    * Can do port forwarding
    * A lot of investment going into that.  
    * Aware it's been a challenge.
    * Focus for us.  Should be 
  * Socket.io - Can have PaaS
    * Can put presence data in CosmosDB
  * Azure Stack 
    * Part of our Edge strategy.
    * Don't see that as ever going away.  (e.g. factory floors.)