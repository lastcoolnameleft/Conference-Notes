# Lessons learned from the Charts Repo

* Who
  * Vic Iglesias, Cloud Soln Architect, Google
  * @vicnastea
* Helm 101
  * Tool for managing k8s apps
  * 2 parts:  client (helm), server (tiller)
  * helm is equivalent of apt
* Charts
  * helm packages
* What is k8s app?
  * pod, config, volumes, services
  * Helm lets you templatize it
  * rollback your app as a unit
    * not just roll back configmap, etc.
  * go templates
  * sprig functions - lets you set default value 
    * string, math, date, default, encoding, list functions
* Charts repo 
  * github.com/kubernetes/charts
  * centralized repo hosting community curated helm charts
  * probbaly not what you'll run in prod, but a stepping stone to get there
  * stats
    * 130+ charts, 2k+ pr, ~100 contributors
* Chart structure
  * chart.yaml - metadata about chart
    * Make sure to add sources + custom image
  * values.yaml - api you providde to users of chart
    * changes to this that are backward incompat, you should change major version
    * usually on spectrum (reproduceable <-> flexible)
      * start closer to reproduceable spectrum
  * requirements.yaml - define what other charts you want to deploy
    * version can be semver
  * templates folder - k8s manifests that can be templated out
  * notes file - nodes as chart creator.  spit out after chart is installed
  * readme.md - in depth of what people can do.
* Chart tricks
  * use helm create
    * scaffolds out a sample chart.  example is nginx webserver
  * use helm create with starter templates (e.g. daemon, service, stateful)
  * Update deployments on conf change
    * checksum/config: {{ include {print $.Template.Basepath "/configmap/spinnaker-config.yaml"} . | sha256sum }}
    * every time config file changes, it will deploy a new release because annotation has changed
  * run out of band steps with hooks
    * helm lets you do things as you install (e.g. post-install)
    * hook types;  Pre + Post install, delete, upgrade, rollback
  * Allow reuse of existing PVC for data
    * PVC: if { existing claim} claimName: { existingclaim}} {{ else }}
  * allow optional ingress config
    * if true, integress will be created.  
  * create a functional test (even if simple)
    * annotation: "helm.sh/hook": test-success
    * e.g. tests jenkins ui is accessible
    * of 130 charts, only ~10% has tests
  * Allow use custom ConfigMaps
    * initializer: customConfigMap: false
    * opposide side of reproduceability, but opens up more use cases for chart
  * Namespace your helper templates
  * Conditional dependencies
  * Use toYaml to give users more flexibility
    * nodeSelector: {{ toYaml .Values.nodeSelector | indent 8 }}
* What's next?
  * future work
    * Allows OWNERS file to dictate who can merge
    * deletegate respo of charts to other git repo
    * purse unmaintained charts
    * more functional tests for charts
