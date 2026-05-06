---
categories: []
consumed_apis: []
description: Eureka REST operations for service registration, discovery, and instance management. Eureka is a REST-based service for locating services for the purpose of load balancing and failover of middle-tier servers.
layout: capability
name: Netflix Eureka REST API
operations:
- description: Get all registered applications
  method: GET
  name: getallapplications
  path: /apps
- description: Get application by name
  method: GET
  name: getapplication
  path: /apps/{appId}
- description: Register a new application instance
  method: POST
  name: registerinstance
  path: /apps/{appId}
- description: Get a specific instance
  method: GET
  name: getinstance
  path: /apps/{appId}/{instanceId}
- description: Deregister an instance
  method: DELETE
  name: deregisterinstance
  path: /apps/{appId}/{instanceId}
- description: Send heartbeat
  method: PUT
  name: sendheartbeat
  path: /apps/{appId}/{instanceId}
- description: Update instance status override
  method: PUT
  name: updateinstancestatus
  path: /apps/{appId}/{instanceId}/status
- description: Remove status override
  method: DELETE
  name: removeinstancestatusoverride
  path: /apps/{appId}/{instanceId}/status
- description: Update instance metadata
  method: PUT
  name: updateinstancemetadata
  path: /apps/{appId}/{instanceId}/metadata
- description: Get instance by ID
  method: GET
  name: getinstancebyid
  path: /instances/{instanceId}
- description: Get recent changes (delta)
  method: GET
  name: getdelta
  path: /apps/delta
- description: Query by VIP address
  method: GET
  name: getbyvipaddress
  path: /vips/{vipAddress}
- description: Query by secure VIP address
  method: GET
  name: getbysecurevipaddress
  path: /svips/{svipAddress}
