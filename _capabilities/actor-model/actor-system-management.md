---
categories: []
consumed_apis: []
description: Workflow for managing actor lifecycle, message passing, supervision hierarchies, and cluster operations in distributed actor model systems. Used by platform engineers and distributed systems developers.
layout: capability
name: Actor System Management
operations:
- description: List all active actors
  method: GET
  name: list-actors
  path: /v1/actors
- description: Spawn a new actor
  method: POST
  name: spawn-actor
  path: /v1/actors
- description: Get system health
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: Actor Model
provider_slug: actor-model
search_terms:
- list cluster members
- concurrency
- distributed systems
- get system health
- inspect pending messages in an actor's mailbox for debugging
- get actor system health including throughput, error rate, and dead letter count
- manage actor lifecycle, message passing, supervision hierarchies, and cluster operations
- list all cluster nodes with their status, roles, and actor counts
- list actors
- get health
- Site Reliability Engineer
- list supervisors with their strategies and child actor counts
- supervision
- send message
- inspect mailbox
- get details of a specific actor including mailbox size and restart count
- spawn actor
- Platform Engineer
- designs concurrent, fault-tolerant systems using actor model patterns
- list supervisors
- system health status
- cluster management
- concurrent computation using actors, message passing, and isolation
- get actor
- Distributed Systems Developer
- spawn a new actor
- list all active actors
- builds and operates distributed platforms using actor model frameworks like akka or orleans
- actor model
- actor lifecycle management
- send a typed message to an actor's mailbox for asynchronous processing
- distributed cluster management, sharding, and fault tolerance
- monitors actor system health, throughput, and failure recovery
- list all actors in the system filtered by status
slug: actor-system-management
source_filename: actor-system-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Actor System Management\n  description: Workflow for managing actor lifecycle, message passing, supervision hierarchies, and cluster operations in\n    distributed actor model systems. Used by platform engineers and distributed systems developers.\n  tags:\n  - Actor Model\n  - Concurrency\n  - Distributed Systems\n  - Supervision\n  - Cluster Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACTOR_SYSTEM_API_TOKEN: ACTOR_SYSTEM_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: actor-model\n    baseUri: https://api.example.com/actor-system/v1\n    description: Actor system management API\n    authentication:\n      type: bearer\n      token: '{{ACTOR_SYSTEM_API_TOKEN}}'\n    resources:\n    - name: actors\n      path: /actors\n      description: Actor lifecycle management\n      operations:\n      - name: list-actors\n        method: GET\n        description: List all\
  \ active actors\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: spawn-actor\n        method: POST\n        description: Spawn a new actor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-actor\n        method: GET\n        description: Get a specific actor\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n\
  \          description: Actor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-actor\n        method: DELETE\n        description: Stop an actor\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n          description: Actor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /actors/{actorId}/messages\n      description: Actor mailbox and message passing\n      operations:\n      - name: send-message\n        method: POST\n        description: Send a message to an actor\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n          description: Target actor ID\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n      - name: inspect-mailbox\n        method: GET\n        description: Inspect pending messages in actor mailbox\n        inputParameters:\n        - name: actorId\n          in: path\n          type: string\n          required: true\n          description: Actor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supervisors\n      path: /supervisors\n      description: Supervision hierarchy management\n      operations:\n      - name: list-supervisors\n        method: GET\n        description: List supervisor actors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supervisor\n        method: GET\n        description: Get a specific supervisor\n        inputParameters:\n        - name: supervisorId\n          in: path\n   \
  \       type: string\n          required: true\n          description: Supervisor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster\n      path: /cluster\n      description: Cluster membership and sharding\n      operations:\n      - name: list-cluster-members\n        method: GET\n        description: List cluster nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-shards\n        method: GET\n        description: List cluster shards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      description: System health endpoints\n      operations:\n      - name: get-health\n        method: GET\n        description: Get system health status\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: actor-system-api\n    description: Unified REST API for actor system management.\n    resources:\n    - path: /v1/actors\n      name: actors\n      description: Actor lifecycle management\n      operations:\n      - method: GET\n        name: list-actors\n        description: List all active actors\n        call: actor-model.list-actors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: spawn-actor\n        description: Spawn a new actor\n        call: actor-model.spawn-actor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: System health status\n      operations:\n      - method: GET\n        name: get-health\n        description: Get system health\n        call: actor-model.get-health\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: actor-system-mcp\n    transport: http\n    description: MCP server for AI-assisted actor system management and observability.\n    tools:\n    - name: list-actors\n      description: List all actors in the system filtered by status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: actor-model.list-actors\n      with:\n        status: tools.status\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-actor\n      description: Get details of a specific actor including mailbox size and restart count\n      hints:\n        readOnly: true\n        openWorld: false\n      call: actor-model.get-actor\n      with:\n        actorId: tools.actorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-message\n      description: Send a typed message to an actor's\
  \ mailbox for asynchronous processing\n      hints:\n        readOnly: false\n        openWorld: true\n      call: actor-model.send-message\n      with:\n        actorId: tools.actorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inspect-mailbox\n      description: Inspect pending messages in an actor's mailbox for debugging\n      hints:\n        readOnly: true\n        openWorld: false\n      call: actor-model.inspect-mailbox\n      with:\n        actorId: tools.actorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supervisors\n      description: List supervisors with their strategies and child actor counts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: actor-model.list-supervisors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-members\n      description: List all cluster nodes with their status, roles, and actor counts\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: actor-model.list-cluster-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-health\n      description: Get actor system health including throughput, error rate, and dead letter count\n      hints:\n        readOnly: true\n        openWorld: true\n      call: actor-model.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/actor-model/refs/heads/main/capabilities/actor-system-management.yaml
tags:
- Actor Model
- Concurrency
- Distributed Systems
- Supervision
- Cluster Management
tools:
- description: List all actors in the system filtered by status
  hints:
    openWorld: true
    readOnly: true
  name: list-actors
- description: Get details of a specific actor including mailbox size and restart count
  hints:
    openWorld: false
    readOnly: true
  name: get-actor
- description: Send a typed message to an actor's mailbox for asynchronous processing
  hints:
    openWorld: true
    readOnly: false
  name: send-message
- description: Inspect pending messages in an actor's mailbox for debugging
  hints:
    openWorld: false
    readOnly: true
  name: inspect-mailbox
- description: List supervisors with their strategies and child actor counts
  hints:
    openWorld: true
    readOnly: true
  name: list-supervisors
- description: List all cluster nodes with their status, roles, and actor counts
  hints:
    openWorld: true
    readOnly: true
  name: list-cluster-members
- description: Get actor system health including throughput, error rate, and dead letter count
  hints:
    openWorld: true
    readOnly: true
  name: get-health
---
