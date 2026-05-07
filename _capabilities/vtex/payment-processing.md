---
categories: []
consumed_apis: []
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
- transactions
- create a refund for a transaction
- create a new shopping cart
- get full details of a vtex payment transaction including status and amounts
- retail
- create cart
- get cart
- checkout
- get transaction by id
- create a new vtex shopping cart for a customer
- vtex
- get transaction
- create a refund for a completed vtex payment transaction
- shopping cart management
- payment refunds
- finance
- single transaction operations
- payment transaction management
- simulate order
- simulate order for pricing and availability
- create refund
- list vtex payment transactions with pagination
- e-commerce
- marketplace
- get current state of a vtex shopping cart including items, prices, and shipping options
- single cart operations
- order simulation
- list payment transactions
- payments
- list transactions
- simulate a vtex order to check real-time pricing, shipping costs, and item availability
- commerce
- get shopping cart by id
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: VTEX Payment Processing\n  description: Workflow capability for VTEX financial and payment operations teams. Combines checkout, payments, and customer\n    credit capabilities for finance teams, payment operations staff, and developers building payment integrations who need\n    to manage transactions, process refunds, and monitor payment flows.\n  tags:\n  - Checkout\n  - Commerce\n  - Finance\n  - Payments\n  - Transactions\n  - VTEX\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VTEX_APP_KEY: VTEX_APP_KEY\n    VTEX_APP_TOKEN: VTEX_APP_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: vtex-checkout\n    baseUri: https://{accountName}.vtexcommercestable.com.br\n    description: VTEX Checkout API for cart management and order placement.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: cart\n      path: /api/checkout/pub/orderForm\n      description: Cart and order form management\n      operations:\n      - name: create-cart\n        method: POST\n        description: Create a New Cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cart\n        method: GET\n        description: Get Cart by ID\n        inputParameters:\n        - name: orderFormId\n          in: path\n          type: string\n          required: true\n          description: Cart (order form) identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: simulation\n      path: /api/checkout/pub/orderForms/simulation\n      description: Order simulation for price and availability checks\n      operations:\n      - name: simulate-order\n        method: POST\n        description: Order Simulation\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n            country: '{{tools.country}}'\n            postalCode: '{{tools.postalCode}}'\n  - type: http\n    namespace: vtex-payments\n    baseUri: https://{accountName}.vtexpayments.com.br\n    description: VTEX Payments Gateway API for managing payment transactions and conditions.\n    authentication:\n      type: apikey\n      key: X-VTEX-API-AppKey\n      value: '{{VTEX_APP_KEY}}'\n      placement: header\n    resources:\n    - name: transactions\n      path: /api/pvt/transactions\n      description: Payment transaction management\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List Transactions\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page\
  \ number\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-transaction\n        method: GET\n        description: Get Transaction by ID\n        inputParameters:\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Transaction identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds\n      path: /api/pvt/transactions/{transactionId}/refunds\n      description: Payment refund management\n      operations:\n      - name: create-refund\n        method: POST\n        description: Create Refund\n        inputParameters:\n        - name: transactionId\n          in: path\n          type: string\n   \
  \       required: true\n          description: Transaction identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            value: '{{tools.amount}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: vtex-payment-processing-api\n    description: Unified REST API for VTEX payment processing and checkout management.\n    resources:\n    - path: /v1/carts\n      name: carts\n      description: Shopping cart management\n      operations:\n      - method: POST\n        name: create-cart\n        description: Create a new shopping cart\n        call: vtex-checkout.create-cart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carts/{orderFormId}\n      name: cart\n      description: Single cart operations\n      operations:\n      - method: GET\n        name: get-cart\n        description: Get shopping cart\
  \ by ID\n        call: vtex-checkout.get-cart\n        with:\n          orderFormId: rest.orderFormId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/order-simulation\n      name: order-simulation\n      description: Order simulation\n      operations:\n      - method: POST\n        name: simulate-order\n        description: Simulate order for pricing and availability\n        call: vtex-checkout.simulate-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Payment transaction management\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List payment transactions\n        call: vtex-payments.list-transactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{transactionId}\n      name: transaction\n      description: Single transaction operations\n\
  \      operations:\n      - method: GET\n        name: get-transaction\n        description: Get transaction by ID\n        call: vtex-payments.get-transaction\n        with:\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{transactionId}/refunds\n      name: refunds\n      description: Payment refunds\n      operations:\n      - method: POST\n        name: create-refund\n        description: Create a refund for a transaction\n        call: vtex-payments.create-refund\n        with:\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: vtex-payment-processing-mcp\n    transport: http\n    description: MCP server for AI-assisted VTEX payment processing and financial operations.\n    tools:\n    - name: create-cart\n      description: Create a new VTEX shopping cart for a customer\n\
  \      hints:\n        readOnly: false\n        destructive: false\n      call: vtex-checkout.create-cart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cart\n      description: Get current state of a VTEX shopping cart including items, prices, and shipping options\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-checkout.get-cart\n      with:\n        orderFormId: tools.orderFormId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: simulate-order\n      description: Simulate a VTEX order to check real-time pricing, shipping costs, and item availability\n      hints:\n        readOnly: true\n        idempotent: false\n      call: vtex-checkout.simulate-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List VTEX payment transactions with pagination\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: vtex-payments.list-transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction\n      description: Get full details of a VTEX payment transaction including status and amounts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vtex-payments.get-transaction\n      with:\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-refund\n      description: Create a refund for a completed VTEX payment transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vtex-payments.create-refund\n      with:\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
