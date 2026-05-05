---
categories: []
consumed_apis: []
description: A capability composition demonstrating API reusability — common steps factored into reusable capabilities composable into higher-order ones.
layout: capability
name: Api Reusability Composition
operations:
- description: ''
  method: POST
  name: compose-capability
  path: /compose/{{parent_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- compose capability
- list capabilities
- mcp
- capabilities
- naftiko
- reusability
- api integration
- governance
- ai
- composition
slug: api-reusability-composition
source_filename: api-reusability-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api Reusability Composition\n  description: A capability composition demonstrating API reusability — common steps factored into reusable capabilities composable into higher-order ones.\n  tags: [Naftiko, Reusability, Composition]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - name: capabilities\n      path: /v1/capabilities\n      operations: [{name: list-capabilities, method: GET}]\n    - name: composition\n      path: /v1/capabilities/{{parent_id}}/compose\n      operations:\n      - {name: compose-capability, method: POST, inputParameters: [{name: parent_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-reusability-composition-rest\n\
  \    description: REST surface for composing reusable capabilities.\n    resources:\n    - name: compose\n      path: /compose/{{parent_id}}\n      operations:\n      - method: POST\n        name: compose-capability\n        inputParameters: [{name: parent_id, in: path, type: string}]\n        call: naftiko-control.compose-capability\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-reusability-composition-mcp\n    description: MCP for capability composition.\n    tools:\n    - {name: list-capabilities, hints: {readOnly: true}, call: naftiko-control.list-capabilities}\n    - name: compose-capability\n      inputParameters: [{name: parent_id, type: string, required: true}]\n      call: naftiko-control.compose-capability\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: api-reusability-composition-skills\n    description: Skill for composition.\n    skills:\n    - name: api-reusability-composition\n      description: Compose reusable capabilities.\n\
  \      location: file:///opt/naftiko/skills/api-reusability-composition\n      allowed-tools: list-capabilities,compose-capability\n      tools:\n      - {name: list-capabilities, from: {sourceNamespace: api-reusability-composition-mcp, action: list-capabilities}}\n      - {name: compose-capability, from: {sourceNamespace: api-reusability-composition-mcp, action: compose-capability}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-reusability-composition.yaml
tags:
- Naftiko
- Reusability
- Composition
tools:
- description: ''
  hints:
    readOnly: true
  name: list-capabilities
- description: ''
  hints: {}
  name: compose-capability
---
