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
- create a payment link.
- create a checkout payment link.
- search catalog objects.
- invoicing
- list payment disputes.
- get details for a specific payment.
- manage payments.
- ecommerce
- create a payment.
- inventory
- list invoices for a location.
- commerce
- create refund
- manage catalog items.
- refunds
- complete payment
- get payment details.
- create or update a catalog object.
- create a subscription.
- payments
- list refunds
- complete a payment.
- list invoices
- search subscriptions
- manage a specific order.
- manage refunds.
- list payments.
- square
- refund a payment.
- point of sale
- batch retrieve inventory counts
- loyalty
- financial technology
- get dispute details.
- get a single catalog object.
- list refunds.
- get dispute
- apply inventory adjustments.
- retail
- accept a dispute.
- get catalog object
- get order
- create invoice
- accept dispute
- get invoice
- get payment
- team
- webhooks
- search catalog objects
- terminal
- retrieve an order by id.
- search orders
- retrieve inventory counts.
- manage invoices.
- search all orders.
- refund payment
- list disputes
- bookings
- get order details.
- catalog
- manage payment links.
- gift cards
- list catalog
- checkout
- create an order.
- get an invoice.
- labor
- list payment links.
- search subscriptions.
- cancel payment
- create order
- manage subscriptions.
- cancel a payment.
- create subscription
- list payment refunds.
- list catalog objects.
- customers
- batch change inventory
- list invoices.
- disputes
- manage disputes.
- list payments taken by the account.
- locations
- manage orders.
- merchants
- create payment link
- manage a specific payment.
- create a new order.
- subscriptions
- list payments
- orders
- create payment
- list disputes.
- upsert catalog object
- list payment links
- create a draft invoice.
slug: commerce-operations
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
