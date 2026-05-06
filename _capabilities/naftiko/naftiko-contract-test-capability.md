---
categories: []
consumed_apis: []
description: A capability that runs contract tests against a target capability spec, comparing live runtime responses against the OpenAPI/AsyncAPI contract.
layout: capability
name: Naftiko Contract Test Capability
operations:
- description: ''
  method: POST
  name: run-contract-test
  path: /run
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- get result
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- run contract test
- contract testing
slug: naftiko-contract-test-capability
source_filename: naftiko-contract-test-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Naftiko Contract Test Capability\n  description: A capability that runs contract tests against a target capability spec, comparing live runtime responses against the OpenAPI/AsyncAPI contract.\n  tags: [Naftiko, Contract Testing]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-test\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: contract-tests, path: /v1/contract-tests, operations: [{name: run-contract-test, method: POST}]}\n    - name: contract-test\n      path: /v1/contract-tests/{{run_id}}\n      operations:\n      - {name: get-contract-test-result, method: GET, inputParameters: [{name: run_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: naftiko-contract-test-capability-rest\n\
  \    description: REST surface for contract tests.\n    resources:\n    - {name: run, path: /run, operations: [{method: POST, name: run-contract-test, call: naftiko-test.run-contract-test}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: naftiko-contract-test-capability-mcp\n    description: MCP for contract tests.\n    tools:\n    - {name: run-contract-test, call: naftiko-test.run-contract-test}\n    - name: get-result\n      hints: {readOnly: true}\n      inputParameters: [{name: run_id, type: string, required: true}]\n      call: naftiko-test.get-contract-test-result\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: naftiko-contract-test-capability-skills\n    description: Skill for contract tests.\n    skills:\n    - name: naftiko-contract-test-capability\n      description: Naftiko contract testing.\n      location: file:///opt/naftiko/skills/naftiko-contract-test-capability\n      allowed-tools: run-contract-test,get-result\n      tools:\n\
  \      - {name: run-contract-test, from: {sourceNamespace: naftiko-contract-test-capability-mcp, action: run-contract-test}}\n      - {name: get-result, from: {sourceNamespace: naftiko-contract-test-capability-mcp, action: get-result}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/naftiko-contract-test-capability.yaml
tags:
- Naftiko
- Contract Testing
tools:
- description: ''
  hints: {}
  name: run-contract-test
- description: ''
  hints:
    readOnly: true
  name: get-result
---
