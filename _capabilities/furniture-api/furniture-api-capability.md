---
categories: []
consumed_apis: []
description: The Furniture API is a software interface that allows developers to access and integrate information about furniture products and designs into their applications. It provides product listings with filtering, product detail lookup by SKU, stock management, featured product flags, and discount application across an inventory of furniture items.
layout: capability
name: Furniture API
operations:
- description: List products
  method: GET
  name: listproducts
  path: /v1/products
- description: Get product by SKU
  method: GET
  name: getproductbysku
  path: /v1/products/{sku}
- description: Update stock levels
  method: PATCH
  name: updatestock
  path: /v1/products/stock
- description: Toggle featured status
  method: PATCH
  name: togglefeatured
  path: /v1/products/{sku}/featured
- description: Apply product discount
  method: PATCH
  name: applydiscount
  path: /v1/products/{sku}/discount
personas: []
provider_name: Furniture API
provider_slug: furniture-api
search_terms:
- updatestock
- e-commerce
- apply product discount
- listproducts
- toggle featured status
- get product by sku
- togglefeatured
- furniture
- list products
- products
- api
- update stock levels
- applydiscount
- getproductbysku
slug: furniture-api-capability
source_filename: furniture-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Furniture API\n  description: The Furniture API is a software interface that allows developers to access and integrate information about\n    furniture products and designs into their applications. It provides product listings with filtering, product detail lookup\n    by SKU, stock management, featured product flags, and discount application across an inventory of furniture items.\n  tags:\n  - Furniture\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: furniture-api\n    baseUri: https://furniture-api.fly.dev\n    description: Furniture API HTTP API.\n    resources:\n    - name: v1-products\n      path: /v1/products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: Filter products by category.\n\
  \        - name: minPrice\n          in: query\n          type: number\n          description: Minimum price filter.\n        - name: maxPrice\n          in: query\n          type: number\n          description: Maximum price filter.\n        - name: woodType\n          in: query\n          type: string\n          description: Filter products by wood type.\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination.\n        - name: limit\n          in: query\n          type: integer\n          description: Number of items returned per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-products-sku\n      path: /v1/products/{sku}\n      operations:\n      - name: getproductbysku\n        method: GET\n        description: Get product by SKU\n        inputParameters:\n        - name: sku\n          in: path\n          type: string\n\
  \          required: true\n          description: The unique stock keeping unit (SKU) for the product.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-products-stock\n      path: /v1/products/stock\n      operations:\n      - name: updatestock\n        method: PATCH\n        description: Update stock levels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-products-sku-featured\n      path: /v1/products/{sku}/featured\n      operations:\n      - name: togglefeatured\n        method: PATCH\n        description: Toggle featured status\n        inputParameters:\n        - name: sku\n          in: path\n          type: string\n          required: true\n          description: The SKU of the product to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: v1-products-sku-discount\n      path: /v1/products/{sku}/discount\n      operations:\n      - name: applydiscount\n        method: PATCH\n        description: Apply product discount\n        inputParameters:\n        - name: sku\n          in: path\n          type: string\n          required: true\n          description: The SKU of the product to discount.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: furniture-api-rest\n    description: REST adapter for Furniture API.\n    resources:\n    - path: /v1/products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n        call: furniture-api.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}\n      name: getproductbysku\n\
  \      operations:\n      - method: GET\n        name: getproductbysku\n        description: Get product by SKU\n        call: furniture-api.getproductbysku\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/stock\n      name: updatestock\n      operations:\n      - method: PATCH\n        name: updatestock\n        description: Update stock levels\n        call: furniture-api.updatestock\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}/featured\n      name: togglefeatured\n      operations:\n      - method: PATCH\n        name: togglefeatured\n        description: Toggle featured status\n        call: furniture-api.togglefeatured\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}/discount\n      name: applydiscount\n      operations:\n      - method:\
  \ PATCH\n        name: applydiscount\n        description: Apply product discount\n        call: furniture-api.applydiscount\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: furniture-api-mcp\n    transport: http\n    description: MCP adapter for Furniture API for AI agent use.\n    tools:\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: furniture-api.listproducts\n      with:\n        category: tools.category\n        minPrice: tools.minPrice\n        maxPrice: tools.maxPrice\n        woodType: tools.woodType\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter products by category.\n      - name: minPrice\n        type: number\n        description: Minimum price\
  \ filter.\n      - name: maxPrice\n        type: number\n        description: Maximum price filter.\n      - name: woodType\n        type: string\n        description: Filter products by wood type.\n      - name: page\n        type: integer\n        description: Page number for pagination.\n      - name: limit\n        type: integer\n        description: Number of items returned per page.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductbysku\n      description: Get product by SKU\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: furniture-api.getproductbysku\n      with:\n        sku: tools.sku\n      inputParameters:\n      - name: sku\n        type: string\n        description: The unique stock keeping unit (SKU) for the product.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatestock\n      description: Update stock levels\n \
  \     hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: furniture-api.updatestock\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: togglefeatured\n      description: Toggle featured status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: furniture-api.togglefeatured\n      with:\n        sku: tools.sku\n      inputParameters:\n      - name: sku\n        type: string\n        description: The SKU of the product to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: applydiscount\n      description: Apply product discount\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: furniture-api.applydiscount\n      with:\n        sku: tools.sku\n      inputParameters:\n      - name: sku\n        type: string\n        description: The SKU of the\
  \ product to discount.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/furniture-api/refs/heads/main/capabilities/furniture-api-capability.yaml
tags:
- Furniture
- Api
- API
tools:
- description: List products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Get product by SKU
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductbysku
- description: Update stock levels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatestock
- description: Toggle featured status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: togglefeatured
- description: Apply product discount
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: applydiscount
---
