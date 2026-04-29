---
categories: []
consumed_apis:
- akka-management
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
- check liveness and readiness of akka cluster nodes
- node readiness check
- cluster management
- join cluster member
- list all current members of the akka cluster
- node liveness check
- operations
- monitor and manage akka cluster health and membership
- check if akka cluster nodes are ready to serve traffic
- actor model
- cluster health checks
- check ready
- akka
- SRE
- check cluster readiness
- distributed systems
- join a cluster member
- list cluster members
- manages akka cluster deployments and configurations
- microservices
- add a new node to the akka cluster
- health monitoring
- monitors cluster health and responds to incidents
- join member
- akka cluster membership and node lifecycle management
- check alive
- reactive
- scala
- frameworks
- Platform Engineer
- list members
- java
- cluster member management
- liveness and readiness health check monitoring
- check cluster health
slug: cluster-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Akka Cluster Operations\"\n  description: \"Workflow for monitoring and managing Akka cluster operations including health checks, member management, and cluster bootstrap. For platform engineers and SREs operating distributed Akka systems.\"\n  tags:\n    - Akka\n    - Cluster Management\n    - Distributed Systems\n    - Operations\n    - Health Monitoring\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AKKA_MANAGEMENT_HOST: AKKA_MANAGEMENT_HOST\n      AKKA_MANAGEMENT_PORT: AKKA_MANAGEMENT_PORT\ncapability:\n  consumes:\n    - import: akka-management\n      location: ./shared/akka-management.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cluster-operations-api\n      description: \"Unified REST API for Akka cluster operations.\"\n      resources:\n        - path: /v1/health\n          name: health\n          description: \"Cluster health checks\"\n     \
  \     operations:\n            - method: GET\n              name: check-alive\n              description: \"Node liveness check\"\n              call: \"akka-management.check-alive\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: check-ready\n              description: \"Node readiness check\"\n              call: \"akka-management.check-ready\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cluster/members\n          name: cluster-members\n          description: \"Cluster member management\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List cluster members\"\n              call: \"akka-management.list-cluster-members\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n\
  \              name: join-member\n              description: \"Join a cluster member\"\n              call: \"akka-management.join-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: cluster-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Akka cluster operations.\"\n      tools:\n        - name: check-cluster-health\n          description: \"Check liveness and readiness of Akka cluster nodes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"akka-management.check-alive\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-cluster-readiness\n          description: \"Check if Akka cluster nodes are ready to serve traffic\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"akka-management.check-ready\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cluster-members\n          description: \"List all current members of the Akka cluster\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"akka-management.list-cluster-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: join-cluster-member\n          description: \"Add a new node to the Akka cluster\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"akka-management.join-cluster\"\n          with:\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
