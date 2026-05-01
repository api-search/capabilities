---
categories: []
consumed_apis:
- jpmorgan-chase
description: A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Mark McAllister
name: JPMorgan Chase Jpmc Bloomberg Tradeweb Cross Source Deterministic Bridge
operations: []
personas: []
provider_name: JPMorgan Chase
provider_slug: jpmorgan-chase
search_terms:
- capability
- that
- joins
- jpmc
- market
slug: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge
source_filename: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: JPMorgan Chase Jpmc Bloomberg Tradeweb Cross Source Deterministic Bridge
    description: A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
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
      namespace: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge-rest
      description: REST API for JPMorgan Chase Jpmc Bloomberg Tradeweb Cross Source Deterministic Bridge.
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
      namespace: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge-mcp
      description: MCP server exposing JPMorgan Chase Jpmc Bloomberg Tradeweb Cross Source Deterministic Bridge for AI agents.
      tools:
      - name: example
        description: A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
        hints:
          readOnly: true
        call: jpmorgan-chase.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge-skills
      description: Agent Skill bundle for JPMorgan Chase Jpmc Bloomberg Tradeweb Cross Source Deterministic Bridge.
      skills:
      - name: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge
        description: A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
        location: file:///opt/naftiko/skills/jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer.
          from:
            sourceNamespace: jpmc-bloomberg-tradeweb-cross-source-deterministic-bridge-mcp
            action: example
---

A capability that joins a JPMC market-data shape with Bloomberg + Tradeweb sample inputs and returns a deterministic, schema-strict output for an AI risk reviewer. AI risk officers at JPMC care about deterministic agent behavior; Bloomberg + Tradeweb are the credible market-data surfaces the persona reads.
