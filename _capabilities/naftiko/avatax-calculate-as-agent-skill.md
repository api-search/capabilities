---
categories: []
consumed_apis: []
description: A capability wrapping Avalara AvaTax CalculateTax as an Agent Skill so AI assistants can compute sales tax inline without raw API access.
layout: capability
name: Avatax Calculate As Agent Skill
operations:
- description: Compute sales tax for a transaction.
  method: POST
  name: calculate-tax
  path: /calculate
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- avatax
- calculate tax
- compute sales tax for a transaction.
- tax
- ai
- capabilities
- spec-driven integration
- calculate sales tax on a transaction.
- api integration
- mcp
- naftiko
slug: avatax-calculate-as-agent-skill
source_filename: avatax-calculate-as-agent-skill.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Avatax Calculate As Agent Skill\n  description: A capability wrapping Avalara AvaTax CalculateTax as an Agent Skill so AI assistants can compute sales tax inline without raw API access.\n  tags: [Naftiko, AvaTax, Tax]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: avatax-env\n  description: Avalara AvaTax account/license credentials.\n  keys: {AVATAX_USERNAME: AVATAX_USERNAME, AVATAX_PASSWORD: AVATAX_PASSWORD}\ncapability:\n  consumes:\n  - namespace: avatax\n    type: http\n    baseUri: https://rest.avatax.com\n    authentication:\n      type: basic\n      username: '{{AVATAX_USERNAME}}'\n      password: '{{AVATAX_PASSWORD}}'\n    resources:\n    - {name: transactions, path: /api/v2/transactions/create, operations: [{name: create-transaction, method: POST, description: Create and calculate tax on a transaction.}]}\n    - name: transaction\n      path: /api/v2/companies/{{company_code}}/transactions/{{transaction_code}}\n\
  \      operations:\n      - {name: get-transaction, method: GET, inputParameters: [{name: company_code, in: path}, {name: transaction_code, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: avatax-calculate-as-agent-skill-rest\n    description: REST surface for AvaTax tax calculation.\n    resources:\n    - {name: calculate, path: /calculate, operations: [{method: POST, name: calculate-tax, description: Compute sales tax for a transaction., call: avatax.create-transaction}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: avatax-calculate-as-agent-skill-mcp\n    description: MCP exposing AvaTax CalculateTax for AI assistants.\n    tools:\n    - {name: calculate-tax, description: Calculate sales tax on a transaction., call: avatax.create-transaction}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: avatax-calculate-as-agent-skill-skills\n    description: Agent Skill bundle for inline tax calculation.\n\
  \    skills:\n    - name: avatax-calculate-as-agent-skill\n      description: Inline AvaTax CalculateTax as an Agent Skill.\n      location: file:///opt/naftiko/skills/avatax-calculate-as-agent-skill\n      allowed-tools: calculate-tax\n      tools:\n      - {name: calculate-tax, from: {sourceNamespace: avatax-calculate-as-agent-skill-mcp, action: calculate-tax}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/avatax-calculate-as-agent-skill.yaml
tags:
- Naftiko
- AvaTax
- Tax
tools:
- description: Calculate sales tax on a transaction.
  hints: {}
  name: calculate-tax
---
