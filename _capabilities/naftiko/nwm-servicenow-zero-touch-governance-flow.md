---
categories: []
consumed_apis: []
description: A Northwestern Mutual ServiceNow flow that auto-creates a governance ticket on every Naftiko-detected control failure.
layout: capability
name: Nwm Servicenow Zero Touch Governance Flow
operations:
- description: ''
  method: POST
  name: create-governance-incident
  path: /incidents
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- list incidents
- get incident
- servicenow
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- nwm
- naftiko
- create governance incident
slug: nwm-servicenow-zero-touch-governance-flow
source_filename: nwm-servicenow-zero-touch-governance-flow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Nwm Servicenow Zero Touch Governance Flow\n  description: A Northwestern Mutual ServiceNow flow that auto-creates a governance ticket on every Naftiko-detected control failure.\n  tags: [Naftiko, NWM, ServiceNow, Governance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: servicenow-env\n  keys: {SN_HOST: SN_HOST, SN_USER: SN_USER, SN_PASSWORD: SN_PASSWORD}\ncapability:\n  consumes:\n  - namespace: servicenow\n    type: http\n    baseUri: https://{{SN_HOST}}\n    authentication: {type: basic, username: '{{SN_USER}}', password: '{{SN_PASSWORD}}'}\n    resources:\n    - {name: incidents, path: /api/now/table/incident, operations: [{name: create-incident, method: POST}, {name: list-incidents, method: GET}]}\n    - name: incident\n      path: /api/now/table/incident/{{sys_id}}\n      operations:\n      - {name: get-incident, method: GET, inputParameters: [{name: sys_id, in: path}]}\n  exposes:\n  - type: rest\n   \
  \ address: 0.0.0.0\n    port: 8080\n    namespace: nwm-servicenow-zero-touch-governance-flow-rest\n    description: REST surface for zero-touch governance.\n    resources:\n    - {name: incident, path: /incidents, operations: [{method: POST, name: create-governance-incident, call: servicenow.create-incident}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: nwm-servicenow-zero-touch-governance-flow-mcp\n    description: MCP for zero-touch governance.\n    tools:\n    - {name: create-governance-incident, call: servicenow.create-incident}\n    - {name: list-incidents, hints: {readOnly: true}, call: servicenow.list-incidents}\n    - name: get-incident\n      hints: {readOnly: true}\n      inputParameters: [{name: sys_id, type: string, required: true}]\n      call: servicenow.get-incident\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: nwm-servicenow-zero-touch-governance-flow-skills\n    description: Skill for zero-touch governance.\n    skills:\n\
  \    - name: nwm-servicenow-zero-touch-governance-flow\n      description: Zero-touch ServiceNow governance flow.\n      location: file:///opt/naftiko/skills/nwm-servicenow-zero-touch-governance-flow\n      allowed-tools: create-governance-incident,list-incidents,get-incident\n      tools:\n      - {name: create-governance-incident, from: {sourceNamespace: nwm-servicenow-zero-touch-governance-flow-mcp, action: create-governance-incident}}\n      - {name: list-incidents, from: {sourceNamespace: nwm-servicenow-zero-touch-governance-flow-mcp, action: list-incidents}}\n      - {name: get-incident, from: {sourceNamespace: nwm-servicenow-zero-touch-governance-flow-mcp, action: get-incident}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/nwm-servicenow-zero-touch-governance-flow.yaml
tags:
- Naftiko
- NWM
- ServiceNow
- Governance
tools:
- description: ''
  hints: {}
  name: create-governance-incident
- description: ''
  hints:
    readOnly: true
  name: list-incidents
- description: ''
  hints:
    readOnly: true
  name: get-incident
---
