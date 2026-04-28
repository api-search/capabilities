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
- opc ua
- prometheus metrics for akri component health
- onvif
- kubernetes
- Edge Computing Operator
- akri prometheus metrics for all components
- edge computing
- device management
- get all akri prometheus metrics
- udev
- akri
- monitoring
- onvif, opc ua, and udev device discovery protocols
- cncf
- iot
- get akri metrics
- open source
- get prometheus metrics from akri including instance discovery counts, discovery handler success/failure rates, discovery latency, and broker pod counts per configuration and node.
- get metrics
- monitor akri edge device discovery and broker health
- manages kubernetes clusters with akri for iot and edge device workloads. monitors device discovery health, broker pod lifecycle, and cluster resource utilization.
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
