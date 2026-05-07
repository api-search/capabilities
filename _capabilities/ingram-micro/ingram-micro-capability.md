---
categories: []
consumed_apis: []
description: The Ingram Micro Reseller API provides REST API access to product catalog, pricing, discounts, stock levels, and order management for IT resellers.
layout: capability
name: Ingram Micro Reseller API
operations:
- description: Search Product Catalog
  method: GET
  name: getcatalog
  path: /catalog
- description: Get Product Details
  method: GET
  name: getproductdetails
  path: /catalog/{ingramPartNumber}
- description: Create Order
  method: POST
  name: createorder
  path: /orders
- description: Get Order Status
  method: GET
  name: getorderstatus
  path: /orders/{orderId}
- description: Get Pricing
  method: POST
  name: getpricing
  path: /pricing
personas: []
provider_name: ingram-micro
provider_slug: ingram-micro
search_terms:
- createorder
- search product catalog
- getproductdetails
- getorderstatus
- get order status
- getpricing
- create order
- get product details
- getcatalog
- micro
- api
- get pricing
- ingram
slug: ingram-micro-capability
source_filename: ingram-micro-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ingram Micro Reseller API\n  description: The Ingram Micro Reseller API provides REST API access to product catalog, pricing, discounts, stock levels,\n    and order management for IT resellers.\n  tags:\n  - Ingram\n  - Micro\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ingram-micro\n    baseUri: https://api.ingrammicro.com/resellers/v6\n    description: Ingram Micro Reseller API HTTP API.\n    resources:\n    - name: catalog\n      path: /catalog\n      operations:\n      - name: getcatalog\n        method: GET\n        description: Search Product Catalog\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n        - name: category\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: catalog-ingrampartnumber\n      path: /catalog/{ingramPartNumber}\n      operations:\n      - name: getproductdetails\n        method: GET\n        description: Get Product Details\n        inputParameters:\n        - name: ingramPartNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      operations:\n      - name: createorder\n        method: POST\n        description: Create Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders-orderid\n      path: /orders/{orderId}\n      operations:\n      - name: getorderstatus\n        method: GET\n        description: Get Order Status\n        inputParameters:\n        - name: orderId\n   \
  \       in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricing\n      path: /pricing\n      operations:\n      - name: getpricing\n        method: POST\n        description: Get Pricing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ingram-micro-rest\n    description: REST adapter for Ingram Micro Reseller API.\n    resources:\n    - path: /catalog\n      name: getcatalog\n      operations:\n      - method: GET\n        name: getcatalog\n        description: Search Product Catalog\n        call: ingram-micro.getcatalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /catalog/{ingramPartNumber}\n      name: getproductdetails\n      operations:\n      - method: GET\n\
  \        name: getproductdetails\n        description: Get Product Details\n        call: ingram-micro.getproductdetails\n        with:\n          ingramPartNumber: rest.ingramPartNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Create Order\n        call: ingram-micro.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orders/{orderId}\n      name: getorderstatus\n      operations:\n      - method: GET\n        name: getorderstatus\n        description: Get Order Status\n        call: ingram-micro.getorderstatus\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pricing\n      name: getpricing\n      operations:\n      - method: POST\n        name: getpricing\n        description: Get Pricing\n\
  \        call: ingram-micro.getpricing\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ingram-micro-mcp\n    transport: http\n    description: MCP adapter for Ingram Micro Reseller API for AI agent use.\n    tools:\n    - name: getcatalog\n      description: Search Product Catalog\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ingram-micro.getcatalog\n      with:\n        keyword: tools.keyword\n        category: tools.category\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: keyword\n        type: string\n        description: keyword\n      - name: category\n        type: string\n        description: category\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductdetails\n      description: Get Product Details\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ingram-micro.getproductdetails\n      with:\n        ingramPartNumber: tools.ingramPartNumber\n      inputParameters:\n      - name: ingramPartNumber\n        type: string\n        description: ingramPartNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Create Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ingram-micro.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorderstatus\n      description: Get Order Status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ingram-micro.getorderstatus\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n    \
  \    required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpricing\n      description: Get Pricing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ingram-micro.getpricing\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ingram-micro/refs/heads/main/capabilities/ingram-micro-capability.yaml
tags:
- Ingram
- Micro
- API
tools:
- description: Search Product Catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcatalog
- description: Get Product Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductdetails
- description: Create Order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Get Order Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorderstatus
- description: Get Pricing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getpricing
---
