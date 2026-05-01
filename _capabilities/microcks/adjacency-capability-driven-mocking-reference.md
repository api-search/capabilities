---
categories: []
consumed_apis:
- microcks
description: A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
layout: capability
naftiko_layer: proposed
naftiko_partner: Laurent Broudoux
name: Microcks Adjacency Capability Driven Mocking Reference
operations: []
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- reference
- capability
- exercising
- driven
- mocking
slug: adjacency-capability-driven-mocking-reference
source_filename: adjacency-capability-driven-mocking-reference.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microcks Adjacency Capability Driven Mocking Reference
    description: A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
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
      namespace: adjacency-capability-driven-mocking-reference-rest
      description: REST API for Microcks Adjacency Capability Driven Mocking Reference.
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
      namespace: adjacency-capability-driven-mocking-reference-mcp
      description: MCP server exposing Microcks Adjacency Capability Driven Mocking Reference for AI agents.
      tools:
      - name: example
        description: A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
        hints:
          readOnly: true
        call: microcks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: adjacency-capability-driven-mocking-reference-skills
      description: Agent Skill bundle for Microcks Adjacency Capability Driven Mocking Reference.
      skills:
      - name: adjacency-capability-driven-mocking-reference
        description: A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
        location: file:///opt/naftiko/skills/adjacency-capability-driven-mocking-reference
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
          from:
            sourceNamespace: adjacency-capability-driven-mocking-reference-mcp
            action: example
---

A reference capability exercising capability-driven mocking against capability specs (Microcks) plus runtime execution (Naftiko) — explicit partnership-boundary artifact. His "unsure about the future" question deserves a clean answer; this framing keeps both products distinct.
