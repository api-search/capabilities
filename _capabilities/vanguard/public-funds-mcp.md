---
categories: []
consumed_apis:
- vanguard
description: A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vanguard
name: Vanguard Public Funds Mcp
operations: []
personas: []
provider_name: Vanguard
provider_slug: vanguard
search_terms:
- vanguard
- shaped
- capability
- wrapping
- public
slug: public-funds-mcp
source_filename: public-funds-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vanguard Public Funds Mcp
    description: A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts.
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
      namespace: public-funds-mcp-rest
      description: REST API for Vanguard Public Funds Mcp.
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
      namespace: public-funds-mcp-mcp
      description: MCP server exposing Vanguard Public Funds Mcp for AI agents.
      tools:
      - name: example
        description: A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts.
        hints:
          readOnly: true
        call: vanguard.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: public-funds-mcp-skills
      description: Agent Skill bundle for Vanguard Public Funds Mcp.
      skills:
      - name: public-funds-mcp
        description: A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts.
        location: file:///opt/naftiko/skills/public-funds-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts.
          from:
            sourceNamespace: public-funds-mcp-mcp
            action: example
---

A Vanguard-shaped capability wrapping a Vanguard-public funds / charitable API, exposed REST + MCP, layered with event-driven adapters when alpha2 lands. The single shared prototype walked through with all four contacts. Targets Vanguard's signaled api/eventDriven/dataPipelines gap with the canonical capability-as-bridge artifact. Owned by **Andrea Sugano** for the email-led 30-min walkthrough, supported by **Sesha Raman** so both Vanguard contacts hear a consistent message.
