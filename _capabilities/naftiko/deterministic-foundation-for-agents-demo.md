---
categories: []
consumed_apis: []
description: A demo capability illustrating the deterministic-foundation-for-agents pattern end-to-end with a small, repeatable workflow.
layout: capability
name: Deterministic Foundation For Agents Demo
operations:
- description: ''
  method: POST
  name: run-demo
  path: /demos/{{workflow_id}}/run
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- run demo
- list demos
- api integration
- governance
- capabilities
- spec-driven integration
- deterministic
- ai
- mcp
- demo
slug: deterministic-foundation-for-agents-demo
source_filename: deterministic-foundation-for-agents-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Foundation For Agents Demo\n  description: A demo capability illustrating the deterministic-foundation-for-agents pattern end-to-end with a small, repeatable workflow.\n  tags: [Naftiko, Deterministic, Demo]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: demo-workflows, path: /v1/demos/workflows, operations: [{name: list-demo-workflows, method: GET}]}\n    - name: demo-workflow-run\n      path: '/v1/demos/workflows/{{workflow_id}}/runs'\n      operations:\n      - {name: run-demo-workflow, method: POST, inputParameters: [{name: workflow_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-foundation-for-agents-demo-rest\n\
  \    description: REST surface for the deterministic-foundation demo.\n    resources:\n    - {name: run, path: '/demos/{{workflow_id}}/run', operations: [{method: POST, name: run-demo, inputParameters: [{name: workflow_id, in: path, type: string}], call: naftiko-control.run-demo-workflow}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-foundation-for-agents-demo-mcp\n    description: MCP for the demo.\n    tools:\n    - {name: list-demos, hints: {readOnly: true}, call: naftiko-control.list-demo-workflows}\n    - name: run-demo\n      inputParameters: [{name: workflow_id, type: string, required: true}]\n      call: naftiko-control.run-demo-workflow\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-foundation-for-agents-demo-skills\n    description: Skill for the demo.\n    skills:\n    - name: deterministic-foundation-for-agents-demo\n      description: Deterministic-foundation demo.\n      location: file:///opt/naftiko/skills/deterministic-foundation-for-agents-demo\n\
  \      allowed-tools: list-demos,run-demo\n      tools:\n      - {name: list-demos, from: {sourceNamespace: deterministic-foundation-for-agents-demo-mcp, action: list-demos}}\n      - {name: run-demo, from: {sourceNamespace: deterministic-foundation-for-agents-demo-mcp, action: run-demo}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-foundation-for-agents-demo.yaml
tags:
- Naftiko
- Deterministic
- Demo
tools:
- description: ''
  hints:
    readOnly: true
  name: list-demos
- description: ''
  hints: {}
  name: run-demo
---
