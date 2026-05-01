---
categories: []
consumed_apis:
- tyk
description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Budhaditya (Budha) Bhattacharya
name: Tyk Overlays Governance Rule Merger Capability
operations: []
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- capability
- that
- consumes
- base
- openapi
slug: overlays-governance-rule-merger-capability
source_filename: overlays-governance-rule-merger-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Tyk Overlays Governance Rule Merger Capability
    description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream.
    tags:
    - Tyk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: tyk-env
    description: Tyk credentials.
    keys:
      TYK_API_KEY: TYK_API_KEY
  capability:
    consumes:
    - namespace: tyk
      type: http
      baseUri: https://api.tyk.com
      authentication:
        type: bearer
        token: '{{TYK_API_KEY}}'
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
      namespace: overlays-governance-rule-merger-capability-rest
      description: REST API for Tyk Overlays Governance Rule Merger Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: tyk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: overlays-governance-rule-merger-capability-mcp
      description: MCP server exposing Tyk Overlays Governance Rule Merger Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream.
        hints:
          readOnly: true
        call: tyk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: overlays-governance-rule-merger-capability-skills
      description: Agent Skill bundle for Tyk Overlays Governance Rule Merger Capability.
      skills:
      - name: overlays-governance-rule-merger-capability
        description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream.
        location: file:///opt/naftiko/skills/overlays-governance-rule-merger-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream.
          from:
            sourceNamespace: overlays-governance-rule-merger-capability-mcp
            action: example
---

A capability that consumes a base OpenAPI doc + a set of OpenAPI Overlays and exposes a merged governance-rules-applied OpenAPI to a Tyk-fronted upstream. Overlays is exactly his OpenAPI-Initiative-chair territory; making them runtime-applicable through Tyk is the joint narrative deepening.
