---
categories: []
consumed_apis: []
description: A Capability Composition wrapping multiple APIs as one reusable capability — the second of her two named asks.
layout: capability
name: Api Reusability Composition
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
- a capability composition wrapping multiple apis as one reusable capability — the second of her two named asks.
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: api-reusability-composition
source_filename: api-reusability-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api Reusability Composition\n  description: A Capability Composition wrapping multiple APIs as one reusable capability — the second of her two named asks.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-reusability-composition-rest\n    description: REST API for Api Reusability Composition.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n\
  \        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-reusability-composition-mcp\n    description: MCP server exposing Api Reusability Composition for AI agents.\n    tools:\n    - name: example\n      description: A Capability Composition wrapping multiple APIs as one reusable capability — the second of her two named asks.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-reusability-composition-skills\n    description: Agent Skill bundle for Api Reusability Composition.\n    skills:\n    - name: api-reusability-composition\n      description: A Capability Composition wrapping multiple APIs as one reusable capability — the second of her two named asks.\n      location: file:///opt/naftiko/skills/api-reusability-composition\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A Capability Composition wrapping\
  \ multiple APIs as one reusable capability — the second of her two named asks.\n        from:\n          sourceNamespace: api-reusability-composition-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-reusability-composition.yaml
tags:
- Naftiko
tools:
- description: A Capability Composition wrapping multiple APIs as one reusable capability — the second of her two named asks.
  hints:
    readOnly: true
  name: example
---
