---
categories: []
consumed_apis:
- ford
description: Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection.
layout: capability
naftiko_layer: proposed
naftiko_partner: John Musser
name: Ford Vehicle Telemetry Mcp
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- wraps
- ford
- shaped
- vehicle
- telemetry
slug: vehicle-telemetry-mcp
source_filename: vehicle-telemetry-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Vehicle Telemetry Mcp
    description: Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection.
    tags:
    - Ford
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: ford-env
    description: Ford credentials.
    keys:
      FORD_API_KEY: FORD_API_KEY
  capability:
    consumes:
    - namespace: ford
      type: http
      baseUri: https://api.ford.com
      authentication:
        type: bearer
        token: '{{FORD_API_KEY}}'
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
      namespace: vehicle-telemetry-mcp-rest
      description: REST API for Ford Vehicle Telemetry Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: ford.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: vehicle-telemetry-mcp-mcp
      description: MCP server exposing Ford Vehicle Telemetry Mcp for AI agents.
      tools:
      - name: example
        description: Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: vehicle-telemetry-mcp-skills
      description: Agent Skill bundle for Ford Vehicle Telemetry Mcp.
      skills:
      - name: vehicle-telemetry-mcp
        description: Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection.
        location: file:///opt/naftiko/skills/vehicle-telemetry-mcp
        allowed-tools: example
        tools:
        - name: example
          description: Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection.
          from:
            sourceNamespace: vehicle-telemetry-mcp-mcp
            action: example
---

Wraps a Ford-shaped vehicle telemetry API as MCP tools an AI assistant can call directly — the entry point in a Compose AI Context (#5) collection. His proposal needs Compose AI context across vehicle/dealer/customer APIs — telemetry is the anchor surface.
