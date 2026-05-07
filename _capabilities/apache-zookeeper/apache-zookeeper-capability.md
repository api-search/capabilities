---
categories: []
consumed_apis: []
description: The ZooKeeper Admin Server provides an HTTP interface for monitoring and management commands. It exposes four-letter-word equivalent commands as REST endpoints for cluster monitoring, configuration, and diagnostics.
layout: capability
name: Apache ZooKeeper Admin Server API
operations:
- description: Apache ZooKeeper Get Server Configuration
  method: GET
  name: getconfiguration
  path: /conf
- description: Apache ZooKeeper List Client Connections
  method: GET
  name: getconnections
  path: /cons
- description: Apache ZooKeeper Reset Connection Statistics
  method: GET
  name: resetconnectionstats
  path: /crst
- description: Apache ZooKeeper List Sessions and Ephemeral Nodes
  method: GET
  name: getdump
  path: /dump
- description: Apache ZooKeeper Get Server Environment
  method: GET
  name: getenvironment
  path: /environment
- description: Apache ZooKeeper Health Check
  method: GET
  name: healthcheck
  path: /ruok
- description: Apache ZooKeeper Get Server Statistics
  method: GET
  name: getserverstats
  path: /stat
- description: Apache ZooKeeper Get Full Server Details
  method: GET
  name: getserverinfo
  path: /srvr
- description: Apache ZooKeeper Reset Server Statistics
  method: GET
  name: resetstats
  path: /srst
- description: Apache ZooKeeper Get Monitoring Metrics
  method: GET
  name: getmonitormetrics
  path: /mntr
- description: Apache ZooKeeper Get Watch Summary
  method: GET
  name: getwatchsummary
  path: /wchs
- description: Apache ZooKeeper Get Watches by Connection
  method: GET
  name: getwatchesbyconnection
  path: /wchc
- description: Apache ZooKeeper Get Watches by Path
  method: GET
  name: getwatchesbypath
  path: /wchp
- description: Apache ZooKeeper Get Data Directory Sizes
  method: GET
  name: getdirectorysize
  path: /dirs
- description: Apache ZooKeeper Check Read-only Mode
  method: GET
  name: isreadonly
  path: /isro
- description: Apache ZooKeeper Get Data Tree Digest
  method: GET
  name: gethash
  path: /hash
- description: Apache ZooKeeper Get Current Voting View
  method: GET
  name: getvotingview
  path: /voting_view
- description: Apache ZooKeeper Check if Leader
  method: GET
  name: getleader
  path: /leader
- description: Apache ZooKeeper Get Initial Configuration
  method: GET
  name: getinitialconfiguration
  path: /initial_configuration
- description: Apache ZooKeeper Get Last Snapshot Info
  method: GET
  name: getlastsnapshot
  path: /last_snapshot
- description: Apache ZooKeeper Get JVM System Properties
  method: GET
  name: getsystemproperties
  path: /system_properties
