---
categories: []
consumed_apis:
- microcks
description: A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1.
layout: capability
naftiko_layer: proposed
naftiko_partner: Laurent Broudoux
name: Microcks Wiki Companion Capability
operations: []
personas: []
provider_name: Microcks
provider_slug: microcks
search_terms:
- capability
- used
- running
- example
- microcks
slug: wiki-companion-capability
source_filename: wiki-companion-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microcks Wiki Companion Capability
    description: A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1.
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
      namespace: wiki-companion-capability-rest
      description: REST API for Microcks Wiki Companion Capability.
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
      namespace: wiki-companion-capability-mcp
      description: MCP server exposing Microcks Wiki Companion Capability for AI agents.
      tools:
      - name: example
        description: A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1.
        hints:
          readOnly: true
        call: microcks.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: wiki-companion-capability-skills
      description: Agent Skill bundle for Microcks Wiki Companion Capability.
      skills:
      - name: wiki-companion-capability
        description: A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1.
        location: file:///opt/naftiko/skills/wiki-companion-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1.
          from:
            sourceNamespace: wiki-companion-capability-mcp
            action: example
---

A capability used as the running example in a new Microcks integration page in the framework wiki, alongside Guide-Linting and Tutorial-Part-1. Documenting the adjacency in the canonical wiki resolves the "future of the partnership" question structurally.
