---
categories: []
consumed_apis:
- procter-gamble
description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
layout: capability
naftiko_layer: proposed
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Enterprise Integration Context Composition
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- compose
- context
- capability
- stitching
- marketing
slug: pg-enterprise-integration-context-composition
source_filename: pg-enterprise-integration-context-composition.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Enterprise Integration Context Composition
    description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
    tags:
    - Procter & Gamble
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: procter-gamble-env
    description: Procter & Gamble credentials.
    keys:
      PROCTER_GAMBLE_API_KEY: PROCTER_GAMBLE_API_KEY
  capability:
    consumes:
    - namespace: procter-gamble
      type: http
      baseUri: https://api.procter-gamble.com
      authentication:
        type: bearer
        token: '{{PROCTER_GAMBLE_API_KEY}}'
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
      namespace: pg-enterprise-integration-context-composition-rest
      description: REST API for Procter & Gamble Pg Enterprise Integration Context Composition.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: procter-gamble.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: pg-enterprise-integration-context-composition-mcp
      description: MCP server exposing Procter & Gamble Pg Enterprise Integration Context Composition for AI agents.
      tools:
      - name: example
        description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-enterprise-integration-context-composition-skills
      description: Agent Skill bundle for Procter & Gamble Pg Enterprise Integration Context Composition.
      skills:
      - name: pg-enterprise-integration-context-composition
        description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
        location: file:///opt/naftiko/skills/pg-enterprise-integration-context-composition
        allowed-tools: example
        tools:
        - name: example
          description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
          from:
            sourceNamespace: pg-enterprise-integration-context-composition-mcp
            action: example
---

Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl. His title IS the persona; build something that visibly addresses enterprise-integration sprawl before nudging again.
