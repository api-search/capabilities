---
categories: []
consumed_apis: []
description: A capability designed to run end-to-end via the Naftiko CLI without any portal interaction — fully scriptable for CI use.
layout: capability
name: Cli Only Runnable Capability
operations:
- description: ''
  method: POST
  name: start-run
  path: /runs
- description: ''
  method: GET
  name: get-run
  path: /runs/{{run_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- start run
- cli
- spec-driven integration
- mcp
- capabilities
- naftiko
- api integration
- get run
- runnable
- governance
- ai
slug: cli-only-runnable-capability
source_filename: cli-only-runnable-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cli Only Runnable Capability\n  description: A capability designed to run end-to-end via the Naftiko CLI without any portal interaction — fully scriptable for CI use.\n  tags: [Naftiko, CLI, Runnable]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: capability-runs, path: /v1/runs, operations: [{name: start-run, method: POST}]}\n    - name: run\n      path: /v1/runs/{{run_id}}\n      operations:\n      - {name: get-run, method: GET, inputParameters: [{name: run_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: cli-only-runnable-capability-rest\n    description: REST surface for CLI-driven runs.\n    resources:\n\
  \    - {name: run, path: /runs, operations: [{method: POST, name: start-run, call: naftiko-control.start-run}]}\n    - name: run-status\n      path: /runs/{{run_id}}\n      operations:\n      - {method: GET, name: get-run, inputParameters: [{name: run_id, in: path, type: string}], call: naftiko-control.get-run}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cli-only-runnable-capability-mcp\n    description: MCP for CLI runs.\n    tools:\n    - {name: start-run, call: naftiko-control.start-run}\n    - name: get-run\n      hints: {readOnly: true}\n      inputParameters: [{name: run_id, type: string, required: true}]\n      call: naftiko-control.get-run\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cli-only-runnable-capability-skills\n    description: Skill for CLI runs.\n    skills:\n    - name: cli-only-runnable-capability\n      description: CLI-only runnable capability.\n      location: file:///opt/naftiko/skills/cli-only-runnable-capability\n\
  \      allowed-tools: start-run,get-run\n      tools:\n      - {name: start-run, from: {sourceNamespace: cli-only-runnable-capability-mcp, action: start-run}}\n      - {name: get-run, from: {sourceNamespace: cli-only-runnable-capability-mcp, action: get-run}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cli-only-runnable-capability.yaml
tags:
- Naftiko
- CLI
- Runnable
tools:
- description: ''
  hints: {}
  name: start-run
- description: ''
  hints:
    readOnly: true
  name: get-run
---
