---
categories: []
consumed_apis: []
description: A capability illustrating composition over an arbitrary set of upstream APIs — generic multi-API orchestration with a single shaped response.
layout: capability
name: Multi Api Composition Capability
operations:
- description: ''
  method: POST
  name: run-composition
  path: /run/{{composition_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- run composition
- api integration
- governance
- capabilities
- spec-driven integration
- ai
- mcp
- multi-api
- list compositions
- composition
slug: multi-api-composition-capability
source_filename: multi-api-composition-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Multi Api Composition Capability\n  description: A capability illustrating composition over an arbitrary set of upstream APIs — generic multi-API orchestration with a single shaped response.\n  tags: [Naftiko, Composition, Multi-API]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: compositions, path: /v1/compositions, operations: [{name: list-compositions, method: GET}]}\n    - name: composition-run\n      path: '/v1/compositions/{{composition_id}}/run'\n      operations:\n      - {name: run-composition, method: POST, inputParameters: [{name: composition_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: multi-api-composition-capability-rest\n\
  \    description: REST surface for multi-API composition.\n    resources:\n    - {name: run, path: '/run/{{composition_id}}', operations: [{method: POST, name: run-composition, inputParameters: [{name: composition_id, in: path, type: string}], call: naftiko-control.run-composition}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: multi-api-composition-capability-mcp\n    description: MCP for composition.\n    tools:\n    - {name: list-compositions, hints: {readOnly: true}, call: naftiko-control.list-compositions}\n    - name: run-composition\n      inputParameters: [{name: composition_id, type: string, required: true}]\n      call: naftiko-control.run-composition\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: multi-api-composition-capability-skills\n    description: Skill for composition.\n    skills:\n    - name: multi-api-composition-capability\n      description: Multi-API composition.\n      location: file:///opt/naftiko/skills/multi-api-composition-capability\n\
  \      allowed-tools: list-compositions,run-composition\n      tools:\n      - {name: list-compositions, from: {sourceNamespace: multi-api-composition-capability-mcp, action: list-compositions}}\n      - {name: run-composition, from: {sourceNamespace: multi-api-composition-capability-mcp, action: run-composition}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/multi-api-composition-capability.yaml
tags:
- Naftiko
- Composition
- Multi-API
tools:
- description: ''
  hints:
    readOnly: true
  name: list-compositions
- description: ''
  hints: {}
  name: run-composition
---
