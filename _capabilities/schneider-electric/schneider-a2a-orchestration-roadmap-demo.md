---
categories: []
consumed_apis:
- schneider-electric
description: A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation.
layout: capability
naftiko_layer: proposed
naftiko_partner: Manu PK
name: Schneider Electric Schneider A2a Orchestration Roadmap Demo
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- collection
- demonstrating
- agent
- orchestration
slug: schneider-a2a-orchestration-roadmap-demo
source_filename: schneider-a2a-orchestration-roadmap-demo.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider A2a Orchestration Roadmap Demo
    description: A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation.
    tags:
    - Schneider Electric
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: schneider-electric-env
    description: Schneider Electric credentials.
    keys:
      SCHNEIDER_ELECTRIC_API_KEY: SCHNEIDER_ELECTRIC_API_KEY
  capability:
    consumes:
    - namespace: schneider-electric
      type: http
      baseUri: https://api.schneider-electric.com
      authentication:
        type: bearer
        token: '{{SCHNEIDER_ELECTRIC_API_KEY}}'
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
      namespace: schneider-a2a-orchestration-roadmap-demo-rest
      description: REST API for Schneider Electric Schneider A2a Orchestration Roadmap Demo.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: schneider-electric.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: schneider-a2a-orchestration-roadmap-demo-mcp
      description: MCP server exposing Schneider Electric Schneider A2a Orchestration Roadmap Demo for AI agents.
      tools:
      - name: example
        description: A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-a2a-orchestration-roadmap-demo-skills
      description: Agent Skill bundle for Schneider Electric Schneider A2a Orchestration Roadmap Demo.
      skills:
      - name: schneider-a2a-orchestration-roadmap-demo
        description: A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation.
        location: file:///opt/naftiko/skills/schneider-a2a-orchestration-roadmap-demo
        allowed-tools: example
        tools:
        - name: example
          description: A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation.
          from:
            sourceNamespace: schneider-a2a-orchestration-roadmap-demo-mcp
            action: example
---

A capability collection demonstrating the Agent-to-Agent (A2A) orchestration roadmap in concrete terms, sized to the Schneider scale conversation. His 2026-04-24 conversation described the canonical fleet/federation use case — this builds it.
