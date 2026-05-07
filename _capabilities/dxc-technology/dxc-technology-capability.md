---
categories: []
consumed_apis: []
description: The DXC Developer Central provides APIs and tools for building and integrating with DXC Technology's enterprise platform services. The portal offers open APIs with modular architecture and flexible connectivity designed to reduce legacy dependencies and ensure scalability across various technology environments.
layout: capability
name: DXC Developer Central API
operations:
- description: List available services
  method: GET
  name: listservices
  path: /services
- description: List integrations
  method: GET
  name: listintegrations
  path: /integrations
personas: []
provider_name: DXC Technology
provider_slug: dxc-technology
search_terms:
- list integrations
- listintegrations
- it services
- dxc
- enterprise
- list available services
- integration
- api
- technology
- platform
- listservices
slug: dxc-technology-capability
source_filename: dxc-technology-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: DXC Developer Central API\n  description: The DXC Developer Central provides APIs and tools for building and integrating with DXC Technology's enterprise\n    platform services. The portal offers open APIs with modular architecture and flexible connectivity designed to reduce\n    legacy dependencies and ensure scalability across various technology environments.\n  tags:\n  - Dxc\n  - Technology\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: dxc-technology\n    baseUri: https://developer.dxc.com/api\n    description: DXC Developer Central API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DXC_TECHNOLOGY_TOKEN}}'\n    resources:\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List available services\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: integrations\n      path: /integrations\n      operations:\n      - name: listintegrations\n        method: GET\n        description: List integrations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dxc-technology-rest\n    description: REST adapter for DXC Developer Central API.\n    resources:\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List available services\n        call: dxc-technology.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /integrations\n      name: listintegrations\n      operations:\n      - method: GET\n        name: listintegrations\n        description: List integrations\n        call: dxc-technology.listintegrations\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dxc-technology-mcp\n    transport: http\n    description: MCP adapter for DXC Developer Central API for AI agent use.\n    tools:\n    - name: listservices\n      description: List available services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dxc-technology.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintegrations\n      description: List integrations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: dxc-technology.listintegrations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DXC_TECHNOLOGY_TOKEN: DXC_TECHNOLOGY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dxc-technology/refs/heads/main/capabilities/dxc-technology-capability.yaml
tags:
- Dxc
- Technology
- API
tools:
- description: List available services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: List integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintegrations
---
