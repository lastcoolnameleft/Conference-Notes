# Dan Kohn - Exec Dir - CNCF

* Now CNCF 2017: 14 projects
* K8S is #9 for commits, and #2 for authors (#1 is Linux)
* devstats.k8s.io
* Google trends - k8s is dominant (over openstk, etc.)
* 4k attendees (more than previous combined)
* Can be certified admin (online proctored exam, 600 people registered)
* 40 sponsors a year ago, 106 this year
* 22 diamond/platinum sponsors
* 28 members when started (2 yrs ago), 150 now)
* k8s Certified service provider - 25 k8s CSP partners (Cardinal )
* Certified k8s - 42 platform is conformant

## Hong Tang - Chief Architect - Alibaba Cloud

* Founded 2009, #1 cloud provier in China (47% market share)
* Launch partner for cert k8s
* $25b on 11/11/17 - SinglesDay
  * 325k order/sec at peak
* Container tech - Probably largest hybrid-cloud  
  * 10k container instances prov in 10 min
  * 100ks of running containers for transaction processing
  * Helm template for Tensorflow

* Serverles @ CNCF
  * 1st kubecon serverless tack 
 * github.com/cncf/wg-serverless
* 2018 
  * Can be certified admin (online proctored exam, 600 people registered)
* 40 sponsors a year ago, 106 this year
* 22 diamond/platinum sponsors
* 28 members when started (2 yrs ago), 150 now)
* k8s Certified service provider - 25 k8s CSP partners (Cardinal )
* Certified k8s - 42 platform is conformant

## Hong Tang - Chief Architect - Alibaba Cloud

* Founded 2009, #1 cloud provier in China (47% market share)
* Launch partner for cert k8s
* $25b on 11/11/17 - SinglesDay
  * 325k order/sec at peak
* Container tech - Probably largest hybrid-cloud  
  * 10k container instances prov in 10 min
  * 100ks of running containers for transaction processing
  * Helm template for Tensorflow

* Serverles @ CNCF
  * 1st kubecon serverless tack 
 * github.com/cncf/wg-serverless
* 2018 - Copenhagen
  * NA - Seattle
  * China - Shanghai
* Diversity Scholarships 
  * 30 scholarships in Austin
  * $70k in scholarships
  * Google + MS added $80k
  * Now $250k
  * 103 scholarships now!

# Michelle Noorali, Sr S/w eng, Azure

* Helm maintainer, SIG coordinator, cochair of conf
* hello world
  * Sessions, SIG, Technical Salons, Hallway Track
* CNCF hosts 14 projects, crazy because it's 2 years old
* Cloud Native Landscape - icons are getting smaller
* how'd we get here?
  * Rise of u-serv
  * Rise of clouda
* k8s is 1st project donated to CNCF
  * Google wanted to donate to vendor neutral party
  * 3 of largest cloud providers announced managed cloud provider
* k8s 1.9
  * Workloads API will be stable - apps/v1, (DaemonSet, Deployment, ReplicaSet, StatefulSet)
  * Windows Containers is beta
* CoreDNS - 1.0 is released
  * Available as replacement for kube-dns
* ContainerD - insdustry std container runtime
  * Allows to exec images
  * Based on Docker Engine's core container runtime
  * CRI - what allows you to swap out container runtimes
  * Containerd is 1.0.0.
* Rkt - rktlet - CRI impl to integrate with k8s
  * culiminated to OCI
  * CNI came out of rkt
* CNI
  * spec + Lib for writing plugins to config n/w
  * approaching 1.0
* Running containers isn't enough
  * Observability
  * Twitter has own observability team
  * Prometheus -> lead into Tom

# Tom Wilkie, Founder Casual
* Prometheus
  * OSS Monitoring + time series DB
  * Powerful, consise query lang
  * 2nd project adapted by CNCF
  * Highly dynamic env put strain on db.  Re-wrote and is Prometheus 2.0
  * Growth is 5x (2x increase in GH stars)
  * PromCon - 220 attendees
  * Prometheus blog for happy-hour

