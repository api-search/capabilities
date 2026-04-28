---
categories:
- payments
consumed_apis:
- square
description: Unified workflow for commerce operations combining payments, orders, catalog, inventory, checkout, invoicing, subscriptions, and refunds. Used by commerce developers and business operators to manage the full sales lifecycle.
layout: capability
name: Square Commerce Operations
operations:
- description: List payments.
  method: GET
  name: list-payments
  path: /v1/payments
- description: Create a payment.
  method: POST
  name: create-payment
  path: /v1/payments
- description: Get payment details.
  method: GET
  name: get-payment
  path: /v1/payments/{payment_id}
- description: List refunds.
  method: GET
  name: list-refunds
  path: /v1/refunds
- description: Refund a payment.
  method: POST
  name: create-refund
  path: /v1/refunds
- description: Create an order.
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order details.
  method: GET
  name: get-order
  path: /v1/orders/{order_id}
- description: List catalog objects.
  method: GET
  name: list-catalog
  path: /v1/catalog
- description: List invoices.
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create a subscription.
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: List payment links.
  method: GET
  name: list-payment-links
  path: /v1/checkout
- description: Create a payment link.
  method: POST
  name: create-payment-link
  path: /v1/checkout
- description: List disputes.
  method: GET
  name: list-disputes
  path: /v1/disputes
