---
categories: []
consumed_apis: []
description: Workflow for monitoring and managing Akka cluster operations including health checks, member management, and cluster bootstrap. For platform engineers and SREs operating distributed Akka systems.
layout: capability
name: Akka Cluster Operations
operations:
- description: Node liveness check
  method: GET
  name: check-alive
  path: /v1/health
- description: Node readiness check
  method: GET
  name: check-ready
  path: /v1/health
- description: List cluster members
  method: GET
  name: list-members
  path: /v1/cluster/members
- description: Join a cluster member
  method: POST
  name: join-member
  path: /v1/cluster/members
personas: []
provider_name: Akka
provider_slug: akka
search_terms:
- health monitoring
- list cluster members
- operations
- distributed systems
- reactive
- monitors cluster health and responds to incidents
- join member
- java
- monitor and manage akka cluster health and membership
- check ready
- list members
- akka cluster membership and node lifecycle management
- check liveness and readiness of akka cluster nodes
- cluster health checks
- Platform Engineer
- liveness and readiness health check monitoring
- scala
- cluster management
- cluster member management
- check if akka cluster nodes are ready to serve traffic
- check cluster readiness
- SRE
- manages akka cluster deployments and configurations
- frameworks
- add a new node to the akka cluster
- node liveness check
- check alive
- join cluster member
- actor model
- akka
- check cluster health
- join a cluster member
- list all current members of the akka cluster
- microservices
- node readiness check
slug: cluster-operations
source_filename: cluster-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Akka Cluster Operations\n  description: Workflow for monitoring and managing Akka cluster operations including health checks, member management, and\n    cluster bootstrap. For platform engineers and SREs operating distributed Akka systems.\n  tags:\n  - Akka\n  - Cluster Management\n  - Distributed Systems\n  - Operations\n  - Health Monitoring\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AKKA_MANAGEMENT_HOST: AKKA_MANAGEMENT_HOST\n    AKKA_MANAGEMENT_PORT: AKKA_MANAGEMENT_PORT\ncapability:\n  consumes:\n  - type: http\n    namespace: akka-management\n    baseUri: http://{host}:{port}\n    description: Akka Management HTTP API\n    resources:\n    - name: health\n      path: /alive\n      description: Liveness health check\n      operations:\n      - name: check-alive\n        method: GET\n        description: Check if the node is alive\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: readiness\n      path: /ready\n      description: Readiness health check\n      operations:\n      - name: check-ready\n        method: GET\n        description: Check if the node is ready to serve traffic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cluster-members\n      path: /cluster/members\n      description: Cluster membership management\n      operations:\n      - name: list-cluster-members\n        method: GET\n        description: List all cluster members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: join-cluster\n        method: POST\n        description: Join a cluster node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n     \
  \   body:\n          type: json\n          data:\n            address: '{{tools.address}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cluster-operations-api\n    description: Unified REST API for Akka cluster operations.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Cluster health checks\n      operations:\n      - method: GET\n        name: check-alive\n        description: Node liveness check\n        call: akka-management.check-alive\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: check-ready\n        description: Node readiness check\n        call: akka-management.check-ready\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cluster/members\n      name: cluster-members\n      description: Cluster member management\n      operations:\n      - method: GET\n        name: list-members\n        description: List cluster members\n     \
  \   call: akka-management.list-cluster-members\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: join-member\n        description: Join a cluster member\n        call: akka-management.join-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cluster-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Akka cluster operations.\n    tools:\n    - name: check-cluster-health\n      description: Check liveness and readiness of Akka cluster nodes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: akka-management.check-alive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-cluster-readiness\n      description: Check if Akka cluster nodes are ready to serve traffic\n      hints:\n        readOnly: true\n        openWorld: false\n      call: akka-management.check-ready\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cluster-members\n      description: List all current members of the Akka cluster\n      hints:\n        readOnly: true\n        openWorld: false\n      call: akka-management.list-cluster-members\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: join-cluster-member\n      description: Add a new node to the Akka cluster\n      hints:\n        readOnly: false\n        destructive: false\n      call: akka-management.join-cluster\n      with:\n        address: tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/akka/refs/heads/main/capabilities/cluster-operations.yaml
tags:
- Akka
- Cluster Management
- Distributed Systems
- Operations
- Health Monitoring
tools:
- description: Check liveness and readiness of Akka cluster nodes
  hints:
    openWorld: false
    readOnly: true
  name: check-cluster-health
- description: Check if Akka cluster nodes are ready to serve traffic
  hints:
    openWorld: false
    readOnly: true
  name: check-cluster-readiness
- description: List all current members of the Akka cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-cluster-members
- description: Add a new node to the Akka cluster
  hints:
    destructive: false
    readOnly: false
  name: join-cluster-member
---
