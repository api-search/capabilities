---
categories: []
consumed_apis:
- jpmorgan-chase
description: 'Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape."'
layout: capability
naftiko_layer: proposed
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Public Market Data Capability
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- wraps
- public
- market
- data
- fred
slug: jpmc-public-market-data-capability
source_filename: jpmc-public-market-data-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Public Market Data Capability
    description: 'Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape."'
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
      namespace: jpmc-public-market-data-capability-rest
      description: REST API for JPMorgan Chase Jpmc Public Market Data Capability.
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
      namespace: jpmc-public-market-data-capability-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Public Market Data Capability for AI agents.
      tools:
      - name: example
        description: 'Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape."'
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-public-market-data-capability-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Public Market Data Capability.
      skills:
      - name: jpmc-public-market-data-capability
        description: 'Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape."'
        location: file:///opt/naftiko/skills/jpmc-public-market-data-capability
        allowed-tools: example
        tools:
        - name: example
          description: 'Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape."'
          from:
            sourceNamespace: jpmc-public-market-data-capability-mcp
            action: example
---

Wraps a public market-data API (e.g., FRED, Alpha Vantage) as a JPMC-shaped reference, sent as the nudge artifact: "we built this against your apparent shape." Stalled threads reopen on built artifacts, not re-sent decks.
