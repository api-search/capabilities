---
categories: []
consumed_apis: []
description: A runtime capability that automates governance evaluation across consumed APIs — every call goes through Spectral + capability-rule + audit pipeline.
layout: capability
name: Governance Automation Runtime Capability
operations:
- description: ''
  method: POST
  name: evaluate
  path: /evaluate
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list rules
- governance
- api integration
- spec-driven integration
- evaluate
- ai
- mcp
- capabilities
- runtime
slug: governance-automation-runtime-capability
source_filename: governance-automation-runtime-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Governance Automation Runtime Capability\n  description: A runtime capability that automates governance evaluation across consumed APIs — every call goes through Spectral + capability-rule + audit pipeline.\n  tags: [Naftiko, Governance, Runtime]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: governance-rules, path: /v1/governance/rules, operations: [{name: list-rules, method: GET}]}\n    - {name: governance-evaluations, path: /v1/governance/evaluations, operations: [{name: evaluate, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: governance-automation-runtime-capability-rest\n    description: REST surface\
  \ for runtime governance.\n    resources:\n    - {name: evaluate, path: /evaluate, operations: [{method: POST, name: evaluate, call: naftiko-control.evaluate}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: governance-automation-runtime-capability-mcp\n    description: MCP for runtime governance.\n    tools:\n    - {name: list-rules, hints: {readOnly: true}, call: naftiko-control.list-rules}\n    - {name: evaluate, call: naftiko-control.evaluate}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: governance-automation-runtime-capability-skills\n    description: Skill for runtime governance.\n    skills:\n    - name: governance-automation-runtime-capability\n      description: Runtime governance automation.\n      location: file:///opt/naftiko/skills/governance-automation-runtime-capability\n      allowed-tools: list-rules,evaluate\n      tools:\n      - {name: list-rules, from: {sourceNamespace: governance-automation-runtime-capability-mcp, action:\
  \ list-rules}}\n      - {name: evaluate, from: {sourceNamespace: governance-automation-runtime-capability-mcp, action: evaluate}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/governance-automation-runtime-capability.yaml
tags:
- Naftiko
- Governance
- Runtime
tools:
- description: ''
  hints:
    readOnly: true
  name: list-rules
- description: ''
  hints: {}
  name: evaluate
---
