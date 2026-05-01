---
categories: []
consumed_apis:
- schneider-electric
description: A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet.
layout: capability
naftiko_layer: proposed
naftiko_partner: Manu PK
name: Schneider Electric Schneider Registry Seed Collection
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- starter
- capability
- collection
- wrapping
- representative
slug: schneider-registry-seed-collection
source_filename: schneider-registry-seed-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Registry Seed Collection
    description: A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-registry-seed-collection-rest
      description: REST API for Schneider Electric Schneider Registry Seed Collection.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-registry-seed-collection-mcp
      description: MCP server exposing Schneider Electric Schneider Registry Seed Collection for AI agents.
      tools:
      - name: example
        description: A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-registry-seed-collection-skills
      description: Agent Skill bundle for Schneider Electric Schneider Registry Seed Collection.
      skills:
      - name: schneider-registry-seed-collection
        description: A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet.
        location: file:///opt/naftiko/skills/schneider-registry-seed-collection
        allowed-tools: example
        tools:
        - name: example
          description: A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet.
          from:
            sourceNamespace: schneider-registry-seed-collection-mcp
            action: example
---

A starter capability collection wrapping representative Schneider internal APIs as MCP tools, populating the registry-of-capabilities as a seeded fleet. His ask is registry-across-thousands-of-services; this is the seed.