personas: []
provider_name: Square
provider_slug: square
search_terms:
- create payment link
- create order
- webhooks
- list invoices.
- upsert catalog object
- cancel a payment.
- list catalog
- retrieve inventory counts.
- manage refunds.
- create refund
- gift cards
- terminal
- create a subscription.
- create invoice
- list refunds.
- list payments.
- refund a payment.
- checkout
- labor
- create or update a catalog object.
- list payment disputes.
- create payment
- complete a payment.
- manage a specific order.
- get payment
- get order details.
- square
- apply inventory adjustments.
- list refunds
- get invoice
- batch change inventory
- get details for a specific payment.
- cancel payment
- create a new order.
- retrieve an order by id.
- get order
- team
- refunds
- search subscriptions.
- create a payment link.
- accept dispute
- manage a specific payment.
- locations
- catalog
- invoicing
- search catalog objects
- complete payment
- financial technology
- subscriptions
- manage payments.
- list payments
- manage payment links.
- search orders
- search all orders.
- manage subscriptions.
- list catalog objects.
- customers
- create an order.
- manage invoices.
- loyalty
- get a single catalog object.
- get catalog object
- manage orders.
- create a draft invoice.
- list invoices
- create subscription
- list payment refunds.
- get dispute
- search subscriptions
- retail
- bookings
- get an invoice.
- get payment details.
- manage catalog items.
- list disputes
- ecommerce
- disputes
- accept a dispute.
- list disputes.
- list payment links
- commerce
- batch retrieve inventory counts
- inventory
- create a payment.
- payments
- list payment links.
- point of sale
- list payments taken by the account.
- get dispute details.
- manage disputes.
- list invoices for a location.
- merchants
- orders
- refund payment
- search catalog objects.
- create a checkout payment link.
slug: commerce-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Square Commerce Operations\"\n  description: \"Unified workflow for commerce operations combining payments, orders, catalog, inventory, checkout, invoicing, subscriptions, and refunds. Used by commerce developers and business operators to manage the full sales lifecycle.\"\n  tags:\n    - Square\n    - Commerce\n    - Payments\n    - Orders\n    - Catalog\n    - Inventory\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SQUARE_ACCESS_TOKEN: SQUARE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: square\n      location: ./shared/square-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: square-commerce-api\n      description: \"Unified REST API for Square commerce operations.\"\n      resources:\n        - path: /v1/payments\n          name: payments\n          description: \"Manage payments.\"\n          operations:\n            - method: GET\n\
  \              name: list-payments\n              description: \"List payments.\"\n              call: \"square.list-payments\"\n              with:\n                begin_time: \"rest.begin_time\"\n                end_time: \"rest.end_time\"\n                location_id: \"rest.location_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment\n              description: \"Create a payment.\"\n              call: \"square.create-payment\"\n              with:\n                source_id: \"rest.source_id\"\n                idempotency_key: \"rest.idempotency_key\"\n                amount_money: \"rest.amount_money\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/{payment_id}\n          name: payment\n          description: \"Manage a specific payment.\"\n          operations:\n            - method:\
  \ GET\n              name: get-payment\n              description: \"Get payment details.\"\n              call: \"square.get-payment\"\n              with:\n                payment_id: \"rest.payment_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/refunds\n          name: refunds\n          description: \"Manage refunds.\"\n          operations:\n            - method: GET\n              name: list-refunds\n              description: \"List refunds.\"\n              call: \"square.list-payment-refunds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-refund\n              description: \"Refund a payment.\"\n              call: \"square.refund-payment\"\n              with:\n                idempotency_key: \"rest.idempotency_key\"\n                payment_id: \"rest.payment_id\"\n                amount_money:\
  \ \"rest.amount_money\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Manage orders.\"\n          operations:\n            - method: POST\n              name: create-order\n              description: \"Create an order.\"\n              call: \"square.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{order_id}\n          name: order\n          description: \"Manage a specific order.\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get order details.\"\n              call: \"square.get-order\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog\n          name:\
  \ catalog\n          description: \"Manage catalog items.\"\n          operations:\n            - method: GET\n              name: list-catalog\n              description: \"List catalog objects.\"\n              call: \"square.list-catalog\"\n              with:\n                types: \"rest.types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: \"Manage invoices.\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List invoices.\"\n              call: \"square.list-invoices\"\n              with:\n                location_id: \"rest.location_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Manage subscriptions.\"\n          operations:\n \
  \           - method: POST\n              name: create-subscription\n              description: \"Create a subscription.\"\n              call: \"square.create-subscription\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/checkout\n          name: checkout\n          description: \"Manage payment links.\"\n          operations:\n            - method: GET\n              name: list-payment-links\n              description: \"List payment links.\"\n              call: \"square.list-payment-links\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment-link\n              description: \"Create a payment link.\"\n              call: \"square.create-payment-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/disputes\n          name:\
  \ disputes\n          description: \"Manage disputes.\"\n          operations:\n            - method: GET\n              name: list-disputes\n              description: \"List disputes.\"\n              call: \"square.list-disputes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: square-commerce-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Square commerce operations.\"\n      tools:\n        - name: list-payments\n          description: \"List payments taken by the account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-payments\"\n          with:\n            begin_time: \"tools.begin_time\"\n            end_time: \"tools.end_time\"\n            location_id: \"tools.location_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-payment\n\
  \          description: \"Create a payment.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-payment\"\n          with:\n            source_id: \"tools.source_id\"\n            idempotency_key: \"tools.idempotency_key\"\n            amount_money: \"tools.amount_money\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-payment\n          description: \"Get details for a specific payment.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-payment\n          description: \"Cancel a payment.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"square.cancel-payment\"\n          with:\n\
  \            payment_id: \"tools.payment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: complete-payment\n          description: \"Complete a payment.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.complete-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-refunds\n          description: \"List payment refunds.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-payment-refunds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: refund-payment\n          description: \"Refund a payment.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.refund-payment\"\n          with:\n\
  \            idempotency_key: \"tools.idempotency_key\"\n            payment_id: \"tools.payment_id\"\n            amount_money: \"tools.amount_money\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-order\n          description: \"Create a new order.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-orders\n          description: \"Search all orders.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-order\n          description: \"Retrieve an order by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-order\"\
  \n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-catalog\n          description: \"List catalog objects.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-catalog\"\n          with:\n            types: \"tools.types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upsert-catalog-object\n          description: \"Create or update a catalog object.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"square.upsert-catalog-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-catalog-object\n          description: \"Get a single catalog object.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-catalog-object\"\
  \n          with:\n            object_id: \"tools.object_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-catalog-objects\n          description: \"Search catalog objects.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-catalog-objects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-retrieve-inventory-counts\n          description: \"Retrieve inventory counts.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.batch-retrieve-inventory-counts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-change-inventory\n          description: \"Apply inventory adjustments.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.batch-change-inventory\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-invoices\n          description: \"List invoices for a location.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-invoices\"\n          with:\n            location_id: \"tools.location_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-invoice\n          description: \"Create a draft invoice.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-invoice\n          description: \"Get an invoice.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-invoice\"\n          with:\n            invoice_id: \"tools.invoice_id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-subscription\n          description: \"Create a subscription.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-subscription\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-subscriptions\n          description: \"Search subscriptions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.search-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-payment-links\n          description: \"List payment links.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-payment-links\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n      \
  \  - name: create-payment-link\n          description: \"Create a checkout payment link.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"square.create-payment-link\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-disputes\n          description: \"List payment disputes.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.list-disputes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-dispute\n          description: \"Get dispute details.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"square.get-dispute\"\n          with:\n            dispute_id: \"tools.dispute_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: accept-dispute\n          description: \"\
  Accept a dispute.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"square.accept-dispute\"\n          with:\n            dispute_id: \"tools.dispute_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/square/refs/heads/main/capabilities/commerce-operations.yaml
