* MSFT IT 
  * Panelist
    * Bing: Jordan Edwards
    * Azure: Mike Kippen
    * Skype: Jennifer Perret
    * Win + Dev group: Tony Seeley
  * Security and redundancy on Azure
    * We work on Azure but also build Azure?  So, what do we do if Azure's done?
    * We have tools that bring git back down
    * "We have VM's that were running since 2014 that had never been rebooted"
    * All code is available for employees to see (except some algorithm code for IP reasons)
    * Can't apply ACL to parts of repos.
    * Windows is a pretty big target.  Multi-national countries coming after us
  * Q: How do you get buy-in for security?
    * Pit of success:  Hope people fall into it.
    * Make it easy to adopt to processes
        * Governance should be in background.
    * Even more important as we go towards micro-services
    * When dealing with h/w, drivers, etc.  Monolith makes sense
        * As you move up a layer, design by contact
    * If going from monolith to uS
        * One big ah-ha moments:  "How many people on ops team have exposure to this code?"
        * Our ops teams running via dev-ops, they have 200 people with exposure to everything
  * Q: How do you gain consensus for new processes and tools?
    * MSFT is getting more requests for OSS now than before
      * If you tell team here's the type of work and here's the tools, you will always lose.
    * Horribly inefficient for each team to build their own thing and then come in and say "everyone have to work this way"
      * Sell the benefits.  (if right with your business)
    * What are the benefits?
      * More frequenct you ship, less bugs
      * Everyone is on same pipeline
      * Get telemetry
      * Ability for time to mitigage significantly decreases
        * With real-time monitoring, we can roll back in 3 minutes
      * It's staggering how much time we spend builting the same thing.
  * Q: As we try 1ES mentality.  Lots of mis-Understanding PM and engineers.  (What is being shipped vs worked on)
    * Different set of compliance for building tools on Azure vs building Azure
  * Q: How/where should we use different repos?
    * Best for deployable artifacts
    * Q: Who makes those decision?
        * A: Product Team
        * Must embrace "Build, Measure, Learn"
    * Q: What about sub-modules?
      * A: We regrest not using them before.
      * They're scary to people.  Not for all scenarios
    * Beauty of Monolith is you know what's inside it.
  * Q: Many pieces of CI/CD, where do you start?
    * Telemetry is 1st thing.  If you cannot measure it...
    * We rely on it heavily.  Have to know you're hitting SLA for customer
    * After that, depends on customer
    * Encourage you to start at weakest point in pipe.  
      * Then you get buy-in
    * If you can own entry-point (PR), your value can change over time.
      * You may be using diff test system in a few months.  But if you can add visibility, will help later
      * Start at early in stream as possible

