---
categories: []
consumed_apis: []
description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
layout: capability
name: Cpaas Mcp Collection
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
- api integration
- spec-driven integration
- capabilities
- naftiko
- mcp
- example op
- example
- governance
- a capability collection wrapping communications apis (sms, voice, video) with mcp exposure — agent-callable communications as the entry-point demo.
slug: cpaas-mcp-collection
source_filename: cpaas-mcp-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cpaas Mcp Collection\n  description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: cpaas-mcp-collection-rest\n    description: REST API for Cpaas Mcp Collection.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n     \
  \   name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cpaas-mcp-collection-mcp\n    description: MCP server exposing Cpaas Mcp Collection for AI agents.\n    tools:\n    - name: example\n      description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cpaas-mcp-collection-skills\n    description: Agent Skill bundle for Cpaas Mcp Collection.\n    skills:\n    - name: cpaas-mcp-collection\n      description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.\n      location: file:///opt/naftiko/skills/cpaas-mcp-collection\n      allowed-tools: example\n      tools:\n      - name: example\n\
  \        description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.\n        from:\n          sourceNamespace: cpaas-mcp-collection-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cpaas-mcp-collection.yaml
tags:
- Naftiko
tools:
- description: A capability collection wrapping communications APIs (SMS, voice, video) with MCP exposure — agent-callable communications as the entry-point demo.
  hints:
    readOnly: true
  name: example
---
