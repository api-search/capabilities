---
categories: []
consumed_apis:
- procter-gamble
description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Kafka Event Driven Supply Chain Mcp
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- capability
- over
- kafka
- topic
- family
slug: pg-kafka-event-driven-supply-chain-mcp
source_filename: pg-kafka-event-driven-supply-chain-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Kafka Event Driven Supply Chain Mcp
    description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
    tags:
    - Procter & Gamble
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: procter-gamble-env
    description: Procter & Gamble credentials.
    keys:
      PROCTER_GAMBLE_API_KEY: PROCTER_GAMBLE_API_KEY
  capability:
    consumes:
    - namespace: procter-gamble
      type: http
      baseUri: https://api.procter-gamble.com
      authentication:
        type: bearer
        token: '{{PROCTER_GAMBLE_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: pg-kafka-event-driven-supply-chain-mcp-rest
      description: REST API for Procter & Gamble Pg Kafka Event Driven Supply Chain Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: procter-gamble.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: pg-kafka-event-driven-supply-chain-mcp-mcp
      description: MCP server exposing Procter & Gamble Pg Kafka Event Driven Supply Chain Mcp for AI agents.
      tools:
      - name: example
        description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-kafka-event-driven-supply-chain-mcp-skills
      description: Agent Skill bundle for Procter & Gamble Pg Kafka Event Driven Supply Chain Mcp.
      skills:
      - name: pg-kafka-event-driven-supply-chain-mcp
        description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
        location: file:///opt/naftiko/skills/pg-kafka-event-driven-supply-chain-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants.
          from:
            sourceNamespace: pg-kafka-event-driven-supply-chain-mcp-mcp
            action: example
---

A capability over a P&G Kafka topic family (supply-chain events) exposing typed event reads as MCP tools for AI ops assistants. He named Kafka as primary; AI agents will need governed event reads more than REST in CPG ops.
