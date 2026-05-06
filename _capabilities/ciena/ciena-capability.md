---
categories: []
consumed_apis: []
description: Ciena Blue Planet provides open APIs for multi-layer SDN network management and automation. The platform supports TM Forum Open APIs, MEF Lifecycle Service Orchestration (LSO) APIs including Legato and Sonata, and integrates with ONAP policy frameworks. APIs enable network topology management, circuit provisioning, performance monitoring, and network operations automation for telecom carriers.
layout: capability
name: Ciena Blue Planet Open API
operations:
- description: List network topology nodes
  method: GET
  name: listtopologynodes
  path: /topology/nodes
- description: Get a specific network topology node
  method: GET
  name: gettopologynode
  path: /topology/nodes/{nodeId}
- description: List network topology links
  method: GET
  name: listtopologylinks
  path: /topology/links
- description: List provisioned network services
  method: GET
  name: listservices
  path: /services
- description: Create a new network service
  method: POST
  name: createservice
  path: /services
- description: Get network service details
  method: GET
  name: getservice
  path: /services/{serviceId}
- description: Delete a network service
  method: DELETE
  name: deleteservice
  path: /services/{serviceId}
- description: Retrieve network performance metrics
  method: GET
  name: getperformancemetrics
  path: /performance/metrics
- description: List network alarms
  method: GET
  name: listalarms
  path: /alarms
