---
categories: []
consumed_apis:
- avalara
description: Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them.
layout: capability
naftiko_layer: proposed
naftiko_partner: Joshua McMillen
name: Avalara Tax Calc Agent Skill
operations: []
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- wraps
- representative
- avalara
- calculation
- capability
slug: tax-calc-agent-skill
source_filename: tax-calc-agent-skill.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Avalara Tax Calc Agent Skill
    description: Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them.
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
      namespace: tax-calc-agent-skill-rest
      description: REST API for Avalara Tax Calc Agent Skill.
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
      namespace: tax-calc-agent-skill-mcp
      description: MCP server exposing Avalara Tax Calc Agent Skill for AI agents.
      tools:
      - name: example
        description: Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them.
        hints:
          readOnly: true
        call: avalara.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: tax-calc-agent-skill-skills
      description: Agent Skill bundle for Avalara Tax Calc Agent Skill.
      skills:
      - name: tax-calc-agent-skill
        description: Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them.
        location: file:///opt/naftiko/skills/tax-calc-agent-skill
        allowed-tools: example
        tools:
        - name: example
          description: Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them.
          from:
            sourceNamespace: tax-calc-agent-skill-mcp
            action: example
---

Wraps a representative Avalara tax-calculation API as a capability with MCP + Agent Skills dual exposure, showing how Avalara's APIs become agent-consumable without rewriting them. His next-step IS this proposal; the AI-lead reframe lands hardest on packaged skills.
