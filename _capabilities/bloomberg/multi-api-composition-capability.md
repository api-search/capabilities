---
categories: []
consumed_apis:
- bloomberg
description: A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
layout: capability
naftiko_layer: proposed
naftiko_partner: Brendan Burgess
name: Bloomberg Multi Api Composition Capability
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
slug: multi-api-composition-capability
source_filename: multi-api-composition-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Bloomberg Multi Api Composition Capability
    description: A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
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
      namespace: multi-api-composition-capability-rest
      description: REST API for Bloomberg Multi Api Composition Capability.
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
      namespace: multi-api-composition-capability-mcp
      description: MCP server exposing Bloomberg Multi Api Composition Capability for AI agents.
      tools:
      - name: example
        description: A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
        hints:
          readOnly: true
        call: bloomberg.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: multi-api-composition-capability-skills
      description: Agent Skill bundle for Bloomberg Multi Api Composition Capability.
      skills:
      - name: multi-api-composition-capability
        description: A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
        location: file:///opt/naftiko/skills/multi-api-composition-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
          from:
            sourceNamespace: multi-api-composition-capability-mcp
            action: example
---

A Capability Composition demo where multiple Bloomberg-internal APIs become one consumable capability — the de-dup story for a Team Lead persona. Team Lead role = sees daily duplication across services; Capability Composition is the de-dup story.