personas: []
provider_name: Apache ZooKeeper
provider_slug: apache-zookeeper
search_terms:
- apache zookeeper reset server statistics
- apache zookeeper get data directory sizes
- apache zookeeper get last snapshot info
- getconfiguration
- apache zookeeper list sessions and ephemeral nodes
- leader election
- apache zookeeper list client connections
- getleader
- apache zookeeper reset connection statistics
- getinitialconfiguration
- getmonitormetrics
- api
- apache zookeeper get jvm system properties
- getenvironment
- isreadonly
- distributed coordination
- apache zookeeper get server environment
- getwatchsummary
- open source
- getconnections
- getdirectorysize
- getvotingview
- apache zookeeper get data tree digest
- gethash
- apache zookeeper get server statistics
- getserverstats
- apache zookeeper get monitoring metrics
- configuration management
- apache zookeeper health check
- getwatchesbypath
- apache
- getwatchesbyconnection
- service discovery
- healthcheck
- getdump
- apache zookeeper get initial configuration
- zookeeper
- resetstats
- apache zookeeper check if leader
- apache zookeeper get full server details
- getsystemproperties
- getserverinfo
- apache zookeeper check read-only mode
- apache zookeeper get server configuration
- resetconnectionstats
- apache zookeeper get watch summary
- apache zookeeper get current voting view
- apache zookeeper get watches by path
- apache zookeeper get watches by connection
- getlastsnapshot
slug: apache-zookeeper-capability
source_filename: apache-zookeeper-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache ZooKeeper Admin Server API\n  description: The ZooKeeper Admin Server provides an HTTP interface for monitoring and management commands. It exposes four-letter-word\n    equivalent commands as REST endpoints for cluster monitoring, configuration, and diagnostics.\n  tags:\n  - Apache\n  - Zookeeper\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: apache-zookeeper\n    baseUri: http://localhost:8080/commands\n    description: Apache ZooKeeper Admin Server API HTTP API.\n    resources:\n    - name: conf\n      path: /conf\n      operations:\n      - name: getconfiguration\n        method: GET\n        description: Apache ZooKeeper Get Server Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cons\n      path: /cons\n      operations:\n      - name: getconnections\n\
  \        method: GET\n        description: Apache ZooKeeper List Client Connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crst\n      path: /crst\n      operations:\n      - name: resetconnectionstats\n        method: GET\n        description: Apache ZooKeeper Reset Connection Statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dump\n      path: /dump\n      operations:\n      - name: getdump\n        method: GET\n        description: Apache ZooKeeper List Sessions and Ephemeral Nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environment\n      path: /environment\n      operations:\n      - name: getenvironment\n        method: GET\n        description: Apache ZooKeeper Get Server Environment\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ruok\n      path: /ruok\n      operations:\n      - name: healthcheck\n        method: GET\n        description: Apache ZooKeeper Health Check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stat\n      path: /stat\n      operations:\n      - name: getserverstats\n        method: GET\n        description: Apache ZooKeeper Get Server Statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: srvr\n      path: /srvr\n      operations:\n      - name: getserverinfo\n        method: GET\n        description: Apache ZooKeeper Get Full Server Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: srst\n      path: /srst\n      operations:\n      - name: resetstats\n        method: GET\n        description: Apache ZooKeeper Reset Server Statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mntr\n      path: /mntr\n      operations:\n      - name: getmonitormetrics\n        method: GET\n        description: Apache ZooKeeper Get Monitoring Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wchs\n      path: /wchs\n      operations:\n      - name: getwatchsummary\n        method: GET\n        description: Apache ZooKeeper Get Watch Summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wchc\n      path: /wchc\n      operations:\n      - name: getwatchesbyconnection\n        method: GET\n\
  \        description: Apache ZooKeeper Get Watches by Connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wchp\n      path: /wchp\n      operations:\n      - name: getwatchesbypath\n        method: GET\n        description: Apache ZooKeeper Get Watches by Path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dirs\n      path: /dirs\n      operations:\n      - name: getdirectorysize\n        method: GET\n        description: Apache ZooKeeper Get Data Directory Sizes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: isro\n      path: /isro\n      operations:\n      - name: isreadonly\n        method: GET\n        description: Apache ZooKeeper Check Read-only Mode\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: hash\n      path: /hash\n      operations:\n      - name: gethash\n        method: GET\n        description: Apache ZooKeeper Get Data Tree Digest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: voting-view\n      path: /voting_view\n      operations:\n      - name: getvotingview\n        method: GET\n        description: Apache ZooKeeper Get Current Voting View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leader\n      path: /leader\n      operations:\n      - name: getleader\n        method: GET\n        description: Apache ZooKeeper Check if Leader\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: initial-configuration\n      path:\
  \ /initial_configuration\n      operations:\n      - name: getinitialconfiguration\n        method: GET\n        description: Apache ZooKeeper Get Initial Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: last-snapshot\n      path: /last_snapshot\n      operations:\n      - name: getlastsnapshot\n        method: GET\n        description: Apache ZooKeeper Get Last Snapshot Info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system-properties\n      path: /system_properties\n      operations:\n      - name: getsystemproperties\n        method: GET\n        description: Apache ZooKeeper Get JVM System Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ apache-zookeeper-rest\n    description: REST adapter for Apache ZooKeeper Admin Server API.\n    resources:\n    - path: /conf\n      name: getconfiguration\n      operations:\n      - method: GET\n        name: getconfiguration\n        description: Apache ZooKeeper Get Server Configuration\n        call: apache-zookeeper.getconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cons\n      name: getconnections\n      operations:\n      - method: GET\n        name: getconnections\n        description: Apache ZooKeeper List Client Connections\n        call: apache-zookeeper.getconnections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /crst\n      name: resetconnectionstats\n      operations:\n      - method: GET\n        name: resetconnectionstats\n        description: Apache ZooKeeper Reset Connection Statistics\n        call: apache-zookeeper.resetconnectionstats\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /dump\n      name: getdump\n      operations:\n      - method: GET\n        name: getdump\n        description: Apache ZooKeeper List Sessions and Ephemeral Nodes\n        call: apache-zookeeper.getdump\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /environment\n      name: getenvironment\n      operations:\n      - method: GET\n        name: getenvironment\n        description: Apache ZooKeeper Get Server Environment\n        call: apache-zookeeper.getenvironment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ruok\n      name: healthcheck\n      operations:\n      - method: GET\n        name: healthcheck\n        description: Apache ZooKeeper Health Check\n        call: apache-zookeeper.healthcheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stat\n      name: getserverstats\n      operations:\n      - method:\
  \ GET\n        name: getserverstats\n        description: Apache ZooKeeper Get Server Statistics\n        call: apache-zookeeper.getserverstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /srvr\n      name: getserverinfo\n      operations:\n      - method: GET\n        name: getserverinfo\n        description: Apache ZooKeeper Get Full Server Details\n        call: apache-zookeeper.getserverinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /srst\n      name: resetstats\n      operations:\n      - method: GET\n        name: resetstats\n        description: Apache ZooKeeper Reset Server Statistics\n        call: apache-zookeeper.resetstats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mntr\n      name: getmonitormetrics\n      operations:\n      - method: GET\n        name: getmonitormetrics\n        description: Apache ZooKeeper Get Monitoring Metrics\n        call:\
  \ apache-zookeeper.getmonitormetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wchs\n      name: getwatchsummary\n      operations:\n      - method: GET\n        name: getwatchsummary\n        description: Apache ZooKeeper Get Watch Summary\n        call: apache-zookeeper.getwatchsummary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wchc\n      name: getwatchesbyconnection\n      operations:\n      - method: GET\n        name: getwatchesbyconnection\n        description: Apache ZooKeeper Get Watches by Connection\n        call: apache-zookeeper.getwatchesbyconnection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wchp\n      name: getwatchesbypath\n      operations:\n      - method: GET\n        name: getwatchesbypath\n        description: Apache ZooKeeper Get Watches by Path\n        call: apache-zookeeper.getwatchesbypath\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /dirs\n      name: getdirectorysize\n      operations:\n      - method: GET\n        name: getdirectorysize\n        description: Apache ZooKeeper Get Data Directory Sizes\n        call: apache-zookeeper.getdirectorysize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /isro\n      name: isreadonly\n      operations:\n      - method: GET\n        name: isreadonly\n        description: Apache ZooKeeper Check Read-only Mode\n        call: apache-zookeeper.isreadonly\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hash\n      name: gethash\n      operations:\n      - method: GET\n        name: gethash\n        description: Apache ZooKeeper Get Data Tree Digest\n        call: apache-zookeeper.gethash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /voting_view\n      name: getvotingview\n      operations:\n      - method:\
  \ GET\n        name: getvotingview\n        description: Apache ZooKeeper Get Current Voting View\n        call: apache-zookeeper.getvotingview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leader\n      name: getleader\n      operations:\n      - method: GET\n        name: getleader\n        description: Apache ZooKeeper Check if Leader\n        call: apache-zookeeper.getleader\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /initial_configuration\n      name: getinitialconfiguration\n      operations:\n      - method: GET\n        name: getinitialconfiguration\n        description: Apache ZooKeeper Get Initial Configuration\n        call: apache-zookeeper.getinitialconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /last_snapshot\n      name: getlastsnapshot\n      operations:\n      - method: GET\n        name: getlastsnapshot\n        description: Apache\
  \ ZooKeeper Get Last Snapshot Info\n        call: apache-zookeeper.getlastsnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /system_properties\n      name: getsystemproperties\n      operations:\n      - method: GET\n        name: getsystemproperties\n        description: Apache ZooKeeper Get JVM System Properties\n        call: apache-zookeeper.getsystemproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apache-zookeeper-mcp\n    transport: http\n    description: MCP adapter for Apache ZooKeeper Admin Server API for AI agent use.\n    tools:\n    - name: getconfiguration\n      description: Apache ZooKeeper Get Server Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnections\n\
  \      description: Apache ZooKeeper List Client Connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getconnections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resetconnectionstats\n      description: Apache ZooKeeper Reset Connection Statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.resetconnectionstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdump\n      description: Apache ZooKeeper List Sessions and Ephemeral Nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getdump\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getenvironment\n      description: Apache ZooKeeper Get Server Environment\n      hints:\n        readOnly: true\n      \
  \  destructive: false\n        idempotent: true\n      call: apache-zookeeper.getenvironment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: healthcheck\n      description: Apache ZooKeeper Health Check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.healthcheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserverstats\n      description: Apache ZooKeeper Get Server Statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getserverstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserverinfo\n      description: Apache ZooKeeper Get Full Server Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getserverinfo\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: resetstats\n      description: Apache ZooKeeper Reset Server Statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.resetstats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmonitormetrics\n      description: Apache ZooKeeper Get Monitoring Metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getmonitormetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwatchsummary\n      description: Apache ZooKeeper Get Watch Summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getwatchsummary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwatchesbyconnection\n      description: Apache ZooKeeper Get Watches by Connection\n   \
  \   hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getwatchesbyconnection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwatchesbypath\n      description: Apache ZooKeeper Get Watches by Path\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getwatchesbypath\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdirectorysize\n      description: Apache ZooKeeper Get Data Directory Sizes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getdirectorysize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isreadonly\n      description: Apache ZooKeeper Check Read-only Mode\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.isreadonly\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethash\n      description: Apache ZooKeeper Get Data Tree Digest\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.gethash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvotingview\n      description: Apache ZooKeeper Get Current Voting View\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getvotingview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getleader\n      description: Apache ZooKeeper Check if Leader\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getleader\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinitialconfiguration\n      description: Apache ZooKeeper Get Initial Configuration\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getinitialconfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlastsnapshot\n      description: Apache ZooKeeper Get Last Snapshot Info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getlastsnapshot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsystemproperties\n      description: Apache ZooKeeper Get JVM System Properties\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: apache-zookeeper.getsystemproperties\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-zookeeper/refs/heads/main/capabilities/apache-zookeeper-capability.yaml
