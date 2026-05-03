---
categories: []
consumed_apis: []
description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
layout: capability
name: Adjacency Capability Driven Mocking Reference
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
- governance
- mcp
- a reference capability exercising capability-driven mocking against capability specs () plus runtime execution (naftiko) — explicit partnership-boundary artifact.
- capabilities
- ai
slug: adjacency-capability-driven-mocking-reference
source_filename: adjacency-capability-driven-mocking-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Adjacency Capability Driven Mocking Reference\n  description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: adjacency-capability-driven-mocking-reference-rest\n    description: REST API for Adjacency Capability Driven Mocking Reference.\n    resources:\n\
  \    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: adjacency-capability-driven-mocking-reference-mcp\n    description: MCP server exposing Adjacency Capability Driven Mocking Reference for AI agents.\n    tools:\n    - name: example\n      description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: adjacency-capability-driven-mocking-reference-skills\n    description: Agent Skill bundle for Adjacency Capability Driven Mocking Reference.\n    skills:\n    - name: adjacency-capability-driven-mocking-reference\n      description: A reference capability exercising capability-driven\
  \ mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.\n      location: file:///opt/naftiko/skills/adjacency-capability-driven-mocking-reference\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.\n        from:\n          sourceNamespace: adjacency-capability-driven-mocking-reference-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/adjacency-capability-driven-mocking-reference.yaml
tags:
- Naftiko
tools:
- description: A reference capability exercising capability-driven mocking against capability specs () plus runtime execution (Naftiko) — explicit partnership-boundary artifact.
  hints:
    readOnly: true
  name: example
---
