---
categories:
- monitoring
consumed_apis:
- bfe-management
description: Workflow capability for managing BFE load balancer operations including runtime metrics collection, configuration hot reload, and observability for infrastructure and platform engineering teams.
layout: capability
name: BFE Load Balancer Management
operations:
- description: Get BFE runtime metrics and performance counters
  method: GET
  name: get-metrics
  path: /v1/metrics
- description: Get available monitoring metric categories
  method: GET
  name: get-categories
  path: /v1/categories
- description: Trigger hot reload of BFE routing rules and configuration
  method: POST
  name: reload-config
  path: /v1/reload
personas: []
provider_name: BFE
provider_slug: bfe
search_terms:
- networking
- get bfe metrics
- monitoring
- retrieve bfe load balancer runtime metrics and performance counters for monitoring
- reload config
- get metric categories
- cncf
- trigger a hot reload of bfe routing and load balancing configuration without restart
- hot reload bfe configuration
- metrics, logging, and distributed tracing
- open source
- configuration
- layer 7 load balancing and traffic routing
- retrieve available metric categories
- load balancer
- bfe
- list available bfe metric categories for targeted monitoring
- get categories
- reload bfe config
- baidu
- get metrics
- management
- get available monitoring metric categories
- get bfe runtime metrics and performance counters
- retrieve bfe runtime monitoring metrics
- dynamic configuration management and reload
- traffic management
- trigger hot reload of bfe routing rules and configuration
- engineer managing bfe load balancer deployments and configuration
slug: load-balancer-management
source_filename: load-balancer-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"BFE Load Balancer Management\"\n  description: >-\n    Workflow capability for managing BFE load balancer operations including\n    runtime metrics collection, configuration hot reload, and observability\n    for infrastructure and platform engineering teams.\n  tags:\n    - BFE\n    - Load Balancer\n    - Management\n    - Monitoring\n    - Configuration\n  created: \"2026-04-21\"\n  modified: \"2026-04-21\"\n\nbinds:\n  - namespace: env\n    keys:\n      BFE_HOST: BFE_HOST\n      BFE_PORT: BFE_PORT\n\ncapability:\n  consumes:\n    - import: bfe-management\n      location: ./shared/management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bfe-management-api\n      description: \"REST API for BFE load balancer management and observability.\"\n      resources:\n        - path: /v1/metrics\n          name: metrics\n          description: \"Retrieve BFE runtime monitoring metrics\"\n          operations:\n\
  \            - method: GET\n              name: get-metrics\n              description: \"Get BFE runtime metrics and performance counters\"\n              call: \"bfe-management.get-monitor-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description: \"Retrieve available metric categories\"\n          operations:\n            - method: GET\n              name: get-categories\n              description: \"Get available monitoring metric categories\"\n              call: \"bfe-management.get-monitor-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reload\n          name: reload\n          description: \"Hot reload BFE configuration\"\n          operations:\n            - method: POST\n              name: reload-config\n              description: \"Trigger hot reload of BFE\
  \ routing rules and configuration\"\n              call: \"bfe-management.reload-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: bfe-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted BFE load balancer management and observability.\"\n      tools:\n        - name: get-bfe-metrics\n          description: \"Retrieve BFE load balancer runtime metrics and performance counters for monitoring\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bfe-management.get-monitor-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-metric-categories\n          description: \"List available BFE metric categories for targeted monitoring\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bfe-management.get-monitor-categories\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reload-bfe-config\n          description: \"Trigger a hot reload of BFE routing and load balancing configuration without restart\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bfe-management.reload-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bfe/refs/heads/main/capabilities/load-balancer-management.yaml
tags:
- BFE
- Load Balancer
- Management
- Monitoring
- Configuration
tools:
- description: Retrieve BFE load balancer runtime metrics and performance counters for monitoring
  hints:
    openWorld: false
    readOnly: true
  name: get-bfe-metrics
- description: List available BFE metric categories for targeted monitoring
  hints:
    openWorld: false
    readOnly: true
  name: get-metric-categories
- description: Trigger a hot reload of BFE routing and load balancing configuration without restart
  hints:
    openWorld: false
    readOnly: false
  name: reload-bfe-config
---
