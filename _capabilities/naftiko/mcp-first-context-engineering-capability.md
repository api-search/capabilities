---
categories: []
consumed_apis: []
description: A capability designed MCP-first — context engineering surface (token budget, ranking, retrieval) exposed as primary MCP tools.
layout: capability
name: Mcp First Context Engineering Capability
operations:
- description: ''
  method: POST
  name: build-context
  path: /context/build
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- context engineering
- build context
- ai
- capabilities
- api integration
- get context build
- mcp
- naftiko
slug: mcp-first-context-engineering-capability
source_filename: mcp-first-context-engineering-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mcp First Context Engineering Capability\n  description: A capability designed MCP-first — context engineering surface (token budget, ranking, retrieval) exposed as primary MCP tools.\n  tags: [Naftiko, MCP, Context Engineering]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-context\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: context-builds, path: /v1/context/builds, operations: [{name: build-context, method: POST}]}\n    - name: context-build\n      path: /v1/context/builds/{{build_id}}\n      operations:\n      - {name: get-context-build, method: GET, inputParameters: [{name: build_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mcp-first-context-engineering-capability-rest\n\
  \    description: REST surface for MCP-first context engineering.\n    resources:\n    - {name: build, path: /context/build, operations: [{method: POST, name: build-context, call: naftiko-context.build-context}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mcp-first-context-engineering-capability-mcp\n    description: MCP for context engineering.\n    tools:\n    - {name: build-context, call: naftiko-context.build-context}\n    - name: get-context-build\n      hints: {readOnly: true}\n      inputParameters: [{name: build_id, type: string, required: true}]\n      call: naftiko-context.get-context-build\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mcp-first-context-engineering-capability-skills\n    description: Skill for context engineering.\n    skills:\n    - name: mcp-first-context-engineering-capability\n      description: MCP-first context engineering.\n      location: file:///opt/naftiko/skills/mcp-first-context-engineering-capability\n\
  \      allowed-tools: build-context,get-context-build\n      tools:\n      - {name: build-context, from: {sourceNamespace: mcp-first-context-engineering-capability-mcp, action: build-context}}\n      - {name: get-context-build, from: {sourceNamespace: mcp-first-context-engineering-capability-mcp, action: get-context-build}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mcp-first-context-engineering-capability.yaml
tags:
- Naftiko
- MCP
- Context Engineering
tools:
- description: ''
  hints: {}
  name: build-context
- description: ''
  hints:
    readOnly: true
  name: get-context-build
---
