---
categories: []
consumed_apis: []
description: A governed capability over Bloomberg EMSX order-management — every order action passes through pre-trade controls and emits an audit event.
layout: capability
name: Emsx Execution Governed Capability
operations:
- description: ''
  method: POST
  name: create-governed-order
  path: /orders
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- trading
- list orders
- emsx
- cancel order
- bloomberg
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- create governed order
slug: emsx-execution-governed-capability
source_filename: emsx-execution-governed-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Emsx Execution Governed Capability\n  description: A governed capability over Bloomberg EMSX order-management — every order action passes through pre-trade controls and emits an audit event.\n  tags: [Naftiko, Bloomberg, EMSX, Trading]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: emsx\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: orders, path: /eap/emsx/v1/orders, operations: [{name: create-order, method: POST}, {name: list-orders, method: GET}]}\n    - name: order\n      path: /eap/emsx/v1/orders/{{order_id}}\n      operations:\n      - {name: get-order, method: GET, inputParameters: [{name: order_id, in: path}]}\n      - {name: cancel-order, method: DELETE, inputParameters: [{name: order_id, in: path}]}\n\
  \  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: emsx-execution-governed-capability-rest\n    description: Governed EMSX execution surface.\n    resources:\n    - {name: orders, path: /orders, operations: [{method: POST, name: create-governed-order, call: emsx.create-order}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: emsx-execution-governed-capability-mcp\n    description: MCP for governed EMSX.\n    tools:\n    - {name: list-orders, hints: {readOnly: true}, call: emsx.list-orders}\n    - {name: create-governed-order, call: emsx.create-order}\n    - name: cancel-order\n      inputParameters: [{name: order_id, type: string, required: true}]\n      call: emsx.cancel-order\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: emsx-execution-governed-capability-skills\n    description: Skill for governed EMSX.\n    skills:\n    - name: emsx-execution-governed-capability\n      description: Governed EMSX execution.\n\
  \      location: file:///opt/naftiko/skills/emsx-execution-governed-capability\n      allowed-tools: list-orders,create-governed-order,cancel-order\n      tools:\n      - {name: list-orders, from: {sourceNamespace: emsx-execution-governed-capability-mcp, action: list-orders}}\n      - {name: create-governed-order, from: {sourceNamespace: emsx-execution-governed-capability-mcp, action: create-governed-order}}\n      - {name: cancel-order, from: {sourceNamespace: emsx-execution-governed-capability-mcp, action: cancel-order}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/emsx-execution-governed-capability.yaml
tags:
- Naftiko
- Bloomberg
- EMSX
- Trading
tools:
- description: ''
  hints:
    readOnly: true
  name: list-orders
- description: ''
  hints: {}
  name: create-governed-order
- description: ''
  hints: {}
  name: cancel-order
---
