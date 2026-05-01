---
categories: []
consumed_apis:
- walmart-global-tech
description: A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
layout: capability
naftiko_layer: proposed
naftiko_partner: Mamta Suri
name: Walmart Global Tech Walmart Aiml Data Platform Context Composition
operations: []
personas: []
provider_name: Walmart Global Tech
provider_slug: walmart-global-tech
search_terms:
- walmart
- global
- tech
- shaped
- capability
slug: walmart-aiml-data-platform-context-composition
source_filename: walmart-aiml-data-platform-context-composition.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Walmart Global Tech Walmart Aiml Data Platform Context Composition
    description: A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
    tags:
    - Walmart Global Tech
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: walmart-global-tech-env
    description: Walmart Global Tech credentials.
    keys:
      WALMART_GLOBAL_TECH_API_KEY: WALMART_GLOBAL_TECH_API_KEY
  capability:
    consumes:
    - namespace: walmart-global-tech
      type: http
      baseUri: https://api.walmart-global-tech.com
      authentication:
        type: bearer
        token: '{{WALMART_GLOBAL_TECH_API_KEY}}'
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
      namespace: walmart-aiml-data-platform-context-composition-rest
      description: REST API for Walmart Global Tech Walmart Aiml Data Platform Context Composition.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: walmart-global-tech.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: walmart-aiml-data-platform-context-composition-mcp
      description: MCP server exposing Walmart Global Tech Walmart Aiml Data Platform Context Composition for AI agents.
      tools:
      - name: example
        description: A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
        hints:
          readOnly: true
        call: walmart-global-tech.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: walmart-aiml-data-platform-context-composition-skills
      description: Agent Skill bundle for Walmart Global Tech Walmart Aiml Data Platform Context Composition.
      skills:
      - name: walmart-aiml-data-platform-context-composition
        description: A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
        location: file:///opt/naftiko/skills/walmart-aiml-data-platform-context-composition
        allowed-tools: example
        tools:
        - name: example
          description: A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
          from:
            sourceNamespace: walmart-aiml-data-platform-context-composition-mcp
            action: example
---

A Walmart-Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context. Twice interested, never scheduled — artifact-led nudges convert better than calendar-led at this stage.
