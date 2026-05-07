---
categories: []
consumed_apis: []
description: Customer-facing workflow that combines Waxell Observe telemetry capture with runtime policy enforcement. Used by platform engineering teams to record every LLM call, evaluate governance policies before risky actions, and audit governance events for AI agents in production.
layout: capability
name: Waxell Agent Governance Workflow
operations: []
personas: []
provider_name: Waxell
provider_slug: waxell
search_terms:
- agent runtime
- start_agent_run
- llm telemetry
- begin a new waxell observe run for an agent.
- list_model_costs
- record_llm_call
- record_audit_event
- mcp
- log an opentelemetry-style span against a run.
- policy enforcement
- cost management
- observability
- return the merged model cost table (defaults plus tenant overrides).
- fetch a versioned managed prompt by name and label.
- record_span
- mark an agent run as completed or failed.
- waxell
- log an llm api call (model, tokens, cost) against a run.
- check_policy
- append a governance or audit event to the audit trail.
- complete_agent_run
- evaluate waxell governance policies before an agent action runs.
- ai agent governance
- get_managed_prompt
slug: agent-governance
source_filename: agent-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Waxell Agent Governance Workflow\n  description: >-\n    Customer-facing workflow that combines Waxell Observe telemetry capture\n    with runtime policy enforcement. Used by platform engineering teams to\n    record every LLM call, evaluate governance policies before risky actions,\n    and audit governance events for AI agents in production.\n  tags:\n    - Waxell\n    - AI Agent Governance\n    - Observability\n    - Policy Enforcement\n    - Cost Management\n  created: '2026-05-06'\n  modified: '2026-05-06'\nbinds:\n  - namespace: env\n    keys:\n      WAXELL_API_KEY: WAXELL_API_KEY\n      WAXELL_API_URL: WAXELL_API_URL\ncapability:\n  imports:\n    - location: shared/observe.yaml\n  exposes:\n    - type: http\n      namespace: waxell-agent-governance\n      description: Unified REST adapter for the agent governance workflow.\n      paths:\n        /agent-runs:\n          post:\n            summary: Start Agent Run\n            operation:\
  \ waxell-observe.runs.startrun\n        /agent-runs/{run_id}/llm-calls:\n          post:\n            summary: Record LLM Call\n            operation: waxell-observe.runs.recordllmcall\n        /agent-runs/{run_id}/spans:\n          post:\n            summary: Record Span\n            operation: waxell-observe.runs.recordspan\n        /agent-runs/{run_id}/complete:\n          post:\n            summary: Complete Agent Run\n            operation: waxell-observe.runs.completerun\n        /policy-checks:\n          post:\n            summary: Check Policy\n            operation: waxell-observe.governance.checkpolicy\n        /audit-events:\n          post:\n            summary: Record Audit Event\n            operation: waxell-observe.governance.recordevent\n        /model-costs:\n          get:\n            summary: List Model Costs\n            operation: waxell-observe.model-costs.listmodelcosts\n        /prompts/{name}:\n          get:\n            summary: Get Managed Prompt\n      \
  \      operation: waxell-observe.prompts.getprompt\n    - type: mcp\n      namespace: waxell-agent-governance\n      description: MCP adapter exposing the governance workflow as agent-callable tools.\n      tools:\n        - name: start_agent_run\n          description: Begin a new Waxell Observe run for an agent.\n          operation: waxell-observe.runs.startrun\n        - name: record_llm_call\n          description: Log an LLM API call (model, tokens, cost) against a run.\n          operation: waxell-observe.runs.recordllmcall\n        - name: record_span\n          description: Log an OpenTelemetry-style span against a run.\n          operation: waxell-observe.runs.recordspan\n        - name: complete_agent_run\n          description: Mark an agent run as completed or failed.\n          operation: waxell-observe.runs.completerun\n        - name: check_policy\n          description: Evaluate Waxell governance policies before an agent action runs.\n          operation: waxell-observe.governance.checkpolicy\n\
  \        - name: record_audit_event\n          description: Append a governance or audit event to the audit trail.\n          operation: waxell-observe.governance.recordevent\n        - name: list_model_costs\n          description: Return the merged model cost table (defaults plus tenant overrides).\n          operation: waxell-observe.model-costs.listmodelcosts\n        - name: get_managed_prompt\n          description: Fetch a versioned managed prompt by name and label.\n          operation: waxell-observe.prompts.getprompt\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/waxell/refs/heads/main/capabilities/agent-governance.yaml
tags:
- Waxell
- AI Agent Governance
- Observability
- Policy Enforcement
- Cost Management
tools:
- description: Begin a new Waxell Observe run for an agent.
  hints: {}
  name: start_agent_run
- description: Log an LLM API call (model, tokens, cost) against a run.
  hints: {}
  name: record_llm_call
- description: Log an OpenTelemetry-style span against a run.
  hints: {}
  name: record_span
- description: Mark an agent run as completed or failed.
  hints: {}
  name: complete_agent_run
- description: Evaluate Waxell governance policies before an agent action runs.
  hints: {}
  name: check_policy
- description: Append a governance or audit event to the audit trail.
  hints: {}
  name: record_audit_event
- description: Return the merged model cost table (defaults plus tenant overrides).
  hints: {}
  name: list_model_costs
- description: Fetch a versioned managed prompt by name and label.
  hints: {}
  name: get_managed_prompt
---
