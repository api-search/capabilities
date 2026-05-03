---
categories: []
consumed_apis:
- vtex-checkout
- vtex-payments
description: Workflow capability for VTEX financial and payment operations teams. Combines checkout, payments, and customer credit capabilities for finance teams, payment operations staff, and developers building payment integrations who need to manage transactions, process refunds, and monitor payment flows.
layout: capability
name: VTEX Payment Processing
operations:
- description: Create a new shopping cart
  method: POST
  name: create-cart
  path: /v1/carts
- description: Get shopping cart by ID
  method: GET
  name: get-cart
  path: /v1/carts/{orderFormId}
- description: Simulate order for pricing and availability
  method: POST
  name: simulate-order
  path: /v1/order-simulation
- description: List payment transactions
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Get transaction by ID
  method: GET
  name: get-transaction
  path: /v1/transactions/{transactionId}
- description: Create a refund for a transaction
  method: POST
  name: create-refund
  path: /v1/transactions/{transactionId}/refunds
personas: []
provider_name: VTEX
provider_slug: vtex
search_terms:
- create a new shopping cart
- shopping cart management
- get full details of a vtex payment transaction including status and amounts
- create refund
- list vtex payment transactions with pagination
- simulate order for pricing and availability
- marketplace
- simulate a vtex order to check real-time pricing, shipping costs, and item availability
- simulate order
- e-commerce
- list transactions
- order simulation
- create a refund for a completed vtex payment transaction
- payments
- get transaction by id
- get cart
- transactions
- finance
- commerce
- get transaction
- get shopping cart by id
- payment transaction management
- retail
- payment refunds
- create cart
- vtex
- create a refund for a transaction
- create a new vtex shopping cart for a customer
- list payment transactions
- single transaction operations
- checkout
- single cart operations
- get current state of a vtex shopping cart including items, prices, and shipping options
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VTEX Payment Processing\"\n  description: >-\n    Workflow capability for VTEX financial and payment operations teams.\n    Combines checkout, payments, and customer credit capabilities for finance teams,\n    payment operations staff, and developers building payment integrations who need\n    to manage transactions, process refunds, and monitor payment flows.\n  tags:\n    - Checkout\n    - Commerce\n    - Finance\n    - Payments\n    - Transactions\n    - VTEX\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VTEX_APP_KEY: VTEX_APP_KEY\n      VTEX_APP_TOKEN: VTEX_APP_TOKEN\n\ncapability:\n  consumes:\n    - import: vtex-checkout\n      location: ./shared/checkout.yaml\n    - import: vtex-payments\n      location: ./shared/payments.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: vtex-payment-processing-api\n      description: \"Unified REST API for VTEX\
  \ payment processing and checkout management.\"\n      resources:\n        - path: /v1/carts\n          name: carts\n          description: \"Shopping cart management\"\n          operations:\n            - method: POST\n              name: create-cart\n              description: \"Create a new shopping cart\"\n              call: \"vtex-checkout.create-cart\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/carts/{orderFormId}\n          name: cart\n          description: \"Single cart operations\"\n          operations:\n            - method: GET\n              name: get-cart\n              description: \"Get shopping cart by ID\"\n              call: \"vtex-checkout.get-cart\"\n              with:\n                orderFormId: \"rest.orderFormId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/order-simulation\n          name: order-simulation\n\
  \          description: \"Order simulation\"\n          operations:\n            - method: POST\n              name: simulate-order\n              description: \"Simulate order for pricing and availability\"\n              call: \"vtex-checkout.simulate-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions\n          name: transactions\n          description: \"Payment transaction management\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List payment transactions\"\n              call: \"vtex-payments.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/{transactionId}\n          name: transaction\n          description: \"Single transaction operations\"\n          operations:\n            - method: GET\n              name:\
  \ get-transaction\n              description: \"Get transaction by ID\"\n              call: \"vtex-payments.get-transaction\"\n              with:\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/{transactionId}/refunds\n          name: refunds\n          description: \"Payment refunds\"\n          operations:\n            - method: POST\n              name: create-refund\n              description: \"Create a refund for a transaction\"\n              call: \"vtex-payments.create-refund\"\n              with:\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: vtex-payment-processing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted VTEX payment processing and financial\
  \ operations.\"\n      tools:\n        - name: create-cart\n          description: \"Create a new VTEX shopping cart for a customer\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"vtex-checkout.create-cart\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cart\n          description: \"Get current state of a VTEX shopping cart including items, prices, and shipping options\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-checkout.get-cart\"\n          with:\n            orderFormId: \"tools.orderFormId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: simulate-order\n          description: \"Simulate a VTEX order to check real-time pricing, shipping costs, and item availability\"\n          hints:\n            readOnly: true\n            idempotent: false\n      \
  \    call: \"vtex-checkout.simulate-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-transactions\n          description: \"List VTEX payment transactions with pagination\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-payments.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-transaction\n          description: \"Get full details of a VTEX payment transaction including status and amounts\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vtex-payments.get-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-refund\n          description: \"Create a refund for a completed VTEX payment transaction\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vtex-payments.create-refund\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vtex/refs/heads/main/capabilities/payment-processing.yaml
tags:
- Checkout
- Commerce
- Finance
- Payments
- Transactions
- VTEX
tools:
- description: Create a new VTEX shopping cart for a customer
  hints:
    destructive: false
    readOnly: false
  name: create-cart
- description: Get current state of a VTEX shopping cart including items, prices, and shipping options
  hints:
    idempotent: true
    readOnly: true
  name: get-cart
- description: Simulate a VTEX order to check real-time pricing, shipping costs, and item availability
  hints:
    idempotent: false
    readOnly: true
  name: simulate-order
- description: List VTEX payment transactions with pagination
  hints:
    idempotent: true
    readOnly: true
  name: list-transactions
- description: Get full details of a VTEX payment transaction including status and amounts
  hints:
    idempotent: true
    readOnly: true
  name: get-transaction
- description: Create a refund for a completed VTEX payment transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-refund
---
