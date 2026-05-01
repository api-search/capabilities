---
categories: []
consumed_apis:
- adorsys
description: Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
layout: capability
naftiko_layer: proposed
naftiko_partner: Daniel Kocot
name: Adorsys Api As Digital Product Collection
operations: []
personas: []
provider_name: Adorsys
provider_slug: adorsys
search_terms:
- composable
- capability
- collection
- that
- wraps
slug: api-as-digital-product-collection
source_filename: api-as-digital-product-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Adorsys Api As Digital Product Collection
    description: Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
    tags:
    - Adorsys
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: adorsys-env
    description: Adorsys credentials.
    keys:
      ADORSYS_API_KEY: ADORSYS_API_KEY
  capability:
    consumes:
    - namespace: adorsys
      type: http
      baseUri: https://api.adorsys.com
      authentication:
        type: bearer
        token: '{{ADORSYS_API_KEY}}'
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
      namespace: api-as-digital-product-collection-rest
      description: REST API for Adorsys Api As Digital Product Collection.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: adorsys.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: api-as-digital-product-collection-mcp
      description: MCP server exposing Adorsys Api As Digital Product Collection for AI agents.
      tools:
      - name: example
        description: Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
        hints:
          readOnly: true
        call: adorsys.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: api-as-digital-product-collection-skills
      description: Agent Skill bundle for Adorsys Api As Digital Product Collection.
      skills:
      - name: api-as-digital-product-collection
        description: Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
        location: file:///opt/naftiko/skills/api-as-digital-product-collection
        allowed-tools: example
        tools:
        - name: example
          description: Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance.
          from:
            sourceNamespace: api-as-digital-product-collection-mcp
            action: example
---

Composable capability collection that wraps a representative Adorsys client API as a "digital product," with multiple `consumes` operations stitched into one externally-shaped capability and governance tags carrying provenance. His "APIs as Digital Products" thesis maps 1:1 to capability-as-business-context; gives both brands a co-brandable artifact for apidays Munich.
