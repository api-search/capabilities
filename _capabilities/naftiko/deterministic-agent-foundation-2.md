---
categories: []
consumed_apis: []
description: A foundational capability defining the deterministic-agent contract — same input, same context, same shaped output, with the contract surfaced as REST + MCP.
layout: capability
name: Deterministic Agent Foundation 2
operations:
- description: ''
  method: POST
  name: start-agent-run
  path: /run
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- agent
- deterministic
- get agent run
- mcp
- foundation
- capabilities
- start agent run
- naftiko
- api integration
- governance
- ai
slug: deterministic-agent-foundation-2
source_filename: deterministic-agent-foundation-2.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Agent Foundation 2\n  description: A foundational capability defining the deterministic-agent contract — same input, same context, same shaped output, with the contract surfaced as REST + MCP.\n  tags: [Naftiko, Deterministic, Agent, Foundation]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: agent-runs, path: /v1/agent-runs, operations: [{name: start-agent-run, method: POST}]}\n    - name: agent-run\n      path: /v1/agent-runs/{{run_id}}\n      operations:\n      - {name: get-agent-run, method: GET, inputParameters: [{name: run_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-agent-foundation-2-rest\n\
  \    description: REST surface for the deterministic-agent contract.\n    resources:\n    - {name: run, path: /run, operations: [{method: POST, name: start-agent-run, call: naftiko-control.start-agent-run}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-agent-foundation-2-mcp\n    description: MCP for deterministic-agent runs.\n    tools:\n    - {name: start-agent-run, call: naftiko-control.start-agent-run}\n    - name: get-agent-run\n      hints: {readOnly: true}\n      inputParameters: [{name: run_id, type: string, required: true}]\n      call: naftiko-control.get-agent-run\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-agent-foundation-2-skills\n    description: Skill for deterministic-agent foundation.\n    skills:\n    - name: deterministic-agent-foundation-2\n      description: Deterministic-agent foundation.\n      location: file:///opt/naftiko/skills/deterministic-agent-foundation-2\n      allowed-tools:\
  \ start-agent-run,get-agent-run\n      tools:\n      - {name: start-agent-run, from: {sourceNamespace: deterministic-agent-foundation-2-mcp, action: start-agent-run}}\n      - {name: get-agent-run, from: {sourceNamespace: deterministic-agent-foundation-2-mcp, action: get-agent-run}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-agent-foundation-2.yaml
tags:
- Naftiko
- Deterministic
- Agent
- Foundation
tools:
- description: ''
  hints: {}
  name: start-agent-run
- description: ''
  hints:
    readOnly: true
  name: get-agent-run
---
