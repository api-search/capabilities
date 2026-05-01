---
categories: []
consumed_apis:
- avalara
description: A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joshua McMillen
name: Avalara Stripe Payments Tax Context Bridge
operations: []
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- capability
- that
- joins
- stripe
- payment
slug: stripe-payments-tax-context-bridge
source_filename: stripe-payments-tax-context-bridge.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Avalara Stripe Payments Tax Context Bridge
    description: A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant.
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
      namespace: stripe-payments-tax-context-bridge-rest
      description: REST API for Avalara Stripe Payments Tax Context Bridge.
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
      namespace: stripe-payments-tax-context-bridge-mcp
      description: MCP server exposing Avalara Stripe Payments Tax Context Bridge for AI agents.
      tools:
      - name: example
        description: A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant.
        hints:
          readOnly: true
        call: avalara.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stripe-payments-tax-context-bridge-skills
      description: Agent Skill bundle for Avalara Stripe Payments Tax Context Bridge.
      skills:
      - name: stripe-payments-tax-context-bridge
        description: A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant.
        location: file:///opt/naftiko/skills/stripe-payments-tax-context-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant.
          from:
            sourceNamespace: stripe-payments-tax-context-bridge-mcp
            action: example
---

A capability that joins a Stripe payment event to an AvaTax calc + Avalara Returns lookup and returns one shaped context object for the AI tax assistant. Compose AI Context is exactly his recommendations' use case #5 — Stripe→AvaTax is the most-recognized version of it.
