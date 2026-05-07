---
categories: []
consumed_apis: []
description: A capability that turns an AsyncAPI document into a mocked event stream usable as REST-poll + MCP tools, so consumers can develop against a contract before broker access exists.
layout: capability
name: Asyncapi Mocked Event Stream Capability
operations:
- description: ''
  method: GET
  name: poll-events
  path: /streams/{{mock_id}}/events
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- create asyncapi mock
- governance
- asyncapi
- mocking
- ai
- capabilities
- spec-driven integration
- api integration
- poll events
- mcp
- naftiko
slug: asyncapi-mocked-event-stream-capability
source_filename: asyncapi-mocked-event-stream-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Asyncapi Mocked Event Stream Capability\n  description: A capability that turns an AsyncAPI document into a mocked event stream usable as REST-poll + MCP tools, so consumers can develop against a contract before broker access exists.\n  tags: [Naftiko, AsyncAPI, Mocking]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-mock\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - name: asyncapi-mocks\n      path: /v1/asyncapi-mocks\n      operations:\n      - {name: create-asyncapi-mock, method: POST, description: Create a mocked event stream from an AsyncAPI doc.}\n    - name: stream-events\n      path: /v1/asyncapi-mocks/{{mock_id}}/events\n      operations:\n      - {name: poll-events, method: GET, inputParameters: [{name:\
  \ mock_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: asyncapi-mocked-event-stream-capability-rest\n    description: REST-poll surface over mocked AsyncAPI event streams.\n    resources:\n    - name: poll\n      path: /streams/{{mock_id}}/events\n      operations:\n      - {method: GET, name: poll-events, inputParameters: [{name: mock_id, in: path, type: string}], call: naftiko-mock.poll-events}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: asyncapi-mocked-event-stream-capability-mcp\n    description: MCP exposing AsyncAPI mock streams.\n    tools:\n    - {name: create-asyncapi-mock, call: naftiko-mock.create-asyncapi-mock}\n    - name: poll-events\n      hints: {readOnly: true}\n      inputParameters: [{name: mock_id, type: string, required: true}]\n      call: naftiko-mock.poll-events\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: asyncapi-mocked-event-stream-capability-skills\n    description:\
  \ Skill bundle for AsyncAPI mock streams.\n    skills:\n    - name: asyncapi-mocked-event-stream-capability\n      description: AsyncAPI mocked event stream consumption.\n      location: file:///opt/naftiko/skills/asyncapi-mocked-event-stream-capability\n      allowed-tools: create-asyncapi-mock,poll-events\n      tools:\n      - {name: create-asyncapi-mock, from: {sourceNamespace: asyncapi-mocked-event-stream-capability-mcp, action: create-asyncapi-mock}}\n      - {name: poll-events, from: {sourceNamespace: asyncapi-mocked-event-stream-capability-mcp, action: poll-events}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/asyncapi-mocked-event-stream-capability.yaml
tags:
- Naftiko
- AsyncAPI
- Mocking
tools:
- description: ''
  hints: {}
  name: create-asyncapi-mock
- description: ''
  hints:
    readOnly: true
  name: poll-events
---
