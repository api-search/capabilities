---
categories: []
consumed_apis: []
description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
layout: capability
name: Deterministic Foundation For Agents Demo
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
- a capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputparameters, jsonpath shaping, governance rules) versus what an agent would otherwise hallucinate against the same api.
- mcp
- example op
- example
- governance
slug: deterministic-foundation-for-agents-demo
source_filename: deterministic-foundation-for-agents-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Foundation For Agents Demo\n  description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-foundation-for-agents-demo-rest\n    description: REST API for Deterministic Foundation\
  \ For Agents Demo.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-foundation-for-agents-demo-mcp\n    description: MCP server exposing Deterministic Foundation For Agents Demo for AI agents.\n    tools:\n    - name: example\n      description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-foundation-for-agents-demo-skills\n    description: Agent Skill bundle for Deterministic Foundation For Agents Demo.\n    skills:\n    - name: deterministic-foundation-for-agents-demo\n\
  \      description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.\n      location: file:///opt/naftiko/skills/deterministic-foundation-for-agents-demo\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.\n        from:\n          sourceNamespace: deterministic-foundation-for-agents-demo-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-foundation-for-agents-demo.yaml
tags:
- Naftiko
tools:
- description: A capability whose `exposes` block is annotated to show the deterministic adapter layer (typed outputParameters, JSONPath shaping, governance rules) versus what an agent would otherwise hallucinate against the same API.
  hints:
    readOnly: true
  name: example
---
