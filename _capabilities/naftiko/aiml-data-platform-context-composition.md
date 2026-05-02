---
categories: []
consumed_apis: []
description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
layout: capability
name: Aiml Data Platform Context Composition
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
- example
- governance
- a -global-tech-shaped capability across ai/ml + data platform apis implementing compose ai context.
slug: aiml-data-platform-context-composition
source_filename: aiml-data-platform-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aiml Data Platform Context Composition\n  description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aiml-data-platform-context-composition-rest\n    description: REST API for Aiml Data Platform Context Composition.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n\
  \        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aiml-data-platform-context-composition-mcp\n    description: MCP server exposing Aiml Data Platform Context Composition for AI agents.\n    tools:\n    - name: example\n      description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aiml-data-platform-context-composition-skills\n    description: Agent Skill bundle for Aiml Data Platform Context Composition.\n    skills:\n    - name: aiml-data-platform-context-composition\n      description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.\n      location: file:///opt/naftiko/skills/aiml-data-platform-context-composition\n      allowed-tools: example\n      tools:\n \
  \     - name: example\n        description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.\n        from:\n          sourceNamespace: aiml-data-platform-context-composition-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aiml-data-platform-context-composition.yaml
tags:
- Naftiko
tools:
- description: A -Global-Tech-shaped capability across AI/ML + data platform APIs implementing Compose AI Context.
  hints:
    readOnly: true
  name: example
---
