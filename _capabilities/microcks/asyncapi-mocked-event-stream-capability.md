---
categories: []
consumed_apis:
- microcks
description: A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Laurent Broudoux
name: Microcks Asyncapi Mocked Event Stream Capability
operations: []
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- capability
- where
- microcks
- mocks
- asyncapi
slug: asyncapi-mocked-event-stream-capability
source_filename: asyncapi-mocked-event-stream-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microcks Asyncapi Mocked Event Stream Capability
    description: A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
    tags:
    - Microcks
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microcks-env
    description: Microcks credentials.
    keys:
      MICROCKS_API_KEY: MICROCKS_API_KEY
  capability:
    consumes:
    - namespace: microcks
      type: http
      baseUri: https://api.microcks.com
      authentication:
        type: bearer
        token: '{{MICROCKS_API_KEY}}'
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
      namespace: asyncapi-mocked-event-stream-capability-rest
      description: REST API for Microcks Asyncapi Mocked Event Stream Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microcks.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: asyncapi-mocked-event-stream-capability-mcp
      description: MCP server exposing Microcks Asyncapi Mocked Event Stream Capability for AI agents.
      tools:
      - name: example
        description: A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
        hints:
          readOnly: true
        call: microcks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: asyncapi-mocked-event-stream-capability-skills
      description: Agent Skill bundle for Microcks Asyncapi Mocked Event Stream Capability.
      skills:
      - name: asyncapi-mocked-event-stream-capability
        description: A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
        location: file:///opt/naftiko/skills/asyncapi-mocked-event-stream-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact.
          from:
            sourceNamespace: asyncapi-mocked-event-stream-capability-mcp
            action: example
---

A capability where Microcks mocks an AsyncAPI-described event stream and the same YAML drives the Naftiko engine's consume side, joining capability + event-driven mocking on one artifact. AsyncAPI is Microcks's growth surface; demonstrating Naftiko's event-driven layer over Microcks AsyncAPI mocks is partnership-deepening.
