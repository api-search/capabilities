---
categories: []
consumed_apis: []
description: A capability composing finance APIs (market data, portfolio, risk) into a token-budgeted AI context for finance agents.
layout: capability
name: Compose Ai Context Finance Capability
operations:
- description: ''
  method: GET
  name: get-finance-ai-context
  path: /finance-ai-context/{{security_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- ai context
- ai
- capabilities
- spec-driven integration
- finance
- api integration
- mcp
- get finance ai context
- naftiko
slug: compose-ai-context-finance-capability
source_filename: compose-ai-context-finance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compose Ai Context Finance Capability\n  description: A capability composing finance APIs (market data, portfolio, risk) into a token-budgeted AI context for finance agents.\n  tags: [Naftiko, Finance, AI Context]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: bloomberg\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: bql, path: /eap/bql/v1/query, operations: [{name: run-bql, method: POST}]}\n    - name: market-data\n      path: '/eap/marketdata/v1/securities/{{security_id}}/quote'\n      operations:\n      - {name: get-quote, method: GET, inputParameters: [{name: security_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compose-ai-context-finance-capability-rest\n\
  \    description: REST surface for composed finance AI context.\n    resources:\n    - {name: ai-context, path: '/finance-ai-context/{{security_id}}', operations: [{method: GET, name: get-finance-ai-context, inputParameters: [{name: security_id, in: path, type: string}], call: bloomberg.get-quote}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compose-ai-context-finance-capability-mcp\n    description: MCP for finance AI context.\n    tools:\n    - name: get-finance-ai-context\n      hints: {readOnly: true}\n      inputParameters: [{name: security_id, type: string, required: true}]\n      call: bloomberg.get-quote\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compose-ai-context-finance-capability-skills\n    description: Skill for finance AI context.\n    skills:\n    - name: compose-ai-context-finance-capability\n      description: Composed finance AI context.\n      location: file:///opt/naftiko/skills/compose-ai-context-finance-capability\n\
  \      allowed-tools: get-finance-ai-context\n      tools:\n      - {name: get-finance-ai-context, from: {sourceNamespace: compose-ai-context-finance-capability-mcp, action: get-finance-ai-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compose-ai-context-finance-capability.yaml
tags:
- Naftiko
- Finance
- AI Context
tools:
- description: ''
  hints:
    readOnly: true
  name: get-finance-ai-context
---
