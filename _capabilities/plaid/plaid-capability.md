---
categories: []
consumed_apis: []
description: Needs description.
layout: capability
name: Plaid accounts/
operations:
- description: Plaid Retrieve accounts
  method: POST
  name: accountsget
  path: /accounts/get
- description: Plaid Retrieve real-time balance data
  method: POST
  name: accountsbalanceget
  path: /accounts/balance/get
personas: []
provider_name: Plaid
provider_slug: plaid
search_terms:
- financial
- plaid retrieve real-time balance data
- api
- accountsbalanceget
- bank accounts
- accountsget
- plaid retrieve accounts
- plaid
slug: plaid-capability
source_filename: plaid-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Plaid accounts/\n  description: Needs description.\n  tags:\n  - Plaid\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: plaid\n    baseUri: https://production.plaid.com\n    description: Plaid accounts/ HTTP API.\n    resources:\n    - name: accounts-get\n      path: /accounts/get\n      operations:\n      - name: accountsget\n        method: POST\n        description: Plaid Retrieve accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-balance-get\n      path: /accounts/balance/get\n      operations:\n      - name: accountsbalanceget\n        method: POST\n        description: Plaid Retrieve real-time balance data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n\
  \    port: 8080\n    namespace: plaid-rest\n    description: REST adapter for Plaid accounts/.\n    resources:\n    - path: /accounts/get\n      name: accountsget\n      operations:\n      - method: POST\n        name: accountsget\n        description: Plaid Retrieve accounts\n        call: plaid.accountsget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/balance/get\n      name: accountsbalanceget\n      operations:\n      - method: POST\n        name: accountsbalanceget\n        description: Plaid Retrieve real-time balance data\n        call: plaid.accountsbalanceget\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: plaid-mcp\n    transport: http\n    description: MCP adapter for Plaid accounts/ for AI agent use.\n    tools:\n    - name: accountsget\n      description: Plaid Retrieve accounts\n      hints:\n        readOnly: false\n        destructive: false\n    \
  \    idempotent: false\n      call: plaid.accountsget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accountsbalanceget\n      description: Plaid Retrieve real-time balance data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: plaid.accountsbalanceget\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/plaid/refs/heads/main/capabilities/plaid-capability.yaml
tags:
- Plaid
- API
tools:
- description: Plaid Retrieve accounts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: accountsget
- description: Plaid Retrieve real-time balance data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: accountsbalanceget
---
