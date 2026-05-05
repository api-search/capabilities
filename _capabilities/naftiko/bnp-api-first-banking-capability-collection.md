---
categories: []
consumed_apis: []
description: A collection of API-first banking capabilities for BNP Paribas — accounts, payments, FX — exposed as one Naftiko capability bundle.
layout: capability
name: Bnp Api First Banking Capability Collection
operations:
- description: ''
  method: GET
  name: list-accounts
  path: /accounts
- description: ''
  method: POST
  name: initiate-payment
  path: /payments
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get fx rates
- spec-driven integration
- banking
- ai
- mcp
- collection
- list accounts
- capabilities
- naftiko
- api integration
- governance
- initiate payment
- bnp paribas
slug: bnp-api-first-banking-capability-collection
source_filename: bnp-api-first-banking-capability-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Api First Banking Capability Collection\n  description: A collection of API-first banking capabilities for BNP Paribas — accounts, payments, FX — exposed as one Naftiko capability bundle.\n  tags: [Naftiko, BNP Paribas, Banking, Collection]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bnp-env\n  keys: {BNP_TOKEN: BNP_TOKEN, BNP_HOST: BNP_HOST}\ncapability:\n  consumes:\n  - namespace: bnp\n    type: http\n    baseUri: https://{{BNP_HOST}}\n    authentication: {type: bearer, token: '{{BNP_TOKEN}}'}\n    resources:\n    - {name: accounts, path: /v1/accounts, operations: [{name: list-accounts, method: GET}]}\n    - {name: payments, path: /v1/payments, operations: [{name: initiate-payment, method: POST}]}\n    - {name: fx-rates, path: /v1/fx/rates, operations: [{name: get-fx-rates, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-api-first-banking-capability-collection-rest\n\
  \    description: REST surface for the BNP banking collection.\n    resources:\n    - {name: accounts, path: /accounts, operations: [{method: GET, name: list-accounts, call: bnp.list-accounts}]}\n    - {name: payments, path: /payments, operations: [{method: POST, name: initiate-payment, call: bnp.initiate-payment}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-api-first-banking-capability-collection-mcp\n    description: MCP for BNP banking collection.\n    tools:\n    - {name: list-accounts, hints: {readOnly: true}, call: bnp.list-accounts}\n    - {name: initiate-payment, call: bnp.initiate-payment}\n    - {name: get-fx-rates, hints: {readOnly: true}, call: bnp.get-fx-rates}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-api-first-banking-capability-collection-skills\n    description: Skill for BNP collection.\n    skills:\n    - name: bnp-api-first-banking-capability-collection\n      description: BNP API-first banking collection.\n\
  \      location: file:///opt/naftiko/skills/bnp-api-first-banking-capability-collection\n      allowed-tools: list-accounts,initiate-payment,get-fx-rates\n      tools:\n      - {name: list-accounts, from: {sourceNamespace: bnp-api-first-banking-capability-collection-mcp, action: list-accounts}}\n      - {name: initiate-payment, from: {sourceNamespace: bnp-api-first-banking-capability-collection-mcp, action: initiate-payment}}\n      - {name: get-fx-rates, from: {sourceNamespace: bnp-api-first-banking-capability-collection-mcp, action: get-fx-rates}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-api-first-banking-capability-collection.yaml
tags:
- Naftiko
- BNP Paribas
- Banking
- Collection
tools:
- description: ''
  hints:
    readOnly: true
  name: list-accounts
- description: ''
  hints: {}
  name: initiate-payment
- description: ''
  hints:
    readOnly: true
  name: get-fx-rates
---
