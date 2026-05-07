---
categories: []
consumed_apis: []
description: A governance capability over Temenos Transact core banking — every account/transaction call passes through Naftiko governance and emits an audit event.
layout: capability
name: Bnp Temenos Transact Core Banking Governance Capability
operations:
- description: ''
  method: GET
  name: get-governed-account
  path: /accounts/{{account_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get account
- governance
- spec-driven integration
- get governed account
- list transactions
- ai
- capabilities
- bnp
- api integration
- mcp
- temenos
- core banking
- naftiko
slug: bnp-temenos-transact-core-banking-governance-capability
source_filename: bnp-temenos-transact-core-banking-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Temenos Transact Core Banking Governance Capability\n  description: A governance capability over Temenos Transact core banking — every account/transaction call passes through Naftiko governance and emits an audit event.\n  tags: [Naftiko, BNP, Temenos, Core Banking]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: temenos-env\n  keys: {TEMENOS_HOST: TEMENOS_HOST, TEMENOS_TOKEN: TEMENOS_TOKEN}\ncapability:\n  consumes:\n  - namespace: temenos\n    type: http\n    baseUri: https://{{TEMENOS_HOST}}\n    authentication: {type: bearer, token: '{{TEMENOS_TOKEN}}'}\n    resources:\n    - name: account\n      path: /irf-provider-container/api/v1.0.0/holdings/accounts/{{account_id}}\n      operations:\n      - {name: get-account, method: GET, inputParameters: [{name: account_id, in: path}]}\n    - name: account-balance\n      path: /irf-provider-container/api/v1.0.0/holdings/accounts/{{account_id}}/balances\n      operations:\n\
  \      - {name: get-account-balance, method: GET, inputParameters: [{name: account_id, in: path}]}\n    - name: transactions\n      path: /irf-provider-container/api/v1.0.0/holdings/accounts/{{account_id}}/transactions\n      operations:\n      - {name: list-transactions, method: GET, inputParameters: [{name: account_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-temenos-transact-core-banking-governance-capability-rest\n    description: Governance-gated Temenos surface.\n    resources:\n    - name: account\n      path: /accounts/{{account_id}}\n      operations:\n      - {method: GET, name: get-governed-account, inputParameters: [{name: account_id, in: path, type: string}], call: temenos.get-account}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-temenos-transact-core-banking-governance-capability-mcp\n    description: MCP for governed Temenos ops.\n    tools:\n    - name: get-account\n      hints: {readOnly:\
  \ true}\n      inputParameters: [{name: account_id, type: string, required: true}]\n      call: temenos.get-account\n    - name: list-transactions\n      hints: {readOnly: true}\n      inputParameters: [{name: account_id, type: string, required: true}]\n      call: temenos.list-transactions\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-temenos-transact-core-banking-governance-capability-skills\n    description: Skill for governed Temenos.\n    skills:\n    - name: bnp-temenos-transact-core-banking-governance-capability\n      description: Governed Temenos Transact access.\n      location: file:///opt/naftiko/skills/bnp-temenos-transact-core-banking-governance-capability\n      allowed-tools: get-account,list-transactions\n      tools:\n      - {name: get-account, from: {sourceNamespace: bnp-temenos-transact-core-banking-governance-capability-mcp, action: get-account}}\n      - {name: list-transactions, from: {sourceNamespace: bnp-temenos-transact-core-banking-governance-capability-mcp,\
  \ action: list-transactions}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-temenos-transact-core-banking-governance-capability.yaml
tags:
- Naftiko
- BNP
- Temenos
- Core Banking
tools:
- description: ''
  hints:
    readOnly: true
  name: get-account
- description: ''
  hints:
    readOnly: true
  name: list-transactions
---
