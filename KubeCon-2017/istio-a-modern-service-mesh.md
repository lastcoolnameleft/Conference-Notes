# Istio
* Louis Ryan @ Google & Shriram Rajajopalan @ IBM

* What is Service Mesh?
  * Network for services, not bytes
    * Observability, reliability, traffic control, security, policy enforcement
* How does Istio work? 
  * Uses sidecar for everything.  Together creates service mesh
  * Acts on inbound + outbound traffic
  * inbound:  rate limits, service auth, authZ, fault injection
  * outbound: service authN, Load balance
* Control Plane
  * 3 components manage mesh
    * Pilot - discovery + config data to proxies
    * Mixer - policy enforce agent, telemetry, policy checks
    * Security - TLS cert to proxy
  * 0 code change, app is unaware of sidecard presence
  * Decoupled from dev policies
* Chose envoy as sidecar
  * C++ based L4/L7 proxy
  * Low memory footprint
  * Battle-tested @ Lyft (100+ serv, 20k VM, 5M rps)
  * Goodies: API driven config updates (no reloads)
    * Zone aware lb w/ failover
    * Traffic routing + splitting
  * NOT tied to Envoy.  Can swap out with others
* Get visibility
  * "Monitoring + tracing should not be an afterthought in infrastructure" 
  * Goals
    * Metrics w/o instrumenting apps
    * Consistent metrics across fleet
    * trace flow of req across svc
    * portable across metric b/e providers
  * istio/zipkin tracing dashboard
* Traffic Splitting
  * A/B testing
    * Can do auto-scalers on each version
