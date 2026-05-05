---
categories: []
consumed_apis: []
description: A capability composing invoicing (QuickBooks) with bank-feed (Plaid) data into a unified AR/AP context for finance agents.
layout: capability
name: Invoices Bank Feeds Compose Context Capability
operations:
- description: ''
  method: GET
  name: get-ar-ap-context
  path: /ar-ap-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get ar ap context
- finance
- spec-driven integration
- plaid
- mcp
- capabilities
- quickbooks
- naftiko
- api integration
- get transactions
- governance
- ai
slug: invoices-bank-feeds-compose-context-capability
source_filename: invoices-bank-feeds-compose-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Invoices Bank Feeds Compose Context Capability\n  description: A capability composing invoicing (QuickBooks) with bank-feed (Plaid) data into a unified AR/AP context for finance agents.\n  tags: [Naftiko, QuickBooks, Plaid, Finance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: quickbooks-env\n  keys: {QB_TOKEN: QB_TOKEN, QB_REALM_ID: QB_REALM_ID}\n- namespace: plaid-env\n  keys: {PLAID_CLIENT_ID: PLAID_CLIENT_ID, PLAID_SECRET: PLAID_SECRET, PLAID_TOKEN: PLAID_TOKEN}\ncapability:\n  consumes:\n  - namespace: quickbooks\n    type: http\n    baseUri: https://quickbooks.api.intuit.com\n    authentication: {type: bearer, token: '{{QB_TOKEN}}'}\n    resources:\n    - {name: invoices-query, path: '/v3/company/{{QB_REALM_ID}}/query', operations: [{name: query-invoices, method: GET}]}\n  - namespace: plaid\n    type: http\n    baseUri: https://production.plaid.com\n    resources:\n    - {name: transactions, path: /transactions/get,\
  \ operations: [{name: get-transactions, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: invoices-bank-feeds-compose-context-capability-rest\n    description: REST surface for invoice + bank-feed AI context.\n    resources:\n    - {name: ar-ap-context, path: /ar-ap-context, operations: [{method: GET, name: get-ar-ap-context, call: quickbooks.query-invoices}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: invoices-bank-feeds-compose-context-capability-mcp\n    description: MCP for AR/AP context.\n    tools:\n    - {name: get-ar-ap-context, hints: {readOnly: true}, call: quickbooks.query-invoices}\n    - {name: get-transactions, hints: {readOnly: true}, call: plaid.get-transactions}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: invoices-bank-feeds-compose-context-capability-skills\n    description: Skill for AR/AP context.\n    skills:\n    - name: invoices-bank-feeds-compose-context-capability\n\
  \      description: Invoice + bank-feed composed context.\n      location: file:///opt/naftiko/skills/invoices-bank-feeds-compose-context-capability\n      allowed-tools: get-ar-ap-context,get-transactions\n      tools:\n      - {name: get-ar-ap-context, from: {sourceNamespace: invoices-bank-feeds-compose-context-capability-mcp, action: get-ar-ap-context}}\n      - {name: get-transactions, from: {sourceNamespace: invoices-bank-feeds-compose-context-capability-mcp, action: get-transactions}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/invoices-bank-feeds-compose-context-capability.yaml
tags:
- Naftiko
- QuickBooks
- Plaid
- Finance
tools:
- description: ''
  hints:
    readOnly: true
  name: get-ar-ap-context
- description: ''
  hints:
    readOnly: true
  name: get-transactions
---
