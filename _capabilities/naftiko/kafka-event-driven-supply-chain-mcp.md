---
categories: []
consumed_apis: []
description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
layout: capability
name: Kafka Event Driven Supply Chain Mcp
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
- a capability over a p&g kafka topic family (supply-chain events) exposing typed event reads as mcp tools for ai ops assistants.
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: kafka-event-driven-supply-chain-mcp
source_filename: kafka-event-driven-supply-chain-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Kafka Event Driven Supply Chain Mcp\n  description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: kafka-event-driven-supply-chain-mcp-rest\n    description: REST API for Kafka Event Driven Supply Chain Mcp.\n    resources:\n    - name: example\n      path: /example\n      operations:\n \
  \     - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: kafka-event-driven-supply-chain-mcp-mcp\n    description: MCP server exposing Kafka Event Driven Supply Chain Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: kafka-event-driven-supply-chain-mcp-skills\n    description: Agent Skill bundle for Kafka Event Driven Supply Chain Mcp.\n    skills:\n    - name: kafka-event-driven-supply-chain-mcp\n      description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.\n      location: file:///opt/naftiko/skills/kafka-event-driven-supply-chain-mcp\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.\n        from:\n          sourceNamespace: kafka-event-driven-supply-chain-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/kafka-event-driven-supply-chain-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
  hints:
    readOnly: true
  name: example
---
