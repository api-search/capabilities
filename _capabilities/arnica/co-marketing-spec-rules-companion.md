---
categories: []
consumed_apis:
- arnica
description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
layout: capability
naftiko_layer: proposed
naftiko_partner: Anna Daugherty
name: Arnica Co Marketing Spec Rules Companion
operations: []
personas: []
provider_name: Arnica
provider_slug: arnica
search_terms:
- reference
- capability
- tied
- authored
- guide
slug: co-marketing-spec-rules-companion
source_filename: co-marketing-spec-rules-companion.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Arnica Co Marketing Spec Rules Companion
    description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
    tags:
    - Arnica
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: arnica-env
    description: Arnica credentials.
    keys:
      ARNICA_API_KEY: ARNICA_API_KEY
  capability:
    consumes:
    - namespace: arnica
      type: http
      baseUri: https://api.arnica.com
      authentication:
        type: bearer
        token: '{{ARNICA_API_KEY}}'
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
      namespace: co-marketing-spec-rules-companion-rest
      description: REST API for Arnica Co Marketing Spec Rules Companion.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: arnica.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: co-marketing-spec-rules-companion-mcp
      description: MCP server exposing Arnica Co Marketing Spec Rules Companion for AI agents.
      tools:
      - name: example
        description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
        hints:
          readOnly: true
        call: arnica.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: co-marketing-spec-rules-companion-skills
      description: Agent Skill bundle for Arnica Co Marketing Spec Rules Companion.
      skills:
      - name: co-marketing-spec-rules-companion
        description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
        location: file:///opt/naftiko/skills/co-marketing-spec-rules-companion
        allowed-tools: example
        tools:
        - name: example
          description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
          from:
            sourceNamespace: co-marketing-spec-rules-companion-mcp
            action: example
---

A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role. She leads PMM for DevEx, AI and Developer Tools; a co-authored guide is the format that fits her role.
