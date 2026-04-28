---
categories:
- ai-platform
consumed_apis:
- google-adk-api
description: Workflow capability for AI platform engineers building agentic systems on the Google Agent Development Kit. Register a Google ADK agent and invoke it with structured input/output for orchestration, allowing platform teams to expose agent definitions, run agents against runtime input, monitor execution, and stream events as a unified runtime surface.
layout: capability
name: Google ADK Agent Registration & Invocation
operations:
- description: Register a new Google ADK agent definition with the runtime
  method: POST
  name: register-agent
  path: /v1/agents
- description: List all registered ADK agents available for invocation
  method: GET
  name: list-agents
  path: /v1/agents
- description: Invoke a registered agent with structured input for orchestration
  method: POST
  name: invoke-agent
  path: /v1/agents/{name}:invoke
- description: Get the current status of an agent run
  method: GET
  name: get-run-status
  path: /v1/runs/{id}
- description: Stream events emitted during an agent run
  method: GET
  name: stream-agent-events
  path: /v1/runs/{id}/events
- description: List recent agent runs for observability
  method: GET
  name: list-runs
  path: /v1/runs
personas:
- AI Platform Engineer
provider_name: Google ADK
provider_slug: google-adk
search_terms:
- register google adk agent
- invoke adk agent
- google agent development kit
- list registered agents
- agent runtime platform
- structured input output
- agent orchestration
- stream agent events
- agent run status
- agent invocation
- adk runtime
- model routing for agents
- agent definition registration
- ai platform engineer
- agentic systems
- expose agents as a runtime
- multi-agent orchestration
- agent observability
- run an adk agent with structured input
- google adk
- adk agents
- list agent runs
- agent execution telemetry
slug: agent-registration-invocation
tags:
- AI Agents
- Google ADK
- Agent Runtime
- Orchestration
- Model Routing
tools:
- description: Register a new Google ADK agent definition so it can be invoked from the runtime
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: register-agent
- description: List all registered Google ADK agents available for invocation
  hints:
    openWorld: false
    readOnly: true
  name: list-agents
- description: Invoke a registered Google ADK agent with structured input and receive structured output
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: invoke-agent
- description: Get the current status of a specific agent run (queued, running, succeeded, failed)
  hints:
    openWorld: false
    readOnly: true
  name: get-run-status
- description: Stream events emitted during an agent run for live observability of agent steps
  hints:
    openWorld: false
    readOnly: true
  name: stream-agent-events
- description: List recent Google ADK agent runs across all registered agents
  hints:
    openWorld: false
    readOnly: true
  name: list-runs
---
