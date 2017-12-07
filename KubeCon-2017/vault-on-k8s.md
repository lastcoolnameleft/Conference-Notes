# Vault on k8s

* Armon, cofounder of hashicorp
  * hashicorp
    * run: nomad, consul
    * secure: vault
    * provision: vagrant, packer, terraform
* agenda
  * use cases, intro to vault, idntity in 0.9, k8s integration
* use cases
  * secret mgmt
    * eliminate secret sprawl
    * what is secret?  "anything used for authN or authZ"
      * sensitive is anythign confidential (cc #)
    * qustions in secret mgmt
      * how do we react to breach, how do we manage
    * state of world
      * secret sprawl
      * decentralized keys
      * limited visibility
      * poorly defined 'break glass' (how to recovery)
  * encryption as a serv
    * securely store data
  * identity + access mgmt
    * govern secret access
  * cryptoagraphy is hard, key mgmt is even harder
* Vautl intro
* single source for secres
* 2 diff audiences
  * app and tooling (want api)
  * human operators (want cli/ui) 
* What's the right way to be in the middle?
* goals
  * single source for secrets
  * oprogrammatic app access (automated)
  * modern dc friendly (pure s/w)
* vault features
  * secure secret storage (in-me, consul, file, rdbms)
  * dynamic secrets
  * leasing/renewal/revocation
  * audit, rich acls
* principles
  * confidentiality, integrity, availability
  * least privilege (need to know access)
  * priv separation (separ of controls
  * priv bracketing (time limited)
  * non-repudiation (audit loggin:  someone did somethign at some time)
* secure secret storage
  * data is encrypted in transit and rest
* dynamic secrets - differenciator
  * never provide "root" credentials to clients
  * provide limited access credentials based on role
  * generated *on demand* when requested
  * leases are enforceable via revocation
  * Pluggable backends
    * support: aws, consul, mssql, mysql, postgres, cassandra, mongodb, rabbitmq, ssh
* leasing, renewal, revocation
  * every dynamic secret (and token) has lease
  * secrets are revoked at end of lease unless renewed
  * secrets may be revoked early by operators
  * why leasing?
    * priv bracketing, non-repudiation (know which one was compromised)
* AuthN, AuthZ, Auditing (AAA)
  * authZ backends
    * machine oriented (tls, tokens, approle)
    * user oriented (user/pass, ldap, github)
  * req/resp auditing, fail closed (non-repudiation)
* Unsealing vault
  * data at rest is encrypted
  * requires descryption key
  * Master key is "key to kingdom"
    * all data could be decrypted
    * protect against insider attack
    * "two man rule"
  * NOONE gets master key
    * Shamir Secret Sharing
    * split in key shares (5-15 parts)  Need a threshold to get access to master key
    * like "red october" scene where you need multiple ones
  * automated unsealing
    * Can automate it, but shamir splitting is default
* Summary
  * solve secret sprawl problem
  * protects against insider threats
  * protects against external threats
  * applies security principles
* Identity
  * Entity - prep of single person/system that is consistent across logins
  * alias - mapping b/w entity and auth backend
  * Why do this in vault if using ldap?
    * If using multiple system, no longer single source of truth
    * take a step back from platform
  * identity groups
    * manage entities by placing them into groups
  * identity group aliases
* k8s auth backend
  * new in 0.8.3
  * binds k8s serv accts to a vault role (bind roles in k8s to roles in vault)
  * uses the tokenreview api to validate jwt's
  * doesn't need any external pieces
  * config
    * enable k8s backend
    * create a role
    * login

