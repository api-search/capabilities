---
categories: []
consumed_apis: []
description: A capability surfacing Microsoft Fabric workspace metrics (capacity, item run state) as observability tools.
layout: capability
name: Fabric Observability Capability
operations:
- description: ''
  method: GET
  name: get-capacity-metrics
  path: /capacities/{{capacity_id}}/metrics
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- observability
- governance
- get capacity metrics
- microsoft fabric
- list capacities
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- naftiko
slug: fabric-observability-capability
source_filename: fabric-observability-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Fabric Observability Capability\n  description: A capability surfacing Microsoft Fabric workspace metrics (capacity, item run state) as observability tools.\n  tags: [Naftiko, Microsoft Fabric, Observability]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: fabric-env\n  keys: {FABRIC_TOKEN: FABRIC_TOKEN}\ncapability:\n  consumes:\n  - namespace: fabric\n    type: http\n    baseUri: https://api.fabric.microsoft.com\n    authentication: {type: bearer, token: '{{FABRIC_TOKEN}}'}\n    resources:\n    - {name: capacities, path: /v1/capacities, operations: [{name: list-capacities, method: GET}]}\n    - name: capacity-metrics\n      path: '/v1/capacities/{{capacity_id}}/metrics'\n      operations:\n      - {name: get-capacity-metrics, method: GET, inputParameters: [{name: capacity_id, in: path}]}\n    - {name: item-jobs, path: '/v1/workspaces/{{workspace_id}}/items/{{item_id}}/jobs/instances', operations: [{name: list-item-jobs,\
  \ method: GET, inputParameters: [{name: workspace_id, in: path}, {name: item_id, in: path}]}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: fabric-observability-capability-rest\n    description: REST surface for Fabric observability.\n    resources:\n    - {name: capacity-metrics, path: '/capacities/{{capacity_id}}/metrics', operations: [{method: GET, name: get-capacity-metrics, inputParameters: [{name: capacity_id, in: path, type: string}], call: fabric.get-capacity-metrics}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: fabric-observability-capability-mcp\n    description: MCP for Fabric observability.\n    tools:\n    - {name: list-capacities, hints: {readOnly: true}, call: fabric.list-capacities}\n    - name: get-capacity-metrics\n      hints: {readOnly: true}\n      inputParameters: [{name: capacity_id, type: string, required: true}]\n      call: fabric.get-capacity-metrics\n  - type: skill\n    address: 0.0.0.0\n    port:\
  \ 3011\n    namespace: fabric-observability-capability-skills\n    description: Skill for Fabric observability.\n    skills:\n    - name: fabric-observability-capability\n      description: Microsoft Fabric observability.\n      location: file:///opt/naftiko/skills/fabric-observability-capability\n      allowed-tools: list-capacities,get-capacity-metrics\n      tools:\n      - {name: list-capacities, from: {sourceNamespace: fabric-observability-capability-mcp, action: list-capacities}}\n      - {name: get-capacity-metrics, from: {sourceNamespace: fabric-observability-capability-mcp, action: get-capacity-metrics}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/fabric-observability-capability.yaml
tags:
- Naftiko
- Microsoft Fabric
- Observability
tools:
- description: ''
  hints:
    readOnly: true
  name: list-capacities
- description: ''
  hints:
    readOnly: true
  name: get-capacity-metrics
---
