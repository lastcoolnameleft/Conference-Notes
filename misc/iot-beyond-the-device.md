* Kent Stroker
    * Cloud/IoT Consultant & Evangelist
* Sponsors
    * Microsoft
    * Hackster.io
* What is IoT?
    * Things
    * Insights
    * Actions
* IoT Future
    * 25 B connected things by 2020
    * $1.7 trillion market for IoT by 2020
    * 70% of value enabled by IoT will come from B2B
* Cloud explained using Cake
    * Cake IaaS - get a provider
    * Cake IaaS + Frosting PaaS
        * Already has IaaS Cake
        * Just add Frosting PaaS
    * Cake PaaS
        * Buy a pre-built Cake
    * Cake as a Service
        * Pay for only what you eat
    * Who is responsible for cake security?
        * The consumer bears ultimate resp for security.  Not the provider
* IoT
    * Things -> Connectivity -> Data -> Analytics -> Action
    * The "thing" is only 20% of the soln
    * If you're not doing analytics, you're not doing IoT
* Tyeps of things
    * Basic - temp probs
        * Just generating and transmitting data
    * Smart
        * Digital Signage (facial recog)
        * Home energy mgmt
    * Non-OS (Arduino) / OS (Win10 IoT Core) Based
        * Win 10 IoT Core - Now free, no shell, x86 or ARM
        * Win 10 IoT Enterprise - Basically Win10
    * Physical / Simulated
    * Certified devices - catalog.azureiotsuite.com
* Today's Workshop
    * Simulated Devices
        * Laptop Based
            * Node.js app console
        * Web Based
            * RPi web simulator
* 3 Pillars of IoT
    * Connectivity
    * Data / Storage
        * Stream/Batch processing, App Business Logic
    * Analytics
* Security
    * Device Security
* Azure IoT Hub
    * why?  Device connectivity is a challenge.
    *  DEvice twins - store, sync, and query service metadata and status info
        * Allows you to handle disconnected data
        * Live construct that sits b/w device and hub
    * Per-device auth key
    * Route device-to-cloud messages to Azure serv on declaratives rules
        * No code ability route messages replacing pre-invest
    * Monitoring of device connectivity
    * Extenstive set of libs
    * IoT protocols and extensibility
        * MQTT v3.1.1, Http1.1, AMQP 1.0
    * Scale
* Device Twin
    * D2C -> Device to cloud
    * C2D -> Cloud to Device
    * Properties:  Desired, reported
    * Can talk direct method
    * Unique to MSFT soln
* Industry protocols
    * Each industry uses diff protocols.  Pick an industry and learn those
* Publisher/Subscribe Messaging
    * MQTT - Message Queue Telemetry Transport
        * Mosquitto - OSS one
        * Open & simple
        * QoS:  3 settings
        * scales to monstrous numbers
        * Gaps: No JMS, Kerberos
    * AMQP - since 2004
        * Evolution of MQTT.
        * Does more
        * Use for new project
* AZure Hubs
    * Azure Notification Hub
    * Azure Service Bus - older
    * Azure Event Hub - IoT Hub is Event Hub with more stuff
    * Use IoT Hub if talking to device, everything else.  EventHub (e.g. webserver)
* Kafka
    * Basically OSS verison of IoT Hub
    * Not auto-scaleable
* Cold/Hot Path Processing
    * Cold:  Data stored for later processing
    * Hot: Data processed in real-time
        * Stream Processing:  Hadoop/Spark
* Azure Functions
    * Scenarios - Real-time stream processing
        * From IoT Hub, write to DB
* Azure Storage
* Azure Databases
    * SQL Database
    * Azure Database for MySQL
    * Azure Database for PostGres
    * SQL Data Warehouse
    * SQL Server Stretch Database
    * Azure Cosmos DB
    * Table Storage
    * Redis Cache
    * Data Factory
* Azure Time Series Insights
    * Get near real-time insights in seconds
* Microsoft Azure IoT Suite
    * 3 models
        * Remote monitoring
        * Predictive Maintenance
        * Connected Factory
* Azure IoT Edge
    * Use existing devices, using existing protocols
    * On-Prem gateway
    * Reduce model learning to the edge to reduce time detection
* Microsoft IoT Central
    * SaaS for IoT
        * Manage everything.  Hardware, Dashboard, etc.
* Project Sopris
    * MSFT Research looked at devices and realized very insecure
    * list 7 properties of highly secure devices
        * H/w based root of trust
        * small trusted computing base
        * defense in depth
        * compartmentalization
        * Certificate-based Auth
        * Renewable Security
        * Failure Reporting
    * Added TPM chip
        * Similiar to Arduino, but believe unhackable
* Next steps
    * https://www.edx.org/
    * https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-get-started
    * https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps
    * https://github.com/kentstroker/IoT-Live-2017
* Quotes
    * "Second mouse always gets the cheese"
    * Each DC is ~2 football fields and 600k servers
        * Shipping container containers 2k servers each
    * New delivery points - In the ocean
        * Why?  Cooling is cheap.  Latency.  International waters.
    * AWS infrastructure is built around e-commerce
        * Focused on IaaS.
        * Microsoft DNA is older
* Commands
    * az group create -n hackster-live -l eastus
    * az iot hub create -g hackster-live -n falgout-iothub-01 -l eastus --sku F1 --unit 1
    * az iot hub show-connection-string -g hackster-live
    * az iot device create --hub-name falgout-iothub-01 --device-id myFirstNodeDevice
