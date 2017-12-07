# Day 2 Keynote

* Kelsey Hightower - Staff Dev Advocate, Google
  * Major Milestone: Changes were so boring, nothing to announce.  
    * Goal: Getting close to boring
    * K8S is NOT the endgame
  * "Kubectl is the new SSH"
  * If you have to use ssh to change prod, you were doing your job wrong
  * They're at their best when they're hidden from your org.  No-one should know you're using k8s
  * If you work in enterprise and need to open tickets to make changes, you need separate environments
  * "do not go down rbac role if you don't have to"
  * As a dev, you have 1 flow in mind.  Everything else is noise
  * Demo
    * git cloned repo, updated go app
    * CI/CD will be table stakes
    * Demo build driggers:  "push to tag" -> stg "push to master" -> push to prod -> qa
    * Do not leak impl details into dev workflow
    * git tag 1.0.0 && git push origin --tags
      * Using "git tag" to pull kubectl files in a different repo.  Justing kubectl patch
    * Noone needs to see this repo, but it's a good place to put
    * If you don't want people to use kubectl, you must give them visibility
    * The more you give people visibility, the less they want to touch infrastructure
* Chen Goldberg  - Eng Dir, Google 
  * Want to talk about future
  * K8S system layers
    * ecosystem
    * interface layer: client lib + tools
    * Governance layer: automation + policy enforcement
    * App layer: deployment + routing
    * Nucleus:  API + execution
  * Automation
    * Reconciliation
      * Act, Observer, Diff
  * k8s api extensions
    * (Flexible) -- Core -> Kube aggregator -> API server build -> Customer resource Def (CRD) -- (Easier)
  * Demo - kube-metacontroller
    * By Anthony Yeh - s/w eng, Google
    * Demo extends statefulSet
    * Install metacontroller (kubectl apply -f manifests/)
    * Can install on any cluster (1.9? requirement)
* Clayton Coleman - arch, k8s + openshift, Redhat
  * Boring is Good
  * Infra is about turning impossible into ordinary
  * Opinion:  Boring K8s = everyone is happy
  * Redhat helps people build boring s/w
  * 3 variantes
    * OpensShift Online - Starter (FREE)
      * Fire #1: Events
      * Fire #2: Too many secrets - 800MB of secrets 
      * Fix #2: etcd3 to the rescue - 66% less mem usage
      * Fire #3: Edge cases can be sharp - 40 writes/sec for 1 cronjob
  * Come and be boring with us
* Zihao Yu, Illya Chekrygin, Sr Staff Eng, HBO
  * Pushing limit w/ Game of Thrones
  * HBO Digital products - provide HBO programming to any device
  * Streaming Serv on EC2
    * API serv in Nodejs, Single Serv = Single EC2 instance
    * ASG + Config, fronted by ELB, Route53
  * HBO Traffic pattern - Felt like John Snow facing the calvery
  * Problems
    * Wasteful - NodeJS + EC2 = 50% of CPU unutilized; multiply by overscaling
    * On Demand scaling up/down = slow
    * Service -> service:  Everyone gets ELB
  * Limis
    * EC2 - IP addr w/ subnet, instance types, ELB's, Autoscaling groups + configs
    * Auxilary - telemetry license (per instance)
  * Why k8s?
    * Utilization, Introspection, Faster, Safer, Batteries incldued
  * Step 1
    * EOY 2015, 0 containerized services
    * kube-up.sh and all defaults
  * Terraforming
    * Features, ha-multi-masters 
    * OIDC authN (coreos Dec, Github oauth)
    * Terraform template for a cluster
    * issues
      * Prometheus pod rescheduled when cluster scaled down
      * AWS insufficient capability for desired instance type
    * github.com/HBO/tf-modules
  * Network - 
    * Chose Flannel, was easiest at the time
    * Under heavy load, increased latency and timeouts
    * UDP packet drop
    * kube-dns
      * /etc/resolv.conf and ndots:5
      * ndots:5 means there will be many invalid lookups
      * k8s issue: 33554
      * Tuning:  --cache-size=10000 <- set to max unless you have memory issue
      * --address is perf booster
      * By not putting ip addr, NOTFOUND returns immediately
  * Telemetry
    * Grafana, Graphite + stats, ELK + Fluentd, Splunk Forwarder, Prometheu + cAdvisor
      * Prometheus - Not so easy with 300 notes @40 cores each + 20k containers
  * When we ready?
    * Load test, load test more!  Load test the shit out of it!
    * Search, report, fix, contribute
  * Advice
    * Trust yourself - small increments
    * Trust the team
    * Watch HBO
* Spike Curtis - Sr S/w eng - Tigera
  * Zero Trust K8s Networks
  * Maintainers of Flannel and CNI, stewards for calico
  * Why ?
    * Our apps are more distributed and
    * If we don't have hold, attackers can infiltrate
  * What happens if n/w itself is compromised?
    * We can use e2e encryp + auth
    * K8S network policy is great way to manage
    * Feature excited about:  Using istio to encrypt across services
  * How would you deploy? (k8s + istio the hard way)
    * Announce:  Calico support for unified policy
  * Calico Policy 
    * label selector:
    * In istio, use service account
    * Like 2FA, but for pods
    * Can bring down to lead priv (e.g. HTTP GET)
  * Zero Trust N/w model
    * The n/w is always assumed to be hostile
    * external + internal threads exist on the n/w at all times
    * network locality is not sufficieent for deciding trust
    * github.com/projectcalico/app-policy
  * talks
    * Istio: Sailing into a Secure Services Mesh - 
  * Announce:  Tigera CNX
    * tigera.io/cnx
* Craig McLuckie - CEO, Heptio
  * Road ahead for k8s
    * Dev productivity matters
    * multi-cloud is happening
    * enterprise is ... complicated
  * Recipe for -as-a-service
    * Technology
    * Provisioning / Integration API
    * Ops Team
    * You should focus on "how long does it take you to recover?"
    * There's a number of aways you can cut those 3 9's
  * Separation of concerns
    * "goldilocks abstraction"
    * Table format: DIY  | Cloud Alt
    * App O|s | SaaS
    * Serv Ops | Cloud Service
    * Cluster Ops | KaaS
    * Infra Ops | IaaS
    * Need Common Ops policy for : Governance, Risk mgmt, Compliance
  * Multi-cloud
    * Conformance matters
    * Congrats all major cloud providers that offer k8s aaS
  * Tool Example: Bringing Heptio Ark 
    * Disaster Recovery and portability to MS Azure
    * Not there yet on persistent volumes, but can move across clouds
  * Jim's Paradox - When you mass increase efficiency, you expect to see consumption go down
    * It actually goes up.  It drove consumption of coal considerablty 
