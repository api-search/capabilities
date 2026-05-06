---
categories: []
consumed_apis: []
description: Workflow capability for VTEX merchandising teams managing product catalogs. Combines catalog, promotions, and pricing capabilities for catalog managers, merchandisers, and content teams who create and maintain product listings, pricing rules, and promotional campaigns.
layout: capability
name: VTEX Catalog Management
operations:
- description: Get full product category tree
  method: GET
  name: get-category-tree
  path: /v1/categories
- description: Create a new product in the catalog
  method: POST
  name: create-product
  path: /v1/products
- description: Get product by ID
  method: GET
  name: get-product
  path: /v1/products/{productId}
- description: Create a new SKU
  method: POST
  name: create-sku
  path: /v1/skus
- description: Get SKU by ID
  method: GET
  name: get-sku
  path: /v1/skus/{skuId}
- description: List all promotions
  method: GET
  name: list-promotions
  path: /v1/promotions
- description: List all coupons
  method: GET
  name: list-coupons
  path: /v1/coupons
- description: Create a new coupon
  method: POST
  name: create-coupon
  path: /v1/coupons
personas: []
provider_name: VTEX
provider_slug: vtex
search_terms:
- list promotions
- marketplace
- retrieve the full product category hierarchy from the vtex catalog
- sku management
- get full product category tree
- create a new sku variant for an existing product
- create a new product in the catalog
- single sku operations
- get sku details by sku id
- list all coupons
- vtex
- get product
- get product by id
- list coupons
- retail
- list all discount coupons configured in vtex
- e-commerce
- get product details from the vtex catalog by product id
- get promotion
- commerce
- create coupon
- product management
- list all active promotions and discount configurations in vtex
- merchandising
- product category management
- get full details of a specific vtex promotion
- create a new coupon
- promotions
- single product operations
- create a new discount coupon for a vtex promotion
- payments
- list all promotions
- coupon management
- promotion and discount management
- pricing
- create product
- get sku
- get category tree
- catalog
- get sku by id
- create sku
- create a new sku
- create a new product entry in the vtex catalog
slug: catalog-management
source_filename: catalog-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VTEX Catalog Management\n  description: Workflow capability for VTEX merchandising teams managing product catalogs. Combines catalog, promotions, and\n    pricing capabilities for catalog managers, merchandisers, and content teams who create and maintain product listings,\n    pricing rules, and promotional campaigns.\n  tags:\n  - Catalog\n  - Commerce\n  - Merchandising\n  - Pricing\n  - Promotions\n  - VTEX\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VTEX_APP_KEY: VTEX_APP_KEY\n    VTEX_APP_TOKEN: VTEX_APP_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vtex-catalog\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Catalog API for managing products, SKUs, categories and brands.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n    - name: categories\n\
  \      path: /api/catalog_system/pub/category/tree\n      description: Product category tree management\n      operations:\n      - name: get-category-tree\n        method: GET\n        description: Get Category Tree\n        inputParameters:\n        - name: categoryLevels\n          in: path\n          type: integer\n          required: false\n          description: Number of levels to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: products\n      path: /api/catalog/pvt/product\n      description: Product management operations\n      operations:\n      - name: create-product\n        method: POST\n        description: Create Product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            CategoryId: '{{tools.categoryId}}'\n\
  \            BrandId: '{{tools.brandId}}'\n      - name: get-product\n        method: GET\n        description: Get Product by ID\n        inputParameters:\n        - name: productId\n          in: path\n          type: integer\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: skus\n      path: /api/catalog/pvt/stockkeepingunit\n      description: SKU management operations\n      operations:\n      - name: create-sku\n        method: POST\n        description: Create SKU\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ProductId: '{{tools.productId}}'\n            Name: '{{tools.name}}'\n            IsActive: '{{tools.isActive}}'\n      - name: get-sku\n        method: GET\n        description:\
  \ Get SKU by ID\n        inputParameters:\n        - name: skuId\n          in: path\n          type: integer\n          required: true\n          description: SKU identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: vtex-promotions\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Promotions and Taxes API for managing campaigns, coupons, and discounts.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n    - name: promotions\n      path: /api/rnb/pvt/benefits/calculatorconfiguration\n      description: Promotion and campaign management\n      operations:\n      - name: list-promotions\n        method: GET\n        description: Get All Promotions and Taxes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: get-promotion\n        method: GET\n        description: Get Promotion or Tax by ID\n        inputParameters:\n        - name: idCalculatorConfiguration\n          in: path\n          type: string\n          required: true\n          description: Promotion configuration identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coupons\n      path: /api/rnb/pvt/coupon\n      description: Coupon management\n      operations:\n      - name: list-coupons\n        method: GET\n        description: Get All Coupons\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-coupon\n        method: POST\n        description: Create Coupon\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            utmSource: '{{tools.utmSource}}'\n            quantity: '{{tools.quantity}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: vtex-catalog-management-api\n    description: Unified REST API for VTEX catalog and promotional content management.\n    resources:\n    - path: /v1/categories\n      name: categories\n      description: Product category management\n      operations:\n      - method: GET\n        name: get-category-tree\n        description: Get full product category tree\n        call: vtex-catalog.get-category-tree\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product management\n      operations:\n      - method: POST\n        name: create-product\n        description: Create a new product in the catalog\n        call: vtex-catalog.create-product\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/products/{productId}\n      name: product\n      description: Single product operations\n      operations:\n      - method: GET\n        name: get-product\n        description: Get product by ID\n        call: vtex-catalog.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skus\n      name: skus\n      description: SKU management\n      operations:\n      - method: POST\n        name: create-sku\n        description: Create a new SKU\n        call: vtex-catalog.create-sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/skus/{skuId}\n      name: sku\n      description: Single SKU operations\n      operations:\n      - method: GET\n        name: get-sku\n        description: Get SKU by ID\n        call: vtex-catalog.get-sku\n        with:\n          skuId: rest.skuId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/promotions\n      name: promotions\n      description: Promotion and discount management\n      operations:\n      - method: GET\n        name: list-promotions\n        description: List all promotions\n        call: vtex-promotions.list-promotions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/coupons\n      name: coupons\n      description: Coupon management\n      operations:\n      - method: GET\n        name: list-coupons\n        description: List all coupons\n        call: vtex-promotions.list-coupons\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-coupon\n        description: Create a new coupon\n        call: vtex-promotions.create-coupon\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: vtex-catalog-management-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted VTEX catalog and promotional content management.\n    tools:\n    - name: get-category-tree\n      description: Retrieve the full product category hierarchy from the VTEX catalog\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-catalog.get-category-tree\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-product\n      description: Create a new product entry in the VTEX catalog\n      hints:\n        readOnly: false\n        destructive: false\n      call: vtex-catalog.create-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get product details from the VTEX catalog by product ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-catalog.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sku\n\
  \      description: Create a new SKU variant for an existing product\n      hints:\n        readOnly: false\n        destructive: false\n      call: vtex-catalog.create-sku\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sku\n      description: Get SKU details by SKU ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-catalog.get-sku\n      with:\n        skuId: tools.skuId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-promotions\n      description: List all active promotions and discount configurations in VTEX\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-promotions.list-promotions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-promotion\n      description: Get full details of a specific VTEX promotion\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-promotions.get-promotion\n\
  \      with:\n        idCalculatorConfiguration: tools.idCalculatorConfiguration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-coupons\n      description: List all discount coupons configured in VTEX\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-promotions.list-coupons\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-coupon\n      description: Create a new discount coupon for a VTEX promotion\n      hints:\n        readOnly: false\n        destructive: false\n      call: vtex-promotions.create-coupon\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vtex/refs/heads/main/capabilities/catalog-management.yaml
tags:
- Catalog
- Commerce
- Merchandising
- Pricing
- Promotions
- VTEX
tools:
- description: Retrieve the full product category hierarchy from the VTEX catalog
  hints:
    idempotent: true
    readOnly: true
  name: get-category-tree
- description: Create a new product entry in the VTEX catalog
  hints:
    destructive: false
    readOnly: false
  name: create-product
- description: Get product details from the VTEX catalog by product ID
  hints:
    idempotent: true
    readOnly: true
  name: get-product
- description: Create a new SKU variant for an existing product
  hints:
    destructive: false
    readOnly: false
  name: create-sku
- description: Get SKU details by SKU ID
  hints:
    idempotent: true
    readOnly: true
  name: get-sku
- description: List all active promotions and discount configurations in VTEX
  hints:
    idempotent: true
    readOnly: true
  name: list-promotions
- description: Get full details of a specific VTEX promotion
  hints:
    idempotent: true
    readOnly: true
  name: get-promotion
- description: List all discount coupons configured in VTEX
  hints:
    idempotent: true
    readOnly: true
  name: list-coupons
- description: Create a new discount coupon for a VTEX promotion
  hints:
    destructive: false
    readOnly: false
  name: create-coupon
---
