---
categories: []
consumed_apis: []
description: A capability mirroring PSD2 (Berlin Group / UK Open Banking) endpoints through Kong with consent and rate-limit policies.
layout: capability
name: Kong Gateway Psd2 Mirror Capability
operations:
- description: ''
  method: GET
  name: list-psd2-services
  path: /psd2-services
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list psd2 services
- kong
- get psd2 service
- open banking
- api integration
- governance
- spec-driven integration
- ai
- psd2
- mcp
- capabilities
slug: kong-gateway-psd2-mirror-capability
source_filename: kong-gateway-psd2-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Kong Gateway Psd2 Mirror Capability\n  description: A capability mirroring PSD2 (Berlin Group / UK Open Banking) endpoints through Kong with consent and rate-limit policies.\n  tags: [Naftiko, Kong, PSD2, Open Banking]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: kong-env\n  keys: {KONG_HOST: KONG_HOST, KONG_TOKEN: KONG_TOKEN}\ncapability:\n  consumes:\n  - namespace: kong\n    type: http\n    baseUri: https://{{KONG_HOST}}\n    authentication: {type: bearer, token: '{{KONG_TOKEN}}'}\n    resources:\n    - {name: services, path: /services, operations: [{name: list-psd2-services, method: GET}]}\n    - name: service\n      path: /services/{{service_id}}\n      operations:\n      - {name: get-psd2-service, method: GET, inputParameters: [{name: service_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: kong-gateway-psd2-mirror-capability-rest\n    description: REST\
  \ surface for PSD2 Kong mirror.\n    resources:\n    - {name: services, path: /psd2-services, operations: [{method: GET, name: list-psd2-services, call: kong.list-psd2-services}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: kong-gateway-psd2-mirror-capability-mcp\n    description: MCP for PSD2 Kong mirror.\n    tools:\n    - {name: list-psd2-services, hints: {readOnly: true}, call: kong.list-psd2-services}\n    - name: get-psd2-service\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: kong.get-psd2-service\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: kong-gateway-psd2-mirror-capability-skills\n    description: Skill for PSD2 Kong mirror.\n    skills:\n    - name: kong-gateway-psd2-mirror-capability\n      description: PSD2 Kong gateway mirror.\n      location: file:///opt/naftiko/skills/kong-gateway-psd2-mirror-capability\n      allowed-tools: list-psd2-services,get-psd2-service\n\
  \      tools:\n      - {name: list-psd2-services, from: {sourceNamespace: kong-gateway-psd2-mirror-capability-mcp, action: list-psd2-services}}\n      - {name: get-psd2-service, from: {sourceNamespace: kong-gateway-psd2-mirror-capability-mcp, action: get-psd2-service}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/kong-gateway-psd2-mirror-capability.yaml
tags:
- Naftiko
- Kong
- PSD2
- Open Banking
tools:
- description: ''
  hints:
    readOnly: true
  name: list-psd2-services
- description: ''
  hints:
    readOnly: true
  name: get-psd2-service
---
