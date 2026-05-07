---
categories: []
consumed_apis: []
description: A capability turning the API-first design surface into a governance touchpoint — every spec change runs through capability-level rules and emits a governance record.
layout: capability
name: Api First As Governance Surface Capability
operations:
- description: Lint a spec, evaluate capability-level rules, emit a governance record.
  method: POST
  name: run-governance-gate
  path: /governance/gate
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- run governance gate
- governance
- spec-driven integration
- api-first
- lint a spec, evaluate capability-level rules, emit a governance record.
- ai
- capabilities
- run governance gate on a spec change.
- api integration
- mcp
- naftiko
slug: api-first-as-governance-surface-capability
source_filename: api-first-as-governance-surface-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Api First As Governance Surface Capability\n  description: A capability turning the API-first design surface into a governance touchpoint — every spec change runs through capability-level rules and emits a governance record.\n  tags: [Naftiko, API-First, Governance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: spectral-env\n  keys: {SPECTRAL_TOKEN: SPECTRAL_TOKEN}\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: spectral\n    type: http\n    baseUri: https://api.stoplight.io\n    authentication: {type: bearer, token: '{{SPECTRAL_TOKEN}}'}\n    resources:\n    - {name: lint, path: '/v1/projects/{{project_id}}/lint', operations: [{name: lint-spec, method: POST, inputParameters: [{name: project_id, in: path}]}]}\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n\
  \    resources:\n    - name: governance-records\n      path: /v1/governance/records\n      operations: [{name: create-governance-record, method: POST}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: api-first-as-governance-surface-capability-rest\n    description: REST surface running governance against an OpenAPI spec change.\n    resources:\n    - name: gate\n      path: /governance/gate\n      operations:\n      - method: POST\n        name: run-governance-gate\n        description: Lint a spec, evaluate capability-level rules, emit a governance record.\n        call: spectral.lint-spec\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: api-first-as-governance-surface-capability-mcp\n    description: MCP for governance gating during API-first design.\n    tools:\n    - {name: run-governance-gate, description: Run governance gate on a spec change., call: spectral.lint-spec}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n \
  \   namespace: api-first-as-governance-surface-capability-skills\n    description: Skill for governance gating.\n    skills:\n    - name: api-first-as-governance-surface-capability\n      description: Governance gate for API-first design.\n      location: file:///opt/naftiko/skills/api-first-as-governance-surface-capability\n      allowed-tools: run-governance-gate\n      tools:\n      - {name: run-governance-gate, from: {sourceNamespace: api-first-as-governance-surface-capability-mcp, action: run-governance-gate}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/api-first-as-governance-surface-capability.yaml
tags:
- Naftiko
- API-First
- Governance
tools:
- description: Run governance gate on a spec change.
  hints: {}
  name: run-governance-gate
---
