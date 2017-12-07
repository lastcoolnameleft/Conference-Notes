* About me
  * Steve sloka - sr sys s/w eng - Customer Success - Heptio
    * Heptio:  offer training, support and professional serv to speed integration of k8s
  * github.com/stevesloka @stevesloka
  * When wrote this preso: s/w arch, UPMC, now Heptio
  * UPMC - Univ of Pittsburgh MEdical Center
  * 80k employees, > 30 hospitals, $16 b integrated global non-profit health enterprise
* Clinical Data @ upmc
  * 1k different apps in upmc
  * Data is counted in PB /yr
  * everything from mental health, HIV status, abuse.
* HIPAA
  * Health Insur Portability and accountability Act
  * Prohibit disclosure or misuse of info about private indv
* types of data
  * ssn
  * MRN - medical record num
  * patent name
  * PII
* why create hippa?
  * standards
  * only strong as weakest link
* HIPPA rules
  * encryption at rest
  * encryption at transit (tls)
  * auditing to user lvl (lots of service accts.  those aren't good enough)
  * BAA - Business Assoc Agreement - contract with you and 3rd party on how to manage data
* OnPrem
  * k8s infra
    * Redhat Atomic
    * looking at migrating to CoreOS Techtonic
  * started journey at 2016
  * storage
    * nfs
    * local storage
    * some might have 20 users.  Somtimes complexity outweights usability
  * LB
    * F5 -> nodeports + ingress
  * workloads
    * ci/cd (gitlab runnsers/jenkins workers)
    * local agents (data colleciton + proxies)
  * OnPrem is hardER
* Public cloud
  * AWS - some services on Azure (AD)
  * Single region/multi-AZ
  * multiple worker Auto-scaling groups (ASG)
  * CloudFormation + CoreOS (container linux)
  * ECR
  * Classic ELB
  * VPN to onPrem
* AWS HIPPA compliant offerring
  * Not everything is compliant
    * New Services (EKS)
    * Internet g/w -> ELB(VPNs)
      * IGW <-> ELB IS NOT ENCRYPTED
  * Mike Kuentz @ AWS - Sr Soln arch @mkuentz
* k8s workloads
  * stateless apps
    * easy-peesy
    * just need to manage encrypt at transit
  * stateful apps
    * how do you manage persistent storage?
    * resize/upgrade
    * reconfigure/templating
    * backup - handle automatically
  * statefulSets
    * allow for persistent storage replicas to have an identity
    * "My Buddy" from 80's.  volume Follows pod
  * How do we resize?
    * Operator - Make it work like a cloud provided offering - Steve Sloka
    * Elastic-Operator  
      * mimic cloud offerings
      * full TLS
        * auto-generate cert
        * encrypted ebs volumes
        * communication tls (searchguard)
      * span AZ in AWS (creating and scaling)
      * Snapshots to S3
      * Deploy Add-ons auto
    * work to do
      * Shard/zone allocation
      * elastic cluster status
      * rolling restarts
* kong API gateway
  * OS API g/w
  * isolate traffic into our apps
  * neat logo
  * program via rest api
  * Deploy kong in every namespace
  * Not sidecars, deployed in every namespace
* Use fluentd - 
  * append HIPPA to log to dump to S3 bucket
* no rules around images, implemented twistlick for image scans    
  * Claire, kate, when new pods spins up checks image with claire.
* extra links
  * https://github.com/upmc-enterprises/kubernetes-on-aws
  * https://github.com/upmc-enterprises/elasticsearch-operator
