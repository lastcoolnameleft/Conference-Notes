# Set Sail with Istio

* who
  * Lachian Evenson - Princ Program Mgr ACS/AKS - Microsoft
  * Going to be buzzword bingo
  * beginner, but will have other content
  * Standing room only
* istio - greek term for sail on boat
  * "Service meshes are the new black" - Jessie Frazelle 
    * This shows a community that is maturing
  * cloud.google.com/kubernetes-engine/kubernetes-comic/
  * Service 11 is down.  Please ring service 1-9 to find out why.
* who am I?
  * run userv in prod in k8s since '15
  * built early incarnations of "istio" like platforms
  * helping customers be successful on k8s
  * built upstream istio helm chart
* U-serv are hard!
  * It's hard 
  * "Kubernetes is a platform for building other platforms.  It's a better place to start; not the endgame" -- Kelsey Hightower
* Why are hard?
  * We're not in green-field.  We have baggage
  * u-serv command overhall of: People, tooling, processes
    * tooling is easy to change.  People and process are hard
    * u-serv expose cracks in arch
  * the first few services are relatively easy
  * contract points, sla, respon
  * "cambrian explosion"
  * tooling is nascent and bespoke
    * working in highly dynamic env
* why use?
  * should dev impl own monitoring, etc.
* Enter Istio
  * userv platform/Service mesh that provides all features
  * plugs into k8s
  * isn't silver bullet, next level platform
* features
  * traffic mgmt
    * smart routing, fault injection, ingress + egress routing
  * policy enforcement, metric, logs, traces (get for free), security (can control mtls)
* Istio for Operators and Istio for Developers
  * istio comprises of several userv
  * Pilot
    * control plane for managing Envoy (nginx/haproxy)
    * system of record for service mesh
    * abstracted from underlying prlatform (k8s, mesos, cf)
    * exposes API for serv disc, lb
    * Envoy is distributed data plane
  * Envoy
    * lives as sidecard on each pod
    * all ingress/egress traffic to/from this pod is routing via envoy cont
    * Services as in/off ramp to service mesh
    * Envoy config is distributed by Pilot
  * Istio for Operators
    * Envoys know about other envoys
    * ingress/egress.  This is important
    * How do you have everythign come from a single IP?  Envoy allows you to do this
  * Mutual TLS
    * Makes really simple.  
    * "You won't be proud if you do this yourself."
    * Istio ships with a CA
    * e2e mTLS established for each connection
  * Mixer
    * Policy engine - comprises all the tools needed to run userv
      * access control, telemetry, quota, billing, tracing
    * generic underlying platform ind abstract
    * Attributes
      * Massive amount of metadata
      * Generated by envoy
* Demo
  * helm install incubator/istio
  * First pass deploys CRD
  * 2nd pass deploys Istia
  * Walking through istio.io walkthrough
  * Had someone come up from crowd and run kubectl apply
  * distributed tracing
    * bundled with zipkin, but can use Jaeger
    * Looks like dev console in chrome
  * QnA:
    * all calls b/w envoy is wrapped in gRPC, but uses HTTP
    * If you have multiple con inside pod, what happens?  Envoy hijacks for all pods
  * gihub.com/lukebond/walk-run-fly-istio-kubernetes-talk