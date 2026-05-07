---
categories: []
consumed_apis: []
description: A capability over a deterministic SDK pipeline (Speakeasy / Stainless / Fern) that regenerates SDKs on every spec change with a verifiable hash.
layout: capability
name: Deterministic Sdk Pipeline Capability
operations:
- description: ''
  method: POST
  name: generate-sdks
  path: /generate/{{workspace_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list workspaces
- governance
- spec-driven integration
- speakeasy
- pipeline
- sdk
- ai
- capabilities
- api integration
- mcp
- naftiko
- generate sdks
slug: deterministic-sdk-pipeline-capability
source_filename: deterministic-sdk-pipeline-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Sdk Pipeline Capability\n  description: A capability over a deterministic SDK pipeline (Speakeasy / Stainless / Fern) that regenerates SDKs on every spec change with a verifiable hash.\n  tags: [Naftiko, SDK, Pipeline, Speakeasy]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: speakeasy-env\n  keys: {SPEAKEASY_API_KEY: SPEAKEASY_API_KEY}\ncapability:\n  consumes:\n  - namespace: speakeasy\n    type: http\n    baseUri: https://api.speakeasy.com\n    authentication: {type: bearer, token: '{{SPEAKEASY_API_KEY}}'}\n    resources:\n    - {name: workspaces, path: /v1/workspaces, operations: [{name: list-workspaces, method: GET}]}\n    - name: sdk-generation\n      path: '/v1/workspaces/{{workspace_id}}/generate'\n      operations:\n      - {name: generate-sdks, method: POST, inputParameters: [{name: workspace_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace:\
  \ deterministic-sdk-pipeline-capability-rest\n    description: REST surface for SDK generation.\n    resources:\n    - {name: generate, path: '/generate/{{workspace_id}}', operations: [{method: POST, name: generate-sdks, inputParameters: [{name: workspace_id, in: path, type: string}], call: speakeasy.generate-sdks}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-sdk-pipeline-capability-mcp\n    description: MCP for SDK pipeline.\n    tools:\n    - {name: list-workspaces, hints: {readOnly: true}, call: speakeasy.list-workspaces}\n    - name: generate-sdks\n      inputParameters: [{name: workspace_id, type: string, required: true}]\n      call: speakeasy.generate-sdks\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-sdk-pipeline-capability-skills\n    description: Skill for SDK pipeline.\n    skills:\n    - name: deterministic-sdk-pipeline-capability\n      description: Deterministic SDK pipeline.\n      location: file:///opt/naftiko/skills/deterministic-sdk-pipeline-capability\n\
  \      allowed-tools: list-workspaces,generate-sdks\n      tools:\n      - {name: list-workspaces, from: {sourceNamespace: deterministic-sdk-pipeline-capability-mcp, action: list-workspaces}}\n      - {name: generate-sdks, from: {sourceNamespace: deterministic-sdk-pipeline-capability-mcp, action: generate-sdks}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-sdk-pipeline-capability.yaml
tags:
- Naftiko
- SDK
- Pipeline
- Speakeasy
tools:
- description: ''
  hints:
    readOnly: true
  name: list-workspaces
- description: ''
  hints: {}
  name: generate-sdks
---
