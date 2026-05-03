---
categories: []
consumed_apis: []
description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
layout: capability
name: Multi Api Composition Capability
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
- governance
- a capability composition demo where multiple -internal apis become one consumable capability — the de-dup story for a team lead persona.
slug: multi-api-composition-capability
source_filename: multi-api-composition-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Multi Api Composition Capability\n  description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: multi-api-composition-capability-rest\n    description: REST API for Multi Api Composition Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n \
  \     - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: multi-api-composition-capability-mcp\n    description: MCP server exposing Multi Api Composition Capability for AI agents.\n    tools:\n    - name: example\n      description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: multi-api-composition-capability-skills\n    description: Agent Skill bundle for Multi Api Composition Capability.\n    skills:\n    - name: multi-api-composition-capability\n      description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.\n      location: file:///opt/naftiko/skills/multi-api-composition-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.\n        from:\n          sourceNamespace: multi-api-composition-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/multi-api-composition-capability.yaml
tags:
- Naftiko
tools:
- description: A Capability Composition demo where multiple -internal APIs become one consumable capability — the de-dup story for a Team Lead persona.
  hints:
    readOnly: true
  name: example
---
