# Day 3 Keynote

* Sarah Novotny, head of OS Strategy, GCP
  * 2015 - Helped launch party for KubeConf
  * 2017 - was unsure if it was still my community
  * k8s is bus, we drive with wings, but we've strapped rockets on it
  * All 7 of creators of 4 founders had industry changing vision
  * growth caused shadowy power struggles
    * gov'n was important
    * steering committee backlog
    * culture, value, making exp better
  * room for improv
  * "culture eats strategy for breakfast" - Peter Drucker
    * If we go from 200 -> 4k in 2 years, what does 1 year look like?
  * Distribution > Centeralization
  * People are the nodes of this distributed system/culture
  * Inclusive > Exclusive
  * "Tell me and I forget, teach me and I may remember, involve me and I learn" - Ben Frank
  * Community > Company
  * bit.ly/k8smentoring 
    * Ead by George Castro, Paris Pitman
  * Automation > Process
    * "OSS projects have lots of hard work that isn't glamorous"
    * "Reward the actions you want to see"  (High work, low glamour)
  * What do we want next 1-5 years to look like?
    * Cross Industry collab
    * Learn from people before us
    * Learn from people who don't think/look like us?
    * "Coming together is a beginning.  Keeping together is progress.  Working together is success" -- Henry Ford
* Kelsey Hightower
  * "Who loves Github?  Who loves when GH does down?  Well, Github runs k8s, so when it goes down, we can all share the blame"
* Jesse Newland - Prin SRE - Github
  * 4 years ago, big DC migration that bought us time
    * Team was excited about new-found time
    * Looked at containers, and realzied it's a lot of work ahead
    * Got feedback from sr eng that was surprising.  They encouraged us to wait, and do nothing and let someone else build
    * Needs team with more exp of containerized workloads. 
    * We want to see this happen, but we're not the right team
    * Called project off
    * Was disappointed/sad, but In retro, was best technical advise was priv to get
  * GH is standardizing on k8s on arch
    * 20% of services is running on k8s
  * Ruby on rails that serves ui:  github.com/github/github
    * in k8s github-production namespace (168d)
  * didn't have exp operating a k8s cluster, but did have experiencing breaking one
  * 3 depoyments in k8s
    * unicorn
    * unicorn-api 
    * consul-service-router - routes traffic from app process to non-k8s services (ha proxy + consul template)
      * direct impl of how we did before - want to replace with Envoy
  * Build GLB - Github Load Balancer
    * Uses nodeport
  * Tools 
    * kube-testlib, kube-health-proxy, kube-namespace-defaults, kube-pod-patrol, node-problem-healder
    * All real s/w projects with tests and own repo
    * a yr ago, we might have used bash and checked into puppet
  * Github flow
    * typically use approved PR when behavior works
    * We bring up new env/ns for each pr
    * It's helpful during code review to see behavior, so it deploys to new env area
    * deploying to prod is risky
      * First deploy is canary deploy
      * to support look for k8s annotations "canary-able"
   * Now all other services deployed to k8s cluster can now use this canary workloads
* Brandon Philips - CTO - CoreOS
  * "Hi, I'm Brandon Philips and I have 5 minutes"
  * goal is to build/deploy/operate/upgrade with minimal toil
  * "It is a confusion of ideas to support that the economical use of fuel is equivalent to diminished consumption.  The contrary is the truth" - William Stanley Jevons
  * Future State - app version -> app catalog -> instances
  * Demo - Techtonic console
  * Want to create shared toolkit
  * See App-Def group + SIG apps
* Clayton Coleman, Arch k8s + OpenShift, Redhat
  * Top Contributor to k8s an OpenShift
  * Yesterday, spoke about why k8s should be boring
  * Call to action:  We should be making everything better
    * Very broad.  What are we building?  S/w  That's still broad
    * Better:  More subjective.  Want to make people happy
  * How do we do this? We already are
  * BUT if you haven't been engaged, or have been heads down
  * 2200 projects on k8s, and a CN landscpape that doesn't fit on a 4k monitor
  * Remember Ruby on Rails?  We didn't have to re-build the wheel.  So easy to add one-more-thing
    * RoR set tone for ecosystem.  Was about people who build gems, templates, etc.
  * 2018 - Year of the service mesh
