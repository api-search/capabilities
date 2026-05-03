---
categories: []
consumed_apis: []
description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
layout: capability
name: Deterministic Agent Foundation
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
- a capability annotated with the sdi "deterministic foundation for agents" framing, designed to be the lead artifact when ai risk officers join the conversation.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: deterministic-agent-foundation
source_filename: deterministic-agent-foundation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Agent Foundation\n  description: A capability annotated with the SDI \"Deterministic Foundation for Agents\" framing, designed to be the lead artifact when AI risk officers join the conversation.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-agent-foundation-rest\n    description: REST API for Deterministic Agent Foundation.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-agent-foundation-mcp\n    description: MCP server exposing Deterministic Agent Foundation for AI agents.\n    tools:\n    - name: example\n      description: A capability annotated with the SDI \"Deterministic Foundation for Agents\" framing, designed to be the lead artifact when AI risk officers join the conversation.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-agent-foundation-skills\n    description: Agent Skill bundle for Deterministic Agent Foundation.\n    skills:\n    - name: deterministic-agent-foundation\n      description: A capability annotated with the SDI \"Deterministic Foundation for Agents\" framing, designed to be the lead artifact when AI risk officers join the conversation.\n  \
  \    location: file:///opt/naftiko/skills/deterministic-agent-foundation\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability annotated with the SDI \"Deterministic Foundation for Agents\" framing, designed to be the lead artifact when AI risk officers join the conversation.\n        from:\n          sourceNamespace: deterministic-agent-foundation-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-agent-foundation.yaml
tags:
- Naftiko
tools:
- description: A capability annotated with the SDI "Deterministic Foundation for Agents" framing, designed to be the lead artifact when AI risk officers join the conversation.
  hints:
    readOnly: true
  name: example
---
