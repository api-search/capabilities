---
categories: []
consumed_apis: []
description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
layout: capability
name: Co Marketing Spec Rules Companion
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
- a reference capability tied to a co-authored guide based on framework-wiki/specification-rules — the partnership format that fits her product-marketing role.
- capabilities
- ai
slug: co-marketing-spec-rules-companion
source_filename: co-marketing-spec-rules-companion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Co Marketing Spec Rules Companion\n  description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: co-marketing-spec-rules-companion-rest\n    description: REST API for Co Marketing Spec Rules Companion.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: co-marketing-spec-rules-companion-mcp\n    description: MCP server exposing Co Marketing Spec Rules Companion for AI agents.\n    tools:\n    - name: example\n      description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: co-marketing-spec-rules-companion-skills\n    description: Agent Skill bundle for Co Marketing Spec Rules Companion.\n    skills:\n    - name: co-marketing-spec-rules-companion\n      description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.\n\
  \      location: file:///opt/naftiko/skills/co-marketing-spec-rules-companion\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.\n        from:\n          sourceNamespace: co-marketing-spec-rules-companion-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/co-marketing-spec-rules-companion.yaml
tags:
- Naftiko
tools:
- description: A reference capability tied to a co-authored guide based on framework-wiki/Specification-Rules — the partnership format that fits her product-marketing role.
  hints:
    readOnly: true
  name: example
---
