---
categories: []
consumed_apis:
- schneider-electric
description: A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Manu PK
name: Schneider Electric Schneider Tableau Mcp Allow Listed Bi Capability
operations: []
personas: []
provider_name: Schneider Electric
provider_slug: schneider-electric
search_terms:
- capability
- that
- exposes
- tableau
- fronted
slug: schneider-tableau-mcp-allow-listed-bi-capability
source_filename: schneider-tableau-mcp-allow-listed-bi-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Schneider Electric Schneider Tableau Mcp Allow Listed Bi Capability
    description: A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses.
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
      namespace: schneider-tableau-mcp-allow-listed-bi-capability-rest
      description: REST API for Schneider Electric Schneider Tableau Mcp Allow Listed Bi Capability.
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
      namespace: schneider-tableau-mcp-allow-listed-bi-capability-mcp
      description: MCP server exposing Schneider Electric Schneider Tableau Mcp Allow Listed Bi Capability for AI agents.
      tools:
      - name: example
        description: A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses.
        hints:
          readOnly: true
        call: schneider-electric.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: schneider-tableau-mcp-allow-listed-bi-capability-skills
      description: Agent Skill bundle for Schneider Electric Schneider Tableau Mcp Allow Listed Bi Capability.
      skills:
      - name: schneider-tableau-mcp-allow-listed-bi-capability
        description: A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses.
        location: file:///opt/naftiko/skills/schneider-tableau-mcp-allow-listed-bi-capability
        allowed-tools: example
        tools:
        - name: example
          description: A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses.
          from:
            sourceNamespace: schneider-tableau-mcp-allow-listed-bi-capability-mcp
            action: example
---

A capability that exposes Tableau-fronted BI datasets as an MCP tool, governed under the same allow-list + data-sensitivity tagging the rest of Schneider's MCP surface uses. Tableau sits in his "utility once" category — BI access pulled through the same governed MCP path keeps the policy story coherent and proves the pattern beyond developer-tooling MCP servers.
