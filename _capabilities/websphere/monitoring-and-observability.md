---
categories:
- monitoring
consumed_apis:
- open-liberty
- admin-rest
- liberty-admin
description: Workflow for monitoring WebSphere environments combining health checks, metrics, performance data, logging, and batch job tracking from Open Liberty and traditional WAS APIs for operations teams.
layout: capability
name: WebSphere Monitoring and Observability
operations:
- description: Get Open Liberty overall health
  method: GET
  name: get-liberty-health
  path: /v1/health
- description: Get WAS server health
  method: GET
  name: get-was-health
  path: /v1/health
- description: Get all Open Liberty metrics
  method: GET
  name: get-all-metrics
  path: /v1/metrics
- description: Get Liberty admin metrics
  method: GET
  name: get-liberty-metrics
  path: /v1/metrics
- description: Get WAS performance monitoring data
  method: GET
  name: get-performance-data
  path: /v1/performance
- description: Get Liberty log messages
  method: GET
  name: get-log-messages
  path: /v1/logs
- description: List batch job instances
  method: GET
  name: list-batch-jobs
  path: /v1/batch-jobs
personas: []
provider_name: IBM WebSphere
provider_slug: websphere
search_terms:
- health check endpoints
- get liberty logging configuration
- observability
- ibm websphere
- metrics
- check if liberty server is ready for traffic
- microservices
- check if liberty server is alive
- performance data
- batch job monitoring
- get open liberty overall health status
- list jakarta batch job instances
- get open liberty overall health
- get performance data
- get recent liberty log messages
- get batch job
- get was server health status
- application server
- get was health
- get all metrics
- get liberty log messages
- j2ee
- cloud native
- list batch job instances
- get liveness
- middleware
- get liberty metrics
- get batch job instance details
- get all open liberty metrics
- get was performance monitoring data
- get log config
- list batch jobs
- log management
- monitoring
- get log messages
- enterprise java
- get liberty admin metrics
- get readiness
- get liberty health
- get was server health
- metrics collection
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WebSphere Monitoring and Observability\"\n  description: \"Workflow for monitoring WebSphere environments combining health checks, metrics, performance data, logging, and batch job tracking from Open Liberty and traditional WAS APIs for operations teams.\"\n  tags:\n    - IBM WebSphere\n    - Monitoring\n    - Observability\n    - Metrics\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBSPHERE_USERNAME: WEBSPHERE_USERNAME\n      WEBSPHERE_PASSWORD: WEBSPHERE_PASSWORD\n      LIBERTY_USERNAME: LIBERTY_USERNAME\n      LIBERTY_PASSWORD: LIBERTY_PASSWORD\n\ncapability:\n  consumes:\n    - import: open-liberty\n      location: ./shared/open-liberty.yaml\n    - import: admin-rest\n      location: ./shared/admin-rest.yaml\n    - import: liberty-admin\n      location: ./shared/liberty-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: monitoring-api\n \
  \     description: \"Unified REST API for WebSphere monitoring and observability.\"\n      resources:\n        - path: /v1/health\n          name: health\n          description: \"Health check endpoints\"\n          operations:\n            - method: GET\n              name: get-liberty-health\n              description: \"Get Open Liberty overall health\"\n              call: \"open-liberty.get-overall-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-was-health\n              description: \"Get WAS server health\"\n              call: \"admin-rest.get-health-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Metrics collection\"\n          operations:\n            - method: GET\n              name: get-all-metrics\n              description:\
  \ \"Get all Open Liberty metrics\"\n              call: \"open-liberty.get-all-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-liberty-metrics\n              description: \"Get Liberty admin metrics\"\n              call: \"liberty-admin.get-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/performance\n          name: performance\n          description: \"Performance data\"\n          operations:\n            - method: GET\n              name: get-performance-data\n              description: \"Get WAS performance monitoring data\"\n              call: \"admin-rest.get-performance-data\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs\n          name: logs\n          description: \"Log management\"\n          operations:\n\
  \            - method: GET\n              name: get-log-messages\n              description: \"Get Liberty log messages\"\n              call: \"liberty-admin.get-log-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/batch-jobs\n          name: batch-jobs\n          description: \"Batch job monitoring\"\n          operations:\n            - method: GET\n              name: list-batch-jobs\n              description: \"List batch job instances\"\n              call: \"open-liberty.list-batch-job-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WebSphere monitoring.\"\n      tools:\n        - name: get-liberty-health\n          description: \"Get Open Liberty overall health status\"\n          hints:\n   \
  \         readOnly: true\n          call: \"open-liberty.get-overall-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-readiness\n          description: \"Check if Liberty server is ready for traffic\"\n          hints:\n            readOnly: true\n          call: \"open-liberty.get-readiness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-liveness\n          description: \"Check if Liberty server is alive\"\n          hints:\n            readOnly: true\n          call: \"open-liberty.get-liveness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-was-health\n          description: \"Get WAS server health status\"\n          hints:\n            readOnly: true\n          call: \"admin-rest.get-health-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: get-all-metrics\n          description: \"Get all Open Liberty metrics\"\n          hints:\n            readOnly: true\n          call: \"open-liberty.get-all-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-performance-data\n          description: \"Get WAS performance monitoring data\"\n          hints:\n            readOnly: true\n          call: \"admin-rest.get-performance-data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-log-messages\n          description: \"Get recent Liberty log messages\"\n          hints:\n            readOnly: true\n          call: \"liberty-admin.get-log-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-log-config\n          description: \"Get Liberty logging configuration\"\n          hints:\n            readOnly: true\n          call: \"\
  liberty-admin.get-log-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-batch-jobs\n          description: \"List Jakarta Batch job instances\"\n          hints:\n            readOnly: true\n          call: \"open-liberty.list-batch-job-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-batch-job\n          description: \"Get batch job instance details\"\n          hints:\n            readOnly: true\n          call: \"open-liberty.get-batch-job-instance\"\n          with:\n            jobInstanceId: \"tools.jobInstanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/websphere/refs/heads/main/capabilities/monitoring-and-observability.yaml
tags:
- IBM WebSphere
- Monitoring
- Observability
- Metrics
tools:
- description: Get Open Liberty overall health status
  hints:
    readOnly: true
  name: get-liberty-health
- description: Check if Liberty server is ready for traffic
  hints:
    readOnly: true
  name: get-readiness
- description: Check if Liberty server is alive
  hints:
    readOnly: true
  name: get-liveness
- description: Get WAS server health status
  hints:
    readOnly: true
  name: get-was-health
- description: Get all Open Liberty metrics
  hints:
    readOnly: true
  name: get-all-metrics
- description: Get WAS performance monitoring data
  hints:
    readOnly: true
  name: get-performance-data
- description: Get recent Liberty log messages
  hints:
    readOnly: true
  name: get-log-messages
- description: Get Liberty logging configuration
  hints:
    readOnly: true
  name: get-log-config
- description: List Jakarta Batch job instances
  hints:
    readOnly: true
  name: list-batch-jobs
- description: Get batch job instance details
  hints:
    readOnly: true
  name: get-batch-job
---
