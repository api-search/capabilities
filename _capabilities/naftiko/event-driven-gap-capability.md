---
categories: []
consumed_apis: []
description: A capability that fills the event-driven gap — wraps a message broker (Kafka/Solace) so consumers can browse and replay topics over REST + MCP.
layout: capability
name: Event Driven Gap Capability
operations:
- description: ''
  method: GET
  name: list-topics
  path: /topics
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- produce record
- kafka
- api integration
- capabilities
- list topics
- ai
- governance
- spec-driven integration
- mcp
- event-driven
- get topic
slug: event-driven-gap-capability
source_filename: event-driven-gap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Event Driven Gap Capability\n  description: A capability that fills the event-driven gap — wraps a message broker (Kafka/Solace) so consumers can browse and replay topics over REST + MCP.\n  tags: [Naftiko, Event-Driven, Kafka]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: kafka-env\n  keys: {KAFKA_REST_HOST: KAFKA_REST_HOST, KAFKA_REST_TOKEN: KAFKA_REST_TOKEN}\ncapability:\n  consumes:\n  - namespace: kafka\n    type: http\n    baseUri: https://{{KAFKA_REST_HOST}}\n    authentication: {type: bearer, token: '{{KAFKA_REST_TOKEN}}'}\n    resources:\n    - {name: topics, path: /topics, operations: [{name: list-topics, method: GET}]}\n    - name: topic\n      path: /topics/{{topic}}\n      operations:\n      - {name: get-topic, method: GET, inputParameters: [{name: topic, in: path}]}\n    - name: topic-records\n      path: /topics/{{topic}}/records\n      operations:\n      - {name: produce-record, method: POST,\
  \ inputParameters: [{name: topic, in: path}]}\n    - name: consume\n      path: /consumers/{{group}}/instances/{{instance}}/records\n      operations:\n      - {name: consume-records, method: GET, inputParameters: [{name: group, in: path}, {name: instance, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: event-driven-gap-capability-rest\n    description: REST surface for browsing/replaying topics.\n    resources:\n    - {name: topics, path: /topics, operations: [{method: GET, name: list-topics, call: kafka.list-topics}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: event-driven-gap-capability-mcp\n    description: MCP for event topics.\n    tools:\n    - {name: list-topics, hints: {readOnly: true}, call: kafka.list-topics}\n    - name: get-topic\n      hints: {readOnly: true}\n      inputParameters: [{name: topic, type: string, required: true}]\n      call: kafka.get-topic\n    - name: produce-record\n      inputParameters:\
  \ [{name: topic, type: string, required: true}]\n      call: kafka.produce-record\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: event-driven-gap-capability-skills\n    description: Skill for event topics.\n    skills:\n    - name: event-driven-gap-capability\n      description: Event-driven gap capability.\n      location: file:///opt/naftiko/skills/event-driven-gap-capability\n      allowed-tools: list-topics,get-topic,produce-record\n      tools:\n      - {name: list-topics, from: {sourceNamespace: event-driven-gap-capability-mcp, action: list-topics}}\n      - {name: get-topic, from: {sourceNamespace: event-driven-gap-capability-mcp, action: get-topic}}\n      - {name: produce-record, from: {sourceNamespace: event-driven-gap-capability-mcp, action: produce-record}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/event-driven-gap-capability.yaml
tags:
- Naftiko
- Event-Driven
- Kafka
tools:
- description: ''
  hints:
    readOnly: true
  name: list-topics
- description: ''
  hints:
    readOnly: true
  name: get-topic
- description: ''
  hints: {}
  name: produce-record
---
