---
categories: []
consumed_apis:
- microsoft
description: A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Sébastien Levert
name: Microsoft M365 Teams Meeting Context Mcp
operations: []
personas: []
provider_name: Microsoft
provider_slug: microsoft
search_terms:
- capability
- over
- microsoft
- teams
- meetings
slug: m365-teams-meeting-context-mcp
source_filename: m365-teams-meeting-context-mcp.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Microsoft M365 Teams Meeting Context Mcp
    description: A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
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
      namespace: m365-teams-meeting-context-mcp-rest
      description: REST API for Microsoft M365 Teams Meeting Context Mcp.
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
      namespace: m365-teams-meeting-context-mcp-mcp
      description: MCP server exposing Microsoft M365 Teams Meeting Context Mcp for AI agents.
      tools:
      - name: example
        description: A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
        hints:
          readOnly: true
        call: microsoft.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: m365-teams-meeting-context-mcp-skills
      description: Agent Skill bundle for Microsoft M365 Teams Meeting Context Mcp.
      skills:
      - name: m365-teams-meeting-context-mcp
        description: A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
        location: file:///opt/naftiko/skills/m365-teams-meeting-context-mcp
        allowed-tools: example
        tools:
        - name: example
          description: A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
          from:
            sourceNamespace: m365-teams-meeting-context-mcp-mcp
            action: example
---

A capability over Microsoft Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically. Teams meetings are the heaviest, most context-rich Work IQ source he described — this is the canonical "Work IQ as MCP" demonstration anchored to the data type that proves the pattern.
