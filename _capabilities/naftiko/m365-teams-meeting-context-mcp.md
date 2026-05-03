---
categories: []
consumed_apis: []
description: A capability over Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
layout: capability
name: M365 Teams Meeting Context Mcp
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
- a capability over teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an mcp tool, the work iq pattern applied to teams specifically.
slug: m365-teams-meeting-context-mcp
source_filename: m365-teams-meeting-context-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Teams Meeting Context Mcp\n  description: A capability over Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-teams-meeting-context-mcp-rest\n    description: REST API for M365 Teams Meeting Context Mcp.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-teams-meeting-context-mcp-mcp\n    description: MCP server exposing M365 Teams Meeting Context Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-teams-meeting-context-mcp-skills\n    description: Agent Skill bundle for M365 Teams Meeting Context Mcp.\n    skills:\n    - name: m365-teams-meeting-context-mcp\n      description: A capability over Teams meetings + chats that returns a single semantic meeting-context\
  \ object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.\n      location: file:///opt/naftiko/skills/m365-teams-meeting-context-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.\n        from:\n          sourceNamespace: m365-teams-meeting-context-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-teams-meeting-context-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over Teams meetings + chats that returns a single semantic meeting-context object (attendees, decisions, action items, linked files) as an MCP tool, the Work IQ pattern applied to Teams specifically.
  hints:
    readOnly: true
  name: example
---
