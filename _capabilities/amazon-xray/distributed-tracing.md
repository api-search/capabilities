---
consumed_apis:
- xray
description: Unified workflow for developers and operations teams to analyze distributed traces, visualize service maps, manage sampling rules, and investigate application performance insights using Amazon X-Ray.
layout: capability
name: Amazon X-Ray Distributed Tracing
operations:
- description: Get trace summaries for a time range.
  method: GET
  name: get-trace-summaries
  path: /v1/traces
- description: Get the service map.
  method: GET
  name: get-service-graph
  path: /v1/service-map
- description: Get sampling rules.
  method: GET
  name: get-sampling-rules
  path: /v1/sampling-rules
- description: Get trace groups.
  method: GET
  name: get-groups
  path: /v1/groups
- description: Get insight summaries.
  method: GET
  name: get-insight-summaries
  path: /v1/insights
personas: []
provider_name: Amazon X-Ray
provider_slug: amazon-xray
search_terms:
- trace filtering groups.
- get summaries of distributed traces for a specified time range.
- get sampling rules
- get trace summaries for a time range.
- workflow for developers and operations teams to analyze traces, service maps, sampling rules, groups, and performance insights.
- application performance insights.
- service dependency visualization.
- analyzes traces to debug application issues.
- get the service map.
- application tracing and service map visualization
- monitors service health and performance using x-ray.
- get sampling rules.
- trace sampling configuration.
- Developer
- distributed tracing
- get insight summaries.
- get trace groups.
- get all trace sampling rules to understand data collection configuration.
- retrieve complete trace documents for specific trace ids.
- latency analysis and bottleneck identification
- batch get traces
- get trace summaries
- get service graph
- trace data access and analysis.
- get insight summaries
- root cause analysis using distributed trace data
- monitoring
- get the service map showing inter-service dependencies and request flow.
- get groups
- observability
- aws
- get x-ray groups used to filter and organize traces.
- get summaries of x-ray insights identifying anomalies and performance issues.
- application performance
- debugging
- Site Reliability Engineer
slug: distributed-tracing
tags:
- AWS
- Distributed Tracing
- Observability
- Application Performance
- Debugging
tools:
- description: Get summaries of distributed traces for a specified time range.
  hints:
    openWorld: true
    readOnly: true
  name: get-trace-summaries
- description: Retrieve complete trace documents for specific trace IDs.
  hints:
    openWorld: false
    readOnly: true
  name: batch-get-traces
- description: Get the service map showing inter-service dependencies and request flow.
  hints:
    openWorld: true
    readOnly: true
  name: get-service-graph
- description: Get all trace sampling rules to understand data collection configuration.
  hints:
    openWorld: true
    readOnly: true
  name: get-sampling-rules
- description: Get X-Ray groups used to filter and organize traces.
  hints:
    openWorld: true
    readOnly: true
  name: get-groups
- description: Get summaries of X-Ray insights identifying anomalies and performance issues.
  hints:
    openWorld: true
    readOnly: true
  name: get-insight-summaries
---
