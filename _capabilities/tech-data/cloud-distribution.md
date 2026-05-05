---
api_specs:
- filename: streamone-ion-openapi.yml
  format: yaml
  label: streamone-ion
  slug: streamone-ion
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tech-data/refs/heads/main/openapi/streamone-ion-openapi.yml
categories: []
consumed_apis:
- streamone-ion
description: Unified cloud distribution workflow for TD SYNNEX reseller partners. Combines customer lifecycle management, product catalog browsing, order processing, subscription management, and business reporting through the StreamOne Ion API. Designed for partner sales engineers, managed service providers, and cloud resellers who need to automate their TD SYNNEX distribution workflows.
layout: capability
name: TD SYNNEX Cloud Distribution
operations:
- description: List all end customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new end customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get customer details
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: List customer subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/customers/{customerId}/subscriptions
- description: Browse available products
  method: GET
  name: list-products
  path: /v1/products
- description: List all orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order details
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Cancel an order
  method: DELETE
  name: cancel-order
  path: /v1/orders/{orderId}
- description: List shopping carts
  method: GET
  name: list-carts
  path: /v1/carts
- description: Create a new cart
  method: POST
  name: create-cart
  path: /v1/carts
- description: List available reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Get data for a report
  method: GET
  name: get-report-data
  path: /v1/reports/{reportId}/data
personas: []
provider_name: Tech Data
provider_slug: tech-data
search_terms:
- create a new cart
- list carts
- list all end customers for the reseller account
- get report data
- checkout cart
- e-commerce
- list products
- list customers
- get order details
- get details for a specific end customer
- list customer subscriptions
- cloud
- check out a cart to create an order
- end customer account management
- cancel an order
- add cart item
- get order
- single customer operations
- list available reports
- list available billing and business reports
- create a new product order for a customer
- business and billing reports
- list all orders
- list all end customers
- get data for a report
- reseller
- list active subscriptions for a customer
- shopping cart management
- get details for a specific order
- get data from a billing or business report
- cancel order
- get customer
- create cart
- cancel an unprocessed order
- single order operations
- get product
- partner
- report data retrieval
- list orders
- create a new end customer account
- get customer details
- create order
- list all orders for the account
- browse the td synnex product catalog
- add a product to a shopping cart
- list subscriptions
- create customer
- browse available products
- list shopping carts
- information technology
- order management
- create a new order
- list reports
- get details for a specific product
- create a new end customer
- product catalog
- distribution
- customer subscription management
- create a new shopping cart for order building
slug: cloud-distribution
source_filename: cloud-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TD SYNNEX Cloud Distribution\"\n  description: >-\n    Unified cloud distribution workflow for TD SYNNEX reseller partners. Combines\n    customer lifecycle management, product catalog browsing, order processing, subscription\n    management, and business reporting through the StreamOne Ion API. Designed for partner\n    sales engineers, managed service providers, and cloud resellers who need to automate\n    their TD SYNNEX distribution workflows.\n  tags:\n    - Cloud\n    - Distribution\n    - E-Commerce\n    - Partner\n    - Reseller\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      STREAMONE_ION_BEARER_TOKEN: STREAMONE_ION_BEARER_TOKEN\n      STREAMONE_ION_ACCOUNT_ID: STREAMONE_ION_ACCOUNT_ID\n\ncapability:\n  consumes:\n    - import: streamone-ion\n      location: ./shared/streamone-ion.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloud-distribution-api\n\
  \      description: \"Unified REST API for TD SYNNEX cloud distribution partner workflows.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"End customer account management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all end customers\"\n              call: \"streamone-ion.list-customers\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new end customer\"\n              call: \"streamone-ion.create-customer\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer\n\
  \          description: \"Single customer operations\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get customer details\"\n              call: \"streamone-ion.get-customer\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}/subscriptions\n          name: customer-subscriptions\n          description: \"Customer subscription management\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List customer subscriptions\"\n              call: \"streamone-ion.list-customer-subscriptions\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"rest.customerId\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: \"Product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"Browse available products\"\n              call: \"streamone-ion.list-products\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Order management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List all orders\"\n              call: \"streamone-ion.list-account-orders\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n\
  \              name: create-order\n              description: \"Create a new order\"\n              call: \"streamone-ion.create-order\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{orderId}\n          name: order\n          description: \"Single order operations\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get order details\"\n              call: \"streamone-ion.get-order\"\n              with:\n                accountId: \"rest.accountId\"\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-order\n              description: \"Cancel an order\"\n              call: \"streamone-ion.cancel-order\"\n              with:\n    \
  \            accountId: \"rest.accountId\"\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/carts\n          name: carts\n          description: \"Shopping cart management\"\n          operations:\n            - method: GET\n              name: list-carts\n              description: \"List shopping carts\"\n              call: \"streamone-ion.list-carts\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cart\n              description: \"Create a new cart\"\n              call: \"streamone-ion.create-cart\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n\
  \          name: reports\n          description: \"Business and billing reports\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List available reports\"\n              call: \"streamone-ion.list-reports\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}/data\n          name: report-data\n          description: \"Report data retrieval\"\n          operations:\n            - method: GET\n              name: get-report-data\n              description: \"Get data for a report\"\n              call: \"streamone-ion.get-report-data\"\n              with:\n                accountId: \"rest.accountId\"\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n     \
  \ port: 9080\n      namespace: cloud-distribution-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TD SYNNEX cloud distribution partner workflows.\"\n      tools:\n        - name: list-customers\n          description: \"List all end customers for the reseller account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.list-customers\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get details for a specific end customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-customer\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: create-customer\n          description: \"Create a new end customer account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.create-customer\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List active subscriptions for a customer\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.list-customer-subscriptions\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: \"Browse the TD SYNNEX product catalog\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"streamone-ion.list-products\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get details for a specific product\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-product\"\n          with:\n            accountId: \"tools.accountId\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List all orders for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.list-account-orders\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n\
  \          description: \"Get details for a specific order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-order\"\n          with:\n            accountId: \"tools.accountId\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-order\n          description: \"Create a new product order for a customer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.create-order\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-order\n          description: \"Cancel an unprocessed order\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"streamone-ion.cancel-order\"\
  \n          with:\n            accountId: \"tools.accountId\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cart\n          description: \"Create a new shopping cart for order building\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.create-cart\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-cart-item\n          description: \"Add a product to a shopping cart\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.add-cart-item\"\n          with:\n            accountId: \"tools.accountId\"\n            cartId: \"tools.cartId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: checkout-cart\n          description: \"Check out a cart to create an order\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.checkout-cart\"\n          with:\n            accountId: \"tools.accountId\"\n            cartId: \"tools.cartId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List available billing and business reports\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.list-reports\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-data\n          description: \"Get data from a billing or business report\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: false\n          call: \"streamone-ion.get-report-data\"\n          with:\n            accountId: \"tools.accountId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tech-data/refs/heads/main/capabilities/cloud-distribution.yaml
tags:
- Cloud
- Distribution
- E-Commerce
- Partner
- Reseller
tools:
- description: List all end customers for the reseller account
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get details for a specific end customer
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Create a new end customer account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: List active subscriptions for a customer
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Browse the TD SYNNEX product catalog
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get details for a specific product
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: List all orders for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get details for a specific order
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Create a new product order for a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Cancel an unprocessed order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order
- description: Create a new shopping cart for order building
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-cart
- description: Add a product to a shopping cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-cart-item
- description: Check out a cart to create an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkout-cart
- description: List available billing and business reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get data from a billing or business report
  hints:
    openWorld: false
    readOnly: true
  name: get-report-data
---
