* Service Meshes and Observability
  * Ben Sigelman (cofounder + CEO, LightStep)
  * Making sense of the Service Mesh
  * Operating u-serv can be challenging, a Service Mesh can help
  * We want to build app s/w, but write same code over and over again that is hard compsci program
  * Can help with security
  * u-Serv transaction - Rubegoldberg machine
    * Tweet:  We replaced our monolith with user so that every outage could be more like a murder mystery - @honest_update
  * Distributed Tracing tell stories about transactions across serv boundaries
    * Jaeger + Lightstep
    * NewRelic/DataDog also provide
    * OpenTracing is linga franca for it
  * Transaction tracing w/o service mesh
    * Many points of integration.  lots of works with different lang
  * With service mesh
    * sidecars all us to put open tracing there
    * Single point of integration
  * Shared timing diagram
  * Observing every RPC is great but...something needs to tie it all together...and we get more detail about the problem
    * Just observing edges is sufficient
    * Able to connect the dots with OpenTracing
    * With OpenTracing, haven't tied yourself to specific tracing system
  * Need to apply to something REAL
    * Demo for donut.zone
* Brendan Burns - distinguished engineer, Azure
  * this is too hard
    * at least 3 files (code, dockerfile, k8s file)
    * at least 3 lang (code, dockerfile, yaml)
    * at least 3 tools (editor, ... 
  * e.g. port to listen on
    * in code, dockerfile, kubeconfig 
    * Need to push in all 3
    * we have not done enough work to make it as a single problem
  * Need to reconsider this to make eaiser
    * Principle #1: Everything in one place
      * 1 way to put port.  Need single source of truth
    * Principle #2: Build libraries not platforms
    * Principle #3: encourage sharing and reuse
      * People used to build their own gui, buttons, etc.
  * How do we do this?
    * When the components can be combined to create a platform, 
    * language idiomatic cloud
      * design your app in code (no more yaml, no more dsl)
    * more approachable
      * CS101, Hobbyists, non-tech professionals
    * better tooling
      * unit tests, style guides, code reviews
    * thoughtful lang features
      * turing completeness, abstraction, inheritance, etc.
    * People are wanting abstraction, inheritence
    * Just as locks went to being assembly, to higher order functions
  * This was always the plan
    * Metaparticle - language idiomatic cloud
    * View Containers/k8s as a complile target
  * Amazing demo showing metaparticle live and deploying in code
  * Syncronization
  * Patterns for distributed systems
    * We need to be in the business of mass production.  It's the only way to scale
  * github.com/metaparticle-io/package  
  * github.com/metaparticle-io/sync
  * metaparticle.io
* Can 100M dev use k8s
  * Alexis Richardson, CEO Weaveworks
  * who are tribes of the future?  developers
    * If you can merge a PR, you can be a dev
    * Today, GH announced 100M merged PR
    * Show example of colorize bot for Tom Baker
      * Uses OpenFaaS, WeaveCloud, GKE
    * NOTE:  HE WAS RIGHT BEHIND ME.  Really cool kid!
* Community Awards
