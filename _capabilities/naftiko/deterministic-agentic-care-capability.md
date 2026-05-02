---
categories: []
consumed_apis: []
description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
layout: capability
name: Deterministic Agentic Care Capability
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
- a capability annotated against sdi "deterministic foundation for agents" as the agentic-care thought-leadership hook.
- mcp
- example op
- example
- governance
slug: deterministic-agentic-care-capability
source_filename: deterministic-agentic-care-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Agentic Care Capability\n  description: A capability annotated against SDI \"Deterministic Foundation for Agents\" as the agentic-care thought-leadership hook.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-agentic-care-capability-rest\n    description: REST API for Deterministic Agentic Care Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n   \
  \   - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-agentic-care-capability-mcp\n    description: MCP server exposing Deterministic Agentic Care Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability annotated against SDI \"Deterministic Foundation for Agents\" as the agentic-care thought-leadership hook.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-agentic-care-capability-skills\n    description: Agent Skill bundle for Deterministic Agentic Care Capability.\n    skills:\n    - name: deterministic-agentic-care-capability\n      description: A capability annotated against SDI \"Deterministic Foundation for Agents\" as the agentic-care thought-leadership hook.\n      location: file:///opt/naftiko/skills/deterministic-agentic-care-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability annotated against SDI \"Deterministic Foundation for Agents\" as the agentic-care thought-leadership hook.\n        from:\n          sourceNamespace: deterministic-agentic-care-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-agentic-care-capability.yaml
tags:
- Naftiko
tools:
- description: A capability annotated against SDI "Deterministic Foundation for Agents" as the agentic-care thought-leadership hook.
  hints:
    readOnly: true
  name: example
---
