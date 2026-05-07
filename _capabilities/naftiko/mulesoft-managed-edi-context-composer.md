---
categories: []
consumed_apis: []
description: A capability composing MuleSoft-managed EDI 850/810 transactions into a unified order-fulfillment context.
layout: capability
name: Mulesoft Managed Edi Context Composer
operations:
- description: ''
  method: GET
  name: get-fulfillment-context
  path: /fulfillment/{{txn_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- mulesoft
- governance
- edi
- get fulfillment context
- list edi transactions
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- naftiko
slug: mulesoft-managed-edi-context-composer
source_filename: mulesoft-managed-edi-context-composer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mulesoft Managed Edi Context Composer\n  description: A capability composing MuleSoft-managed EDI 850/810 transactions into a unified order-fulfillment context.\n  tags: [Naftiko, MuleSoft, EDI]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: mulesoft-env\n  keys: {MULESOFT_TOKEN: MULESOFT_TOKEN}\ncapability:\n  consumes:\n  - namespace: mulesoft-edi\n    type: http\n    baseUri: https://anypoint.mulesoft.com\n    authentication: {type: bearer, token: '{{MULESOFT_TOKEN}}'}\n    resources:\n    - {name: edi-transactions, path: /edi/v1/transactions, operations: [{name: list-edi-transactions, method: GET}]}\n    - name: edi-transaction\n      path: '/edi/v1/transactions/{{txn_id}}'\n      operations:\n      - {name: get-edi-transaction, method: GET, inputParameters: [{name: txn_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mulesoft-managed-edi-context-composer-rest\n\
  \    description: REST surface for EDI fulfillment context.\n    resources:\n    - {name: fulfillment, path: '/fulfillment/{{txn_id}}', operations: [{method: GET, name: get-fulfillment-context, inputParameters: [{name: txn_id, in: path, type: string}], call: mulesoft-edi.get-edi-transaction}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mulesoft-managed-edi-context-composer-mcp\n    description: MCP for EDI context.\n    tools:\n    - {name: list-edi-transactions, hints: {readOnly: true}, call: mulesoft-edi.list-edi-transactions}\n    - name: get-fulfillment-context\n      hints: {readOnly: true}\n      inputParameters: [{name: txn_id, type: string, required: true}]\n      call: mulesoft-edi.get-edi-transaction\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mulesoft-managed-edi-context-composer-skills\n    description: Skill for EDI context.\n    skills:\n    - name: mulesoft-managed-edi-context-composer\n      description: MuleSoft EDI\
  \ fulfillment context.\n      location: file:///opt/naftiko/skills/mulesoft-managed-edi-context-composer\n      allowed-tools: list-edi-transactions,get-fulfillment-context\n      tools:\n      - {name: list-edi-transactions, from: {sourceNamespace: mulesoft-managed-edi-context-composer-mcp, action: list-edi-transactions}}\n      - {name: get-fulfillment-context, from: {sourceNamespace: mulesoft-managed-edi-context-composer-mcp, action: get-fulfillment-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mulesoft-managed-edi-context-composer.yaml
tags:
- Naftiko
- MuleSoft
- EDI
tools:
- description: ''
  hints:
    readOnly: true
  name: list-edi-transactions
- description: ''
  hints:
    readOnly: true
  name: get-fulfillment-context
---
