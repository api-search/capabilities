---
categories: []
consumed_apis:
- vonage
description: A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
layout: capability
naftiko_layer: proposed
naftiko_partner: Vonage
name: Vonage Cpaas Mcp Collection
operations: []
personas: []
provider_name: Vonage
provider_slug: vonage
search_terms:
- capability
- collection
- wrapping
- vonage
- communications
slug: cpaas-mcp-collection
source_filename: cpaas-mcp-collection.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Vonage Cpaas Mcp Collection
    description: A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
    tags:
    - Vonage
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: vonage-env
    description: Vonage credentials.
    keys:
      VONAGE_API_KEY: VONAGE_API_KEY
  capability:
    consumes:
    - namespace: vonage
      type: http
      baseUri: https://api.vonage.com
      authentication:
        type: bearer
        token: '{{VONAGE_API_KEY}}'
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
      namespace: cpaas-mcp-collection-rest
      description: REST API for Vonage Cpaas Mcp Collection.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: vonage.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: cpaas-mcp-collection-mcp
      description: MCP server exposing Vonage Cpaas Mcp Collection for AI agents.
      tools:
      - name: example
        description: A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
        hints:
          readOnly: true
        call: vonage.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: cpaas-mcp-collection-skills
      description: Agent Skill bundle for Vonage Cpaas Mcp Collection.
      skills:
      - name: cpaas-mcp-collection
        description: A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
        location: file:///opt/naftiko/skills/cpaas-mcp-collection
        allowed-tools: example
        tools:
        - name: example
          description: A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
          from:
            sourceNamespace: cpaas-mcp-collection-mcp
            action: example
---

A capability collection wrapping Vonage's communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo. Conversation cycled and stalled; a built artifact is the un-stickier next-step than another intro thread.
