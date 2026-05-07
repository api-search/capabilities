---
categories: []
consumed_apis: []
description: Workflow capability for operating and monitoring TiKV distributed clusters. Uses the TiKV HTTP management API to inspect node health, retrieve configuration, collect metrics, and examine Raft region distribution. Designed for database administrators, platform engineers, and SRE teams.
layout: capability
name: TiKV Cluster Operations
operations:
- description: Get TiKV node status
  method: GET
  name: get-status
  path: /v1/nodes/status
- description: Get Prometheus metrics from a TiKV node
  method: GET
  name: get-metrics
  path: /v1/nodes/metrics
- description: Get TiKV node runtime configuration
  method: GET
  name: get-config
  path: /v1/nodes/config
- description: Update TiKV node runtime configuration
  method: POST
  name: update-config
  path: /v1/nodes/config
- description: Get metadata for all Raft regions
  method: GET
  name: get-all-regions-meta
  path: /v1/regions
personas: []
provider_name: TiKV
provider_slug: tikv
search_terms:
- check tikv node health status and version
- distributed systems
- update tikv node runtime configuration online
- update config
- inspect raft region distribution and metadata across the tikv node
- node health and version
- tikv
- get metadata for all raft regions
- retrieve the runtime configuration of a tikv node
- get node config
- rust
- monitoring
- open source
- get tikv node status
- get raft regions
- cluster operations
- update node config
- acid
- retrieve prometheus metrics from a tikv node for performance analysis
- get status
- get node status
- node configuration
- get config
- get metrics
- cncf
- database
- update tikv node runtime configuration
- get node metrics
- key-value store
- node prometheus metrics
- get all regions meta
- get tikv node runtime configuration
- get prometheus metrics from a tikv node
- raft region inspection
slug: cluster-operations
source_filename: cluster-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TiKV Cluster Operations\n  description: Workflow capability for operating and monitoring TiKV distributed clusters. Uses the TiKV HTTP management API\n    to inspect node health, retrieve configuration, collect metrics, and examine Raft region distribution. Designed for database\n    administrators, platform engineers, and SRE teams.\n  tags:\n  - TiKV\n  - Database\n  - Distributed Systems\n  - Cluster Operations\n  - Monitoring\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIKV_NODE_HOST: TIKV_NODE_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: tikv-http\n    baseUri: http://{{TIKV_NODE_HOST}}:20160\n    description: TiKV HTTP management API\n    resources:\n    - name: status\n      path: /status\n      description: Node status and health\n      operations:\n      - name: get-status\n        method: GET\n        description: Get TiKV node status and version information\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Prometheus metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get Prometheus metrics for the TiKV node\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: config\n      path: /config\n      description: Configuration management\n      operations:\n      - name: get-config\n        method: GET\n        description: Get TiKV node runtime configuration\n        inputParameters:\n        - name: section\n          in: query\n          type: string\n          required: false\n        - name: key\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: update-config\n        method: POST\n        description: Update TiKV node runtime configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            config: '{{tools.config}}'\n    - name: regions\n      path: /regions/meta\n      description: Region inspection\n      operations:\n      - name: get-all-regions-meta\n        method: GET\n        description: Get metadata for all Raft regions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tikv-cluster-ops-api\n    description: Unified REST API for TiKV cluster operations and monitoring.\n    resources:\n    - path: /v1/nodes/status\n      name: node-status\n      description: Node health and version\n      operations:\n      -\
  \ method: GET\n        name: get-status\n        description: Get TiKV node status\n        call: tikv-http.get-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/metrics\n      name: node-metrics\n      description: Node Prometheus metrics\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get Prometheus metrics from a TiKV node\n        call: tikv-http.get-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes/config\n      name: node-config\n      description: Node configuration\n      operations:\n      - method: GET\n        name: get-config\n        description: Get TiKV node runtime configuration\n        call: tikv-http.get-config\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: update-config\n        description: Update TiKV node runtime configuration\n        call: tikv-http.update-config\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/regions\n      name: regions\n      description: Raft region inspection\n      operations:\n      - method: GET\n        name: get-all-regions-meta\n        description: Get metadata for all Raft regions\n        call: tikv-http.get-all-regions-meta\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tikv-cluster-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted TiKV cluster operations.\n    tools:\n    - name: get-node-status\n      description: Check TiKV node health status and version\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tikv-http.get-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node-metrics\n      description: Retrieve Prometheus metrics from a TiKV node for performance analysis\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: tikv-http.get-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-node-config\n      description: Retrieve the runtime configuration of a TiKV node\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tikv-http.get-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-node-config\n      description: Update TiKV node runtime configuration online\n      hints:\n        readOnly: false\n        idempotent: true\n      call: tikv-http.update-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-raft-regions\n      description: Inspect Raft region distribution and metadata across the TiKV node\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tikv-http.get-all-regions-meta\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tikv/refs/heads/main/capabilities/cluster-operations.yaml
tags:
- TiKV
- Database
- Distributed Systems
- Cluster Operations
- Monitoring
tools:
- description: Check TiKV node health status and version
  hints:
    idempotent: true
    readOnly: true
  name: get-node-status
- description: Retrieve Prometheus metrics from a TiKV node for performance analysis
  hints:
    idempotent: true
    readOnly: true
  name: get-node-metrics
- description: Retrieve the runtime configuration of a TiKV node
  hints:
    idempotent: true
    readOnly: true
  name: get-node-config
- description: Update TiKV node runtime configuration online
  hints:
    idempotent: true
    readOnly: false
  name: update-node-config
- description: Inspect Raft region distribution and metadata across the TiKV node
  hints:
    idempotent: true
    readOnly: true
  name: get-raft-regions
---
