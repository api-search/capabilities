---
categories: []
consumed_apis:
- ford
description: A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: John Musser
name: Ford Microsoft Agent 365 Identity Bridge
operations: []
personas: []
provider_name: Ford
provider_slug: ford
search_terms:
- capability
- that
- consumes
- microsoft
- agent
slug: microsoft-agent-365-identity-bridge
source_filename: microsoft-agent-365-identity-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Ford Microsoft Agent 365 Identity Bridge
    description: A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls.
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
      namespace: microsoft-agent-365-identity-bridge-rest
      description: REST API for Ford Microsoft Agent 365 Identity Bridge.
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
      namespace: microsoft-agent-365-identity-bridge-mcp
      description: MCP server exposing Ford Microsoft Agent 365 Identity Bridge for AI agents.
      tools:
      - name: example
        description: A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls.
        hints:
          readOnly: true
        call: ford.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: microsoft-agent-365-identity-bridge-skills
      description: Agent Skill bundle for Ford Microsoft Agent 365 Identity Bridge.
      skills:
      - name: microsoft-agent-365-identity-bridge
        description: A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls.
        location: file:///opt/naftiko/skills/microsoft-agent-365-identity-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls.
          from:
            sourceNamespace: microsoft-agent-365-identity-bridge-mcp
            action: example
---

A capability that consumes Microsoft Agent 365 identity claims and signs them into Ford's existing API governance layer, producing a per-call audit record for agent calls. He named agent identity as the unsolved problem and named Microsoft Agent 365 as the chosen substrate — build on that exact stack.
