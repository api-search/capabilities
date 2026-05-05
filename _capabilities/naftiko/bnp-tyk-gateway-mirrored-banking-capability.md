---
categories: []
consumed_apis: []
description: A capability mirroring BNP banking APIs through a Tyk gateway with rate-limit and quota-policy enforcement.
layout: capability
name: Bnp Tyk Gateway Mirrored Banking Capability
operations:
- description: ''
  method: GET
  name: list-mirrored-apis
  path: /apis
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- tyk
- bnp
- create key
- mcp
- list mirrored apis
- gateway
- capabilities
- naftiko
- api integration
- governance
- ai
slug: bnp-tyk-gateway-mirrored-banking-capability
source_filename: bnp-tyk-gateway-mirrored-banking-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Tyk Gateway Mirrored Banking Capability\n  description: A capability mirroring BNP banking APIs through a Tyk gateway with rate-limit and quota-policy enforcement.\n  tags: [Naftiko, BNP, Tyk, Gateway]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: tyk-env\n  keys: {TYK_HOST: TYK_HOST, TYK_TOKEN: TYK_TOKEN}\ncapability:\n  consumes:\n  - namespace: tyk\n    type: http\n    baseUri: https://{{TYK_HOST}}\n    authentication: {type: bearer, token: '{{TYK_TOKEN}}'}\n    resources:\n    - {name: apis, path: /api/apis, operations: [{name: list-apis, method: GET}]}\n    - name: api\n      path: /api/apis/{{api_id}}\n      operations:\n      - {name: get-api, method: GET, inputParameters: [{name: api_id, in: path}]}\n    - name: keys\n      path: /api/keys\n      operations: [{name: create-key, method: POST}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-rest\n\
  \    description: REST surface listing mirrored Tyk APIs.\n    resources:\n    - {name: apis, path: /apis, operations: [{method: GET, name: list-mirrored-apis, call: tyk.list-apis}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-mcp\n    description: MCP for Tyk-mirrored banking ops.\n    tools:\n    - {name: list-mirrored-apis, hints: {readOnly: true}, call: tyk.list-apis}\n    - name: create-key\n      call: tyk.create-key\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-tyk-gateway-mirrored-banking-capability-skills\n    description: Skill for Tyk-mirrored banking.\n    skills:\n    - name: bnp-tyk-gateway-mirrored-banking-capability\n      description: Tyk-mirrored BNP banking.\n      location: file:///opt/naftiko/skills/bnp-tyk-gateway-mirrored-banking-capability\n      allowed-tools: list-mirrored-apis,create-key\n      tools:\n      - {name: list-mirrored-apis, from: {sourceNamespace: bnp-tyk-gateway-mirrored-banking-capability-mcp,\
  \ action: list-mirrored-apis}}\n      - {name: create-key, from: {sourceNamespace: bnp-tyk-gateway-mirrored-banking-capability-mcp, action: create-key}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-tyk-gateway-mirrored-banking-capability.yaml
tags:
- Naftiko
- BNP
- Tyk
- Gateway
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mirrored-apis
- description: ''
  hints: {}
  name: create-key
---
