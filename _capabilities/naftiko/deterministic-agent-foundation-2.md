---
categories: []
consumed_apis: []
description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
layout: capability
name: Deterministic Agent Foundation 2
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
- a capability annotated against the sdi "deterministic foundation for agents" framing, used as the ai-data-enterprise-tech opening artifact.
- governance
- mcp
- capabilities
- ai
slug: deterministic-agent-foundation-2
source_filename: deterministic-agent-foundation-2.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Agent Foundation 2\n  description: A capability annotated against the SDI \"Deterministic Foundation for Agents\" framing, used as the AI-Data-Enterprise-Tech opening artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-agent-foundation-2-rest\n    description: REST API for Deterministic Agent Foundation 2.\n    resources:\n    - name: example\n      path: /example\n      operations:\n\
  \      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-agent-foundation-2-mcp\n    description: MCP server exposing Deterministic Agent Foundation 2 for AI agents.\n    tools:\n    - name: example\n      description: A capability annotated against the SDI \"Deterministic Foundation for Agents\" framing, used as the AI-Data-Enterprise-Tech opening artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-agent-foundation-2-skills\n    description: Agent Skill bundle for Deterministic Agent Foundation 2.\n    skills:\n    - name: deterministic-agent-foundation-2\n      description: A capability annotated against the SDI \"Deterministic Foundation for Agents\" framing, used as the AI-Data-Enterprise-Tech opening artifact.\n      location: file:///opt/naftiko/skills/deterministic-agent-foundation-2\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability annotated against the SDI \"Deterministic Foundation for Agents\" framing, used as the AI-Data-Enterprise-Tech opening artifact.\n        from:\n          sourceNamespace: deterministic-agent-foundation-2-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-agent-foundation-2.yaml
tags:
- Naftiko
tools:
- description: A capability annotated against the SDI "Deterministic Foundation for Agents" framing, used as the AI-Data-Enterprise-Tech opening artifact.
  hints:
    readOnly: true
  name: example
---
