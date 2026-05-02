---
categories: []
consumed_apis: []
description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
layout: capability
name: M365 Graph Work Iq Semantic Context Mcp
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- a capability over graph + work iq that returns one semantic context object joining mail, files, teams, and people for the m365 copilot agent path.
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: m365-graph-work-iq-semantic-context-mcp
source_filename: m365-graph-work-iq-semantic-context-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Graph Work Iq Semantic Context Mcp\n  description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-graph-work-iq-semantic-context-mcp-rest\n    description: REST API for M365 Graph Work Iq Semantic Context Mcp.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-graph-work-iq-semantic-context-mcp-mcp\n    description: MCP server exposing M365 Graph Work Iq Semantic Context Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-graph-work-iq-semantic-context-mcp-skills\n    description: Agent Skill bundle for M365 Graph Work Iq Semantic Context Mcp.\n    skills:\n    - name: m365-graph-work-iq-semantic-context-mcp\n      description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365\
  \ Copilot agent path.\n      location: file:///opt/naftiko/skills/m365-graph-work-iq-semantic-context-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.\n        from:\n          sourceNamespace: m365-graph-work-iq-semantic-context-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-graph-work-iq-semantic-context-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability over Graph + Work IQ that returns one semantic context object joining mail, files, Teams, and people for the M365 Copilot agent path.
  hints:
    readOnly: true
  name: example
---
