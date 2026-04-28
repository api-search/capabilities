---
categories:
- observability
- ai-ops
consumed_apis:
- datadog-api
description: Workflow capability for AI Platform Engineers and Observability Leads at Ford to trace AI agent invocations and token spend per model in Datadog LLM Observability. Combines span search, agent session traces, model token metrics, AI cost rollups, and monitor creation into a unified interface for cross-platform AI cost telemetry.
layout: capability
name: Datadog AI Agent Observability
operations:
- description: Search LLM observability spans for agent invocations and model calls
  method: GET
  name: search-llm-spans
  path: /api/v2/spans
- description: Get the full set of spans for a specific agent session trace
  method: GET
  name: get-agent-session-traces
  path: /api/v2/spans/{traceId}
- description: Query token usage metrics by model and agent
  method: GET
  name: query-token-usage
  path: /api/v1/query
- description: List AI cost rollups by model across the agent fleet
  method: GET
  name: list-ai-cost-by-model
  path: /api/v1/query/cost
- description: Create a monitor that fires on token spend exceeding a threshold
  method: POST
  name: create-token-spend-monitor
  path: /api/v1/monitor
personas:
- AI Platform Engineer
- Observability Lead
provider_name: Datadog
provider_slug: datadog
search_terms:
- search llm observability spans
- llm spans
- agent session traces
- token usage metrics
- ai cost by model
- create token spend monitor
- datadog llm observability
- trace ai agent invocations
- token spend per model
- model token metrics
- ai cost telemetry
- ford ai cost
- agent invocation tracing
- monitor token spend
- spans search
- datadog monitor
- query metrics
- ai ops
- llm cost
- cross-platform telemetry
- agent runtime visibility
- datadog spans api
- datadog metrics query
- list ai cost rollups by model
slug: ai-agent-observability
tags:
- LLM Observability
- AI Agents
- Token Spend
- Monitors
- Datadog
tools:
- description: Search LLM observability spans for agent invocations and model calls across the Datadog estate
  hints:
    openWorld: false
    readOnly: true
  name: search-llm-spans
- description: Get the full set of spans for a specific agent session trace including model-call timings and prompts
  hints:
    openWorld: false
    readOnly: true
  name: get-agent-session-traces
- description: Query token usage metrics by model and agent to track per-model consumption
  hints:
    openWorld: false
    readOnly: true
  name: query-token-usage
- description: List AI cost rollups by model across the agent fleet for cross-platform AI cost telemetry
  hints:
    openWorld: false
    readOnly: true
  name: list-ai-cost-by-model
- description: Create a Datadog monitor that fires when token spend for a model or agent exceeds a threshold
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-token-spend-monitor
---
