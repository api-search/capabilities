---
categories: []
consumed_apis: []
description: A demo capability over Microsoft Fabric exposing the platform explorer (workspaces, items, lakehouses) as a Naftiko capability.
layout: capability
name: Fabric Explorer Platform Demo
operations:
- description: ''
  method: GET
  name: list-workspaces
  path: /workspaces
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list workspace items
- microsoft fabric
- api integration
- governance
- capabilities
- spec-driven integration
- list workspaces
- ai
- mcp
- demo
slug: fabric-explorer-platform-demo
source_filename: fabric-explorer-platform-demo.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Fabric Explorer Platform Demo\n  description: A demo capability over Microsoft Fabric exposing the platform explorer (workspaces, items, lakehouses) as a Naftiko capability.\n  tags: [Naftiko, Microsoft Fabric, Demo]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: fabric-env\n  keys: {FABRIC_TOKEN: FABRIC_TOKEN}\ncapability:\n  consumes:\n  - namespace: fabric\n    type: http\n    baseUri: https://api.fabric.microsoft.com\n    authentication: {type: bearer, token: '{{FABRIC_TOKEN}}'}\n    resources:\n    - {name: workspaces, path: /v1/workspaces, operations: [{name: list-workspaces, method: GET}]}\n    - name: workspace-items\n      path: /v1/workspaces/{{workspace_id}}/items\n      operations:\n      - {name: list-workspace-items, method: GET, inputParameters: [{name: workspace_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: fabric-explorer-platform-demo-rest\n\
  \    description: REST surface for Fabric platform explorer.\n    resources:\n    - {name: workspaces, path: /workspaces, operations: [{method: GET, name: list-workspaces, call: fabric.list-workspaces}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: fabric-explorer-platform-demo-mcp\n    description: MCP for Fabric explorer.\n    tools:\n    - {name: list-workspaces, hints: {readOnly: true}, call: fabric.list-workspaces}\n    - name: list-workspace-items\n      hints: {readOnly: true}\n      inputParameters: [{name: workspace_id, type: string, required: true}]\n      call: fabric.list-workspace-items\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: fabric-explorer-platform-demo-skills\n    description: Skill for Fabric explorer.\n    skills:\n    - name: fabric-explorer-platform-demo\n      description: Microsoft Fabric platform explorer demo.\n      location: file:///opt/naftiko/skills/fabric-explorer-platform-demo\n      allowed-tools: list-workspaces,list-workspace-items\n\
  \      tools:\n      - {name: list-workspaces, from: {sourceNamespace: fabric-explorer-platform-demo-mcp, action: list-workspaces}}\n      - {name: list-workspace-items, from: {sourceNamespace: fabric-explorer-platform-demo-mcp, action: list-workspace-items}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/fabric-explorer-platform-demo.yaml
tags:
- Naftiko
- Microsoft Fabric
- Demo
tools:
- description: ''
  hints:
    readOnly: true
  name: list-workspaces
- description: ''
  hints:
    readOnly: true
  name: list-workspace-items
---
