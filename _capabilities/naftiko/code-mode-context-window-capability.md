---
categories: []
consumed_apis: []
description: 'A capability that exposes "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
layout: capability
name: Code Mode Context Window Capability
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
- 'a capability that exposes "code mode" rightsizing pattern as a naftiko mcp tool: feed it a base openapi + a target task, get back the right-sized agent context.'
slug: code-mode-context-window-capability
source_filename: code-mode-context-window-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Code Mode Context Window Capability\n  description: 'A capability that exposes \"code mode\" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: code-mode-context-window-capability-rest\n    description: REST API for Code Mode Context Window Capability.\n    resources:\n    - name: example\n     \
  \ path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: code-mode-context-window-capability-mcp\n    description: MCP server exposing Code Mode Context Window Capability for AI agents.\n    tools:\n    - name: example\n      description: 'A capability that exposes \"code mode\" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: code-mode-context-window-capability-skills\n    description: Agent Skill bundle for Code Mode Context Window Capability.\n    skills:\n    - name: code-mode-context-window-capability\n      description: 'A capability that exposes \"code mode\" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task,\
  \ get back the right-sized agent context.'\n      location: file:///opt/naftiko/skills/code-mode-context-window-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: 'A capability that exposes \"code mode\" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'\n        from:\n          sourceNamespace: code-mode-context-window-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/code-mode-context-window-capability.yaml
tags:
- Naftiko
tools:
- description: 'A capability that exposes "code mode" rightsizing pattern as a Naftiko MCP tool: feed it a base OpenAPI + a target task, get back the right-sized agent context.'
  hints:
    readOnly: true
  name: example
---
