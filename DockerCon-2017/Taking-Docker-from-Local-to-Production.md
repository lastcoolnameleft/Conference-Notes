* JanJaap Lahpor - Sr. Mgr, DevOps, Intuit
* Harish Jayakumar - Lead Solutions Engineer, Docker Inc.
* Intuit Proconnect - Taxes are done, Dockercon!
  * Crazy to be here instead of in Plano, looking at stats
  * 200k professional tax preparers
  * 25M+ tax returns
  * this year, backend runs on Docker Enterprise
* How did we get here?
  * Will share
  * Intuit business case
  * Pilot project
  * problems we encountered
  * lessons learned
* Timeline
  * Discovered Docker - Dec 2013
  * Dockercon 2015 - June 2015
    * Great on Macbook but not for prod
    * Had to stitch multiple things together (security approval, etc)
  * Dockercon 2016 - June 2016
    * Ah ha moment.  Introduced Swarm Mode
    * Very attractive to use single vendor, and single product suite
  * Docker 1.12 - aug 2016
    * Where project kicks off
    * Went comfortable to ask leadership to go to Docker
  * Difficult to explain to people outside of this room what Docker is.
  * Developer Productivity
    * Hard to show metrics for this in Enterprise
  * Hybrid Hosting
    * Hard to maintain for multiple environments
    * Great for AWS/OnPrem/Azure
  * Patching-as-code
    * Patching thousands of vm's is terrible experience
    * "out-of-sightly"
      * IT says "need to update kernel"
      * Doesn't happen inside sprint
    * Can use same pipeline to implement features and patches
* Alright, go provde it
  * Start small
  * No "i" in Docker
    * Mission based teams
    * Specialities in
      * Ops
      * Dev
      * Perf
      * Security
      * Partnership with strong vendor for bad days
* Guardrails for speed
  * Hosting
    * isolated hosts, running RHEL7
    * No data stored inside containers or on teh hosts
    * No container-to-container communication
    * Use existing supporting tech
  * App
    * Only Java 8, stateless service
    * Only Tomcat on rhel7
    * applied to entire SDLC:local to prod
    * Need problems in production to get good
* Not local anymore
  * Have to get off the Macbook
  * Great to run local on macbook, but need to consider other values
  * Use DockerEnterprise
* Docker on Enterprise
  * Docker Engine (container runtime, orchestration, networkign, volumes, plugin)
  * Docker Trusted Registry (secure img mgmt & distro)
    * Scanning service runs in background
  * Universal Control Plan
    * App and cluster mgmt
* ProConnect Impl
  * 4 swarms
    * 2 prod, 2 pre-prod
  * 1 sprint to get 1 service in prod
  * 5 sprints to get 9 services in prod
  * We expect problems, but not the big problems we encountered
* Stale ingress load balancer
  * Docker 1.12 - updating a docker service could leave an old, dead cont in the ingress lb
  * Docker 1.13 - Health checks for containers in ingress lb
* Trouble w/ bare metals
  * Apps were the real problem
  * Tune connection & socket timeouts instead relying on default value
* zombie containers
  * The wrong way
    * alloow automated OS patching to occur on your Docker hosts
    * Patch kernel packages on live docker hosts
  * Right way
    * Drain a docker host and remove before ...
* Lessons learned
  * Got in hot-water 
  * Needed partnership
  * Need to be transparent and set right expectations w/ your teams
  * Need room for unexpected problems and mistakes
    * Benefit will be there, but will be hiccups along way
  * You need to be open to frequent change
  * It's not a VM
    * 
