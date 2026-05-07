---
categories: []
consumed_apis: []
description: A reference capability articulating the capability-first reusability pattern — capabilities as first-class units composed into higher-order capabilities.
layout: capability
name: Capability First Reusability Reference
operations:
- description: ''
  method: GET
  name: list-capabilities
  path: /capabilities
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- reference
- list capabilities
- ai
- reusability
- capabilities
- api integration
- mcp
- naftiko
- compose
slug: capability-first-reusability-reference
source_filename: capability-first-reusability-reference.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Capability First Reusability Reference\n  description: A reference capability articulating the capability-first reusability pattern — capabilities as first-class units composed into higher-order capabilities.\n  tags: [Naftiko, Reusability, Reference]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: capabilities, path: /v1/capabilities, operations: [{name: list-capabilities, method: GET}]}\n    - name: capability-spec\n      path: /v1/capabilities/{{capability_id}}/spec\n      operations:\n      - {name: get-capability-spec, method: GET, inputParameters: [{name: capability_id, in: path}]}\n    - name: composition\n      path: /v1/capabilities/{{parent_id}}/compose\n\
  \      operations:\n      - {name: compose, method: POST, inputParameters: [{name: parent_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: capability-first-reusability-reference-rest\n    description: REST surface for capability-first composition.\n    resources:\n    - {name: capabilities, path: /capabilities, operations: [{method: GET, name: list-capabilities, call: naftiko-control.list-capabilities}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: capability-first-reusability-reference-mcp\n    description: MCP for capability-first composition.\n    tools:\n    - {name: list-capabilities, hints: {readOnly: true}, call: naftiko-control.list-capabilities}\n    - name: compose\n      inputParameters: [{name: parent_id, type: string, required: true}]\n      call: naftiko-control.compose\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: capability-first-reusability-reference-skills\n    description:\
  \ Skill for the reusability reference.\n    skills:\n    - name: capability-first-reusability-reference\n      description: Capability-first reusability reference.\n      location: file:///opt/naftiko/skills/capability-first-reusability-reference\n      allowed-tools: list-capabilities,compose\n      tools:\n      - {name: list-capabilities, from: {sourceNamespace: capability-first-reusability-reference-mcp, action: list-capabilities}}\n      - {name: compose, from: {sourceNamespace: capability-first-reusability-reference-mcp, action: compose}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/capability-first-reusability-reference.yaml
tags:
- Naftiko
- Reusability
- Reference
tools:
- description: ''
  hints:
    readOnly: true
  name: list-capabilities
- description: ''
  hints: {}
  name: compose
---
