---
categories: []
consumed_apis: []
description: A cohort capability for Natixis under PSD2 — Berlin Group accounts/balances/payments exposed as a single Naftiko capability.
layout: capability
name: Natixis Psd2 Open Banking Cohort Capability
operations:
- description: ''
  method: GET
  name: list-accounts
  path: /accounts
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- psd2
- berlin group
- mcp
- list accounts
- natixis
- capabilities
- naftiko
- api integration
- governance
- ai
- get account balances
slug: natixis-psd2-open-banking-cohort-capability
source_filename: natixis-psd2-open-banking-cohort-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Natixis Psd2 Open Banking Cohort Capability\n  description: A cohort capability for Natixis under PSD2 — Berlin Group accounts/balances/payments exposed as a single Naftiko capability.\n  tags: [Naftiko, Natixis, PSD2, Berlin Group]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: natixis-env\n  keys: {NATIXIS_HOST: NATIXIS_HOST, NATIXIS_TOKEN: NATIXIS_TOKEN}\ncapability:\n  consumes:\n  - namespace: natixis\n    type: http\n    baseUri: https://{{NATIXIS_HOST}}\n    authentication: {type: bearer, token: '{{NATIXIS_TOKEN}}'}\n    resources:\n    - {name: accounts, path: /berlingroup/v1/accounts, operations: [{name: list-accounts, method: GET}]}\n    - name: account-balances\n      path: /berlingroup/v1/accounts/{{account_id}}/balances\n      operations:\n      - {name: get-account-balances, method: GET, inputParameters: [{name: account_id, in: path}]}\n    - name: payments\n      path: /berlingroup/v1/payments/{{payment_product}}\n\
  \      operations:\n      - {name: initiate-payment, method: POST, inputParameters: [{name: payment_product, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: natixis-psd2-open-banking-cohort-capability-rest\n    description: REST surface for Natixis PSD2.\n    resources:\n    - {name: accounts, path: /accounts, operations: [{method: GET, name: list-accounts, call: natixis.list-accounts}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: natixis-psd2-open-banking-cohort-capability-mcp\n    description: MCP for Natixis PSD2.\n    tools:\n    - {name: list-accounts, hints: {readOnly: true}, call: natixis.list-accounts}\n    - name: get-account-balances\n      hints: {readOnly: true}\n      inputParameters: [{name: account_id, type: string, required: true}]\n      call: natixis.get-account-balances\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: natixis-psd2-open-banking-cohort-capability-skills\n    description:\
  \ Skill for Natixis PSD2.\n    skills:\n    - name: natixis-psd2-open-banking-cohort-capability\n      description: Natixis PSD2 cohort.\n      location: file:///opt/naftiko/skills/natixis-psd2-open-banking-cohort-capability\n      allowed-tools: list-accounts,get-account-balances\n      tools:\n      - {name: list-accounts, from: {sourceNamespace: natixis-psd2-open-banking-cohort-capability-mcp, action: list-accounts}}\n      - {name: get-account-balances, from: {sourceNamespace: natixis-psd2-open-banking-cohort-capability-mcp, action: get-account-balances}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/natixis-psd2-open-banking-cohort-capability.yaml
tags:
- Naftiko
- Natixis
- PSD2
- Berlin Group
tools:
- description: ''
  hints:
    readOnly: true
  name: list-accounts
- description: ''
  hints:
    readOnly: true
  name: get-account-balances
---
