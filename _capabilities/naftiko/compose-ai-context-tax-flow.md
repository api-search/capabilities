---
categories: []
consumed_apis: []
description: A capability composing AvaTax + ledger context into an AI context for an end-to-end tax-determination flow.
layout: capability
name: Compose Ai Context Tax Flow
operations:
- description: ''
  method: POST
  name: get-tax-flow-context
  path: /tax-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- get tax flow context
- ai context
- avatax
- tax
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
slug: compose-ai-context-tax-flow
source_filename: compose-ai-context-tax-flow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compose Ai Context Tax Flow\n  description: A capability composing AvaTax + ledger context into an AI context for an end-to-end tax-determination flow.\n  tags: [Naftiko, Tax, AvaTax, AI Context]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: avatax-env\n  keys: {AVATAX_USERNAME: AVATAX_USERNAME, AVATAX_PASSWORD: AVATAX_PASSWORD}\ncapability:\n  consumes:\n  - namespace: avatax\n    type: http\n    baseUri: https://rest.avatax.com\n    authentication: {type: basic, username: '{{AVATAX_USERNAME}}', password: '{{AVATAX_PASSWORD}}'}\n    resources:\n    - {name: transactions, path: /api/v2/transactions/create, operations: [{name: create-transaction, method: POST}]}\n    - name: transaction\n      path: /api/v2/companies/{{company_code}}/transactions/{{transaction_code}}\n      operations:\n      - {name: get-transaction, method: GET, inputParameters: [{name: company_code, in: path}, {name: transaction_code, in: path}]}\n\
  \  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compose-ai-context-tax-flow-rest\n    description: REST surface for composed tax-flow AI context.\n    resources:\n    - {name: tax-context, path: /tax-context, operations: [{method: POST, name: get-tax-flow-context, call: avatax.create-transaction}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compose-ai-context-tax-flow-mcp\n    description: MCP for tax-flow context.\n    tools:\n    - {name: get-tax-flow-context, call: avatax.create-transaction}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compose-ai-context-tax-flow-skills\n    description: Skill for tax-flow context.\n    skills:\n    - name: compose-ai-context-tax-flow\n      description: Composed tax-flow AI context.\n      location: file:///opt/naftiko/skills/compose-ai-context-tax-flow\n      allowed-tools: get-tax-flow-context\n      tools:\n      - {name: get-tax-flow-context, from: {sourceNamespace:\
  \ compose-ai-context-tax-flow-mcp, action: get-tax-flow-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compose-ai-context-tax-flow.yaml
tags:
- Naftiko
- Tax
- AvaTax
- AI Context
tools:
- description: ''
  hints: {}
  name: get-tax-flow-context
---
