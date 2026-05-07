---
categories: []
consumed_apis: []
description: A bridge capability between Microcks (mocks-as-a-service) and Naftiko — Microcks-defined services appear as Naftiko sandbox capabilities.
layout: capability
name: Microcks Sandbox Bridge Capability
operations:
- description: ''
  method: GET
  name: list-sandboxes
  path: /sandboxes
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- microcks
- governance
- sandbox
- naftiko
- ai
- capabilities
- spec-driven integration
- get sandbox
- api integration
- mcp
- list sandboxes
slug: microcks-sandbox-bridge-capability
source_filename: microcks-sandbox-bridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Microcks Sandbox Bridge Capability\n  description: A bridge capability between Microcks (mocks-as-a-service) and Naftiko — Microcks-defined services appear as Naftiko sandbox capabilities.\n  tags: [Naftiko, Microcks, Sandbox]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: microcks-env\n  keys: {MICROCKS_HOST: MICROCKS_HOST, MICROCKS_TOKEN: MICROCKS_TOKEN}\ncapability:\n  consumes:\n  - namespace: microcks\n    type: http\n    baseUri: https://{{MICROCKS_HOST}}\n    authentication: {type: bearer, token: '{{MICROCKS_TOKEN}}'}\n    resources:\n    - {name: services, path: /api/services, operations: [{name: list-microcks-services, method: GET}]}\n    - name: service\n      path: /api/services/{{service_id}}\n      operations:\n      - {name: get-microcks-service, method: GET, inputParameters: [{name: service_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: microcks-sandbox-bridge-capability-rest\n\
  \    description: REST surface for Microcks bridge.\n    resources:\n    - {name: sandboxes, path: /sandboxes, operations: [{method: GET, name: list-sandboxes, call: microcks.list-microcks-services}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: microcks-sandbox-bridge-capability-mcp\n    description: MCP for Microcks bridge.\n    tools:\n    - {name: list-sandboxes, hints: {readOnly: true}, call: microcks.list-microcks-services}\n    - name: get-sandbox\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: microcks.get-microcks-service\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: microcks-sandbox-bridge-capability-skills\n    description: Skill for Microcks bridge.\n    skills:\n    - name: microcks-sandbox-bridge-capability\n      description: Microcks sandbox bridge.\n      location: file:///opt/naftiko/skills/microcks-sandbox-bridge-capability\n      allowed-tools: list-sandboxes,get-sandbox\n\
  \      tools:\n      - {name: list-sandboxes, from: {sourceNamespace: microcks-sandbox-bridge-capability-mcp, action: list-sandboxes}}\n      - {name: get-sandbox, from: {sourceNamespace: microcks-sandbox-bridge-capability-mcp, action: get-sandbox}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/microcks-sandbox-bridge-capability.yaml
tags:
- Naftiko
- Microcks
- Sandbox
tools:
- description: ''
  hints:
    readOnly: true
  name: list-sandboxes
- description: ''
  hints:
    readOnly: true
  name: get-sandbox
---
