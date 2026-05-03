---
categories: []
consumed_apis: []
description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool returns task-ready context.
layout: capability
name: M365 Graph Copilot Capability Collection
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
- office 365 / graph capabilities exposing mcp tools, with output shaping (typed outputparameters + jsonpath) so each tool returns task-ready context.
- capabilities
- example op
- governance
slug: m365-graph-copilot-capability-collection
source_filename: m365-graph-copilot-capability-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Graph Copilot Capability Collection\n  description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool returns task-ready context.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-graph-copilot-capability-collection-rest\n    description: REST API for M365 Graph Copilot Capability Collection.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-graph-copilot-capability-collection-mcp\n    description: MCP server exposing M365 Graph Copilot Capability Collection for AI agents.\n    tools:\n    - name: example\n      description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool returns task-ready context.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-graph-copilot-capability-collection-skills\n    description: Agent Skill bundle for M365 Graph Copilot Capability Collection.\n    skills:\n    - name: m365-graph-copilot-capability-collection\n      description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool\
  \ returns task-ready context.\n      location: file:///opt/naftiko/skills/m365-graph-copilot-capability-collection\n      allowed-tools: example\n      tools:\n      - name: example\n        description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool returns task-ready context.\n        from:\n          sourceNamespace: m365-graph-copilot-capability-collection-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-graph-copilot-capability-collection.yaml
tags:
- Naftiko
tools:
- description: Office 365 / Graph capabilities exposing MCP tools, with output shaping (typed outputParameters + JSONPath) so each tool returns task-ready context.
  hints:
    readOnly: true
  name: example
---
