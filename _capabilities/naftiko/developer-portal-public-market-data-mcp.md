---
categories: []
consumed_apis: []
description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
layout: capability
name: Developer Portal Public Market Data Mcp
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
- a capability wrapping a public developer portal endpoint (markets / onyx public data) plus fred as a backing public source, governance-tagged for banking compliance.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: developer-portal-public-market-data-mcp
source_filename: developer-portal-public-market-data-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Developer Portal Public Market Data Mcp\n  description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: developer-portal-public-market-data-mcp-rest\n    description: REST API for Developer Portal Public Market Data Mcp.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: developer-portal-public-market-data-mcp-mcp\n    description: MCP server exposing Developer Portal Public Market Data Mcp for AI agents.\n    tools:\n    - name: example\n      description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: developer-portal-public-market-data-mcp-skills\n    description: Agent Skill bundle for Developer Portal Public Market Data Mcp.\n    skills:\n    - name: developer-portal-public-market-data-mcp\n      description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as\
  \ a backing public source, governance-tagged for banking compliance.\n      location: file:///opt/naftiko/skills/developer-portal-public-market-data-mcp\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.\n        from:\n          sourceNamespace: developer-portal-public-market-data-mcp-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/developer-portal-public-market-data-mcp.yaml
tags:
- Naftiko
tools:
- description: A capability wrapping a public developer portal endpoint (markets / Onyx public data) plus FRED as a backing public source, governance-tagged for banking compliance.
  hints:
    readOnly: true
  name: example
---
