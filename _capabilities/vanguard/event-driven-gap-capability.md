---
categories: []
consumed_apis:
- vanguard
description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vanguard
name: Vanguard Event Driven Gap Capability
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- capability
- that
- explicitly
- bridges
- eventdriven
slug: event-driven-gap-capability
source_filename: event-driven-gap-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Event Driven Gap Capability
    description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
    tags:
    - Vanguard
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vanguard-env
    description: Vanguard credentials.
    keys:
      VANGUARD_API_KEY: VANGUARD_API_KEY
  capability:
    consumes:
    - namespace: vanguard
      type: http
      baseUri: https://api.vanguard.com
      authentication:
        type: bearer
        token: '{{VANGUARD_API_KEY}}'
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
      namespace: event-driven-gap-capability-rest
      description: REST API for Vanguard Event Driven Gap Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vanguard.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: event-driven-gap-capability-mcp
      description: MCP server exposing Vanguard Event Driven Gap Capability for AI agents.
      tools:
      - name: example
        description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: event-driven-gap-capability-skills
      description: Agent Skill bundle for Vanguard Event Driven Gap Capability.
      skills:
      - name: event-driven-gap-capability
        description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
        location: file:///opt/naftiko/skills/event-driven-gap-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on.
          from:
            sourceNamespace: event-driven-gap-capability-mcp
            action: example
---

A capability that explicitly bridges the api/eventDriven/dataPipelines gap surfaced in Vanguard's Signals — wraps an existing Vanguard-shaped REST API and exposes both REST + MCP with event-driven adapters layered on. The gap is exactly what Vanguard's published Signals story describes; this is the diagnosis-plus-prescription artifact for any of the four contacts. Useful for **Sesha Raman** as the role-agnostic shared message until role is captured.
