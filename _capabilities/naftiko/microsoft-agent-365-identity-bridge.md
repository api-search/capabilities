---
categories: []
consumed_apis: []
description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing a per-call audit record for agent calls.
layout: capability
name: Microsoft Agent 365 Identity Bridge
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
- a capability that consumes microsoft agent 365 identity claims and signs them into existing api governance layer, producing a per-call audit record for agent calls.
- governance
slug: microsoft-agent-365-identity-bridge
source_filename: microsoft-agent-365-identity-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microsoft Agent 365 Identity Bridge\n  description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing a per-call audit record for agent calls.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microsoft-agent-365-identity-bridge-rest\n    description: REST API for Microsoft Agent 365 Identity Bridge.\n    resources:\n    - name: example\n     \
  \ path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microsoft-agent-365-identity-bridge-mcp\n    description: MCP server exposing Microsoft Agent 365 Identity Bridge for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing a per-call audit record for agent calls.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microsoft-agent-365-identity-bridge-skills\n    description: Agent Skill bundle for Microsoft Agent 365 Identity Bridge.\n    skills:\n    - name: microsoft-agent-365-identity-bridge\n      description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing\
  \ a per-call audit record for agent calls.\n      location: file:///opt/naftiko/skills/microsoft-agent-365-identity-bridge\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing a per-call audit record for agent calls.\n        from:\n          sourceNamespace: microsoft-agent-365-identity-bridge-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microsoft-agent-365-identity-bridge.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes Microsoft Agent 365 identity claims and signs them into existing API governance layer, producing a per-call audit record for agent calls.
  hints:
    readOnly: true
  name: example
---
