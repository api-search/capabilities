---
categories: []
consumed_apis:
- port-of-context
description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
layout: capability
naftiko_layer: proposed
naftiko_partner: Patrick Kelly
name: Port of Context Mcp First Context Engineering Capability
operations: []
personas: []
provider_name: Port of Context
provider_slug: port-of-context
search_terms:
- capability
- implementing
- first
- context
- engineering
slug: mcp-first-context-engineering-capability
source_filename: mcp-first-context-engineering-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Port of Context Mcp First Context Engineering Capability
    description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
    tags:
    - Port of Context
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: port-of-context-env
    description: Port of Context credentials.
    keys:
      PORT_OF_CONTEXT_API_KEY: PORT_OF_CONTEXT_API_KEY
  capability:
    consumes:
    - namespace: port-of-context
      type: http
      baseUri: https://api.port-of-context.com
      authentication:
        type: bearer
        token: '{{PORT_OF_CONTEXT_API_KEY}}'
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
      namespace: mcp-first-context-engineering-capability-rest
      description: REST API for Port of Context Mcp First Context Engineering Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: port-of-context.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: mcp-first-context-engineering-capability-mcp
      description: MCP server exposing Port of Context Mcp First Context Engineering Capability for AI agents.
      tools:
      - name: example
        description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
        hints:
          readOnly: true
        call: port-of-context.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: mcp-first-context-engineering-capability-skills
      description: Agent Skill bundle for Port of Context Mcp First Context Engineering Capability.
      skills:
      - name: mcp-first-context-engineering-capability
        description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
        location: file:///opt/naftiko/skills/mcp-first-context-engineering-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
          from:
            sourceNamespace: mcp-first-context-engineering-capability-mcp
            action: example
---

A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs. Port of Context's name and his MCP-level synergy align with use case #8 1:1.
