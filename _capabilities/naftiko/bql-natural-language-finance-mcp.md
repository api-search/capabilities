---
categories: []
consumed_apis: []
description: A capability that exposes Query Language (BQL) as a natural-language MCP tool for an analyst agent.
layout: capability
name: Bql Natural Language Finance Mcp
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
- a capability that exposes query language (bql) as a natural-language mcp tool for an analyst agent.
- example
- governance
slug: bql-natural-language-finance-mcp
source_filename: bql-natural-language-finance-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bql Natural Language Finance Mcp\n  description: A capability that exposes Query Language (BQL) as a natural-language MCP tool for an analyst agent.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bql-natural-language-finance-mcp-rest\n    description: REST API for Bql Natural Language Finance Mcp.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n\
  \        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bql-natural-language-finance-mcp-mcp\n    description: MCP server exposing Bql Natural Language Finance Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability that exposes Query Language (BQL) as a natural-language MCP tool for an analyst agent.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bql-natural-language-finance-mcp-skills\n    description: Agent Skill bundle for Bql Natural Language Finance Mcp.\n    skills:\n    - name: bql-natural-language-finance-mcp\n      description: A capability that exposes Query Language (BQL) as a natural-language MCP tool for an analyst agent.\n      location: file:///opt/naftiko/skills/bql-natural-language-finance-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that exposes\
  \ Query Language (BQL) as a natural-language MCP tool for an analyst agent.\n        from:\n          sourceNamespace: bql-natural-language-finance-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bql-natural-language-finance-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability that exposes Query Language (BQL) as a natural-language MCP tool for an analyst agent.
  hints:
    readOnly: true
  name: example
---
