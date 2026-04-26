---
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
- udev
- get prometheus metrics from akri including instance discovery counts, discovery handler success/failure rates, discovery latency, and broker pod counts per configuration and node.
- get metrics
- onvif
- akri
- monitor akri edge device discovery and broker health
- prometheus metrics for akri component health
- get all akri prometheus metrics
- get akri metrics
- edge computing
- onvif, opc ua, and udev device discovery protocols
- kubernetes
- monitoring
- opc ua
- iot
- device management
- akri prometheus metrics for all components
- Edge Computing Operator
- cncf
- manages kubernetes clusters with akri for iot and edge device workloads. monitors device discovery health, broker pod lifecycle, and cluster resource utilization.
- open source
slug: edge-device-monitoring
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
