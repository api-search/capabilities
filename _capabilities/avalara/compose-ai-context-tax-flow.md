---
categories: []
consumed_apis:
- avalara
description: Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant.
layout: capability
naftiko_layer: proposed
naftiko_partner: Joshua McMillen
name: Avalara Compose Ai Context Tax Flow
operations: []
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- compose
- context
- case
- wrapping
- invoice
slug: compose-ai-context-tax-flow
source_filename: compose-ai-context-tax-flow.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Avalara Compose Ai Context Tax Flow
    description: Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant.
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
      namespace: compose-ai-context-tax-flow-rest
      description: REST API for Avalara Compose Ai Context Tax Flow.
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
      namespace: compose-ai-context-tax-flow-mcp
      description: MCP server exposing Avalara Compose Ai Context Tax Flow for AI agents.
      tools:
      - name: example
        description: Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant.
        hints:
          readOnly: true
        call: avalara.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: compose-ai-context-tax-flow-skills
      description: Agent Skill bundle for Avalara Compose Ai Context Tax Flow.
      skills:
      - name: compose-ai-context-tax-flow
        description: Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant.
        location: file:///opt/naftiko/skills/compose-ai-context-tax-flow
        allowed-tools: example
        tools:
        - name: example
          description: Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant.
          from:
            sourceNamespace: compose-ai-context-tax-flow-mcp
            action: example
---

Compose AI Context use case (#5) wrapping tax + invoice + customer Avalara endpoints into one shaped context object for an AI assistant. His recommendations cite use cases #1 (AI integration) and #5 (Compose AI context) as the AI-lead primer.
