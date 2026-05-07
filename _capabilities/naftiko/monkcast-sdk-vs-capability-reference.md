---
categories: []
consumed_apis: []
description: A reference capability used in the MonkCast podcast comparing raw SDK use vs Naftiko-capability use, with the same target API exposed both ways.
layout: capability
name: Monkcast Sdk Vs Capability Reference
operations:
- description: ''
  method: GET
  name: list-customers
  path: /customers
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- monkcast
- get customer
- reference
- sdk
- ai
- capabilities
- list customers
- api integration
- mcp
- naftiko
slug: monkcast-sdk-vs-capability-reference
source_filename: monkcast-sdk-vs-capability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Monkcast Sdk Vs Capability Reference\n  description: A reference capability used in the MonkCast podcast comparing raw SDK use vs Naftiko-capability use, with the same target API exposed both ways.\n  tags: [Naftiko, MonkCast, SDK, Reference]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: stripe-env\n  keys: {STRIPE_API_KEY: STRIPE_API_KEY}\ncapability:\n  consumes:\n  - namespace: stripe\n    type: http\n    baseUri: https://api.stripe.com\n    authentication: {type: bearer, token: '{{STRIPE_API_KEY}}'}\n    resources:\n    - {name: customers, path: /v1/customers, operations: [{name: list-customers, method: GET}]}\n    - name: customer\n      path: /v1/customers/{{customer_id}}\n      operations:\n      - {name: get-customer, method: GET, inputParameters: [{name: customer_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: monkcast-sdk-vs-capability-reference-rest\n\
  \    description: REST surface for the SDK-vs-capability reference.\n    resources:\n    - {name: customers, path: /customers, operations: [{method: GET, name: list-customers, call: stripe.list-customers}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: monkcast-sdk-vs-capability-reference-mcp\n    description: MCP for the reference.\n    tools:\n    - {name: list-customers, hints: {readOnly: true}, call: stripe.list-customers}\n    - name: get-customer\n      hints: {readOnly: true}\n      inputParameters: [{name: customer_id, type: string, required: true}]\n      call: stripe.get-customer\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: monkcast-sdk-vs-capability-reference-skills\n    description: Skill for the reference.\n    skills:\n    - name: monkcast-sdk-vs-capability-reference\n      description: SDK-vs-capability reference.\n      location: file:///opt/naftiko/skills/monkcast-sdk-vs-capability-reference\n      allowed-tools: list-customers,get-customer\n\
  \      tools:\n      - {name: list-customers, from: {sourceNamespace: monkcast-sdk-vs-capability-reference-mcp, action: list-customers}}\n      - {name: get-customer, from: {sourceNamespace: monkcast-sdk-vs-capability-reference-mcp, action: get-customer}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/monkcast-sdk-vs-capability-reference.yaml
tags:
- Naftiko
- MonkCast
- SDK
- Reference
tools:
- description: ''
  hints:
    readOnly: true
  name: list-customers
- description: ''
  hints:
    readOnly: true
  name: get-customer
---
