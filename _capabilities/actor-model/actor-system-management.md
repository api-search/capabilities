---
api_specs:
- filename: actor-model.json
  format: json
  label: actor-model
  slug: actor-model
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/actor-model/refs/heads/main/openapi/actor-model.json
categories: []
consumed_apis:
- actor-model
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
- actor model
- concurrency
- Site Reliability Engineer
- inspect pending messages in an actor's mailbox for debugging
- list all actors in the system filtered by status
- designs concurrent, fault-tolerant systems using actor model patterns
- spawn actor
- list actors
- list supervisors with their strategies and child actor counts
- concurrent computation using actors, message passing, and isolation
- send message
- cluster management
- Platform Engineer
- get actor system health including throughput, error rate, and dead letter count
- distributed cluster management, sharding, and fault tolerance
- builds and operates distributed platforms using actor model frameworks like akka or orleans
- monitors actor system health, throughput, and failure recovery
- list all cluster nodes with their status, roles, and actor counts
- actor lifecycle management
- get details of a specific actor including mailbox size and restart count
- list cluster members
- get system health
- supervision
- list supervisors
- manage actor lifecycle, message passing, supervision hierarchies, and cluster operations
- distributed systems
- inspect mailbox
- Distributed Systems Developer
- spawn a new actor
- list all active actors
- get actor
- system health status
- send a typed message to an actor's mailbox for asynchronous processing
- get health
slug: actor-system-management
source_filename: actor-system-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Actor System Management\"\n  description: \"Workflow for managing actor lifecycle, message passing, supervision hierarchies, and cluster operations in distributed actor model systems. Used by platform engineers and distributed systems developers.\"\n  tags:\n    - Actor Model\n    - Concurrency\n    - Distributed Systems\n    - Supervision\n    - Cluster Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ACTOR_SYSTEM_API_TOKEN: ACTOR_SYSTEM_API_TOKEN\n\ncapability:\n  consumes:\n    - import: actor-model\n      location: ./shared/actor-model.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: actor-system-api\n      description: \"Unified REST API for actor system management.\"\n      resources:\n        - path: /v1/actors\n          name: actors\n          description: \"Actor lifecycle management\"\n          operations:\n            - method:\
  \ GET\n              name: list-actors\n              description: \"List all active actors\"\n              call: \"actor-model.list-actors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: spawn-actor\n              description: \"Spawn a new actor\"\n              call: \"actor-model.spawn-actor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"System health status\"\n          operations:\n            - method: GET\n              name: get-health\n              description: \"Get system health\"\n              call: \"actor-model.get-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: actor-system-mcp\n      transport: http\n      description: \"\
  MCP server for AI-assisted actor system management and observability.\"\n      tools:\n        - name: list-actors\n          description: \"List all actors in the system filtered by status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actor-model.list-actors\"\n          with:\n            status: \"tools.status\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-actor\n          description: \"Get details of a specific actor including mailbox size and restart count\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"actor-model.get-actor\"\n          with:\n            actorId: \"tools.actorId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-message\n          description: \"Send a typed message to an actor's mailbox for asynchronous processing\"\
  \n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"actor-model.send-message\"\n          with:\n            actorId: \"tools.actorId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: inspect-mailbox\n          description: \"Inspect pending messages in an actor's mailbox for debugging\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"actor-model.inspect-mailbox\"\n          with:\n            actorId: \"tools.actorId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-supervisors\n          description: \"List supervisors with their strategies and child actor counts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actor-model.list-supervisors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: list-cluster-members\n          description: \"List all cluster nodes with their status, roles, and actor counts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actor-model.list-cluster-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-health\n          description: \"Get actor system health including throughput, error rate, and dead letter count\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"actor-model.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
