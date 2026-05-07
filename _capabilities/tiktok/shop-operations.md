---
categories: []
consumed_apis: []
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
- social media
- video
- get product
- get product details
- list products
- list all shop orders
- fulfillment
- orders
- order management
- get tiktok shop product details
- individual product management
- list products in tiktok shop catalog
- products
- list orders
- content
- financial settlement records
- e-commerce
- individual order management
- list tiktok shop payment settlement records
- get detailed tiktok shop order information
- get order details
- list tiktok shop orders with status filtering
- list products in the shop catalog
- list payment settlements
- tiktok
- product catalog management
- advertising
- commerce
- list payments
- get order
slug: shop-operations
source_filename: shop-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TikTok Shop Operations\n  description: Workflow capability for TikTok Shop e-commerce operations. Uses the TikTok Shop API to manage product catalogs,\n    fulfill orders, track logistics, and monitor financial settlements. Designed for sellers, marketplace integrators, and\n    e-commerce platforms.\n  tags:\n  - TikTok\n  - Commerce\n  - E-Commerce\n  - Products\n  - Orders\n  - Fulfillment\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIKTOK_SHOP_ACCESS_TOKEN: TIKTOK_SHOP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tiktok-shop\n    baseUri: https://open-api.tiktokglobalshop.com\n    description: TikTok Shop API for seller product and order management\n    authentication:\n      type: apikey\n      key: x-tts-access-token\n      value: '{{TIKTOK_SHOP_ACCESS_TOKEN}}'\n      placement: header\n    resources:\n    - name: products\n      path: /product/202309/products\n\
  \      description: Product catalog management\n      operations:\n      - name: list-products\n        method: GET\n        description: Retrieve products from seller catalog\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        - name: page_token\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get product details by ID\n        inputParameters:\n        - name: product_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path:\
  \ /order/202309/orders\n      description: Order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List seller orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        - name: order_status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get order details by ID\n        inputParameters:\n        - name: order_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: finance\n      path: /finance/202309/payments\n      description: Payment and settlement data\n      operations:\n      - name:\
  \ list-payments\n        method: GET\n        description: List payment settlement records\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: tiktok-shop-operations-api\n    description: Unified REST API for TikTok Shop operations.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Product catalog management\n      operations:\n      - method: GET\n        name: list-products\n        description: List products in the shop catalog\n        call: tiktok-shop.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{product_id}\n      name: product-detail\n      description: Individual product management\n      operations:\n      - method: GET\n\
  \        name: get-product\n        description: Get product details\n        call: tiktok-shop.get-product\n        with:\n          product_id: rest.product_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List all shop orders\n        call: tiktok-shop.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{order_id}\n      name: order-detail\n      description: Individual order management\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order details\n        call: tiktok-shop.get-order\n        with:\n          order_id: rest.order_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Financial settlement\
  \ records\n      operations:\n      - method: GET\n        name: list-payments\n        description: List payment settlements\n        call: tiktok-shop.list-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: tiktok-shop-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted TikTok Shop operations.\n    tools:\n    - name: list-products\n      description: List products in TikTok Shop catalog\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-shop.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get TikTok Shop product details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-shop.get-product\n      with:\n        product_id: tools.product_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n    \
  \  description: List TikTok Shop orders with status filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-shop.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get detailed TikTok Shop order information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-shop.get-order\n      with:\n        order_id: tools.order_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payments\n      description: List TikTok Shop payment settlement records\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tiktok-shop.list-payments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
