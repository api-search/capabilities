---
categories: []
consumed_apis:
- schneider-electric
description: A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Figma Mcp Ux Design Token Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- over
- figma
- scoped
- design
slug: schneider-figma-mcp-ux-design-token-capability
source_filename: schneider-figma-mcp-ux-design-token-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Figma Mcp Ux Design Token Capability
    description: A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow.
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
      namespace: schneider-figma-mcp-ux-design-token-capability-rest
      description: REST API for Schneider Electric Schneider Figma Mcp Ux Design Token Capability.
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
      namespace: schneider-figma-mcp-ux-design-token-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Figma Mcp Ux Design Token Capability for AI agents.
      tools:
      - name: example
        description: A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-figma-mcp-ux-design-token-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Figma Mcp Ux Design Token Capability.
      skills:
      - name: schneider-figma-mcp-ux-design-token-capability
        description: A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow.
        location: file:///opt/naftiko/skills/schneider-figma-mcp-ux-design-token-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow.
          from:
            sourceNamespace: schneider-figma-mcp-ux-design-token-capability-mcp
            action: example
---

A capability over Figma MCP scoped to design-token and component-metadata extraction for the UX layer of Schneider's developer workflow. Figma is the first stage in his explicit developer-workflow registry target list (Figma → Atlassian → GitHub). Owning the UX leg as a capability matches his "wherever you have the developer workflow cover, that is our first target" framing.
