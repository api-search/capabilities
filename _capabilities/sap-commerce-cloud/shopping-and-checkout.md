---
categories: []
consumed_apis:
- sap-commerce-occ
description: Workflow capability for the customer shopping journey in SAP Commerce Cloud. Covers product discovery, cart management, checkout, and order tracking for both B2B and B2C scenarios. Used by storefront developers, mobile app developers, and commerce integration engineers.
layout: capability
name: SAP Commerce Cloud Shopping and Checkout
operations:
- description: Search the product catalog.
  method: GET
  name: search-products
  path: /v1/products
- description: Get product details.
  method: GET
  name: get-product
  path: /v1/products/{productCode}
- description: List user order history.
  method: GET
  name: list-orders
  path: /v1/users/{userId}/orders
- description: Get order details.
  method: GET
  name: get-order
  path: /v1/users/{userId}/orders/{code}
- description: Find nearby stores.
  method: GET
  name: find-stores
  path: /v1/stores
personas: []
provider_name: SAP Commerce Cloud
provider_slug: sap-commerce-cloud
search_terms:
- get details and status of a specific order.
- list user order history.
- ecommerce
- add to cart
- get product details.
- commerce
- list order history for a customer.
- get order details.
- get order
- find nearby stores.
- add a product to the customer's shopping cart.
- store locator.
- get detailed product information including price, stock, images, and reviews.
- get the customer's current shopping cart contents and totals.
- customer experience
- single order.
- get cart
- omnichannel
- retail
- b2b
- get product
- find physical store locations for click-and-collect or in-store assistance.
- product catalog search.
- search the product catalog.
- list orders
- search the sap commerce cloud product catalog using keywords or facets.
- order management.
- single product.
- sap
- search products
- find stores
- b2c
slug: shopping-and-checkout
source_filename: shopping-and-checkout.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Commerce Cloud Shopping and Checkout\"\n  description: \"Workflow capability for the customer shopping journey in SAP Commerce Cloud. Covers product discovery, cart management, checkout, and order tracking for both B2B and B2C scenarios. Used by storefront developers, mobile app developers, and commerce integration engineers.\"\n  tags:\n    - B2B\n    - B2C\n    - Commerce\n    - Customer Experience\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_COMMERCE_OAUTH_TOKEN: SAP_COMMERCE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-commerce-occ\n      location: ./shared/commerce-web-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sap-commerce-shopping-api\n      description: \"Unified REST API for SAP Commerce Cloud shopping and order management.\"\n      resources:\n        - path: /v1/products\n          name: products\n\
  \          description: \"Product catalog search.\"\n          operations:\n            - method: GET\n              name: search-products\n              description: \"Search the product catalog.\"\n              call: \"sap-commerce-occ.search-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{productCode}\n          name: product\n          description: \"Single product.\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get product details.\"\n              call: \"sap-commerce-occ.get-product\"\n              with:\n                productCode: \"rest.productCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}/orders\n          name: orders\n          description: \"Order management.\"\n          operations:\n            - method: GET\n   \
  \           name: list-orders\n              description: \"List user order history.\"\n              call: \"sap-commerce-occ.list-orders\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}/orders/{code}\n          name: order\n          description: \"Single order.\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get order details.\"\n              call: \"sap-commerce-occ.get-order\"\n              with:\n                userId: \"rest.userId\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores\n          name: stores\n          description: \"Store locator.\"\n          operations:\n            - method: GET\n              name: find-stores\n              description:\
  \ \"Find nearby stores.\"\n              call: \"sap-commerce-occ.list-stores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sap-commerce-shopping-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Commerce Cloud shopping and checkout.\"\n      tools:\n        - name: search-products\n          description: \"Search the SAP Commerce Cloud product catalog using keywords or facets.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-occ.search-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get detailed product information including price, stock, images, and reviews.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-commerce-occ.get-product\"\
  \n          with:\n            productCode: \"tools.productCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-to-cart\n          description: \"Add a product to the customer's shopping cart.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sap-commerce-occ.add-to-cart\"\n          with:\n            userId: \"tools.userId\"\n            cartId: \"tools.cartId\"\n            productCode: \"tools.productCode\"\n            quantity: \"tools.quantity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cart\n          description: \"Get the customer's current shopping cart contents and totals.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-commerce-occ.get-cart\"\n          with:\n            userId: \"tools.userId\"\n            cartId: \"tools.cartId\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List order history for a customer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-commerce-occ.list-orders\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Get details and status of a specific order.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-commerce-occ.get-order\"\n          with:\n            userId: \"tools.userId\"\n            code: \"tools.orderCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-stores\n          description: \"Find physical store locations for click-and-collect or in-store assistance.\"\n          hints:\n   \
  \         readOnly: true\n            openWorld: true\n          call: \"sap-commerce-occ.list-stores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-commerce-cloud/refs/heads/main/capabilities/shopping-and-checkout.yaml
tags:
- B2B
- B2C
- Commerce
- Customer Experience
- SAP
tools:
- description: Search the SAP Commerce Cloud product catalog using keywords or facets.
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get detailed product information including price, stock, images, and reviews.
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Add a product to the customer's shopping cart.
  hints:
    idempotent: false
    readOnly: false
  name: add-to-cart
- description: Get the customer's current shopping cart contents and totals.
  hints:
    openWorld: false
    readOnly: true
  name: get-cart
- description: List order history for a customer.
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get details and status of a specific order.
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Find physical store locations for click-and-collect or in-store assistance.
  hints:
    openWorld: true
    readOnly: true
  name: find-stores
---
