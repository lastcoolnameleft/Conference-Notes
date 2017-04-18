* Swarm is Cluster Orchestration
* Uses "Desired State Reconsiliation".
  * Comapres desired state vs actual state
  * Reconsiles till desired state = actual state
  * Node goes down affects
* Swarm topology
  * Manager - makes all decisions on how/where to run containers
    * If just 1 mgr, managers are group
    * Share info over "Raft" to ensure all nodes have same data
    * If fails, another manager decision
    * MOre than half must be participating to Raft
  * Worker runs container and reports status
  * In prod cluster
    * 3-5 is normal # of masters
* new features
  * HA Scheduling
    * ?? Priorprize spreaking out a # of containers to = # of nodes
    * Under old algorithm, try to spread out services across containers so that if node goes down, we can 
    # "docker service create --replicas 3 dockercon"
  * Topology Aware Scheduling
    * Nodes being aware in different Availability Zones
    * "docker node update --label-add az=1"
    * "docker service create --placement-pref 'spread=node.labels.az'
      * All unlabled nodes get own group
    * Now all contaienrs are guaranteed to get own AZ
  * Encrypted raft log
    * Security should not be an option
    * make easy to use
    * Raft log is backed up on disk.
    * Contains sensitive log data
    * "docker swarm init" - That's it
      * Encrypted by default
    * encryption keys
      * The keys are on disk and unencrypted
      * make sure to encrypt the keys themselves
      * "docker swarm init --autolock"
        * creates key to encrypt encryption keys
        * need this key to bring mgr back up
      * If using env-vars, you might expose secrets
        * if service crashes, might get env printed to file
      * Keys in Volumes -  
        * Put password in volume, then service moves, leave secret on this volumn that sticks around
    * Docker secrets
      * Manage secrets for you
      * On client: "docker secret create my-passwd password.file"
      * secret is encrypted and sent to Manager
      * Can update and then one-by-one services get secrets
      * How to access?
        * Stored in file.  Stored in tmpfs mounted to contaienr
          * If app goes down, then secret is gone
          * If service moves, secret goes with it
  * health-aware orchestration
    * Define Image healthcheck in Dockerfile
      * "HEATHCHECK --interval 10x CMD curl http://localhost/check"
    * Swarm can make healthchecks while in service
    * If healthcheck fails, manager can create new instance
    * key point: container doesn't mean it's crashed.  Just not healthy
  * Service Rollback
    * roll back a service to rpevious spec
      * Manually, or as part of rollback action
    * "docker service create --name docekrCon - replicas 1845"
    * 'docker service update --replicas 2017 --publish-add 443:443 --image dockercon Dockercon
      * new active spec
      * retain ref to prev spec
      * don't have to remember any changes from prev spec
    * 'docker service rollback'
    * rollback a rollback gets you back where you were
    * Rolling Update Modes
      * Update and wait until the next one is ready
      * Types:
        * continue
          * If service fails, you can set mode to "continue" to keep going
        * pause
          * stop rollout and evaluate manually
        * rollback
          * two failure options:  Pause or Continue
          * prevent infinite loop of rollback
  * Update tuning
    * e.g. 'docker service create --name Dockercon --update-failure-action rollback --update-max-failure-ratio 0.1 --update-monitor-period 10s'
  * Service Logs
    * Getting service logs is different from container logs
    * options:  ssh into each node?  setup logging system
    * SL is a way to fetch all logs from all services in one stream
    * Fetch logs from contaienrs of a service
    * includes logs from stopped contaienrs
    * use same API options as container logs
    * send logs context
    * 'docker service logs --tail 10 dockercon | sort -k3 k4'
      * Useful for getting all logs in date order
    * Log model
      * Swarm manager creates a subscription
