---
categories: []
consumed_apis: []
description: A companion capability for AsyncAPI Service Discovery Integration (SDI) — pulls AsyncAPI documents from a registry and exposes channel browse + subscribe-test as agent tools.
layout: capability
name: Async Sdi Companion Capability
operations:
- description: ''
  method: GET
  name: list-services
  path: /services
- description: ''
  method: GET
  name: get-asyncapi-doc
  path: /services/{{service_id}}/asyncapi.yaml
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list services
- asyncapi
- api integration
- governance
- sdi
- spec-driven integration
- ai
- mcp
- capabilities
- get asyncapi doc
slug: async-sdi-companion-capability
source_filename: async-sdi-companion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Async Sdi Companion Capability\n  description: A companion capability for AsyncAPI Service Discovery Integration (SDI) — pulls AsyncAPI documents from a registry and exposes channel browse + subscribe-test as agent tools.\n  tags: [Naftiko, AsyncAPI, SDI]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: asyncapi-env\n  description: AsyncAPI registry/host URL and token.\n  keys: {ASYNCAPI_HOST: ASYNCAPI_HOST, ASYNCAPI_TOKEN: ASYNCAPI_TOKEN}\ncapability:\n  consumes:\n  - namespace: asyncapi\n    type: http\n    baseUri: https://{{ASYNCAPI_HOST}}\n    authentication: {type: bearer, token: '{{ASYNCAPI_TOKEN}}'}\n    resources:\n    - {name: services, path: /sdi/services, operations: [{name: list-services, method: GET}]}\n    - name: service-asyncapi\n      path: /sdi/services/{{service_id}}/asyncapi.yaml\n      operations:\n      - {name: get-asyncapi-doc, method: GET, inputParameters: [{name: service_id, in: path}]}\n\
  \  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: async-sdi-companion-capability-rest\n    description: REST surface for browsing AsyncAPI services.\n    resources:\n    - {name: services, path: /services, operations: [{method: GET, name: list-services, call: asyncapi.list-services}]}\n    - name: service-doc\n      path: /services/{{service_id}}/asyncapi.yaml\n      operations:\n      - method: GET\n        name: get-asyncapi-doc\n        inputParameters: [{name: service_id, in: path, type: string}]\n        call: asyncapi.get-asyncapi-doc\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: async-sdi-companion-capability-mcp\n    description: MCP for AsyncAPI SDI browsing.\n    tools:\n    - {name: list-services, hints: {readOnly: true}, call: asyncapi.list-services}\n    - name: get-asyncapi-doc\n      hints: {readOnly: true}\n      inputParameters: [{name: service_id, type: string, required: true}]\n      call: asyncapi.get-asyncapi-doc\n\
  \  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: async-sdi-companion-capability-skills\n    description: Skill bundle for AsyncAPI SDI.\n    skills:\n    - name: async-sdi-companion-capability\n      description: AsyncAPI SDI browse companion.\n      location: file:///opt/naftiko/skills/async-sdi-companion-capability\n      allowed-tools: list-services,get-asyncapi-doc\n      tools:\n      - {name: list-services, from: {sourceNamespace: async-sdi-companion-capability-mcp, action: list-services}}\n      - {name: get-asyncapi-doc, from: {sourceNamespace: async-sdi-companion-capability-mcp, action: get-asyncapi-doc}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/async-sdi-companion-capability.yaml
tags:
- Naftiko
- AsyncAPI
- SDI
tools:
- description: ''
  hints:
    readOnly: true
  name: list-services
- description: ''
  hints:
    readOnly: true
  name: get-asyncapi-doc
---