tags:
- Apache
- Zookeeper
- API
tools:
- description: Apache ZooKeeper Get Server Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfiguration
- description: Apache ZooKeeper List Client Connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnections
- description: Apache ZooKeeper Reset Connection Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: resetconnectionstats
- description: Apache ZooKeeper List Sessions and Ephemeral Nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdump
- description: Apache ZooKeeper Get Server Environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvironment
- description: Apache ZooKeeper Health Check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: healthcheck
- description: Apache ZooKeeper Get Server Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverstats
- description: Apache ZooKeeper Get Full Server Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserverinfo
- description: Apache ZooKeeper Reset Server Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: resetstats
- description: Apache ZooKeeper Get Monitoring Metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonitormetrics
- description: Apache ZooKeeper Get Watch Summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwatchsummary
- description: Apache ZooKeeper Get Watches by Connection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwatchesbyconnection
- description: Apache ZooKeeper Get Watches by Path
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwatchesbypath
- description: Apache ZooKeeper Get Data Directory Sizes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdirectorysize
- description: Apache ZooKeeper Check Read-only Mode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: isreadonly
- description: Apache ZooKeeper Get Data Tree Digest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethash
- description: Apache ZooKeeper Get Current Voting View
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvotingview
- description: Apache ZooKeeper Check if Leader
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getleader
- description: Apache ZooKeeper Get Initial Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinitialconfiguration
- description: Apache ZooKeeper Get Last Snapshot Info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlastsnapshot
- description: Apache ZooKeeper Get JVM System Properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystemproperties
---
