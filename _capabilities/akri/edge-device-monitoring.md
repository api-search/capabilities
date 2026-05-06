---
categories:
- iot
consumed_apis: []
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
- opc ua
- get metrics
- manages kubernetes clusters with akri for iot and edge device workloads. monitors device discovery health, broker pod lifecycle, and cluster resource utilization.
- get akri metrics
- device management
- iot
- prometheus metrics for akri component health
- monitoring
- akri prometheus metrics for all components
- get prometheus metrics from akri including instance discovery counts, discovery handler success/failure rates, discovery latency, and broker pod counts per configuration and node.
- kubernetes
- open source
- edge computing
- onvif
- onvif, opc ua, and udev device discovery protocols
- monitor akri edge device discovery and broker health
- akri
- cncf
- Edge Computing Operator
- get all akri prometheus metrics
- udev
slug: edge-device-monitoring
source_filename: edge-device-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Akri Edge Device Monitoring\n  description: Workflow capability for monitoring Akri edge device discovery and broker health in Kubernetes clusters. Combines\n    Prometheus metrics to provide visibility into discovered instances, discovery handler performance, and broker pod lifecycle\n    for Edge Computing operators.\n  tags:\n  - Akri\n  - Edge Computing\n  - IoT\n  - Monitoring\n  - Kubernetes\n  - Device Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AKRI_METRICS_HOST: AKRI_METRICS_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: akri-metrics\n    baseUri: http://{{env.AKRI_METRICS_HOST}}:8080\n    description: Akri Prometheus metrics endpoint\n    resources:\n    - name: metrics\n      path: /metrics\n      description: Prometheus metrics for Akri components\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Get Prometheus-format\
  \ metrics for Akri Agent, Controller, and broker pods\n        outputRawFormat: text\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: akri-edge-monitoring-api\n    description: Unified REST API for Akri edge device monitoring.\n    resources:\n    - path: /v1/metrics\n      name: metrics\n      description: Akri Prometheus metrics for all components\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get all Akri Prometheus metrics\n        call: akri-metrics.get-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: akri-edge-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted Akri edge device monitoring.\n    tools:\n    - name: get-akri-metrics\n      description: Get Prometheus metrics from Akri including instance discovery counts, discovery\
  \ handler success/failure\n        rates, discovery latency, and broker pod counts per configuration and node.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: akri-metrics.get-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
