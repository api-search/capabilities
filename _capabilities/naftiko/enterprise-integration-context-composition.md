---
categories: []
consumed_apis: []
description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
layout: capability
name: Enterprise Integration Context Composition
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
- compose ai context (#5) capability stitching marketing + ops + supply-chain apis into one composed context object — the integration story that addresses enterprise-integration sprawl.
- naftiko
- governance
- mcp
- capabilities
- ai
slug: enterprise-integration-context-composition
source_filename: enterprise-integration-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Enterprise Integration Context Composition\n  description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: enterprise-integration-context-composition-rest\n    description: REST API for Enterprise Integration Context Composition.\n  \
  \  resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: enterprise-integration-context-composition-mcp\n    description: MCP server exposing Enterprise Integration Context Composition for AI agents.\n    tools:\n    - name: example\n      description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: enterprise-integration-context-composition-skills\n    description: Agent Skill bundle for Enterprise Integration Context Composition.\n    skills:\n    - name: enterprise-integration-context-composition\n      description: Compose AI Context (#5) capability\
  \ stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.\n      location: file:///opt/naftiko/skills/enterprise-integration-context-composition\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.\n        from:\n          sourceNamespace: enterprise-integration-context-composition-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/enterprise-integration-context-composition.yaml
tags:
- Naftiko
tools:
- description: Compose AI Context (#5) capability stitching marketing + ops + supply-chain APIs into one composed context object — the integration story that addresses enterprise-integration sprawl.
  hints:
    readOnly: true
  name: example
---
