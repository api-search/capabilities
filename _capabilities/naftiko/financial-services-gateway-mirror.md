---
categories: []
consumed_apis: []
description: A capability that mirrors a financial-services API gateway (Kong / Apigee) and exposes governed read access to mirrored APIs.
layout: capability
name: Financial Services Gateway Mirror
operations:
- description: ''
  method: GET
  name: list-mirrored-services
  path: /mirrored-services
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- kong
- financial services
- governance
- api integration
- get service
- ai
- capabilities
- spec-driven integration
- list mirrored services
- mcp
- naftiko
slug: financial-services-gateway-mirror
source_filename: financial-services-gateway-mirror.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Financial Services Gateway Mirror\n  description: A capability that mirrors a financial-services API gateway (Kong / Apigee) and exposes governed read access to mirrored APIs.\n  tags: [Naftiko, Kong, Financial Services]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: kong-env\n  keys: {KONG_HOST: KONG_HOST, KONG_TOKEN: KONG_TOKEN}\ncapability:\n  consumes:\n  - namespace: kong\n    type: http\n    baseUri: https://{{KONG_HOST}}\n    authentication: {type: bearer, token: '{{KONG_TOKEN}}'}\n    resources:\n    - {name: services, path: /services, operations: [{name: list-services, method: GET}]}\n    - name: service\n      path: /services/{{service_id}}\n      operations:\n      - {name: get-service, method: GET, inputParameters: [{name: service_id, in: path}]}\n    - name: routes\n      path: /routes\n      operations: [{name: list-routes, method: GET}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port:\
  \ 8080\n    namespace: financial-services-gateway-mirror-rest\n    description: REST surface for FS gateway mirror.\n    resources:\n    - {name: services, path: /mirrored-services, operations: [{method: GET, name: list-mirrored-services, call: kong.list-services}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: financial-services-gateway-mirror-mcp\n    description: MCP for FS gateway mirror.\n    tools:\n    - {name: list-mirrored-services, hints: {readOnly: true}, call: kong.list-services}\n    - name: get-service\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: kong.get-service\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: financial-services-gateway-mirror-skills\n    description: Skill for FS gateway mirror.\n    skills:\n    - name: financial-services-gateway-mirror\n      description: Financial-services gateway mirror.\n      location: file:///opt/naftiko/skills/financial-services-gateway-mirror\n\
  \      allowed-tools: list-mirrored-services,get-service\n      tools:\n      - {name: list-mirrored-services, from: {sourceNamespace: financial-services-gateway-mirror-mcp, action: list-mirrored-services}}\n      - {name: get-service, from: {sourceNamespace: financial-services-gateway-mirror-mcp, action: get-service}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/financial-services-gateway-mirror.yaml
tags:
- Naftiko
- Kong
- Financial Services
tools:
- description: ''
  hints:
    readOnly: true
  name: list-mirrored-services
- description: ''
  hints:
    readOnly: true
  name: get-service
---
