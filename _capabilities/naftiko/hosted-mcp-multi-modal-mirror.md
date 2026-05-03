---
categories: []
consumed_apis: []
description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
layout: capability
name: Hosted Mcp Multi Modal Mirror
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
- a capability that mirrors a object across rest + graphql + hosted mcp and exposes the same agent surface so governance lives in one openapi doc — kris's exact methodology argument.
- governance
slug: hosted-mcp-multi-modal-mirror
source_filename: hosted-mcp-multi-modal-mirror.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Hosted Mcp Multi Modal Mirror\n  description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: hosted-mcp-multi-modal-mirror-rest\n    description: REST API for Hosted Mcp Multi Modal Mirror.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: hosted-mcp-multi-modal-mirror-mcp\n    description: MCP server exposing Hosted Mcp Multi Modal Mirror for AI agents.\n    tools:\n    - name: example\n      description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: hosted-mcp-multi-modal-mirror-skills\n    description: Agent Skill bundle for Hosted Mcp Multi Modal Mirror.\n    skills:\n    - name: hosted-mcp-multi-modal-mirror\n      description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc\
  \ — Kris's exact methodology argument.\n      location: file:///opt/naftiko/skills/hosted-mcp-multi-modal-mirror\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.\n        from:\n          sourceNamespace: hosted-mcp-multi-modal-mirror-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/hosted-mcp-multi-modal-mirror.yaml
tags:
- Naftiko
tools:
- description: A capability that mirrors a object across REST + GraphQL + hosted MCP and exposes the same agent surface so governance lives in one OpenAPI doc — Kris's exact methodology argument.
  hints:
    readOnly: true
  name: example
---
