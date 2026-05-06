---
categories: []
consumed_apis: []
description: A demo capability simulating Fortune 50 fleet-scale deployment of Naftiko capabilities — bulk capability registration and parallel deploys.
layout: capability
name: Fortune50 Fleet Scale Demo
operations:
- description: ''
  method: POST
  name: bulk-register-capabilities
  path: /bulk-register
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- bulk register capabilities
- fortune 50
- scale
- trigger deployment
- api integration
- capabilities
- ai
- governance
- spec-driven integration
- mcp
- demo
slug: fortune50-fleet-scale-demo
source_filename: fortune50-fleet-scale-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Fortune50 Fleet Scale Demo\n  description: A demo capability simulating Fortune 50 fleet-scale deployment of Naftiko capabilities — bulk capability registration and parallel deploys.\n  tags: [Naftiko, Fortune 50, Demo, Scale]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: capabilities-bulk, path: /v1/capabilities/bulk, operations: [{name: bulk-register, method: POST}]}\n    - {name: deployments, path: /v1/deployments, operations: [{name: trigger-deployment, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: fortune50-fleet-scale-demo-rest\n    description: REST surface for fleet-scale demo.\n    resources:\n\
  \    - {name: bulk, path: /bulk-register, operations: [{method: POST, name: bulk-register-capabilities, call: naftiko-control.bulk-register}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: fortune50-fleet-scale-demo-mcp\n    description: MCP for fleet-scale demo.\n    tools:\n    - {name: bulk-register-capabilities, call: naftiko-control.bulk-register}\n    - {name: trigger-deployment, call: naftiko-control.trigger-deployment}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: fortune50-fleet-scale-demo-skills\n    description: Skill for fleet-scale demo.\n    skills:\n    - name: fortune50-fleet-scale-demo\n      description: Fortune 50 fleet-scale demo.\n      location: file:///opt/naftiko/skills/fortune50-fleet-scale-demo\n      allowed-tools: bulk-register-capabilities,trigger-deployment\n      tools:\n      - {name: bulk-register-capabilities, from: {sourceNamespace: fortune50-fleet-scale-demo-mcp, action: bulk-register-capabilities}}\n \
  \     - {name: trigger-deployment, from: {sourceNamespace: fortune50-fleet-scale-demo-mcp, action: trigger-deployment}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/fortune50-fleet-scale-demo.yaml
tags:
- Naftiko
- Fortune 50
- Demo
- Scale
tools:
- description: ''
  hints: {}
  name: bulk-register-capabilities
- description: ''
  hints: {}
  name: trigger-deployment
---
