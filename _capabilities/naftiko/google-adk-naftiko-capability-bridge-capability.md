---
categories: []
consumed_apis: []
description: A bridge capability between Google's Agent Development Kit (ADK) and Naftiko — Naftiko capabilities surface as ADK-callable tools.
layout: capability
name: Google Adk Naftiko Capability Bridge Capability
operations:
- description: ''
  method: GET
  name: list-adk-tools
  path: /adk/tools
- description: ''
  method: POST
  name: invoke-adk-tool
  path: /adk/tools/{{capability_id}}/invoke
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list adk tools
- google adk
- mcp
- invoke adk tool
- api integration
- governance
- spec-driven integration
- ai
- bridge
- capabilities
slug: google-adk-naftiko-capability-bridge-capability
source_filename: google-adk-naftiko-capability-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Google Adk Naftiko Capability Bridge Capability\n  description: A bridge capability between Google's Agent Development Kit (ADK) and Naftiko — Naftiko capabilities surface as ADK-callable tools.\n  tags: [Naftiko, Google ADK, Bridge]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: capabilities, path: /v1/capabilities, operations: [{name: list-capabilities, method: GET}]}\n    - name: capability-invoke\n      path: /v1/capabilities/{{capability_id}}/invoke\n      operations:\n      - {name: invoke-capability, method: POST, inputParameters: [{name: capability_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace:\
  \ google-adk-naftiko-capability-bridge-capability-rest\n    description: ADK-shaped REST surface for Naftiko capabilities.\n    resources:\n    - {name: tools, path: /adk/tools, operations: [{method: GET, name: list-adk-tools, call: naftiko-control.list-capabilities}]}\n    - name: invoke\n      path: /adk/tools/{{capability_id}}/invoke\n      operations:\n      - {method: POST, name: invoke-adk-tool, inputParameters: [{name: capability_id, in: path, type: string}], call: naftiko-control.invoke-capability}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: google-adk-naftiko-capability-bridge-capability-mcp\n    description: MCP mirror of ADK bridge.\n    tools:\n    - {name: list-adk-tools, hints: {readOnly: true}, call: naftiko-control.list-capabilities}\n    - name: invoke-adk-tool\n      inputParameters: [{name: capability_id, type: string, required: true}]\n      call: naftiko-control.invoke-capability\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace:\
  \ google-adk-naftiko-capability-bridge-capability-skills\n    description: Skill for ADK bridge.\n    skills:\n    - name: google-adk-naftiko-capability-bridge-capability\n      description: Google ADK bridge.\n      location: file:///opt/naftiko/skills/google-adk-naftiko-capability-bridge-capability\n      allowed-tools: list-adk-tools,invoke-adk-tool\n      tools:\n      - {name: list-adk-tools, from: {sourceNamespace: google-adk-naftiko-capability-bridge-capability-mcp, action: list-adk-tools}}\n      - {name: invoke-adk-tool, from: {sourceNamespace: google-adk-naftiko-capability-bridge-capability-mcp, action: invoke-adk-tool}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/google-adk-naftiko-capability-bridge-capability.yaml
tags:
- Naftiko
- Google ADK
- Bridge
tools:
- description: ''
  hints:
    readOnly: true
  name: list-adk-tools
- description: ''
  hints: {}
  name: invoke-adk-tool
---