personas: []
provider_name: Netflix Eureka
provider_slug: netflix-eureka
search_terms:
- update instance status override
- query by secure vip address
- sendheartbeat
- removeinstancestatusoverride
- deregister an instance
- send heartbeat
- update instance metadata
- service registry
- java
- remove status override
- netflix
- eureka
- getbysecurevipaddress
- getallapplications
- getdelta
- getinstancebyid
- failover
- cloud native
- getinstance
- registerinstance
- deregisterinstance
- get recent changes (delta)
- updateinstancemetadata
- service discovery
- api
- getbyvipaddress
- get application by name
- register a new application instance
- get a specific instance
- query by vip address
- getapplication
- updateinstancestatus
- get instance by id
- load balancing
- microservices
- get all registered applications
slug: netflix-eureka-capability
source_filename: netflix-eureka-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Netflix Eureka REST API\n  description: Eureka REST operations for service registration, discovery, and instance management. Eureka is a REST-based\n    service for locating services for the purpose of load balancing and failover of middle-tier servers.\n  tags:\n  - Netflix\n  - Eureka\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: netflix-eureka\n    baseUri: http://localhost:8761/eureka\n    description: Netflix Eureka REST API HTTP API.\n    resources:\n    - name: apps\n      path: /apps\n      operations:\n      - name: getallapplications\n        method: GET\n        description: Get all registered applications\n        inputParameters:\n        - name: regions\n          in: query\n          type: string\n          description: Comma-separated list of remote regions to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: apps-appid\n      path: /apps/{appId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Get application by name\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerinstance\n        method: POST\n        description: Register a new application instance\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: Application name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-instanceid\n      path: /apps/{appId}/{instanceId}\n      operations:\n      -\
  \ name: getinstance\n        method: GET\n        description: Get a specific instance\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n          description: Instance ID (typically hostname)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregisterinstance\n        method: DELETE\n        description: Deregister an instance\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sendheartbeat\n        method: PUT\n        description:\
  \ Send heartbeat\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          description: Overridden status value\n        - name: lastDirtyTimestamp\n          in: query\n          type: string\n          description: Last dirty timestamp for conflict resolution\n        - name: overriddenstatus\n          in: query\n          type: string\n          description: Overridden status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-instanceid-status\n      path: /apps/{appId}/{instanceId}/status\n      operations:\n      - name: updateinstancestatus\n        method: PUT\n        description: Update instance status override\n        inputParameters:\n    \
  \    - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: value\n          in: query\n          type: string\n          required: true\n          description: New status value\n        - name: lastDirtyTimestamp\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeinstancestatusoverride\n        method: DELETE\n        description: Remove status override\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        - name: lastDirtyTimestamp\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-instanceid-metadata\n      path: /apps/{appId}/{instanceId}/metadata\n      operations:\n      - name: updateinstancemetadata\n        method: PUT\n        description: Update instance metadata\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instances-instanceid\n      path: /instances/{instanceId}\n      operations:\n      - name: getinstancebyid\n        method: GET\n        description: Get instance by ID\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: apps-delta\n      path: /apps/delta\n      operations:\n      - name: getdelta\n        method: GET\n        description: Get recent changes (delta)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vips-vipaddress\n      path: /vips/{vipAddress}\n      operations:\n      - name: getbyvipaddress\n        method: GET\n        description: Query by VIP address\n        inputParameters:\n        - name: vipAddress\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: svips-svipaddress\n      path: /svips/{svipAddress}\n      operations:\n      - name: getbysecurevipaddress\n        method: GET\n        description: Query by secure VIP address\n        inputParameters:\n\
  \        - name: svipAddress\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: netflix-eureka-rest\n    description: REST adapter for Netflix Eureka REST API.\n    resources:\n    - path: /apps\n      name: getallapplications\n      operations:\n      - method: GET\n        name: getallapplications\n        description: Get all registered applications\n        call: netflix-eureka.getallapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Get application by name\n        call: netflix-eureka.getapplication\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n    - path: /apps/{appId}\n      name: registerinstance\n      operations:\n      - method: POST\n        name: registerinstance\n        description: Register a new application instance\n        call: netflix-eureka.registerinstance\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Get a specific instance\n        call: netflix-eureka.getinstance\n        with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}\n      name: deregisterinstance\n      operations:\n      - method: DELETE\n        name: deregisterinstance\n        description: Deregister an instance\n        call: netflix-eureka.deregisterinstance\n     \
  \   with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}\n      name: sendheartbeat\n      operations:\n      - method: PUT\n        name: sendheartbeat\n        description: Send heartbeat\n        call: netflix-eureka.sendheartbeat\n        with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}/status\n      name: updateinstancestatus\n      operations:\n      - method: PUT\n        name: updateinstancestatus\n        description: Update instance status override\n        call: netflix-eureka.updateinstancestatus\n        with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}/status\n      name:\
  \ removeinstancestatusoverride\n      operations:\n      - method: DELETE\n        name: removeinstancestatusoverride\n        description: Remove status override\n        call: netflix-eureka.removeinstancestatusoverride\n        with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/{instanceId}/metadata\n      name: updateinstancemetadata\n      operations:\n      - method: PUT\n        name: updateinstancemetadata\n        description: Update instance metadata\n        call: netflix-eureka.updateinstancemetadata\n        with:\n          appId: rest.appId\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instances/{instanceId}\n      name: getinstancebyid\n      operations:\n      - method: GET\n        name: getinstancebyid\n        description: Get instance by ID\n        call: netflix-eureka.getinstancebyid\n\
  \        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/delta\n      name: getdelta\n      operations:\n      - method: GET\n        name: getdelta\n        description: Get recent changes (delta)\n        call: netflix-eureka.getdelta\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vips/{vipAddress}\n      name: getbyvipaddress\n      operations:\n      - method: GET\n        name: getbyvipaddress\n        description: Query by VIP address\n        call: netflix-eureka.getbyvipaddress\n        with:\n          vipAddress: rest.vipAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /svips/{svipAddress}\n      name: getbysecurevipaddress\n      operations:\n      - method: GET\n        name: getbysecurevipaddress\n        description: Query by secure VIP address\n        call: netflix-eureka.getbysecurevipaddress\n\
  \        with:\n          svipAddress: rest.svipAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: netflix-eureka-mcp\n    transport: http\n    description: MCP adapter for Netflix Eureka REST API for AI agent use.\n    tools:\n    - name: getallapplications\n      description: Get all registered applications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getallapplications\n      with:\n        regions: tools.regions\n      inputParameters:\n      - name: regions\n        type: string\n        description: Comma-separated list of remote regions to include\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplication\n      description: Get application by name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getapplication\n      with:\n\
  \        appId: tools.appId\n      inputParameters:\n      - name: appId\n        type: string\n        description: Application name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerinstance\n      description: Register a new application instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-eureka.registerinstance\n      with:\n        appId: tools.appId\n      inputParameters:\n      - name: appId\n        type: string\n        description: Application name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Get a specific instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getinstance\n      with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n      inputParameters:\n    \
  \  - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description: Instance ID (typically hostname)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregisterinstance\n      description: Deregister an instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: netflix-eureka.deregisterinstance\n      with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendheartbeat\n      description: Send heartbeat\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: netflix-eureka.sendheartbeat\n      with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n        status: tools.status\n        lastDirtyTimestamp: tools.lastDirtyTimestamp\n        overriddenstatus: tools.overriddenstatus\n      inputParameters:\n      - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: status\n        type: string\n        description: Overridden status value\n      - name: lastDirtyTimestamp\n        type: string\n        description: Last dirty timestamp for conflict resolution\n      - name: overriddenstatus\n        type: string\n        description: Overridden status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstancestatus\n      description: Update instance status override\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: netflix-eureka.updateinstancestatus\n      with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n        value: tools.value\n        lastDirtyTimestamp: tools.lastDirtyTimestamp\n      inputParameters:\n      - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: value\n        type: string\n        description: New status value\n        required: true\n      - name: lastDirtyTimestamp\n        type: string\n        description: lastDirtyTimestamp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeinstancestatusoverride\n      description: Remove status override\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: netflix-eureka.removeinstancestatusoverride\n     \
  \ with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n        lastDirtyTimestamp: tools.lastDirtyTimestamp\n      inputParameters:\n      - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      - name: lastDirtyTimestamp\n        type: string\n        description: lastDirtyTimestamp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstancemetadata\n      description: Update instance metadata\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.updateinstancemetadata\n      with:\n        appId: tools.appId\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: appId\n        type: string\n        description: appId\n        required: true\n      - name: instanceId\n        type: string\n        description:\
  \ instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstancebyid\n      description: Get instance by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getinstancebyid\n      with:\n        instanceId: tools.instanceId\n      inputParameters:\n      - name: instanceId\n        type: string\n        description: instanceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdelta\n      description: Get recent changes (delta)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getdelta\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbyvipaddress\n      description: Query by VIP address\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getbyvipaddress\n\
  \      with:\n        vipAddress: tools.vipAddress\n      inputParameters:\n      - name: vipAddress\n        type: string\n        description: vipAddress\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbysecurevipaddress\n      description: Query by secure VIP address\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-eureka.getbysecurevipaddress\n      with:\n        svipAddress: tools.svipAddress\n      inputParameters:\n      - name: svipAddress\n        type: string\n        description: svipAddress\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netflix-eureka/refs/heads/main/capabilities/netflix-eureka-capability.yaml
tags:
- Netflix
- Eureka
- API
tools:
- description: Get all registered applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallapplications
- description: Get application by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Register a new application instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerinstance
- description: Get a specific instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Deregister an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deregisterinstance
- description: Send heartbeat
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendheartbeat
- description: Update instance status override
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstancestatus
- description: Remove status override
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeinstancestatusoverride
- description: Update instance metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstancemetadata
- description: Get instance by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstancebyid
- description: Get recent changes (delta)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdelta
- description: Query by VIP address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbyvipaddress
- description: Query by secure VIP address
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbysecurevipaddress
---
