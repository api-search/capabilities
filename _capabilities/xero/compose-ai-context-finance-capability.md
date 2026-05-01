---
categories: []
consumed_apis:
- xero
description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
layout: capability
naftiko_layer: proposed
naftiko_partner: Rose Missier
name: Xero Compose Ai Context Finance Capability
operations: []
personas: []
provider_name: Xero
provider_slug: xero
search_terms:
- compose
- context
- showing
- accounting
- finance
slug: compose-ai-context-finance-capability
source_filename: compose-ai-context-finance-capability.yaml
source_heading: Capability Spec
source_yaml: |
  naftiko: 1.0.0-alpha2
  info:
    title: Xero Compose Ai Context Finance Capability
    description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
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
      namespace: compose-ai-context-finance-capability-rest
      description: REST API for Xero Compose Ai Context Finance Capability.
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
      namespace: compose-ai-context-finance-capability-mcp
      description: MCP server exposing Xero Compose Ai Context Finance Capability for AI agents.
      tools:
      - name: example
        description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
        hints:
          readOnly: true
        call: xero.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: compose-ai-context-finance-capability-skills
      description: Agent Skill bundle for Xero Compose Ai Context Finance Capability.
      skills:
      - name: compose-ai-context-finance-capability
        description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
        location: file:///opt/naftiko/skills/compose-ai-context-finance-capability
        allowed-tools: example
        tools:
        - name: example
          description: Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant.
          from:
            sourceNamespace: compose-ai-context-finance-capability-mcp
            action: example
---

Compose AI Context (#5) showing accounting + finance + customer APIs as multi-source context for an AI assistant. Xero's product surface is accounting-centric and naturally multi-source; the use case maps directly.
