---
categories: []
consumed_apis: []
description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
layout: capability
name: Capability First Reusability Reference
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
- 'a reference capability tied to guide-use-cases #9 (capability-first api reusability), used as the dual-track proposal anchor.'
- governance
slug: capability-first-reusability-reference
source_filename: capability-first-reusability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Capability First Reusability Reference\n  description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: capability-first-reusability-reference-rest\n    description: REST API for Capability First Reusability Reference.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: capability-first-reusability-reference-mcp\n    description: MCP server exposing Capability First Reusability Reference for AI agents.\n    tools:\n    - name: example\n      description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: capability-first-reusability-reference-skills\n    description: Agent Skill bundle for Capability First Reusability Reference.\n    skills:\n    - name: capability-first-reusability-reference\n      description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'\n      location: file:///opt/naftiko/skills/capability-first-reusability-reference\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'\n        from:\n          sourceNamespace: capability-first-reusability-reference-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/capability-first-reusability-reference.yaml
tags:
- Naftiko
tools:
- description: 'A reference capability tied to Guide-Use-Cases #9 (Capability-first API reusability), used as the dual-track proposal anchor.'
  hints:
    readOnly: true
  name: example
---
