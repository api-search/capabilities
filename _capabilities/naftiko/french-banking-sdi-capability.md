---
categories: []
consumed_apis: []
description: A capability over the French Service Discovery Integration (SDI) for banking — AsyncAPI/OpenAPI service registry exposed through Naftiko.
layout: capability
name: French Banking Sdi Capability
operations:
- description: ''
  method: GET
  name: list-services
  path: /services
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- sdi
- spec-driven integration
- list services
- mcp
- capabilities
- naftiko
- api integration
- french banking
- governance
- get service spec
- ai
slug: french-banking-sdi-capability
source_filename: french-banking-sdi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: French Banking Sdi Capability\n  description: A capability over the French Service Discovery Integration (SDI) for banking — AsyncAPI/OpenAPI service registry exposed through Naftiko.\n  tags: [Naftiko, French Banking, SDI]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: sdi-env\n  keys: {SDI_HOST: SDI_HOST, SDI_TOKEN: SDI_TOKEN}\ncapability:\n  consumes:\n  - namespace: sdi\n    type: http\n    baseUri: https://{{SDI_HOST}}\n    authentication: {type: bearer, token: '{{SDI_TOKEN}}'}\n    resources:\n    - {name: services, path: /sdi/services, operations: [{name: list-services, method: GET}]}\n    - name: service-spec\n      path: /sdi/services/{{service_id}}/spec\n      operations:\n      - {name: get-service-spec, method: GET, inputParameters: [{name: service_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: french-banking-sdi-capability-rest\n    description: REST\
  \ surface for French banking SDI.\n    resources:\n    - {name: services, path: /services, operations: [{method: GET, name: list-services, call: sdi.list-services}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: french-banking-sdi-capability-mcp\n    description: MCP for French banking SDI.\n    tools:\n    - {name: list-services, hints: {readOnly: true}, call: sdi.list-services}\n    - name: get-service-spec\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: sdi.get-service-spec\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: french-banking-sdi-capability-skills\n    description: Skill for French banking SDI.\n    skills:\n    - name: french-banking-sdi-capability\n      description: French banking SDI registry.\n      location: file:///opt/naftiko/skills/french-banking-sdi-capability\n      allowed-tools: list-services,get-service-spec\n      tools:\n      - {name: list-services,\
  \ from: {sourceNamespace: french-banking-sdi-capability-mcp, action: list-services}}\n      - {name: get-service-spec, from: {sourceNamespace: french-banking-sdi-capability-mcp, action: get-service-spec}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/french-banking-sdi-capability.yaml
tags:
- Naftiko
- French Banking
- SDI
tools:
- description: ''
  hints:
    readOnly: true
  name: list-services
- description: ''
  hints:
    readOnly: true
  name: get-service-spec
---