# Eduardo Silva, OSS Eng, Treasure Data
* Fluentd - logging
  * Why logging?  Want to analyze app behavior
  * Logging pipeline
    * Logging -> logs -> input -> parse -> filter -> buffer -> Output -> Storage
    * Logging -> FluentD -> Storage
 * Data transformation
 * Fluentd 1.0 announced
 * New:  multi-process workers, sub-second time resolution, native TLS support, 
  * Use Apache Kafka 
  * Better integration with Prometheus
  * Ported to windows
* Announce - FluentBit
  * github.com/fluentd/fluentbit

# Open Tracing
* Distributed tracing standards
  * 4 new lan, 9 total
* Jaeger - distributed tracing system,
* Built by eng team at Uber

# Oliver Gould, CTO, Buoyant

* Linkerd - Reliability
* release every 2 weeks, current 1.3.3
* What if we could build the ideal service mesh based on everything we've learned?
* Introduce
  * Conduit - not part of Linkerd, other than same people
  * Live demo
    * install conduit "conduit install -v k8s-demo | kubectl apply -f -
    * Redeploy app while running
    * Sidecar 
    * "contuid stat paths all"
    * See latency
    * "conduit tap deploy ..." - sends query into all proxies as running and puts in CLI
      * See grpc errors
      * All running live
      * has nice dashboard
    * Conduit.io
  * Clean break to focus on lightweight for what service mesh should be

# Envoy
* Enboy is edge and service proxy. abstracts n/w in platform/lang independent manor
* edge + service proxy
* makes n/w transparent
* Originally built at lyft
* v1.5.0, gRPS v2 API

# gRPC
* Makes easier to create distributed apps and serv

# Security
* TUF - s/w update spec
  * Attacks are expected
  * Secure key revocation
  * used around iot
* Notary has adapted TUF
  * add any digital distribution sys 

# Imad Sousou - VP s/w serv group & GM, OS Tech Center, Intel

* Isolation continuum - Containers on one end, VM on the other
* Issue 
  * Container: is if kernel is compromised, all containers are compromised
  * VM: slow.
* Choice:  Spee or Secuirty
* How do you make containers more secure?
* Announce:  katacontainers - Intel Clear containers + Hyper runV
  * hw/ accelerated containers that use virtualization Tech 

# Dianne Marsh - Dir of Eng, Netflix
* Cloud native CD - Spinnaker + Culture behind tech
* Culture impacts the tech
* Netflix Culture
  * avoid rules
  * Courage + Selflessness
* Spinnaker
  * Originally created Asgard, then Edge Center
* Result product was CD + Infra mgmt tool
* Spinnaker was internal tool at 2014
* Spinnaker features
  * bake, dep, hotfix, ....
  * Persistent properties
* Want to deter deploying globally at the same time, because it undoes "active-active" deployment.
  * Allow it, but discourage
* Pluggable architecture
  * CHaP - Chaos Automation Platform
  * Automated Canary
* CONTEXT: Provide Guardrails, not Gates
  * Engineers decide when to deploy
  * With context from execution windows (graph to see when service is minimally used)
  * Provide contexts with traffic guards
* Allow "manual judgment" - 
  * Goes against CD, but good for getting started
* Smart defaults based upon crticiality
* Culture
  * Interest to delegate
    * 2013 - Let us configure all the things
    * 2017 - Give us smart defaults (what are you making your users know?)
  * Best Practices across providers
  * Deploy more often ~8k orchestrations/day
* Choose tools wisely, don't fight culturea

# Adrian Cockcroft - VP Cloud Arch Strag, AWS
* Cloud Native Principles (see: re:Invent talk ARC219 on YouTube)
  * Pay as you go, afterwards
  * self-service no waiting
  * globally distributed by default
  * x-zone/region AZ
  * high util - turn idle resources off
  * Immutable code deployments
 * Fargate
  * No machine instances to manage
  * container is Natively managed by AWS 
  * Takes away AMI, need to run daemon
  * w/in ECS, same task definition schema
  * use ECS API to launch Fargate containers
  * Easy migration, Run Fargate + EC2 launch type tasks
* Also announced bare-metal on AWS
* 63% of K8S workloads run on AWS
* AKS
  * Want OS K8S Experience
  * Want Native AWS integration
  * Heptio IAM Authenticator
  * IAM roles for Pods
    * github.com/jtblin/kube2iam
    * Runs as DaemonSet
  * Hashicorp Vault
  * SPIFFE - Security Protection Identity Framework for Everyone
    

