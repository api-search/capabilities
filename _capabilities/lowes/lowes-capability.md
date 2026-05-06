---
categories: []
consumed_apis: []
description: The Lowe's Product API provides programmatic access to Lowe's home improvement product catalog, inventory availability, pricing, and store information. Built on Microsoft Azure API Management, the API enables partners and developers to integrate with Lowe's retail operations for ecommerce and supply chain use cases.
layout: capability
name: Lowe's Product API
operations:
- description: List products
  method: GET
  name: listproducts
  path: /products
- description: List inventory
  method: GET
  name: listinventory
  path: /inventory
- description: List stores
  method: GET
  name: liststores
  path: /stores
personas: []
provider_name: Lowe's
provider_slug: lowes
search_terms:
- listinventory
- home improvement
- lowes
- list products
- listproducts
- retail
- products
- liststores
- ecommerce
- api
- list inventory
- list stores
slug: lowes-capability
source_filename: lowes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lowe's Product API\n  description: The Lowe's Product API provides programmatic access to Lowe's home improvement product catalog, inventory availability,\n    pricing, and store information. Built on Microsoft Azure API Management, the API enables partners and developers to integrate\n    with Lowe's retail operations for ecommerce and supply chain use cases.\n  tags:\n  - Lowes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lowes\n    baseUri: https://apis.lowes.com\n    description: Lowe's Product API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LOWES_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description:\
  \ Filter by product category.\n        - name: keyword\n          in: query\n          type: string\n          description: Search by keyword.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /inventory\n      operations:\n      - name: listinventory\n        method: GET\n        description: List inventory\n        inputParameters:\n        - name: productId\n          in: query\n          type: string\n          required: true\n          description: The product identifier.\n        - name: storeId\n          in: query\n          type: string\n          description: The store identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /stores\n      operations:\n      - name: liststores\n        method: GET\n        description: List stores\n        inputParameters:\n\
  \        - name: zipCode\n          in: query\n          type: string\n          description: Filter stores by zip code proximity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lowes-rest\n    description: REST adapter for Lowe's Product API.\n    resources:\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n        call: lowes.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /inventory\n      name: listinventory\n      operations:\n      - method: GET\n        name: listinventory\n        description: List inventory\n        call: lowes.listinventory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stores\n      name: liststores\n      operations:\n      -\
  \ method: GET\n        name: liststores\n        description: List stores\n        call: lowes.liststores\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lowes-mcp\n    transport: http\n    description: MCP adapter for Lowe's Product API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lowes.listproducts\n      with:\n        category: tools.category\n        keyword: tools.keyword\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter by product category.\n      - name: keyword\n        type: string\n        description: Search by keyword.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinventory\n      description: List inventory\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: lowes.listinventory\n      with:\n        productId: tools.productId\n        storeId: tools.storeId\n      inputParameters:\n      - name: productId\n        type: string\n        description: The product identifier.\n        required: true\n      - name: storeId\n        type: string\n        description: The store identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststores\n      description: List stores\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lowes.liststores\n      with:\n        zipCode: tools.zipCode\n      inputParameters:\n      - name: zipCode\n        type: string\n        description: Filter stores by zip code proximity.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LOWES_TOKEN: LOWES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lowes/refs/heads/main/capabilities/lowes-capability.yaml
tags:
- Lowes
- API
tools:
- description: List products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: List inventory
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinventory
- description: List stores
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststores
---
