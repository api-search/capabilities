---
categories: []
consumed_apis:
- xero
description: A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Rose Missier
name: Xero Invoices Bank Feeds Compose Context Capability
operations: []
personas: []
provider_name: Xero
provider_slug: xero
search_terms:
- composite
- capability
- over
- xero
- invoices
slug: invoices-bank-feeds-compose-context-capability
source_filename: invoices-bank-feeds-compose-context-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Xero Invoices Bank Feeds Compose Context Capability
    description: A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
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
      namespace: invoices-bank-feeds-compose-context-capability-rest
      description: REST API for Xero Invoices Bank Feeds Compose Context Capability.
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
      namespace: invoices-bank-feeds-compose-context-capability-mcp
      description: MCP server exposing Xero Invoices Bank Feeds Compose Context Capability for AI agents.
      tools:
      - name: example
        description: A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
        hints:
          readOnly: true
        call: xero.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: invoices-bank-feeds-compose-context-capability-skills
      description: Agent Skill bundle for Xero Invoices Bank Feeds Compose Context Capability.
      skills:
      - name: invoices-bank-feeds-compose-context-capability
        description: A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
        location: file:///opt/naftiko/skills/invoices-bank-feeds-compose-context-capability
        allowed-tools: example
        tools:
        - name: example
          description: A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant.
          from:
            sourceNamespace: invoices-bank-feeds-compose-context-capability-mcp
            action: example
---

A composite capability over Xero Invoices + Xero Bank Feeds that returns one shaped accounting-context object for an SMB AI assistant. Xero's product surface is naturally multi-source within Xero itself; this is the apidays NYC follow-on artifact she can show internally.
