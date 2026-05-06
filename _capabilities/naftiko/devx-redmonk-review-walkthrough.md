---
categories: []
consumed_apis: []
description: A walkthrough capability used to demo Naftiko DevX to RedMonk analysts — exposes a stripped-down, narratable surface.
layout: capability
name: Devx Redmonk Review Walkthrough
operations:
- description: ''
  method: GET
  name: list-capabilities
  path: /capabilities
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- devx
- api integration
- governance
- capabilities
- spec-driven integration
- redmonk
- ai
- mcp
- get capability
- list capabilities
slug: devx-redmonk-review-walkthrough
source_filename: devx-redmonk-review-walkthrough.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Devx Redmonk Review Walkthrough\n  description: A walkthrough capability used to demo Naftiko DevX to RedMonk analysts — exposes a stripped-down, narratable surface.\n  tags: [Naftiko, DevX, RedMonk]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: capabilities, path: /v1/capabilities, operations: [{name: list-capabilities, method: GET}]}\n    - name: capability\n      path: /v1/capabilities/{{capability_id}}\n      operations:\n      - {name: get-capability, method: GET, inputParameters: [{name: capability_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: devx-redmonk-review-walkthrough-rest\n    description:\
  \ REST surface for the analyst walkthrough.\n    resources:\n    - {name: capabilities, path: /capabilities, operations: [{method: GET, name: list-capabilities, call: naftiko-control.list-capabilities}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: devx-redmonk-review-walkthrough-mcp\n    description: MCP for the walkthrough.\n    tools:\n    - {name: list-capabilities, hints: {readOnly: true}, call: naftiko-control.list-capabilities}\n    - name: get-capability\n      hints: {readOnly: true}\n      inputParameters: [{name: capability_id, type: string, required: true}]\n      call: naftiko-control.get-capability\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: devx-redmonk-review-walkthrough-skills\n    description: Skill for the walkthrough.\n    skills:\n    - name: devx-redmonk-review-walkthrough\n      description: RedMonk DevX walkthrough.\n      location: file:///opt/naftiko/skills/devx-redmonk-review-walkthrough\n      allowed-tools:\
  \ list-capabilities,get-capability\n      tools:\n      - {name: list-capabilities, from: {sourceNamespace: devx-redmonk-review-walkthrough-mcp, action: list-capabilities}}\n      - {name: get-capability, from: {sourceNamespace: devx-redmonk-review-walkthrough-mcp, action: get-capability}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/devx-redmonk-review-walkthrough.yaml
tags:
- Naftiko
- DevX
- RedMonk
tools:
- description: ''
  hints:
    readOnly: true
  name: list-capabilities
- description: ''
  hints:
    readOnly: true
  name: get-capability
---
