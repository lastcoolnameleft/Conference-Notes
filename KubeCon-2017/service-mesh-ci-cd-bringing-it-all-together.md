* Brian Redmond
  * Azure Global black Belt Team
  * At MSFT for last 17 years
* Concepts
  * CI/CD, blue/green updates, canary testing, pipeliens as code, service mesh
* CI/CD
  * think of as assembly line
  * Need better ways to verify we don't break things in prod
  * Canary testing is difficult across microservices
* What's missing?
  * advanced routing - do canary testing at any layer
  * observability - how does API perform with test?
  * chaos test - everything that could go wrong, will
* pipeline examples
  * Prod: build u-serv -> build docker -> deploy canary - modify routing -> score by metric -> merge PR -> update prod
* enter istio
  * service disc + routing
  * uses sidecars to proxy
  * what can I do?
    * adv routing -> route rules, traffic shaping
    * observability -> metrics, logs, & tracing
    * chaos testing -> fault inject (delays, faults)
* CI/CD
  * Brigade
    * encapsulate functions in containers
    * run in parallel or serial
    * trigger workflow from GH, Docker reg, etc.
    * JS (pipeline as code)
    * project conf stored as secrets
    * well suited for ci/cd pipelines
* Kashti 
  * Dashboard for brigade projects
  * Announced a few hours ago
  * easy viewing and constructing brigate pipelines
  * waterfall diagram of brigade builds
  * view log output of build steps
  * quick peek at conf for builda
* Demo.
  * Really cool demo show canary release with istio/brigade

