---
categories: []
consumed_apis:
- schneider-electric
description: A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Mcp Allow List Registry Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- consumes
- open
- source
slug: schneider-mcp-allow-list-registry-capability
source_filename: schneider-mcp-allow-list-registry-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Mcp Allow List Registry Capability
    description: A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read.
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
      namespace: schneider-mcp-allow-list-registry-capability-rest
      description: REST API for Schneider Electric Schneider Mcp Allow List Registry Capability.
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
      namespace: schneider-mcp-allow-list-registry-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Mcp Allow List Registry Capability for AI agents.
      tools:
      - name: example
        description: A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-mcp-allow-list-registry-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Mcp Allow List Registry Capability.
      skills:
      - name: schneider-mcp-allow-list-registry-capability
        description: A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read.
        location: file:///opt/naftiko/skills/schneider-mcp-allow-list-registry-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read.
          from:
            sourceNamespace: schneider-mcp-allow-list-registry-capability-mcp
            action: example
---

A capability that consumes the open-source MCP registry JSON and exposes a per-Schneider allow-list view that VS Code Copilot extensions can read. His 2026-04-24 conversation described this exact pattern — modeling the registry-as-Naftiko-capability is the artifact he hinted at building.
