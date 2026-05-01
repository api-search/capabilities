---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Developer Portal Public Market Data Mcp
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- wrapping
- public
- jpmc
- developer
slug: jpmc-developer-portal-public-market-data-mcp
source_filename: jpmc-developer-portal-public-market-data-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Developer Portal Public Market Data Mcp
    description: A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
    tags:
    - JPMorgan Chase
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: jpmorgan-chase-env
    description: JPMorgan Chase credentials.
    keys:
      JPMORGAN_CHASE_API_KEY: JPMORGAN_CHASE_API_KEY
  capability:
    consumes:
    - namespace: jpmorgan-chase
      type: http
      baseUri: https://api.jpmorgan-chase.com
      authentication:
        type: bearer
        token: '{{JPMORGAN_CHASE_API_KEY}}'
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
      namespace: jpmc-developer-portal-public-market-data-mcp-rest
      description: REST API for JPMorgan Chase Jpmc Developer Portal Public Market Data Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: jpmorgan-chase.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: jpmc-developer-portal-public-market-data-mcp-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Developer Portal Public Market Data Mcp for AI agents.
      tools:
      - name: example
        description: A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-developer-portal-public-market-data-mcp-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Developer Portal Public Market Data Mcp.
      skills:
      - name: jpmc-developer-portal-public-market-data-mcp
        description: A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
        location: file:///opt/naftiko/skills/jpmc-developer-portal-public-market-data-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
          from:
            sourceNamespace: jpmc-developer-portal-public-market-data-mcp-mcp
            action: example
---

A capability wrapping a public JPMC developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance. His stalled thread reopens on built artifacts, not re-sent decks — show one against JPMC's actual public surface plus a public macro source.
