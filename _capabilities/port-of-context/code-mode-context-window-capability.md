---
categories: []
consumed_apis:
- port-of-context
description: 'A capability that exposes Port of Context''s "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Patrick Kelly
name: Port of Context Code Mode Context Window Capability
operations: []
personas: []
provider_name: Port of Context
provider_slug: port-of-context
search_terms:
- capability
- that
- exposes
- port
- context
slug: code-mode-context-window-capability
source_filename: code-mode-context-window-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Port of Context Code Mode Context Window Capability
    description: 'A capability that exposes Port of Context''s "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
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
      namespace: code-mode-context-window-capability-rest
      description: REST API for Port of Context Code Mode Context Window Capability.
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
      namespace: code-mode-context-window-capability-mcp
      description: MCP server exposing Port of Context Code Mode Context Window Capability for AI agents.
      tools:
      - name: example
        description: 'A capability that exposes Port of Context''s "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
        hints:
          readOnly: true
        call: port-of-context.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: code-mode-context-window-capability-skills
      description: Agent Skill bundle for Port of Context Code Mode Context Window Capability.
      skills:
      - name: code-mode-context-window-capability
        description: 'A capability that exposes Port of Context''s "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
        location: file:///opt/naftiko/skills/code-mode-context-window-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'A capability that exposes Port of Context''s "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
          from:
            sourceNamespace: code-mode-context-window-capability-mcp
            action: example
---

A capability that exposes Port of Context's "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context. Code mode IS his named technique; turning it into a runnable Naftiko capability cross-promotes both products at the MCP layer.