tags:
- Square
- Commerce
- Payments
- Orders
- Catalog
- Inventory
tools:
- description: List payments taken by the account.
  hints:
    openWorld: true
    readOnly: true
  name: list-payments
- description: Create a payment.
  hints:
    idempotent: false
    readOnly: false
  name: create-payment
- description: Get details for a specific payment.
  hints:
    openWorld: true
    readOnly: true
  name: get-payment
- description: Cancel a payment.
  hints:
    destructive: true
    readOnly: false
  name: cancel-payment
- description: Complete a payment.
  hints:
    idempotent: false
    readOnly: false
  name: complete-payment
- description: List payment refunds.
  hints:
    openWorld: true
    readOnly: true
  name: list-refunds
- description: Refund a payment.
  hints:
    idempotent: false
    readOnly: false
  name: refund-payment
- description: Create a new order.
  hints:
    idempotent: false
    readOnly: false
  name: create-order
- description: Search all orders.
  hints:
    openWorld: true
    readOnly: true
  name: search-orders
- description: Retrieve an order by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-order
- description: List catalog objects.
  hints:
    openWorld: true
    readOnly: true
  name: list-catalog
- description: Create or update a catalog object.
  hints:
    idempotent: true
    readOnly: false
  name: upsert-catalog-object
- description: Get a single catalog object.
  hints:
    openWorld: true
    readOnly: true
  name: get-catalog-object
- description: Search catalog objects.
  hints:
    openWorld: true
    readOnly: true
  name: search-catalog-objects
- description: Retrieve inventory counts.
  hints:
    openWorld: true
    readOnly: true
  name: batch-retrieve-inventory-counts
- description: Apply inventory adjustments.
  hints:
    idempotent: false
    readOnly: false
  name: batch-change-inventory
- description: List invoices for a location.
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Create a draft invoice.
  hints:
    idempotent: false
    readOnly: false
  name: create-invoice
- description: Get an invoice.
  hints:
    openWorld: true
    readOnly: true
  name: get-invoice
- description: Create a subscription.
  hints:
    idempotent: false
    readOnly: false
  name: create-subscription
- description: Search subscriptions.
  hints:
    openWorld: true
    readOnly: true
  name: search-subscriptions
- description: List payment links.
  hints:
    openWorld: true
    readOnly: true
  name: list-payment-links
- description: Create a checkout payment link.
  hints:
    idempotent: false
    readOnly: false
  name: create-payment-link
- description: List payment disputes.
  hints:
    openWorld: true
    readOnly: true
  name: list-disputes
- description: Get dispute details.
  hints:
    openWorld: true
    readOnly: true
  name: get-dispute
- description: Accept a dispute.
  hints:
    idempotent: true
    readOnly: false
  name: accept-dispute
---
