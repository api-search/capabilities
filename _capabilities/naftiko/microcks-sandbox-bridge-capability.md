---
categories: []
consumed_apis: []
description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
layout: capability
name: Microcks Sandbox Bridge Capability
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
- a capability that takes a naftiko-published openapi spec, generates microcks sandboxes via git, and returns runnable mock urls as mcp-callable tools.
- mcp
- example op
- example
- governance
slug: microcks-sandbox-bridge-capability
source_filename: microcks-sandbox-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microcks Sandbox Bridge Capability\n  description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microcks-sandbox-bridge-capability-rest\n    description: REST API for Microcks Sandbox Bridge Capability.\n    resources:\n    - name: example\n      path: /example\n \
  \     operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microcks-sandbox-bridge-capability-mcp\n    description: MCP server exposing Microcks Sandbox Bridge Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microcks-sandbox-bridge-capability-skills\n    description: Agent Skill bundle for Microcks Sandbox Bridge Capability.\n    skills:\n    - name: microcks-sandbox-bridge-capability\n      description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.\n      location:\
  \ file:///opt/naftiko/skills/microcks-sandbox-bridge-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.\n        from:\n          sourceNamespace: microcks-sandbox-bridge-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microcks-sandbox-bridge-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that takes a Naftiko-published OpenAPI spec, generates Microcks sandboxes via Git, and returns runnable mock URLs as MCP-callable tools.
  hints:
    readOnly: true
  name: example
---
