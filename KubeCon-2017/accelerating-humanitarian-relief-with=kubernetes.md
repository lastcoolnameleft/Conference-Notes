# Accelerating Humanitarian Relief with K8S

* building a highly avail native spark pipeline on k8s
* who
  * Erik Schlegel - MS, prin eng
    * github.com/erikschlegel
  * Christoph Schittko - MS, prin eng
    * github.com/xtophs @cthearchitect
* Part of UN provides humanitarian need
  * Try to get more insight 
* UN challenges
  * Humanitarian aid plans are manually composed
  * imprecise aid relief plans
  * aid planners monitor 400+ sources daily
* Project Fortis:  Goals
  * accelerate the construction of aid planning
  * improve data accuracy
  * deeper insights and trends
  * real-time analytics
  * predict where Zika was spread.  Find high risk zones
* Architecture
  * incoming data streams (fb, kafka, twitter)
  * send to spark streaming
    * extract space/time/location.  store in postgres
  * filter -> message pusher -> cassandra -> graphql (storage adapters)
* Spark on k8s
  * resource sharing / utilization across spark + cassandra
  * simplified deployment model (helm, deis, spark-submit, etc.)
  * HA - k8s replaces zookeeper
  * elastic executor scaling with kubectl min/max replicas
* Fortis k8s setup
  * 2 namespaces: spark + cassandra
* Cassandra Azure HA
  * 1 pod per node, node affinity
  * Azure fault domain aware
    * customized docker image
  * github.com/xtophs/azure-fault-domain-on-dcos-nodes
* Demo - multi-cloud setup
* Code
  * Cassandra / Spark Helm charts: github.com/CatalystCode/charts
  * fortis: 

