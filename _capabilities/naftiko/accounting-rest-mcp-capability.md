---
categories: []
consumed_apis: []
description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.
layout: capability
name: Accounting Rest Mcp Capability
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
- a accounting-api capability (rest + mcp dual exposure) wrapping a representative endpoint, brought as the apidays nyc follow-on artifact.
slug: accounting-rest-mcp-capability
source_filename: accounting-rest-mcp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Accounting Rest Mcp Capability\n  description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: accounting-rest-mcp-capability-rest\n    description: REST API for Accounting Rest Mcp Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      -\
  \ method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: accounting-rest-mcp-capability-mcp\n    description: MCP server exposing Accounting Rest Mcp Capability for AI agents.\n    tools:\n    - name: example\n      description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: accounting-rest-mcp-capability-skills\n    description: Agent Skill bundle for Accounting Rest Mcp Capability.\n    skills:\n    - name: accounting-rest-mcp-capability\n      description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.\n      location: file:///opt/naftiko/skills/accounting-rest-mcp-capability\n   \
  \   allowed-tools: example\n      tools:\n      - name: example\n        description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.\n        from:\n          sourceNamespace: accounting-rest-mcp-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/accounting-rest-mcp-capability.yaml
tags:
- Naftiko
tools:
- description: A accounting-API capability (REST + MCP dual exposure) wrapping a representative endpoint, brought as the apidays NYC follow-on artifact.
  hints:
    readOnly: true
  name: example
---
