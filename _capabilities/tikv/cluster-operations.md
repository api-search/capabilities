---
api_specs:
- filename: tikv-http-api-openapi.yml
  format: yaml
  label: tikv-http
  slug: tikv-http
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tikv/refs/heads/main/openapi/tikv-http-api-openapi.yml
categories: []
consumed_apis:
- tikv-http
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
- update tikv node runtime configuration online
- get tikv node runtime configuration
- tikv
- key-value store
- inspect raft region distribution and metadata across the tikv node
- get prometheus metrics from a tikv node
- monitoring
- open source
- get status
- node prometheus metrics
- get metadata for all raft regions
- rust
- retrieve prometheus metrics from a tikv node for performance analysis
- node configuration
- node health and version
- acid
- update tikv node runtime configuration
- get metrics
- cncf
- get tikv node status
- cluster operations
- update node config
- get node metrics
- distributed systems
- database
- update config
- get all regions meta
- get config
- get node status
- check tikv node health status and version
- get node config
- raft region inspection
- get raft regions
- retrieve the runtime configuration of a tikv node
slug: cluster-operations
source_filename: cluster-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TiKV Cluster Operations\"\n  description: >-\n    Workflow capability for operating and monitoring TiKV distributed clusters.\n    Uses the TiKV HTTP management API to inspect node health, retrieve\n    configuration, collect metrics, and examine Raft region distribution.\n    Designed for database administrators, platform engineers, and SRE teams.\n  tags:\n    - TiKV\n    - Database\n    - Distributed Systems\n    - Cluster Operations\n    - Monitoring\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TIKV_NODE_HOST: TIKV_NODE_HOST\n\ncapability:\n  consumes:\n    - import: tikv-http\n      location: ./shared/tikv-http-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tikv-cluster-ops-api\n      description: \"Unified REST API for TiKV cluster operations and monitoring.\"\n      resources:\n        - path: /v1/nodes/status\n          name: node-status\n\
  \          description: \"Node health and version\"\n          operations:\n            - method: GET\n              name: get-status\n              description: \"Get TiKV node status\"\n              call: \"tikv-http.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes/metrics\n          name: node-metrics\n          description: \"Node Prometheus metrics\"\n          operations:\n            - method: GET\n              name: get-metrics\n              description: \"Get Prometheus metrics from a TiKV node\"\n              call: \"tikv-http.get-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nodes/config\n          name: node-config\n          description: \"Node configuration\"\n          operations:\n            - method: GET\n              name: get-config\n              description: \"Get TiKV node runtime configuration\"\
  \n              call: \"tikv-http.get-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: update-config\n              description: \"Update TiKV node runtime configuration\"\n              call: \"tikv-http.update-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/regions\n          name: regions\n          description: \"Raft region inspection\"\n          operations:\n            - method: GET\n              name: get-all-regions-meta\n              description: \"Get metadata for all Raft regions\"\n              call: \"tikv-http.get-all-regions-meta\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tikv-cluster-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TiKV\
  \ cluster operations.\"\n      tools:\n        - name: get-node-status\n          description: \"Check TiKV node health status and version\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tikv-http.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-node-metrics\n          description: \"Retrieve Prometheus metrics from a TiKV node for performance analysis\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tikv-http.get-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-node-config\n          description: \"Retrieve the runtime configuration of a TiKV node\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tikv-http.get-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: update-node-config\n          description: \"Update TiKV node runtime configuration online\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tikv-http.update-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-raft-regions\n          description: \"Inspect Raft region distribution and metadata across the TiKV node\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tikv-http.get-all-regions-meta\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
