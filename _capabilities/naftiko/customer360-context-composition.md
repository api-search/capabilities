---
categories: []
consumed_apis: []
description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
layout: capability
name: Customer360 Context Composition
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
- compose ai context (#5) using + a complementary system (e.g., marketing cloud or an external billing api) as the orchestration example.
- example op
- governance
slug: customer360-context-composition
source_filename: customer360-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Customer360 Context Composition\n  description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: customer360-context-composition-rest\n    description: REST API for Customer360 Context Composition.\n    resources:\n    - name: example\n      path: /example\n      operations:\n     \
  \ - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: customer360-context-composition-mcp\n    description: MCP server exposing Customer360 Context Composition for AI agents.\n    tools:\n    - name: example\n      description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: customer360-context-composition-skills\n    description: Agent Skill bundle for Customer360 Context Composition.\n    skills:\n    - name: customer360-context-composition\n      description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.\n      location: file:///opt/naftiko/skills/customer360-context-composition\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.\n        from:\n          sourceNamespace: customer360-context-composition-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/customer360-context-composition.yaml
tags:
- Naftiko
tools:
- description: Compose AI Context (#5) using + a complementary system (e.g., Marketing Cloud or an external billing API) as the orchestration example.
  hints:
    readOnly: true
  name: example
---
