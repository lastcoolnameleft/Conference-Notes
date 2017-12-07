# Kubernetes Deconstructed - Carson Anderson, DOMO @carsonoid

* Full session - Standing room only
  * Good presentation of quickly describing docker/k8s
* Going into dirty work of k8s - pull apart curtain
* User
  * Describe svc -> deploy -> pods
    * Ingress Rules - from outside cluster to inside cluster
    * bit.do/kube-decon
* Cluster
  * kube-api server - 
    * Custom Resource Def
    * Talks to etcd
  * kube-scheduler
    * Maître D of API service
    * Watch API server and makes decisions of who sits where
    * affinity,
    * Custom Schedulers
      * Can do both, custom + kube sched
  * Kube-controller manager
    * Doesn't do any real work himself.  In charge of guys that do work
    * namespace controller, replicaset controlle
    * operators
    * Controlles talk to API
    * When k8s does something, it's the controller/controller manger that does it
  * kubelet - can be replace with rocketlet
    * Hooks to api server.  Lives on every node and makes thigns real
    * "Maître D" said to do x, do it.
    * Talks to runtime, makes it real
    * Talks to liveliness probes
  * kube-proxy
    * Talk to API server and make services real
    * Every service is made real by kube-proxy
    * can swap out kube-proxy (diff n/w providers do this)
* Network
  * pod networking
    * every pod gets unique ip (across entire cluster)
    * nodes have unique ip
    * also CIDR range for Pods
  * Network providers
  * Cluster provider
    * 3 things to become a cluster network provider
      * all contaainers can communicate w/o NAT
      * all nodes comm to pods w/o NAT
      * IP that a container sees itself as is the same IP other see itself as
        * don't munge IP
  * Services
    * Has selector for subset of pods
    * kube-proxy talks to iptables and makes service real
    * NodePort - builds on clusterIP
      * Also get Node Port - can configure in controller manager
      * Use IPtables to make another rule
* Cloud
  * Execution - elect a controller manager
  * kubelet is the only thing that's running on your system.  everythign else is in docker
  * kubelet/kubeproxy runs on all nodes
  * ingress
    * just rules
    * ingress-controller (pod) - it's open
      * uses rules
    * Example: sEtup ingress nodes for ingress controller
* Linux
  * container essentials
    * linux kernel namespaces:  way of isolating processes in contaiens
      * for file, process, network, etc.
      * you can join other processes into others 
      * cgroups are how you do for linux.  Can get 
    * union file systems
    * When creating pod, kubelet makes "infra" contaienr
      * small piece of code that's designed to just stay alive
    * rkt is other big alternative
      * CNI came from rkt
      * rkt is pod-native
      * You can just spin it off.  No longer a long-running daemon
      * Can do hypervisor isolation with rkt - get extra isolation.
      * can do just for some pods
* power user
  * bit.do/kube-decon-power    
  * SecurityContext - can define exec rules (read-only)
  * Network Policy - just labels/yaml (these pods can only talk to these pods, via labels)
  * Downward API - take metadata
  * ConfigMap/Secrets - key/value data.  Can mount as volume
  * Affinity - extra info for scheduler to tell what you want
  * Anti-affinity - have things that don't like each other.  Usually paired. (affinity /anti-affinity for GPU)
* Credits
  * Sozi: @senshu - sozi.baierouge.fr
  * OpenClipart.org
  * video: bit.do/kube-decon-full
  * basic: bit.do/kube-decon
  * power: bit.do/kube-decon-power
  * github: @carsonoid
