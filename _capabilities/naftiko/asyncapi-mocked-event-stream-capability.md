---
categories: []
consumed_apis: []
description: A capability where mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
layout: capability
name: Asyncapi Mocked Event Stream Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
- a capability where mocks an asyncapi-described event stream and the same yaml drives the naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
slug: asyncapi-mocked-event-stream-capability
source_filename: asyncapi-mocked-event-stream-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Asyncapi Mocked Event Stream Capability\n  description: A capability where mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: asyncapi-mocked-event-stream-capability-rest\n    description: REST API for Asyncapi Mocked Event Stream Capability.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: asyncapi-mocked-event-stream-capability-mcp\n    description: MCP server exposing Asyncapi Mocked Event Stream Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability where mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: asyncapi-mocked-event-stream-capability-skills\n    description: Agent Skill bundle for Asyncapi Mocked Event Stream Capability.\n    skills:\n    - name: asyncapi-mocked-event-stream-capability\n      description: A capability where mocks an AsyncAPI-described event stream and\
  \ the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.\n      location: file:///opt/naftiko/skills/asyncapi-mocked-event-stream-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability where mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.\n        from:\n          sourceNamespace: asyncapi-mocked-event-stream-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/asyncapi-mocked-event-stream-capability.yaml
tags:
- Naftiko
tools:
- description: A capability where mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
  hints:
    readOnly: true
  name: example
---
