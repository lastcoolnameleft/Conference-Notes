# UDP in k8s: Signed, Sealed but delivered?

* who
  * Amanpreet Singh, s/w eng, Crowdfire
  * Twitter/GH/Medium @apsops
* Where do we use udp?
  * KubeDNS
    * Service Discovery!
    * Crucial in cluster where svc call all the time
    * Protip:  Use pre-existing env vars like these to save all the DNS calls ${MYAPP\_SERVICE\_HOST} 
  * StatsD - used in prometheus
    * statsd + graphite for custom business and serv metrics
    * simple pod deployment backed by EBS
    * Not HA since k8s restarts it quickly in case of fail
* k8s network primer
  * key concepts
    * every pod has unique ip
    * every node gets a distinct cidr block
    * these ips are routable from all the pods (even on diff nodes)
  * comm across app
    * pod ips change all the time
    * reasons include rolling update, 
  * k8s svc
    * static virtual IP that act as LB
  * How do these svc work?
    * magic.
    * Actually more complicated than magic.
    * IP tables
    * kube-proxy
      * name is misleading, is not actually a proxy, but was resource intensive
      * controller that watches the api server for svc/endpoint updates
      * modifies iptables
      * Does DNAT
      * Why?  When reponse comes back, can use that
    * shows output from
      * sudo conntrack -L -p udp --dst <ip> --dport
* what went wrong?
  * when statsd pod is recreated, the metrics from some of teh apps won't reach statsd
  * some apps will still able to send metrics successfully
  * restarting the app pods fixed it w/o touching
  * observ:  Problem happen for apps that send metrics very often
    * prob goes away when those pods are re-created
* how'd figutre out?
  * conntrack -L -p udp --dst <ip> --reply-src <same ip>
  * entries were present even after the statsd pod came back!
* Consolutions
  * stale conntrack entries
  * ttl not expirign for pods
* Mitigation
  * run conntrack command (via cron) to delete stales
  * modify kube-proxy to run control loop
* Why?
  * bug in kube-proxy, update/remov of endpoints, delet of serv/ports
  * entries not flushed when endpoint set changes
  * when endpoint set is empty, contract entries blackhole the traffic
* fixed?
  * PR 48524 in kube-proxy
* qna
  * Recomm for CNI for UDP?
    * still new, so no recomm