personas: []
provider_name: Ciena
provider_slug: ciena
search_terms:
- delete a network service
- listalarms
- gettopologynode
- tm forum
- list provisioned network services
- getperformancemetrics
- listtopologylinks
- getservice
- ciena
- list network topology links
- network management
- deleteservice
- sdn
- optical
- api
- get network service details
- mef
- list network topology nodes
- listtopologynodes
- netconf
- create a new network service
- network automation
- retrieve network performance metrics
- listservices
- restconf
- createservice
- get a specific network topology node
- telecom
- list network alarms
slug: ciena-capability
source_filename: ciena-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ciena Blue Planet Open API\n  description: Ciena Blue Planet provides open APIs for multi-layer SDN network management and automation. The platform supports\n    TM Forum Open APIs, MEF Lifecycle Service Orchestration (LSO) APIs including Legato and Sonata, and integrates with ONAP\n    policy frameworks. APIs enable network topology management, circuit provisioning, performance monitoring, and network\n    operations automation for telecom carriers.\n  tags:\n  - Ciena\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ciena\n    baseUri: https://api.blueplanet.com/bpocore/market/api/v1\n    description: Ciena Blue Planet Open API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CIENA_TOKEN}}'\n    resources:\n    - name: topology-nodes\n      path: /topology/nodes\n      operations:\n      - name: listtopologynodes\n        method: GET\n        description:\
  \ List network topology nodes\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Filter by node type\n        - name: adminState\n          in: query\n          type: string\n          description: Filter by administrative state\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topology-nodes-nodeid\n      path: /topology/nodes/{nodeId}\n      operations:\n      - name: gettopologynode\n        method: GET\n        description: Get a specific network topology node\n        inputParameters:\n        - name: nodeId\n          in: path\n          type: string\n          required: true\n          description: Unique node identifier\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: topology-links\n      path: /topology/links\n      operations:\n      - name: listtopologylinks\n        method: GET\n        description: List network topology links\n        inputParameters:\n        - name: nodeId\n          in: query\n          type: string\n          description: Filter links connected to a specific node\n        - name: type\n          in: query\n          type: string\n          description: Filter by link type\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List provisioned network services\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          description: Filter\
  \ by service state\n        - name: serviceType\n          in: query\n          type: string\n          description: Filter by service type\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: Create a new network service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-serviceid\n      path: /services/{serviceId}\n      operations:\n      - name: getservice\n        method: GET\n        description: Get network service details\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: deleteservice\n        method: DELETE\n        description: Delete a network service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performance-metrics\n      path: /performance/metrics\n      operations:\n      - name: getperformancemetrics\n        method: GET\n        description: Retrieve network performance metrics\n        inputParameters:\n        - name: resourceId\n          in: query\n          type: string\n          required: true\n          description: ID of the network resource to query metrics for\n        - name: metricType\n          in: query\n          type: string\n          description: Type of performance metric\n        - name: granularity\n          in: query\n          type: string\n          description: Data granularity period\n  \
  \      - name: startTime\n          in: query\n          type: string\n          description: Start of query window (ISO 8601)\n        - name: endTime\n          in: query\n          type: string\n          description: End of query window (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alarms\n      path: /alarms\n      operations:\n      - name: listalarms\n        method: GET\n        description: List network alarms\n        inputParameters:\n        - name: severity\n          in: query\n          type: string\n          description: Filter by alarm severity\n        - name: resourceId\n          in: query\n          type: string\n          description: Filter alarms for a specific resource\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ciena-rest\n    description: REST adapter for Ciena Blue Planet Open API.\n    resources:\n    - path: /topology/nodes\n      name: listtopologynodes\n      operations:\n      - method: GET\n        name: listtopologynodes\n        description: List network topology nodes\n        call: ciena.listtopologynodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topology/nodes/{nodeId}\n      name: gettopologynode\n      operations:\n      - method: GET\n        name: gettopologynode\n        description: Get a specific network topology node\n        call: ciena.gettopologynode\n        with:\n          nodeId: rest.nodeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topology/links\n      name: listtopologylinks\n      operations:\n      - method: GET\n        name: listtopologylinks\n        description: List network topology links\n        call:\
  \ ciena.listtopologylinks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List provisioned network services\n        call: ciena.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Create a new network service\n        call: ciena.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{serviceId}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Get network service details\n        call: ciena.getservice\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /services/{serviceId}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Delete a network service\n        call: ciena.deleteservice\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /performance/metrics\n      name: getperformancemetrics\n      operations:\n      - method: GET\n        name: getperformancemetrics\n        description: Retrieve network performance metrics\n        call: ciena.getperformancemetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alarms\n      name: listalarms\n      operations:\n      - method: GET\n        name: listalarms\n        description: List network alarms\n        call: ciena.listalarms\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ciena-mcp\n    transport: http\n  \
  \  description: MCP adapter for Ciena Blue Planet Open API for AI agent use.\n    tools:\n    - name: listtopologynodes\n      description: List network topology nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.listtopologynodes\n      with:\n        type: tools.type\n        adminState: tools.adminState\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: type\n        type: string\n        description: Filter by node type\n      - name: adminState\n        type: string\n        description: Filter by administrative state\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopologynode\n      description: Get a specific network topology node\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: ciena.gettopologynode\n      with:\n        nodeId: tools.nodeId\n      inputParameters:\n      - name: nodeId\n        type: string\n        description: Unique node identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtopologylinks\n      description: List network topology links\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.listtopologylinks\n      with:\n        nodeId: tools.nodeId\n        type: tools.type\n        limit: tools.limit\n      inputParameters:\n      - name: nodeId\n        type: string\n        description: Filter links connected to a specific node\n      - name: type\n        type: string\n        description: Filter by link type\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n\
  \      description: List provisioned network services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.listservices\n      with:\n        state: tools.state\n        serviceType: tools.serviceType\n        limit: tools.limit\n      inputParameters:\n      - name: state\n        type: string\n        description: Filter by service state\n      - name: serviceType\n        type: string\n        description: Filter by service type\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Create a new network service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ciena.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Get network service details\n      hints:\n       \
  \ readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.getservice\n      with:\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Delete a network service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ciena.deleteservice\n      with:\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperformancemetrics\n      description: Retrieve network performance metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.getperformancemetrics\n\
  \      with:\n        resourceId: tools.resourceId\n        metricType: tools.metricType\n        granularity: tools.granularity\n        startTime: tools.startTime\n        endTime: tools.endTime\n      inputParameters:\n      - name: resourceId\n        type: string\n        description: ID of the network resource to query metrics for\n        required: true\n      - name: metricType\n        type: string\n        description: Type of performance metric\n      - name: granularity\n        type: string\n        description: Data granularity period\n      - name: startTime\n        type: string\n        description: Start of query window (ISO 8601)\n      - name: endTime\n        type: string\n        description: End of query window (ISO 8601)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalarms\n      description: List network alarms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ciena.listalarms\n\
  \      with:\n        severity: tools.severity\n        resourceId: tools.resourceId\n        limit: tools.limit\n      inputParameters:\n      - name: severity\n        type: string\n        description: Filter by alarm severity\n      - name: resourceId\n        type: string\n        description: Filter alarms for a specific resource\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CIENA_TOKEN: CIENA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ciena/refs/heads/main/capabilities/ciena-capability.yaml
tags:
- Ciena
- API
tools:
- description: List network topology nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopologynodes
- description: Get a specific network topology node
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopologynode
- description: List network topology links
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtopologylinks
- description: List provisioned network services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Create a new network service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: Get network service details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Delete a network service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Retrieve network performance metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperformancemetrics
- description: List network alarms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalarms
---
