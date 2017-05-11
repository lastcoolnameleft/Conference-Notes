* Presentor: Rimma Nehme
* Started in 2010
* What?
  * Most DB are not available for turnkey globally distributed db
  * Will seemlessly replicate data
  * Schema agnostic
  * Key/value, graph, Object
  * multiple consistency choices
  * ms latency at 99 percentile
* Designed as db for planet-scale apps
  * App starts in one spot, but then grows to global
  * Core differentiator: 
    * Turn-key global distribution
    * Just select to specify new region
* Features
    * Global Distribution, from ground up
    * Cosmos is a Ring 0 Azure Service
        * Avail in Azure Regions by default 
        * Including sovereign/gov't clouds
    * Policy-based geo-fencing
    * e.g. Only a specific IP set can access
    * Multi-homing API's
    * Don't need to do anything to deply new region + failover
    * Support manual/auto failover
    * Can simulate failure
    * Can specify priroities in failovers
    * Can horizontally scale storage + throughput
      * From GB of Data -> PB
      * 100's trans/sec -> Mill of trans/sec
* Scale
  * Scale worldwide
  * Storage: GB -> PB
  * Pay only what you need
* Latency
  * r/w served from local region
  * Guaranteed ms latency, worldwide
  * write optimized, latch free db engine
  * auto indexing
  * Reads 1KB: 50th: < 2ms, 99th < 10ms
  * writes 1kb: 50th: < 6ms, 99th < 15ms
  * Wants customers to just store data, we'll deal with it
* belief:  No data is born relational
  * We'll store and support in whatever form it comes
  * multi-model + multi-APi
  * models
    * key-value
    * document
    * graph
  * apis
    * documentdb
    * mongodb (ga'ed in march)
    * tables (corresponds to azure table store)
    * gremlin graph
* Features
  * Schema-agnostic, multi-model, multi-API
* Consistency models
  * 1 - Strong
  * 2 - Bounded Staleness
  * 3 - Session
  * 4 - Consistent Prefix (new)
  * 5 - Eventual
  * Based on CAP theory
    * https://en.wikipedia.org/wiki/CAP_theorem
    * When faced with failures, have to choose b/w consistency and avail 
  * Taken 50 yrs of distributed system development
  * Most choices now
    * Red/blue pill
    * Give 5 options
  * Pick model via API or Portal
  * Metrics
    * 3% strong consitency
    * 4% eventual consistency
    * LOTS of potential in the middle
  * Video with Dr. Leslie Lampert
    * Turing Award Winner
    * expert in distributed systems
    * Any sytem has tradeoff of consistency or avail
    * Most db's on market provide: PErfect/Strong or Eventual
      * CosmosDB  provides 3 more
    * TLA Plus made CosmosDB in 2 ways
      * helped provide consistency conditions
      * HElped prevent concurrency issues usually found in prod 
    * http://lamport.azurewebsites.net/video/videos.html
* Security
  * Encrytpion at rest
  * enc is enabled auto by default
    * transparent to app
  * Compliance
    * HIPPA 
* Core values
  * Glboal distributed db
  * Limitless Scale
  * Well-defined consistency
  * Multi-model
  * ms latency
  * Comprehensive SLA
* Customer
  * Johnston Controlsa
    * Why?
      * Polyglot Hub for IoT Data
      * Semi-structured data with semantic translations/Master schema included
      * Multi Access Types 
        * Faste enough for simple key/val, doc for semi-structured, SQL query lang
      * Free form text search
  * Own stream analytics
    * CosmosDB as underlying storage
    * Flexibility is great, store single events or wide, densely packaged samples
    * Scale up as needed
* request unit per minute (RU/m)
  * Predictable perf for unpredict needs
    * billed hourly similar to RU/S
    * Spread provisioning throughput across the minute
    * Good for spikey workloads
    * Up to 73% reduction in cost
  * Azure Tables
    * k/v store for quick dev
    * low cost
    * Customers ask: 2nd indices + perf
  * Gremlin API in Azure CosmosDB
    * Gremlin Standard
    * Apache Tinkerpop
    * How is Gremlin diff from Neo4J?
* Demo - Graph
  * Demo will be available via Github
  * Use Gremlin to create customized data
  * "g.addV('person').propery('name', 'Stephen')
  * Adding edges and vertices
* LInks
  * cosmosdb.com
  * aka.ms/cosmosdb
  * aka.ms/CosmosDB-emulator
* Q&A
  * CosmosDB = "Hot data lake"
  * Spark tie-ins
  * Fast enough to get rid of Redis cache