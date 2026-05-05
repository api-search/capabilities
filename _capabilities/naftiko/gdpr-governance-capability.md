---
categories: []
consumed_apis: []
description: A governance capability that enforces GDPR data-subject rights (access, erasure, portability) on top of any consumer API.
layout: capability
name: Gdpr Governance Capability
operations:
- description: ''
  method: POST
  name: create-dsr
  path: /dsr
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- create dsr
- list dsr
- gdpr
- mcp
- capabilities
- naftiko
- api integration
- governance
- ai
- privacy
- get dsr
slug: gdpr-governance-capability
source_filename: gdpr-governance-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gdpr Governance Capability\n  description: A governance capability that enforces GDPR data-subject rights (access, erasure, portability) on top of any consumer API.\n  tags: [Naftiko, GDPR, Privacy]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: onetrust-env\n  keys: {ONETRUST_HOST: ONETRUST_HOST, ONETRUST_TOKEN: ONETRUST_TOKEN}\ncapability:\n  consumes:\n  - namespace: onetrust\n    type: http\n    baseUri: https://{{ONETRUST_HOST}}\n    authentication: {type: bearer, token: '{{ONETRUST_TOKEN}}'}\n    resources:\n    - {name: dsr-requests, path: /api/datasubject/v3/requests, operations: [{name: create-dsr-request, method: POST}, {name: list-dsr-requests, method: GET}]}\n    - name: dsr-request\n      path: /api/datasubject/v3/requests/{{request_id}}\n      operations:\n      - {name: get-dsr-request, method: GET, inputParameters: [{name: request_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n\
  \    port: 8080\n    namespace: gdpr-governance-capability-rest\n    description: REST surface for GDPR DSR requests.\n    resources:\n    - {name: dsr, path: /dsr, operations: [{method: POST, name: create-dsr, call: onetrust.create-dsr-request}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gdpr-governance-capability-mcp\n    description: MCP for GDPR DSR.\n    tools:\n    - {name: create-dsr, call: onetrust.create-dsr-request}\n    - {name: list-dsr, hints: {readOnly: true}, call: onetrust.list-dsr-requests}\n    - name: get-dsr\n      hints: {readOnly: true}\n      inputParameters: [{name: request_id, type: string, required: true}]\n      call: onetrust.get-dsr-request\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gdpr-governance-capability-skills\n    description: Skill for GDPR governance.\n    skills:\n    - name: gdpr-governance-capability\n      description: GDPR data-subject-rights governance.\n      location: file:///opt/naftiko/skills/gdpr-governance-capability\n\
  \      allowed-tools: create-dsr,list-dsr,get-dsr\n      tools:\n      - {name: create-dsr, from: {sourceNamespace: gdpr-governance-capability-mcp, action: create-dsr}}\n      - {name: list-dsr, from: {sourceNamespace: gdpr-governance-capability-mcp, action: list-dsr}}\n      - {name: get-dsr, from: {sourceNamespace: gdpr-governance-capability-mcp, action: get-dsr}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gdpr-governance-capability.yaml
tags:
- Naftiko
- GDPR
- Privacy
tools:
- description: ''
  hints: {}
  name: create-dsr
- description: ''
  hints:
    readOnly: true
  name: list-dsr
- description: ''
  hints:
    readOnly: true
  name: get-dsr
---
