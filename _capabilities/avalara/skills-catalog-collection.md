---
categories: []
consumed_apis:
- avalara
description: A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally.
layout: capability
naftiko_layer: proposed
naftiko_partner: Joshua McMillen
name: Avalara Skills Catalog Collection
operations: []
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- multi
- capability
- collection
- where
- each
slug: skills-catalog-collection
source_filename: skills-catalog-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Avalara Skills Catalog Collection
    description: A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally.
    tags:
    - Avalara
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: avalara-env
    description: Avalara credentials.
    keys:
      AVALARA_API_KEY: AVALARA_API_KEY
  capability:
    consumes:
    - namespace: avalara
      type: http
      baseUri: https://api.avalara.com
      authentication:
        type: bearer
        token: '{{AVALARA_API_KEY}}'
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
      namespace: skills-catalog-collection-rest
      description: REST API for Avalara Skills Catalog Collection.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: avalara.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: skills-catalog-collection-mcp
      description: MCP server exposing Avalara Skills Catalog Collection for AI agents.
      tools:
      - name: example
        description: A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally.
        hints:
          readOnly: true
        call: avalara.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: skills-catalog-collection-skills
      description: Agent Skill bundle for Avalara Skills Catalog Collection.
      skills:
      - name: skills-catalog-collection
        description: A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally.
        location: file:///opt/naftiko/skills/skills-catalog-collection
        allowed-tools: example
        tools:
        - name: example
          description: A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally.
          from:
            sourceNamespace: skills-catalog-collection-mcp
            action: example
---

A multi-capability collection where each Avalara API becomes a downloadable Agent Skill, packaged as a catalog the AI-lead role can ship internally. His new role manages packaged-skills delivery; a catalog is the artifact that fits.
