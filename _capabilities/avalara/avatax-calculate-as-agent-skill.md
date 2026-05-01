---
categories: []
consumed_apis:
- avalara
description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joshua McMillen
name: Avalara Avatax Calculate As Agent Skill
operations: []
personas: []
provider_name: Avalara
provider_slug: avalara
search_terms:
- wraps
- avatax
- transactions
- createoradjust
- endpoint
slug: avatax-calculate-as-agent-skill
source_filename: avatax-calculate-as-agent-skill.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Avalara Avatax Calculate As Agent Skill
    description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
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
      namespace: avatax-calculate-as-agent-skill-rest
      description: REST API for Avalara Avatax Calculate As Agent Skill.
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
      namespace: avatax-calculate-as-agent-skill-mcp
      description: MCP server exposing Avalara Avatax Calculate As Agent Skill for AI agents.
      tools:
      - name: example
        description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
        hints:
          readOnly: true
        call: avalara.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: avatax-calculate-as-agent-skill-skills
      description: Agent Skill bundle for Avalara Avatax Calculate As Agent Skill.
      skills:
      - name: avatax-calculate-as-agent-skill
        description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
        location: file:///opt/naftiko/skills/avatax-calculate-as-agent-skill
        allowed-tools: example
        tools:
        - name: example
          description: Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant.
          from:
            sourceNamespace: avatax-calculate-as-agent-skill-mcp
            action: example
---

Wraps the AvaTax `/transactions/createoradjust` endpoint as a downloadable Agent Skill folder + MCP tool, with shaped jurisdiction-aware output for an AI checkout assistant. His new AI-lead role packages skills internally; AvaTax is the Avalara API every agent demo asks for.
