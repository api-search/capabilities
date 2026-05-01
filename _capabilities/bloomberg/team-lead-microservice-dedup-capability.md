---
categories: []
consumed_apis:
- bloomberg
description: A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Brendan Burgess
name: Bloomberg Team Lead Microservice Dedup Capability
operations: []
personas: []
provider_name: Bloomberg
provider_slug: bloomberg
search_terms:
- capability
- composition
- demo
- where
- multiple
slug: team-lead-microservice-dedup-capability
source_filename: team-lead-microservice-dedup-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Team Lead Microservice Dedup Capability
    description: A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona.
    tags:
    - Bloomberg
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: bloomberg-env
    description: Bloomberg credentials.
    keys:
      BLOOMBERG_API_KEY: BLOOMBERG_API_KEY
  capability:
    consumes:
    - namespace: bloomberg
      type: http
      baseUri: https://api.bloomberg.com
      authentication:
        type: bearer
        token: '{{BLOOMBERG_API_KEY}}'
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
      namespace: team-lead-microservice-dedup-capability-rest
      description: REST API for Bloomberg Team Lead Microservice Dedup Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: bloomberg.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: team-lead-microservice-dedup-capability-mcp
      description: MCP server exposing Bloomberg Team Lead Microservice Dedup Capability for AI agents.
      tools:
      - name: example
        description: A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: team-lead-microservice-dedup-capability-skills
      description: Agent Skill bundle for Bloomberg Team Lead Microservice Dedup Capability.
      skills:
      - name: team-lead-microservice-dedup-capability
        description: A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona.
        location: file:///opt/naftiko/skills/team-lead-microservice-dedup-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona.
          from:
            sourceNamespace: team-lead-microservice-dedup-capability-mcp
            action: example
---

A Capability Composition demo where multiple internal Bloomberg services are reduced to one consumable capability — the de-dup pattern for a Team Lead persona. Team Leads see daily duplication; Capability Composition is the de-dup story he can repeat at the booth.
