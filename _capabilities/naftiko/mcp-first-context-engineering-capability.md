---
categories: []
consumed_apis: []
description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
layout: capability
name: Mcp First Context Engineering Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- example op
- example
- api integration
- naftiko
- a capability implementing the capability-first context engineering use case (#8) — design tools as mcp first, then map to apis.
- governance
- mcp
- capabilities
- ai
slug: mcp-first-context-engineering-capability
source_filename: mcp-first-context-engineering-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp First Context Engineering Capability\n  description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-first-context-engineering-capability-rest\n    description: REST API for Mcp First Context Engineering Capability.\n    resources:\n    - name: example\n      path: /example\n     \
  \ operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-first-context-engineering-capability-mcp\n    description: MCP server exposing Mcp First Context Engineering Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-first-context-engineering-capability-skills\n    description: Agent Skill bundle for Mcp First Context Engineering Capability.\n    skills:\n    - name: mcp-first-context-engineering-capability\n      description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.\n      location: file:///opt/naftiko/skills/mcp-first-context-engineering-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.\n        from:\n          sourceNamespace: mcp-first-context-engineering-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-first-context-engineering-capability.yaml
tags:
- Naftiko
tools:
- description: A capability implementing the Capability-First Context Engineering use case (#8) — design tools as MCP first, then map to APIs.
  hints:
    readOnly: true
  name: example
---
