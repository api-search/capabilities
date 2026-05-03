---
categories: []
consumed_apis:
- vtex-catalog
- vtex-promotions
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
- list all promotions
- create a new coupon
- create product
- product management
- create a new sku variant for an existing product
- get sku by id
- create a new sku
- list promotions
- list coupons
- marketplace
- get sku
- e-commerce
- create a new product entry in the vtex catalog
- get full details of a specific vtex promotion
- get product details from the vtex catalog by product id
- single sku operations
- promotion and discount management
- get full product category tree
- list all active promotions and discount configurations in vtex
- catalog
- single product operations
- pricing
- create coupon
- payments
- retrieve the full product category hierarchy from the vtex catalog
- create a new discount coupon for a vtex promotion
- create sku
- list all coupons
- commerce
- merchandising
- coupon management
- get product by id
- retail
- create a new product in the catalog
- promotions
- sku management
- get promotion
- product category management
- vtex
- get product
- get category tree
- list all discount coupons configured in vtex
- get sku details by sku id
slug: catalog-management
source_filename: catalog-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VTEX Catalog Management\"\n  description: >-\n    Workflow capability for VTEX merchandising teams managing product catalogs.\n    Combines catalog, promotions, and pricing capabilities for catalog managers,\n    merchandisers, and content teams who create and maintain product listings,\n    pricing rules, and promotional campaigns.\n  tags:\n    - Catalog\n    - Commerce\n    - Merchandising\n    - Pricing\n    - Promotions\n    - VTEX\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VTEX_APP_KEY: VTEX_APP_KEY\n      VTEX_APP_TOKEN: VTEX_APP_TOKEN\n\ncapability:\n  consumes:\n    - import: vtex-catalog\n      location: ./shared/catalog.yaml\n    - import: vtex-promotions\n      location: ./shared/promotions.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: vtex-catalog-management-api\n      description: \"Unified REST API for VTEX catalog and promotional\
  \ content management.\"\n      resources:\n        - path: /v1/categories\n          name: categories\n          description: \"Product category management\"\n          operations:\n            - method: GET\n              name: get-category-tree\n              description: \"Get full product category tree\"\n              call: \"vtex-catalog.get-category-tree\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products\n          description: \"Product management\"\n          operations:\n            - method: POST\n              name: create-product\n              description: \"Create a new product in the catalog\"\n              call: \"vtex-catalog.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{productId}\n          name: product\n          description: \"Single product operations\"\
  \n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get product by ID\"\n              call: \"vtex-catalog.get-product\"\n              with:\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/skus\n          name: skus\n          description: \"SKU management\"\n          operations:\n            - method: POST\n              name: create-sku\n              description: \"Create a new SKU\"\n              call: \"vtex-catalog.create-sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/skus/{skuId}\n          name: sku\n          description: \"Single SKU operations\"\n          operations:\n            - method: GET\n              name: get-sku\n              description: \"Get SKU by ID\"\n              call: \"vtex-catalog.get-sku\"\
  \n              with:\n                skuId: \"rest.skuId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/promotions\n          name: promotions\n          description: \"Promotion and discount management\"\n          operations:\n            - method: GET\n              name: list-promotions\n              description: \"List all promotions\"\n              call: \"vtex-promotions.list-promotions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/coupons\n          name: coupons\n          description: \"Coupon management\"\n          operations:\n            - method: GET\n              name: list-coupons\n              description: \"List all coupons\"\n              call: \"vtex-promotions.list-coupons\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n            - method: POST\n\
  \              name: create-coupon\n              description: \"Create a new coupon\"\n              call: \"vtex-promotions.create-coupon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: vtex-catalog-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VTEX catalog and promotional content management.\"\n      tools:\n        - name: get-category-tree\n          description: \"Retrieve the full product category hierarchy from the VTEX catalog\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-catalog.get-category-tree\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-product\n          description: \"Create a new product entry in the VTEX catalog\"\n          hints:\n            readOnly: false\n            destructive: false\n   \
  \       call: \"vtex-catalog.create-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product\n          description: \"Get product details from the VTEX catalog by product ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-catalog.get-product\"\n          with:\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-sku\n          description: \"Create a new SKU variant for an existing product\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vtex-catalog.create-sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sku\n          description: \"Get SKU details by SKU ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n  \
  \        call: \"vtex-catalog.get-sku\"\n          with:\n            skuId: \"tools.skuId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-promotions\n          description: \"List all active promotions and discount configurations in VTEX\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-promotions.list-promotions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-promotion\n          description: \"Get full details of a specific VTEX promotion\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-promotions.get-promotion\"\n          with:\n            idCalculatorConfiguration: \"tools.idCalculatorConfiguration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-coupons\n          description: \"List\
  \ all discount coupons configured in VTEX\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-promotions.list-coupons\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-coupon\n          description: \"Create a new discount coupon for a VTEX promotion\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vtex-promotions.create-coupon\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
