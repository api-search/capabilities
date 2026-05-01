---
categories: []
consumed_apis:
- procter-gamble
description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
layout: capability
naftiko_layer: proposed
naftiko_partner: Norbert Anthony
name: Procter & Gamble Pg Backstage Scaffolding Standard
operations: []
personas: []
provider_name: Procter & Gamble
provider_slug: procter-gamble
search_terms:
- capability
- scaffolded
- from
- backstage
- template
slug: pg-backstage-scaffolding-standard
source_filename: pg-backstage-scaffolding-standard.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Procter & Gamble Pg Backstage Scaffolding Standard
    description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
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
      namespace: pg-backstage-scaffolding-standard-rest
      description: REST API for Procter & Gamble Pg Backstage Scaffolding Standard.
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
      namespace: pg-backstage-scaffolding-standard-mcp
      description: MCP server exposing Procter & Gamble Pg Backstage Scaffolding Standard for AI agents.
      tools:
      - name: example
        description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
        hints:
          readOnly: true
        call: procter-gamble.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: pg-backstage-scaffolding-standard-skills
      description: Agent Skill bundle for Procter & Gamble Pg Backstage Scaffolding Standard.
      skills:
      - name: pg-backstage-scaffolding-standard
        description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
        location: file:///opt/naftiko/skills/pg-backstage-scaffolding-standard
        allowed-tools: example
        tools:
        - name: example
          description: A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate."
          from:
            sourceNamespace: pg-backstage-scaffolding-standard-mcp
            action: example
---

A capability scaffolded from a Backstage template, intended as the "scaffolding standard a P&G enterprise-integration org could mandate." Backstage is the catalog of choice for that org type; scaffolding standardization is what the role buys.
