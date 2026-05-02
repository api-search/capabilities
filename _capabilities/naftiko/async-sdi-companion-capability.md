---
categories: []
consumed_apis: []
description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
layout: capability
name: Async Sdi Companion Capability
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
- a capability paired with framework-wiki/spec-driven-integration.md as the standalone read, freeing her from needing to schedule.
- example
- governance
slug: async-sdi-companion-capability
source_filename: async-sdi-companion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Async Sdi Companion Capability\n  description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: async-sdi-companion-capability-rest\n    description: REST API for Async Sdi Companion Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: async-sdi-companion-capability-mcp\n    description: MCP server exposing Async Sdi Companion Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: async-sdi-companion-capability-skills\n    description: Agent Skill bundle for Async Sdi Companion Capability.\n    skills:\n    - name: async-sdi-companion-capability\n      description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.\n      location: file:///opt/naftiko/skills/async-sdi-companion-capability\n      allowed-tools: example\n\
  \      tools:\n      - name: example\n        description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.\n        from:\n          sourceNamespace: async-sdi-companion-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/async-sdi-companion-capability.yaml
tags:
- Naftiko
tools:
- description: A capability paired with framework-wiki/Spec-Driven-Integration.md as the standalone read, freeing her from needing to schedule.
  hints:
    readOnly: true
  name: example
---
