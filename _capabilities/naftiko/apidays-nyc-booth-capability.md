---
categories: []
consumed_apis: []
description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
layout: capability
name: Apidays Nyc Booth Capability
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
- a built -shaped capability used as the apidays nyc re-engagement hook — designed for booth conversation, not screen-share.
- naftiko
- api integration
- spec-driven integration
- capabilities
- example op
- governance
slug: apidays-nyc-booth-capability
source_filename: apidays-nyc-booth-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apidays Nyc Booth Capability\n  description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apidays-nyc-booth-capability-rest\n    description: REST API for Apidays Nyc Booth Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n      \
  \  name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apidays-nyc-booth-capability-mcp\n    description: MCP server exposing Apidays Nyc Booth Capability for AI agents.\n    tools:\n    - name: example\n      description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: apidays-nyc-booth-capability-skills\n    description: Agent Skill bundle for Apidays Nyc Booth Capability.\n    skills:\n    - name: apidays-nyc-booth-capability\n      description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.\n      location: file:///opt/naftiko/skills/apidays-nyc-booth-capability\n      allowed-tools: example\n      tools:\n      - name: example\n\
  \        description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.\n        from:\n          sourceNamespace: apidays-nyc-booth-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apidays-nyc-booth-capability.yaml
tags:
- Naftiko
tools:
- description: A built -shaped capability used as the apidays NYC re-engagement hook — designed for booth conversation, not screen-share.
  hints:
    readOnly: true
  name: example
---
