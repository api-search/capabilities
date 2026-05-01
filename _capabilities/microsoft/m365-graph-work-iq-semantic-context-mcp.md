---
categories: []
consumed_apis:
- microsoft
description: A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Graph Work Iq Semantic Context Mcp
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- over
- microsoft
- graph
- work
slug: m365-graph-work-iq-semantic-context-mcp
source_filename: m365-graph-work-iq-semantic-context-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Graph Work Iq Semantic Context Mcp
    description: A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
    tags:
    - Microsoft
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: microsoft-env
    description: Microsoft credentials.
    keys:
      MICROSOFT_API_KEY: MICROSOFT_API_KEY
  capability:
    consumes:
    - namespace: microsoft
      type: http
      baseUri: https://api.microsoft.com
      authentication:
        type: bearer
        token: '{{MICROSOFT_API_KEY}}'
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
      namespace: m365-graph-work-iq-semantic-context-mcp-rest
      description: REST API for Microsoft M365 Graph Work Iq Semantic Context Mcp.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: microsoft.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: m365-graph-work-iq-semantic-context-mcp-mcp
      description: MCP server exposing Microsoft M365 Graph Work Iq Semantic Context Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-graph-work-iq-semantic-context-mcp-skills
      description: Agent Skill bundle for Microsoft M365 Graph Work Iq Semantic Context Mcp.
      skills:
      - name: m365-graph-work-iq-semantic-context-mcp
        description: A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
        location: file:///opt/naftiko/skills/m365-graph-work-iq-semantic-context-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
          from:
            sourceNamespace: m365-graph-work-iq-semantic-context-mcp-mcp
            action: example
---

A capability over Microsoft Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path. His own podcast framed this exact pattern; this is the artifact he can publish as the M365 ISV reference.
