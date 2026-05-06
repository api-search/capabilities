---
categories: []
consumed_apis: []
description: A capability over the Continuous Compliance Framework (CCF) that runs continuous control checks against capability deployments and emits compliance events.
layout: capability
name: Ccf Continuous Compliance Capability
operations:
- description: ''
  method: POST
  name: assess
  path: /assess
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- run assessment
- assess
- list controls
- compliance
- api integration
- governance
- spec-driven integration
- ai
- mcp
- get assessment
- capabilities
- ccf
slug: ccf-continuous-compliance-capability
source_filename: ccf-continuous-compliance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ccf Continuous Compliance Capability\n  description: A capability over the Continuous Compliance Framework (CCF) that runs continuous control checks against capability deployments and emits compliance events.\n  tags: [Naftiko, CCF, Compliance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: ccf-env\n  keys: {CCF_HOST: CCF_HOST, CCF_TOKEN: CCF_TOKEN}\ncapability:\n  consumes:\n  - namespace: ccf\n    type: http\n    baseUri: https://{{CCF_HOST}}\n    authentication: {type: bearer, token: '{{CCF_TOKEN}}'}\n    resources:\n    - {name: controls, path: /api/v1/controls, operations: [{name: list-controls, method: GET}]}\n    - {name: assessments, path: /api/v1/assessments, operations: [{name: run-assessment, method: POST}]}\n    - name: assessment\n      path: /api/v1/assessments/{{assessment_id}}\n      operations:\n      - {name: get-assessment, method: GET, inputParameters: [{name: assessment_id, in: path}]}\n \
  \ exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ccf-continuous-compliance-capability-rest\n    description: REST surface for continuous compliance checks.\n    resources:\n    - {name: assess, path: /assess, operations: [{method: POST, name: assess, call: ccf.run-assessment}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ccf-continuous-compliance-capability-mcp\n    description: MCP for continuous compliance.\n    tools:\n    - {name: list-controls, hints: {readOnly: true}, call: ccf.list-controls}\n    - {name: run-assessment, call: ccf.run-assessment}\n    - name: get-assessment\n      hints: {readOnly: true}\n      inputParameters: [{name: assessment_id, type: string, required: true}]\n      call: ccf.get-assessment\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ccf-continuous-compliance-capability-skills\n    description: Skill for continuous compliance.\n    skills:\n    - name: ccf-continuous-compliance-capability\n\
  \      description: CCF continuous compliance.\n      location: file:///opt/naftiko/skills/ccf-continuous-compliance-capability\n      allowed-tools: list-controls,run-assessment,get-assessment\n      tools:\n      - {name: list-controls, from: {sourceNamespace: ccf-continuous-compliance-capability-mcp, action: list-controls}}\n      - {name: run-assessment, from: {sourceNamespace: ccf-continuous-compliance-capability-mcp, action: run-assessment}}\n      - {name: get-assessment, from: {sourceNamespace: ccf-continuous-compliance-capability-mcp, action: get-assessment}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ccf-continuous-compliance-capability.yaml
tags:
- Naftiko
- CCF
- Compliance
tools:
- description: ''
  hints:
    readOnly: true
  name: list-controls
- description: ''
  hints: {}
  name: run-assessment
- description: ''
  hints:
    readOnly: true
  name: get-assessment
---
