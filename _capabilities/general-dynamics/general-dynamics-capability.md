---
categories: []
consumed_apis: []
description: General Dynamics Mission Systems provides technology products and services for aerospace and defense applications, supporting mission-critical systems and government IT solutions.
layout: capability
name: General Dynamics Mission Systems API
operations:
- description: Get Systems
  method: GET
  name: getsystems
  path: /systems
- description: Get System by ID
  method: GET
  name: getsystembyid
  path: /systems/{systemId}
- description: Get Products
  method: GET
  name: getproducts
  path: /products
personas: []
provider_name: General Dynamics
provider_slug: general-dynamics
search_terms:
- getproducts
- mission systems
- government
- getsystembyid
- get system by id
- getsystems
- get systems
- api
- general
- dynamics
- get products
- defense
- aerospace
slug: general-dynamics-capability
source_filename: general-dynamics-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: General Dynamics Mission Systems API\n  description: General Dynamics Mission Systems provides technology products and services for aerospace and defense applications,\n    supporting mission-critical systems and government IT solutions.\n  tags:\n  - General\n  - Dynamics\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: general-dynamics\n    baseUri: https://api.gdmissionsystems.com\n    description: General Dynamics Mission Systems API HTTP API.\n    resources:\n    - name: systems\n      path: /systems\n      operations:\n      - name: getsystems\n        method: GET\n        description: Get Systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: systems-systemid\n      path: /systems/{systemId}\n      operations:\n      - name: getsystembyid\n        method: GET\n        description:\
  \ Get System by ID\n        inputParameters:\n        - name: systemId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      operations:\n      - name: getproducts\n        method: GET\n        description: Get Products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: general-dynamics-rest\n    description: REST adapter for General Dynamics Mission Systems API.\n    resources:\n    - path: /systems\n      name: getsystems\n      operations:\n      - method: GET\n        name: getsystems\n        description: Get Systems\n        call: general-dynamics.getsystems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /systems/{systemId}\n\
  \      name: getsystembyid\n      operations:\n      - method: GET\n        name: getsystembyid\n        description: Get System by ID\n        call: general-dynamics.getsystembyid\n        with:\n          systemId: rest.systemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: getproducts\n      operations:\n      - method: GET\n        name: getproducts\n        description: Get Products\n        call: general-dynamics.getproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: general-dynamics-mcp\n    transport: http\n    description: MCP adapter for General Dynamics Mission Systems API for AI agent use.\n    tools:\n    - name: getsystems\n      description: Get Systems\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: general-dynamics.getsystems\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getsystembyid\n      description: Get System by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: general-dynamics.getsystembyid\n      with:\n        systemId: tools.systemId\n      inputParameters:\n      - name: systemId\n        type: string\n        description: systemId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproducts\n      description: Get Products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: general-dynamics.getproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/general-dynamics/refs/heads/main/capabilities/general-dynamics-capability.yaml
tags:
- General
- Dynamics
- API
tools:
- description: Get Systems
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystems
- description: Get System by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystembyid
- description: Get Products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproducts
---
