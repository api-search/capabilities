---
categories:
- observability
- monitoring
consumed_apis:
- dynatrace-api
description: Workflow capability for SREs and AI Platform Engineers at Ford to get a Davis-driven view of agent runtime health and anomalies in Dynatrace. Combines metric queries, problem detection, distributed traces, DQL log queries, and synthetic monitors into a unified interface for tracing AI agent runtime behavior, model calls, and cross-platform AI cost telemetry.
layout: capability
name: Dynatrace Agent Runtime Observability
operations:
- description: Query metrics using a Dynatrace metric selector for agent runtime telemetry
  method: GET
  name: query-metrics
  path: /api/v2/metrics/query
- description: List Davis-detected problems for a specific agent service
  method: GET
  name: list-problems-for-service
  path: /api/v2/problems
- description: Get a distributed trace including spans for a specific agent invocation
  method: GET
  name: get-distributed-trace
  path: /api/v2/spans/{traceId}
- description: Query logs using DQL to inspect agent runtime events and model calls
  method: POST
  name: query-logs-dql
  path: /api/v2/logs/query
- description: List configured synthetic monitors covering agent endpoints
  method: GET
  name: list-synthetic-monitors
  path: /api/v2/synthetic/monitors
personas:
- SRE
- AI Platform Engineer
provider_name: Dynatrace
provider_slug: dynatrace
search_terms:
- query metrics via metric selector
- dynatrace metrics
- list problems for service
- davis ai
- get distributed trace
- query logs dql
- list synthetic monitors
- agent runtime health
- agent anomalies
- dynatrace observability
- ford agent runtime
- model call traces
- cross-platform ai cost telemetry
- dql query
- synthetic monitoring
- problem detection
- distributed tracing
- log analytics
- ai ops
- agent observability
- davis-driven
- dynatrace api
- runtime anomalies
- agent health
slug: agent-runtime-observability
tags:
- Observability
- Davis AI
- DQL
- Distributed Tracing
- Synthetic Monitoring
tools:
- description: Query metrics using a Dynatrace metric selector for agent runtime telemetry and model-call latency
  hints:
    openWorld: false
    readOnly: true
  name: query-metrics
- description: List Davis-detected problems for a specific agent service to surface anomalies in agent runtime health
  hints:
    openWorld: false
    readOnly: true
  name: list-problems-for-service
- description: Get a distributed trace including all spans for a specific agent invocation across services
  hints:
    openWorld: false
    readOnly: true
  name: get-distributed-trace
- description: Query logs using DQL (Dynatrace Query Language) to inspect agent runtime events and model calls
  hints:
    openWorld: false
    readOnly: true
  name: query-logs-dql
- description: List configured synthetic monitors covering agent endpoints to verify availability across regions
  hints:
    openWorld: false
    readOnly: true
  name: list-synthetic-monitors
---
