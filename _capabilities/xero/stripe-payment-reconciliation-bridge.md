---
categories: []
consumed_apis:
- xero
description: A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Rose Missier
name: Xero Stripe Payment Reconciliation Bridge
operations: []
personas: []
provider_name: Xero
provider_slug: xero
search_terms:
- capability
- that
- reconciles
- stripe
- payment
slug: stripe-payment-reconciliation-bridge
source_filename: stripe-payment-reconciliation-bridge.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Xero Stripe Payment Reconciliation Bridge
    description: A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant.
    tags:
    - Xero
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: xero-env
    description: Xero credentials.
    keys:
      XERO_API_KEY: XERO_API_KEY
  capability:
    consumes:
    - namespace: xero
      type: http
      baseUri: https://api.xero.com
      authentication:
        type: bearer
        token: '{{XERO_API_KEY}}'
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
      namespace: stripe-payment-reconciliation-bridge-rest
      description: REST API for Xero Stripe Payment Reconciliation Bridge.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: xero.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: stripe-payment-reconciliation-bridge-mcp
      description: MCP server exposing Xero Stripe Payment Reconciliation Bridge for AI agents.
      tools:
      - name: example
        description: A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant.
        hints:
          readOnly: true
        call: xero.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: stripe-payment-reconciliation-bridge-skills
      description: Agent Skill bundle for Xero Stripe Payment Reconciliation Bridge.
      skills:
      - name: stripe-payment-reconciliation-bridge
        description: A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant.
        location: file:///opt/naftiko/skills/stripe-payment-reconciliation-bridge
        allowed-tools: example
        tools:
        - name: example
          description: A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant.
          from:
            sourceNamespace: stripe-payment-reconciliation-bridge-mcp
            action: example
---

A capability that reconciles a Stripe payment to a Xero invoice and returns a shaped context object for a finance AI assistant. Xero PMs see Stripe-reconciliation pain daily; making it agent-callable is the highest-recognition Xero demo.
