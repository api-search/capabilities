---
categories: []
consumed_apis: []
description: A capability composing dealer DMS + CRM into a unified customer context for automotive sales-floor agents.
layout: capability
name: Dealer Customer Context Composition
operations:
- description: ''
  method: GET
  name: get-customer-context
  path: /customers/{{customer_id}}/context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- crm
- mcp
- api integration
- get customer context
- governance
- spec-driven integration
- ai
- dealer
- capabilities
- automotive
slug: dealer-customer-context-composition
source_filename: dealer-customer-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Dealer Customer Context Composition\n  description: A capability composing dealer DMS + CRM into a unified customer context for automotive sales-floor agents.\n  tags: [Naftiko, Automotive, Dealer, CRM]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: dms-env\n  keys: {DMS_HOST: DMS_HOST, DMS_TOKEN: DMS_TOKEN}\ncapability:\n  consumes:\n  - namespace: dms\n    type: http\n    baseUri: https://{{DMS_HOST}}\n    authentication: {type: bearer, token: '{{DMS_TOKEN}}'}\n    resources:\n    - name: customer\n      path: /api/v1/customers/{{customer_id}}\n      operations:\n      - {name: get-customer, method: GET, inputParameters: [{name: customer_id, in: path}]}\n    - name: customer-deals\n      path: /api/v1/customers/{{customer_id}}/deals\n      operations:\n      - {name: list-customer-deals, method: GET, inputParameters: [{name: customer_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port:\
  \ 8080\n    namespace: dealer-customer-context-composition-rest\n    description: REST surface for dealer customer context.\n    resources:\n    - name: customer-context\n      path: /customers/{{customer_id}}/context\n      operations:\n      - {method: GET, name: get-customer-context, inputParameters: [{name: customer_id, in: path, type: string}], call: dms.get-customer}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: dealer-customer-context-composition-mcp\n    description: MCP for dealer customer context.\n    tools:\n    - name: get-customer-context\n      hints: {readOnly: true}\n      inputParameters: [{name: customer_id, type: string, required: true}]\n      call: dms.get-customer\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: dealer-customer-context-composition-skills\n    description: Skill for dealer context.\n    skills:\n    - name: dealer-customer-context-composition\n      description: Dealer customer context.\n      location:\
  \ file:///opt/naftiko/skills/dealer-customer-context-composition\n      allowed-tools: get-customer-context\n      tools:\n      - {name: get-customer-context, from: {sourceNamespace: dealer-customer-context-composition-mcp, action: get-customer-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/dealer-customer-context-composition.yaml
tags:
- Naftiko
- Automotive
- Dealer
- CRM
tools:
- description: ''
  hints:
    readOnly: true
  name: get-customer-context
---
