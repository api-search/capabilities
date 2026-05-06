---
categories: []
consumed_apis: []
description: The Assurant APEX (Assurant Product Experience Exchange) platform provides embedded insurance APIs that enable partners to integrate protection products, claims management, and diagnostics into their workflows. The scalable API platform supports 99.95% uptime and covers multiple product lines across various industries.
layout: capability
name: Assurant APEX Embedded Insurance API
operations:
- description: List insurance products
  method: GET
  name: listproducts
  path: /products
- description: Create enrollment
  method: POST
  name: createenrollment
  path: /enrollments
- description: File a claim
  method: POST
  name: fileclaim
  path: /claims
- description: Get claim status
  method: GET
  name: getclaim
  path: /claims/{claimId}
- description: List policies
  method: GET
  name: listpolicies
  path: /policies
personas: []
provider_name: Assurant
provider_slug: assurant
search_terms:
- fileclaim
- insurance
- list policies
- housing
- listproducts
- assurant
- getclaim
- listpolicies
- api
- embedded insurance
- claims
- create enrollment
- get claim status
- createenrollment
- device protection
- file a claim
- list insurance products
slug: assurant-capability
source_filename: assurant-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Assurant APEX Embedded Insurance API\n  description: The Assurant APEX (Assurant Product Experience Exchange) platform provides embedded insurance APIs that enable\n    partners to integrate protection products, claims management, and diagnostics into their workflows. The scalable API platform\n    supports 99.95% uptime and covers multiple product lines across various industries.\n  tags:\n  - Assurant\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: assurant\n    baseUri: https://api-prod.portal.assurant.com\n    description: Assurant APEX Embedded Insurance API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{ASSURANT_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List insurance products\n     \
  \   inputParameters:\n        - name: category\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enrollments\n      path: /enrollments\n      operations:\n      - name: createenrollment\n        method: POST\n        description: Create enrollment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims\n      path: /claims\n      operations:\n      - name: fileclaim\n        method: POST\n        description: File a claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims-claimid\n      path: /claims/{claimId}\n      operations:\n      - name: getclaim\n        method: GET\n        description: Get claim status\n        inputParameters:\n        - name: claimId\n      \
  \    in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: assurant-rest\n    description: REST adapter for Assurant APEX Embedded Insurance API.\n    resources:\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List insurance products\n        call: assurant.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enrollments\n      name: createenrollment\n      operations:\n      - method: POST\n\
  \        name: createenrollment\n        description: Create enrollment\n        call: assurant.createenrollment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims\n      name: fileclaim\n      operations:\n      - method: POST\n        name: fileclaim\n        description: File a claim\n        call: assurant.fileclaim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims/{claimId}\n      name: getclaim\n      operations:\n      - method: GET\n        name: getclaim\n        description: Get claim status\n        call: assurant.getclaim\n        with:\n          claimId: rest.claimId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List policies\n        call: assurant.listpolicies\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: assurant-mcp\n    transport: http\n    description: MCP adapter for Assurant APEX Embedded Insurance API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List insurance products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assurant.listproducts\n      with:\n        category: tools.category\n      inputParameters:\n      - name: category\n        type: string\n        description: category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createenrollment\n      description: Create enrollment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: assurant.createenrollment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fileclaim\n      description: File a claim\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: assurant.fileclaim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclaim\n      description: Get claim status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assurant.getclaim\n      with:\n        claimId: tools.claimId\n      inputParameters:\n      - name: claimId\n        type: string\n        description: claimId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpolicies\n      description: List policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: assurant.listpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ASSURANT_TOKEN: ASSURANT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/assurant/refs/heads/main/capabilities/assurant-capability.yaml
tags:
- Assurant
- API
tools:
- description: List insurance products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Create enrollment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenrollment
- description: File a claim
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fileclaim
- description: Get claim status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclaim
- description: List policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
---
