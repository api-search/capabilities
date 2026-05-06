---
categories: []
consumed_apis: []
description: A reference capability showing API reusability across UK Open Banking endpoints — accounts/balances/transactions composed once, reused across consumer apps.
layout: capability
name: Api Reusability Open Banking Reference
operations:
- description: Composed account snapshot (balance + recent transactions) reusable across apps.
  method: GET
  name: get-account-snapshot
  path: /accounts/{{account_id}}/snapshot
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- composed account snapshot (balance + recent transactions) reusable across apps.
- open banking
- list accounts
- reusability
- get account snapshot
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
slug: api-reusability-open-banking-reference
source_filename: api-reusability-open-banking-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api Reusability Open Banking Reference\n  description: A reference capability showing API reusability across UK Open Banking endpoints — accounts/balances/transactions composed once, reused across consumer apps.\n  tags: [Naftiko, Open Banking, Reusability]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: openbanking-env\n  description: UK Open Banking OAuth bearer with accounts scope.\n  keys: {OB_TOKEN: OB_TOKEN, OB_HOST: OB_HOST}\ncapability:\n  consumes:\n  - namespace: openbanking\n    type: http\n    baseUri: https://{{OB_HOST}}\n    authentication: {type: bearer, token: '{{OB_TOKEN}}'}\n    resources:\n    - {name: accounts, path: /open-banking/v3.1/aisp/accounts, operations: [{name: list-accounts, method: GET}]}\n    - name: balances\n      path: /open-banking/v3.1/aisp/accounts/{{account_id}}/balances\n      operations:\n      - {name: get-account-balances, method: GET, inputParameters: [{name: account_id,\
  \ in: path}]}\n    - name: transactions\n      path: /open-banking/v3.1/aisp/accounts/{{account_id}}/transactions\n      operations:\n      - {name: list-account-transactions, method: GET, inputParameters: [{name: account_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-reusability-open-banking-reference-rest\n    description: Reusable Open Banking surface — accounts/balances/transactions in one shape.\n    resources:\n    - name: account-snapshot\n      path: /accounts/{{account_id}}/snapshot\n      operations:\n      - method: GET\n        name: get-account-snapshot\n        description: Composed account snapshot (balance + recent transactions) reusable across apps.\n        inputParameters: [{name: account_id, in: path, type: string}]\n        call: openbanking.list-accounts\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-reusability-open-banking-reference-mcp\n    description: MCP for Open Banking account\
  \ snapshots.\n    tools:\n    - {name: list-accounts, hints: {readOnly: true}, call: openbanking.list-accounts}\n    - name: get-account-snapshot\n      hints: {readOnly: true}\n      inputParameters: [{name: account_id, type: string, required: true}]\n      call: openbanking.list-accounts\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-reusability-open-banking-reference-skills\n    description: Skill for Open Banking account snapshots.\n    skills:\n    - name: api-reusability-open-banking-reference\n      description: Reusable Open Banking account snapshot.\n      location: file:///opt/naftiko/skills/api-reusability-open-banking-reference\n      allowed-tools: list-accounts,get-account-snapshot\n      tools:\n      - {name: list-accounts, from: {sourceNamespace: api-reusability-open-banking-reference-mcp, action: list-accounts}}\n      - {name: get-account-snapshot, from: {sourceNamespace: api-reusability-open-banking-reference-mcp, action: get-account-snapshot}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-reusability-open-banking-reference.yaml
tags:
- Naftiko
- Open Banking
- Reusability
tools:
- description: ''
  hints:
    readOnly: true
  name: list-accounts
- description: ''
  hints:
    readOnly: true
  name: get-account-snapshot
---
