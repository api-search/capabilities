---
categories: []
consumed_apis: []
description: A capability that mirrors a Naftiko-hosted MCP server across multiple agent surfaces (Claude, Copilot, ADK) so the same tools are reachable everywhere.
layout: capability
name: Hosted Mcp Multi Modal Mirror
operations:
- description: ''
  method: GET
  name: list-mirrored-servers
  path: /servers
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- get server
- multi-modal
- list mirrored servers
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
slug: hosted-mcp-multi-modal-mirror
source_filename: hosted-mcp-multi-modal-mirror.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Hosted Mcp Multi Modal Mirror\n  description: A capability that mirrors a Naftiko-hosted MCP server across multiple agent surfaces (Claude, Copilot, ADK) so the same tools are reachable everywhere.\n  tags: [Naftiko, MCP, Multi-Modal]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: naftiko-env\n  keys: {NAFTIKO_API_KEY: NAFTIKO_API_KEY}\ncapability:\n  consumes:\n  - namespace: naftiko-control\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication: {type: bearer, token: '{{NAFTIKO_API_KEY}}'}\n    resources:\n    - {name: mcp-servers, path: /v1/mcp-servers, operations: [{name: list-mcp-servers, method: GET}]}\n    - name: mcp-server\n      path: /v1/mcp-servers/{{server_id}}\n      operations:\n      - {name: get-mcp-server, method: GET, inputParameters: [{name: server_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: hosted-mcp-multi-modal-mirror-rest\n\
  \    description: REST surface for hosted MCP mirror.\n    resources:\n    - {name: servers, path: /servers, operations: [{method: GET, name: list-mirrored-servers, call: naftiko-control.list-mcp-servers}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: hosted-mcp-multi-modal-mirror-mcp\n    description: MCP for the hosted mirror.\n    tools:\n    - {name: list-mirrored-servers, hints: {readOnly: true}, call: naftiko-control.list-mcp-servers}\n    - name: get-server\n      hints: {readOnly: true}\n      inputParameters: [{name: server_id, type: string, required: true}]\n      call: naftiko-control.get-mcp-server\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: hosted-mcp-multi-modal-mirror-skills\n    description: Skill for hosted MCP mirror.\n    skills:\n    - name: hosted-mcp-multi-modal-mirror\n      description: Hosted MCP multi-modal mirror.\n      location: file:///opt/naftiko/skills/hosted-mcp-multi-modal-mirror\n      allowed-tools:\
  \ list-mirrored-servers,get-server\n      tools:\n      - {name: list-mirrored-servers, from: {sourceNamespace: hosted-mcp-multi-modal-mirror-mcp, action: list-mirrored-servers}}\n      - {name: get-server, from: {sourceNamespace: hosted-mcp-multi-modal-mirror-mcp, action: get-server}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/hosted-mcp-multi-modal-mirror.yaml
tags:
- Naftiko
- MCP
- Multi-Modal
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mirrored-servers
- description: ''
  hints:
    readOnly: true
  name: get-server
---
