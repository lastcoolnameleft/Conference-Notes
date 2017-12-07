# The Good, The Bad, The Ugly of Migrating Hundreds of applications to K8S

* Josef Adersberger - QAware
* Can legacy apps benefit from containers?
* Started because Germany Insurance CIO decided to move and cancelled DC contract 
* Priorities
  * Security lvl, time, opex expenses
* The Good 
  * Visibility
  * Questionare
    * tech stack (OS, JVM) -> what images to prvide?
    * resources (mem, cpu -> how many apps will be hard/inefficient to schedule (<3GB RAM,< 2 cores)
    * writes to storage (local/remote storage, write mode, data volume -> what storage sol'mn to provide
    * special req - (native libs, special h/w)
    * protocols
    * ability to exec
    * client authN (sso) -> what IAM and sec mechanisms have to be ported
    * Wrote program called Cloudalyzer to understand
    * Used Tableau to show the analytics 
  * Emergent design of s/w landscapes
    * All web apps (~400)
      * Old apps (~200) - re-arch to run on k8s on aws
      * more modern apps (~200), lift and shift to AWS ec2
    * Did risk front-loading (risky parts at start)
  * Targeted "cloud-friendliness" instead of cloud-native
    * migrated to 12 factor apps
  * K8s Constraints
    * Thought we'd run into issues like:  No support for multi-cast, No RWX PVC avail
    * We did, but cutting these app reqs lead to better arch in each case
    * i.e. Removing those requirements made it a better app
* Bad
  * State
    * Databases - Let them stay onPrem DC
      * Didn't migrate to AWS (right now), BUT latency
    * Files
      * used in 10% of apps
      * no RWX PVC avail
    * Sesstion state
      * 90% of apps have session state, 100% of apps have +1 instance
  * Diagnostability
    * Metrics - Prometheus
    * events/logs - fluentd
    * Traces - Open Tracing
    * problems 
      * wasn't sure if they could setup central sol'n for all apps
      * didn't want to setup per app
    * Use Dynatrace for sol'n
      * not using fancy cloud-native apps, instead dynatrace works
  * Security
    * Came far and added layers
    * issues: Certificate mgmt
      * 3 employees doing just cert mgmt
      * VAR 1: Cloud native style cert mgmt
        * e.g. istio
      * var 2: Replace by policies (at networking lvl)
        * e.g. tigera, twistlock, cilium, aqua3 employees doing just cert mgmt
* Ugly
  * "hostUsPokus"
  * Legacy F/w
    * developed in 2000's, 500kLOC + 0% test coverage
    * 70% of migration was the hardway
* Now
  * 100 systems are live on target (after 8 mo)
  * 200 sys live on target by 1st q of 2018
  * other 200 sys by EOQ1 2018 via vitual Liftandshift.  Migrate to k8s later
* learned from migrating java
  * get close as possible to "cloud friendly"
  * increase sec level by order of magnitutde
