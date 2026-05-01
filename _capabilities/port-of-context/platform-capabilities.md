---
categories: []
consumed_apis:
- port-of-context
description: A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through.
layout: capability
naftiko_layer: proposed
naftiko_partner: Patrick Kelly
name: Port of Context Platform Capabilities
operations: []
personas: []
provider_name: Port of Context
provider_slug: port-of-context
search_terms:
- full
- naftiko
- capabilities
- port
- context
slug: platform-capabilities
source_filename: platform-capabilities.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Port of Context Platform Capabilities
    description: A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through.
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
      namespace: platform-capabilities-rest
      description: REST API for Port of Context Platform Capabilities.
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
      namespace: platform-capabilities-mcp
      description: MCP server exposing Port of Context Platform Capabilities for AI agents.
      tools:
      - name: example
        description: A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through.
        hints:
          readOnly: true
        call: port-of-context.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: platform-capabilities-skills
      description: Agent Skill bundle for Port of Context Platform Capabilities.
      skills:
      - name: platform-capabilities
        description: A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through.
        location: file:///opt/naftiko/skills/platform-capabilities
        allowed-tools: example
        tools:
        - name: example
          description: A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through.
          from:
            sourceNamespace: platform-capabilities-mcp
            action: example
---

A full set of Naftiko capabilities for Port of Context's platform, generated via the generate-partner-capabilities pattern — one capability per OpenAPI operation with MCP pass-through. His next-step is literally "generate capabilities for their platform" — this is the deliverable.
