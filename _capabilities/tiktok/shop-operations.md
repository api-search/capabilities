---
categories: []
consumed_apis:
- tiktok-shop
description: Workflow capability for TikTok Shop e-commerce operations. Uses the TikTok Shop API to manage product catalogs, fulfill orders, track logistics, and monitor financial settlements. Designed for sellers, marketplace integrators, and e-commerce platforms.
layout: capability
name: TikTok Shop Operations
operations:
- description: List products in the shop catalog
  method: GET
  name: list-products
  path: /v1/products
- description: Get product details
  method: GET
  name: get-product
  path: /v1/products/{product_id}
- description: List all shop orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get order details
  method: GET
  name: get-order
  path: /v1/orders/{order_id}
- description: List payment settlements
  method: GET
  name: list-payments
  path: /v1/payments
personas: []
provider_name: TikTok
provider_slug: tiktok
search_terms:
- video
- list payments
- list products in the shop catalog
- fulfillment
- orders
- get tiktok shop product details
- e-commerce
- advertising
- get product details
- individual product management
- products
- financial settlement records
- content
- list payment settlements
- order management
- get order
- commerce
- get order details
- list all shop orders
- product catalog management
- list tiktok shop payment settlement records
- tiktok
- social media
- list products
- list products in tiktok shop catalog
- get product
- list orders
- list tiktok shop orders with status filtering
- individual order management
- get detailed tiktok shop order information
slug: shop-operations
source_filename: shop-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TikTok Shop Operations\"\n  description: >-\n    Workflow capability for TikTok Shop e-commerce operations. Uses the TikTok\n    Shop API to manage product catalogs, fulfill orders, track logistics, and\n    monitor financial settlements. Designed for sellers, marketplace integrators,\n    and e-commerce platforms.\n  tags:\n    - TikTok\n    - Commerce\n    - E-Commerce\n    - Products\n    - Orders\n    - Fulfillment\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TIKTOK_SHOP_ACCESS_TOKEN: TIKTOK_SHOP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tiktok-shop\n      location: ./shared/shop-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: tiktok-shop-operations-api\n      description: \"Unified REST API for TikTok Shop operations.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Product\
  \ catalog management\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List products in the shop catalog\"\n              call: \"tiktok-shop.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{product_id}\n          name: product-detail\n          description: \"Individual product management\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get product details\"\n              call: \"tiktok-shop.get-product\"\n              with:\n                product_id: \"rest.product_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Order management\"\n          operations:\n            - method: GET\n              name: list-orders\n      \
  \        description: \"List all shop orders\"\n              call: \"tiktok-shop.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{order_id}\n          name: order-detail\n          description: \"Individual order management\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get order details\"\n              call: \"tiktok-shop.get-order\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: \"Financial settlement records\"\n          operations:\n            - method: GET\n              name: list-payments\n              description: \"List payment settlements\"\n              call: \"tiktok-shop.list-payments\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: tiktok-shop-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TikTok Shop operations.\"\n      tools:\n        - name: list-products\n          description: \"List products in TikTok Shop catalog\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tiktok-shop.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get TikTok Shop product details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tiktok-shop.get-product\"\n          with:\n            product_id: \"tools.product_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List TikTok Shop\
  \ orders with status filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tiktok-shop.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Get detailed TikTok Shop order information\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tiktok-shop.get-order\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payments\n          description: \"List TikTok Shop payment settlement records\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tiktok-shop.list-payments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tiktok/refs/heads/main/capabilities/shop-operations.yaml
tags:
- TikTok
- Commerce
- E-Commerce
- Products
- Orders
- Fulfillment
tools:
- description: List products in TikTok Shop catalog
  hints:
    idempotent: true
    readOnly: true
  name: list-products
- description: Get TikTok Shop product details
  hints:
    idempotent: true
    readOnly: true
  name: get-product
- description: List TikTok Shop orders with status filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
- description: Get detailed TikTok Shop order information
  hints:
    idempotent: true
    readOnly: true
  name: get-order
- description: List TikTok Shop payment settlement records
  hints:
    idempotent: true
    readOnly: true
  name: list-payments
---
