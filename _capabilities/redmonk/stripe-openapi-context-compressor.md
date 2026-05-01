---
categories: []
consumed_apis:
- redmonk
description: A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window."
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Kate Holterhoff
name: Redmonk Stripe Openapi Context Compressor
operations: []
personas: []
provider_name: Redmonk
provider_slug: redmonk
search_terms:
- capability
- that
- ingests
- full
- stripe
slug: stripe-openapi-context-compressor
source_filename: stripe-openapi-context-compressor.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Redmonk Stripe Openapi Context Compressor
    description: A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window."
    tags:
    - Redmonk
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: redmonk-env
    description: Redmonk credentials.
    keys:
      REDMONK_API_KEY: REDMONK_API_KEY
  capability:
    consumes:
    - namespace: redmonk
      type: http
      baseUri: https://api.redmonk.com
      authentication:
        type: bearer
        token: '{{REDMONK_API_KEY}}'
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
      namespace: stripe-openapi-context-compressor-rest
      description: REST API for Redmonk Stripe Openapi Context Compressor.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: redmonk.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: stripe-openapi-context-compressor-mcp
      description: MCP server exposing Redmonk Stripe Openapi Context Compressor for AI agents.
      tools:
      - name: example
        description: A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window."
        hints:
          readOnly: true
        call: redmonk.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stripe-openapi-context-compressor-skills
      description: Agent Skill bundle for Redmonk Stripe Openapi Context Compressor.
      skills:
      - name: stripe-openapi-context-compressor
        description: A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window."
        location: file:///opt/naftiko/skills/stripe-openapi-context-compressor
        allowed-tools: example
        tools:
        - name: example
          description: A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window."
          from:
            sourceNamespace: stripe-openapi-context-compressor-mcp
            action: example
---

A capability that ingests the full Stripe OpenAPI and exposes a per-task compressed slice as MCP — the Kate-quotable artifact behind "feed Stripe's OpenAPI to Claude and reduce the context window." The "compress Stripe's OpenAPI" beat is the most clippable part of her own episode — make it runnable.
