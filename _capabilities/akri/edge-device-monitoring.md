---
categories:
- iot
consumed_apis:
- akri-metrics
description: Workflow capability for monitoring Akri edge device discovery and broker health in Kubernetes clusters. Combines Prometheus metrics to provide visibility into discovered instances, discovery handler performance, and broker pod lifecycle for Edge Computing operators.
layout: capability
name: Akri Edge Device Monitoring
operations:
- description: Get all Akri Prometheus metrics
  method: GET
  name: get-metrics
  path: /v1/metrics
personas: []
provider_name: Akri
provider_slug: akri
search_terms:
- monitoring
- onvif, opc ua, and udev device discovery protocols
- get akri metrics
- manages kubernetes clusters with akri for iot and edge device workloads. monitors device discovery health, broker pod lifecycle, and cluster resource utilization.
- onvif
- opc ua
- akri prometheus metrics for all components
- open source
- device management
- get prometheus metrics from akri including instance discovery counts, discovery handler success/failure rates, discovery latency, and broker pod counts per configuration and node.
- monitor akri edge device discovery and broker health
- get all akri prometheus metrics
- cncf
- kubernetes
- akri
- prometheus metrics for akri component health
- iot
- edge computing
- get metrics
- Edge Computing Operator
- udev
slug: edge-device-monitoring
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Akri Edge Device Monitoring\n  description: >-\n    Workflow capability for monitoring Akri edge device discovery and broker\n    health in Kubernetes clusters. Combines Prometheus metrics to provide\n    visibility into discovered instances, discovery handler performance, and\n    broker pod lifecycle for Edge Computing operators.\n  tags:\n    - Akri\n    - Edge Computing\n    - IoT\n    - Monitoring\n    - Kubernetes\n    - Device Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AKRI_METRICS_HOST: AKRI_METRICS_HOST\n\ncapability:\n  consumes:\n    - import: akri-metrics\n      location: ./shared/metrics.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: akri-edge-monitoring-api\n      description: Unified REST API for Akri edge device monitoring.\n      resources:\n        - path: /v1/metrics\n          name: metrics\n          description:\
  \ Akri Prometheus metrics for all components\n          operations:\n            - method: GET\n              name: get-metrics\n              description: Get all Akri Prometheus metrics\n              call: \"akri-metrics.get-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: akri-edge-monitoring-mcp\n      transport: http\n      description: MCP server for AI-assisted Akri edge device monitoring.\n      tools:\n        - name: get-akri-metrics\n          description: >-\n            Get Prometheus metrics from Akri including instance discovery counts,\n            discovery handler success/failure rates, discovery latency, and\n            broker pod counts per configuration and node.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"akri-metrics.get-metrics\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/akri/refs/heads/main/capabilities/edge-device-monitoring.yaml
tags:
- Akri
- Edge Computing
- IoT
- Monitoring
- Kubernetes
- Device Management
tools:
- description: Get Prometheus metrics from Akri including instance discovery counts, discovery handler success/failure rates, discovery latency, and broker pod counts per configuration and node.
  hints:
    openWorld: false
    readOnly: true
  name: get-akri-metrics
---
