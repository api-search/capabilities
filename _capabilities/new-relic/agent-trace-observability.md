---
categories:
- observability
- ai-ops
consumed_apis:
- new-relic-graphql
description: Workflow capability for SREs and AI Platform Engineers at Ford to query agent traces and model-call latency across the New Relic estate. Combines NRQL trace queries, distributed trace inspection, and alert condition management into a unified interface for tracing AI agent runtime behavior, model calls, and cross-platform AI cost telemetry.
layout: capability
name: New Relic Agent Trace Observability
operations:
- description: Run an NRQL query to retrieve agent traces and model-call telemetry
  method: POST
  name: query-nrql
  path: /v1/accounts/{accountId}/query
- description: List distributed traces across services running agent workloads
  method: GET
  name: list-distributed-traces
  path: /v1/traces
- description: Get full detail for a specific distributed trace including spans
  method: GET
  name: get-trace-details
  path: /v1/traces/{traceId}
- description: List recent errors grouped by service for AI agent runtimes
  method: GET
  name: list-errors-by-service
  path: /v1/traces/errors
- description: Create a new alert condition for agent latency or model-call failures
  method: POST
  name: create-alert-condition
  path: /v1/alerts/conditions
personas:
- SRE
- AI Platform Engineer
provider_name: New Relic
provider_slug: new-relic
search_terms:
- query agent traces
- nrql query
- model call latency
- distributed tracing
- list distributed traces
- get trace details
- list errors by service
- create alert condition
- ai agent observability
- new relic nrql
- agent runtime telemetry
- cross-platform ai cost telemetry
- ford observability
- model call traces
- llm trace inspection
- alert on agent latency
- agent error telemetry
- span analysis
- service health
- ai ops
- platform engineering
- run an nrql query to retrieve agent traces
- list recent errors for ai agent runtimes
- create an alert for agent latency or model-call failures
slug: agent-trace-observability
tags:
- Observability
- Distributed Tracing
- NRQL
- AI Agents
- Alerts
tools:
- description: Run an NRQL query to retrieve agent traces, model-call latency, and AI runtime telemetry
  hints:
    openWorld: false
    readOnly: true
  name: query-nrql
- description: List distributed traces across services running AI agent workloads in the New Relic estate
  hints:
    openWorld: false
    readOnly: true
  name: list-distributed-traces
- description: Get full detail for a specific distributed trace including all spans and model-call timings
  hints:
    openWorld: false
    readOnly: true
  name: get-trace-details
- description: List recent errors grouped by service for AI agent runtimes to triage failing model calls
  hints:
    openWorld: false
    readOnly: true
  name: list-errors-by-service
- description: Create a new alert condition for agent latency, model-call failures, or token-spend anomalies
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-alert-condition
---
