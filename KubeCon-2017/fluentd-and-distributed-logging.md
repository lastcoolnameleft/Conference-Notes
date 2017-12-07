# Fluentd and Distributed Logging

* Masahiro Nakagawa - Sr s/w eng - Treasure Data
* Logging on Prod
  * service logs
    * web access, ad logs, transaction logs (game, etc)
    * logs for business, KPI, ML
  * system logs
    * syslog, systemd, audit logs, metrics (cpu, mem, etc)
    * logs for Ops
* Container era
  * log collection for server era: syslogd/rsync
  * log collection container era: ??
* Logging challenges with contaienrs
  * no perm storage - transfer logs asap
  * no fixed phys addr - push logs from cont
  * no fixed mappings b/w servers + roles - label logs w/ service/tags
  * logs of app types - need to handle various logs
* what's fluentd
  * extensible + reliable data sollection tool
  * extensible = simple core + variety of plugins
  * rediable - buffering, ha, secondary output
  * data collection - like syslog in streaming manner
* M x N problem for data integration
  * Input: apache, twitter, android, mac
  * output: hadoop, elastic, GCP, MySQL
  * Fluentd M+N
* Fluentd arch
  * Internal arch - simplified
    * input -> filter -> buffer -> output
    * all are plugins
  * Logs of 3rd party plugins 
    * S3, elastic, hadoop, kafka, graphite, influxdb, zabbix, postgres
  * source (container/agent -> transferring / aggregation later -> destination
    * source - retrief logs (file, n/w, api), parse payload for structured logging
    * aggregator - get logs from multiple sources, split/merge logs into streams
    * dest - receive logs from aggregators, store formatted logs
* How to collect logs 
  * "docker run --log-driver=fluentd --log-opt= fluentd-address=localhost:24224
  * Metrics collection w/ fluent-logger
  * Shared data volume + tailing
* aggregation servers
  * logging directly from u-serv makes log storages overloaded
  * aggregation servers make logging infra more reliable + scalable
    * conn aggregation, buffering for less frequ import API calls, data pers
  * Matrix:  Source side aggr + dest side aggr
  * should you use these patterns?
    * source-side aggr:  Yes
    * dest-side aggr:  it depends
      * good for high traffic
      * maybe, no need for cloud logging servers
* Scalable distributed logging
  * network
      * split heavy traffic into traffics to nodes
* fluentd loves container
  * fluentd model fits container based systems
  * pluggable + robust pipelines
  * support typical deployment patterns

  
