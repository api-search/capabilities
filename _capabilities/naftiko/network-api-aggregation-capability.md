---
categories: []
consumed_apis: []
description: A capability that aggregates network APIs (Cisco DNA, Meraki, Aruba) into a unified network-state surface for ops agents.
layout: capability
name: Network Api Aggregation Capability
operations:
- description: ''
  method: GET
  name: list-networks
  path: /networks
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- list networks
- list organizations
- aggregation
- ai
- capabilities
- spec-driven integration
- api integration
- list devices
- mcp
- network
- naftiko
slug: network-api-aggregation-capability
source_filename: network-api-aggregation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Network Api Aggregation Capability\n  description: A capability that aggregates network APIs (Cisco DNA, Meraki, Aruba) into a unified network-state surface for ops agents.\n  tags: [Naftiko, Network, Aggregation]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: meraki-env\n  keys: {MERAKI_TOKEN: MERAKI_TOKEN}\ncapability:\n  consumes:\n  - namespace: meraki\n    type: http\n    baseUri: https://api.meraki.com\n    authentication: {type: bearer, token: '{{MERAKI_TOKEN}}'}\n    resources:\n    - {name: organizations, path: /api/v1/organizations, operations: [{name: list-organizations, method: GET}]}\n    - name: networks\n      path: /api/v1/organizations/{{org_id}}/networks\n      operations:\n      - {name: list-networks, method: GET, inputParameters: [{name: org_id, in: path}]}\n    - name: network-devices\n      path: /api/v1/networks/{{network_id}}/devices\n      operations:\n      - {name: list-devices, method:\
  \ GET, inputParameters: [{name: network_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: network-api-aggregation-capability-rest\n    description: REST surface for aggregated network state.\n    resources:\n    - {name: networks, path: /networks, operations: [{method: GET, name: list-networks, call: meraki.list-organizations}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: network-api-aggregation-capability-mcp\n    description: MCP for aggregated network state.\n    tools:\n    - {name: list-organizations, hints: {readOnly: true}, call: meraki.list-organizations}\n    - name: list-networks\n      hints: {readOnly: true}\n      inputParameters: [{name: org_id, type: string, required: true}]\n      call: meraki.list-networks\n    - name: list-devices\n      hints: {readOnly: true}\n      inputParameters: [{name: network_id, type: string, required: true}]\n      call: meraki.list-devices\n  - type: skill\n    address:\
  \ 0.0.0.0\n    port: 3011\n    namespace: network-api-aggregation-capability-skills\n    description: Skill for network aggregation.\n    skills:\n    - name: network-api-aggregation-capability\n      description: Network API aggregation.\n      location: file:///opt/naftiko/skills/network-api-aggregation-capability\n      allowed-tools: list-organizations,list-networks,list-devices\n      tools:\n      - {name: list-organizations, from: {sourceNamespace: network-api-aggregation-capability-mcp, action: list-organizations}}\n      - {name: list-networks, from: {sourceNamespace: network-api-aggregation-capability-mcp, action: list-networks}}\n      - {name: list-devices, from: {sourceNamespace: network-api-aggregation-capability-mcp, action: list-devices}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/network-api-aggregation-capability.yaml
tags:
- Naftiko
- Network
- Aggregation
tools:
- description: ''
  hints:
    readOnly: true
  name: list-organizations
- description: ''
  hints:
    readOnly: true
  name: list-networks
- description: ''
  hints:
    readOnly: true
  name: list-devices
---
