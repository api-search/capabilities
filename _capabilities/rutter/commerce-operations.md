---
categories: []
consumed_apis:
- rutter
description: Unified workflow for managing commerce operations across platforms like Shopify, WooCommerce, Amazon, BigCommerce, and Magento. Enables operations teams to read and manage orders, products, customers, and fulfillments through a single interface regardless of the underlying commerce platform.
layout: capability
name: Rutter Commerce Operations
operations:
- description: List orders from connected commerce platform
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order in connected commerce platform
  method: POST
  name: create-order
  path: /v1/orders
- description: Get a specific order by ID
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Mark an order as fulfilled
  method: POST
  name: fulfill-order
  path: /v1/orders/{orderId}/fulfillments
- description: List products from connected commerce platform
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product in connected commerce platform
  method: POST
  name: create-product
  path: /v1/products
- description: Get a specific product by ID
  method: GET
  name: get-product
  path: /v1/products/{productId}
- description: Update a product in connected commerce platform
  method: PUT
  name: update-product
  path: /v1/products/{productId}
- description: List customers from connected platform
  method: GET
  name: list-customers
  path: /v1/customers
- description: Get a specific customer by ID
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
personas: []
provider_name: Rutter
provider_slug: rutter
search_terms:
- create product
- list orders from connected commerce platform (shopify, woocommerce, amazon)
- get a specific customer by id
- e-commerce
- list products
- create a new order in the connected commerce platform
- list customers
- get a specific customer by id from connected platform
- list customers from connected commerce or accounting platform
- commerce
- single product
- accounting
- update a product in connected commerce platform
- get order
- update product
- single customer
- financial data
- update an existing product in the connected commerce platform
- get a specific order by id from connected commerce platform
- mark an order as fulfilled with tracking information
- create a new product in the connected commerce platform
- get a specific order by id
- get a specific product by id
- customer data
- products
- create a new product in connected commerce platform
- list orders from connected commerce platform
- get a specific product by id from connected commerce platform
- commerce orders
- get customer
- payments
- mark an order as fulfilled
- b2b
- list customers from connected platform
- order fulfillments
- get product
- unified api
- list orders
- orders
- fulfill order
- create order
- list products from connected commerce platform
- product catalog
- create a new order in connected commerce platform
- single order
slug: commerce-operations
source_filename: commerce-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Rutter Commerce Operations\"\n  description: >-\n    Unified workflow for managing commerce operations across platforms like Shopify,\n    WooCommerce, Amazon, BigCommerce, and Magento. Enables operations teams to\n    read and manage orders, products, customers, and fulfillments through a single\n    interface regardless of the underlying commerce platform.\n  tags:\n    - B2B\n    - Commerce\n    - E-Commerce\n    - Orders\n    - Products\n    - Unified API\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RUTTER_CLIENT_ID: RUTTER_CLIENT_ID\n      RUTTER_CLIENT_SECRET: RUTTER_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: rutter\n      location: ./shared/unified-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: rutter-commerce-ops-api\n      description: \"Unified REST API for commerce operations across e-commerce platforms.\"\n      resources:\n\
  \        - path: /v1/orders\n          name: orders\n          description: \"Commerce orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders from connected commerce platform\"\n              call: \"rutter.list-orders\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                cursor: \"rest.query.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new order in connected commerce platform\"\n              call: \"rutter.create-order\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n \
  \                 mapping: \"$.\"\n        - path: /v1/orders/{orderId}\n          name: order\n          description: \"Single order\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get a specific order by ID\"\n              call: \"rutter.get-order\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                orderId: \"rest.path.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{orderId}/fulfillments\n          name: fulfillments\n          description: \"Order fulfillments\"\n          operations:\n            - method: POST\n              name: fulfill-order\n              description: \"Mark an order as fulfilled\"\n              call: \"rutter.fulfill-order\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\
  \n                access_token: \"rest.query.access_token\"\n                orderId: \"rest.path.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: \"Product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List products from connected commerce platform\"\n              call: \"rutter.list-products\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new product in connected commerce platform\"\n              call: \"rutter.create-product\"\n              with:\n                X-Rutter-Version:\
  \ \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{productId}\n          name: product\n          description: \"Single product\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get a specific product by ID\"\n              call: \"rutter.get-product\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                productId: \"rest.path.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-product\n              description: \"Update a product in connected commerce platform\"\n              call: \"rutter.update-product\"\n              with:\n\
  \                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                productId: \"rest.path.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: \"Customer data\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers from connected platform\"\n              call: \"rutter.list-customers\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer\n          description: \"Single customer\"\n          operations:\n            - method: GET\n   \
  \           name: get-customer\n              description: \"Get a specific customer by ID\"\n              call: \"rutter.get-customer\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                customerId: \"rest.path.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: rutter-commerce-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted commerce operations across e-commerce platforms.\"\n      tools:\n        - name: list-orders\n          description: \"List orders from connected commerce platform (Shopify, WooCommerce, Amazon)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-orders\"\n          with:\n            access_token: \"tools.access_token\"\n            cursor: \"tools.cursor\"\
  \n            updated_at_min: \"tools.updated_at_min\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Get a specific order by ID from connected commerce platform\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rutter.get-order\"\n          with:\n            access_token: \"tools.access_token\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-order\n          description: \"Create a new order in the connected commerce platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rutter.create-order\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ fulfill-order\n          description: \"Mark an order as fulfilled with tracking information\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rutter.fulfill-order\"\n          with:\n            access_token: \"tools.access_token\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: \"List products from connected commerce platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-products\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get a specific product by ID from connected commerce platform\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: false\n          call: \"rutter.get-product\"\n          with:\n            access_token: \"tools.access_token\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-product\n          description: \"Create a new product in the connected commerce platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rutter.create-product\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-product\n          description: \"Update an existing product in the connected commerce platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"rutter.update-product\"\n          with:\n            access_token:\
  \ \"tools.access_token\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: \"List customers from connected commerce or accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-customers\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get a specific customer by ID from connected platform\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rutter.get-customer\"\n          with:\n            access_token: \"tools.access_token\"\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rutter/refs/heads/main/capabilities/commerce-operations.yaml
tags:
- B2B
- Commerce
- E-Commerce
- Orders
- Products
- Unified API
tools:
- description: List orders from connected commerce platform (Shopify, WooCommerce, Amazon)
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get a specific order by ID from connected commerce platform
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Create a new order in the connected commerce platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Mark an order as fulfilled with tracking information
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfill-order
- description: List products from connected commerce platform
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get a specific product by ID from connected commerce platform
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Create a new product in the connected commerce platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-product
- description: Update an existing product in the connected commerce platform
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-product
- description: List customers from connected commerce or accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get a specific customer by ID from connected platform
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
---
