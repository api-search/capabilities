---
categories: []
consumed_apis: []
description: A capability mirroring FHIR endpoints through a Kong gateway with rate-limit and audit policies for healthcare integrations.
layout: capability
name: Kong Gateway Fhir Mirror Capability
operations:
- description: ''
  method: GET
  name: list-fhir-services
  path: /fhir-services
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list fhir services
- fhir
- healthcare
- spec-driven integration
- mcp
- kong
- list service routes
- capabilities
- naftiko
- api integration
- governance
- ai
slug: kong-gateway-fhir-mirror-capability
source_filename: kong-gateway-fhir-mirror-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Kong Gateway Fhir Mirror Capability\n  description: A capability mirroring FHIR endpoints through a Kong gateway with rate-limit and audit policies for healthcare integrations.\n  tags: [Naftiko, Kong, FHIR, Healthcare]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: kong-env\n  keys: {KONG_HOST: KONG_HOST, KONG_TOKEN: KONG_TOKEN}\ncapability:\n  consumes:\n  - namespace: kong\n    type: http\n    baseUri: https://{{KONG_HOST}}\n    authentication: {type: bearer, token: '{{KONG_TOKEN}}'}\n    resources:\n    - {name: services, path: /services, operations: [{name: list-fhir-services, method: GET}]}\n    - name: service-routes\n      path: /services/{{service_id}}/routes\n      operations:\n      - {name: list-service-routes, method: GET, inputParameters: [{name: service_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: kong-gateway-fhir-mirror-capability-rest\n   \
  \ description: REST surface for FHIR Kong mirror.\n    resources:\n    - {name: services, path: /fhir-services, operations: [{method: GET, name: list-fhir-services, call: kong.list-fhir-services}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: kong-gateway-fhir-mirror-capability-mcp\n    description: MCP for FHIR Kong mirror.\n    tools:\n    - {name: list-fhir-services, hints: {readOnly: true}, call: kong.list-fhir-services}\n    - name: list-service-routes\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: kong.list-service-routes\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: kong-gateway-fhir-mirror-capability-skills\n    description: Skill for FHIR Kong mirror.\n    skills:\n    - name: kong-gateway-fhir-mirror-capability\n      description: FHIR Kong gateway mirror.\n      location: file:///opt/naftiko/skills/kong-gateway-fhir-mirror-capability\n      allowed-tools:\
  \ list-fhir-services,list-service-routes\n      tools:\n      - {name: list-fhir-services, from: {sourceNamespace: kong-gateway-fhir-mirror-capability-mcp, action: list-fhir-services}}\n      - {name: list-service-routes, from: {sourceNamespace: kong-gateway-fhir-mirror-capability-mcp, action: list-service-routes}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/kong-gateway-fhir-mirror-capability.yaml
tags:
- Naftiko
- Kong
- FHIR
- Healthcare
tools:
- description: ''
  hints:
    readOnly: true
  name: list-fhir-services
- description: ''
  hints:
    readOnly: true
  name: list-service-routes
---
