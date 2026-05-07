---
categories: []
consumed_apis: []
description: A capability over Kafka topics for supply-chain events (order, shipment, exception) exposed as MCP tools for agent flows.
layout: capability
name: Kafka Event Driven Supply Chain Mcp
operations:
- description: ''
  method: POST
  name: emit-order
  path: /events/orders
- description: ''
  method: POST
  name: emit-shipment
  path: /events/shipments
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- emit order
- consume events
- emit shipment
- ai
- capabilities
- spec-driven integration
- kafka
- api integration
- mcp
- naftiko
- supply chain
slug: kafka-event-driven-supply-chain-mcp
source_filename: kafka-event-driven-supply-chain-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Kafka Event Driven Supply Chain Mcp\n  description: A capability over Kafka topics for supply-chain events (order, shipment, exception) exposed as MCP tools for agent flows.\n  tags: [Naftiko, Kafka, Supply Chain]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: kafka-env\n  keys: {KAFKA_REST_HOST: KAFKA_REST_HOST, KAFKA_REST_TOKEN: KAFKA_REST_TOKEN}\ncapability:\n  consumes:\n  - namespace: kafka\n    type: http\n    baseUri: https://{{KAFKA_REST_HOST}}\n    authentication: {type: bearer, token: '{{KAFKA_REST_TOKEN}}'}\n    resources:\n    - name: order-events\n      path: /topics/orders/records\n      operations: [{name: produce-order-event, method: POST}]\n    - name: shipment-events\n      path: /topics/shipments/records\n      operations: [{name: produce-shipment-event, method: POST}]\n    - name: consumer-records\n      path: /consumers/{{group}}/instances/{{instance}}/records\n      operations:\n      - {name:\
  \ consume-records, method: GET, inputParameters: [{name: group, in: path}, {name: instance, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: kafka-event-driven-supply-chain-mcp-rest\n    description: REST surface for supply-chain events.\n    resources:\n    - {name: orders, path: /events/orders, operations: [{method: POST, name: emit-order, call: kafka.produce-order-event}]}\n    - {name: shipments, path: /events/shipments, operations: [{method: POST, name: emit-shipment, call: kafka.produce-shipment-event}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: kafka-event-driven-supply-chain-mcp-mcp\n    description: MCP for supply-chain events.\n    tools:\n    - {name: emit-order, call: kafka.produce-order-event}\n    - {name: emit-shipment, call: kafka.produce-shipment-event}\n    - name: consume-events\n      hints: {readOnly: true}\n      inputParameters: [{name: group, type: string, required: true}, {name: instance, type:\
  \ string, required: true}]\n      call: kafka.consume-records\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: kafka-event-driven-supply-chain-mcp-skills\n    description: Skill for supply-chain events.\n    skills:\n    - name: kafka-event-driven-supply-chain-mcp\n      description: Kafka supply-chain events.\n      location: file:///opt/naftiko/skills/kafka-event-driven-supply-chain-mcp\n      allowed-tools: emit-order,emit-shipment,consume-events\n      tools:\n      - {name: emit-order, from: {sourceNamespace: kafka-event-driven-supply-chain-mcp-mcp, action: emit-order}}\n      - {name: emit-shipment, from: {sourceNamespace: kafka-event-driven-supply-chain-mcp-mcp, action: emit-shipment}}\n      - {name: consume-events, from: {sourceNamespace: kafka-event-driven-supply-chain-mcp-mcp, action: consume-events}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/kafka-event-driven-supply-chain-mcp.yaml
tags:
- Naftiko
- Kafka
- Supply Chain
tools:
- description: ''
  hints: {}
  name: emit-order
- description: ''
  hints: {}
  name: emit-shipment
- description: ''
  hints:
    readOnly: true
  name: consume-events
---
