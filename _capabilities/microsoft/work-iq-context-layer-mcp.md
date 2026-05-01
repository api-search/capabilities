---
categories: []
consumed_apis:
- microsoft
description: A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object.
layout: capability
naftiko_layer: proposed
naftiko_partner: Sébastien Levert
name: Microsoft Work Iq Context Layer Mcp
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- that
- mirrors
- work
- exposed
slug: work-iq-context-layer-mcp
source_filename: work-iq-context-layer-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft Work Iq Context Layer Mcp
    description: A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object.
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
      namespace: work-iq-context-layer-mcp-rest
      description: REST API for Microsoft Work Iq Context Layer Mcp.
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
      namespace: work-iq-context-layer-mcp-mcp
      description: MCP server exposing Microsoft Work Iq Context Layer Mcp for AI agents.
      tools:
      - name: example
        description: A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: work-iq-context-layer-mcp-skills
      description: Agent Skill bundle for Microsoft Work Iq Context Layer Mcp.
      skills:
      - name: work-iq-context-layer-mcp
        description: A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object.
        location: file:///opt/naftiko/skills/work-iq-context-layer-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object.
          from:
            sourceNamespace: work-iq-context-layer-mcp-mcp
            action: example
---

A capability that mirrors the Work IQ as MCP-exposed context layer pattern from his podcast — multi-source Microsoft Graph context returned as a single agent-ready object. His podcast already framed Work IQ this way; this is the artifact that proves it.
