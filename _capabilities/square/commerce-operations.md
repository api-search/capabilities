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
- create invoice
- retail
- batch retrieve inventory counts
- list catalog
- retrieve an order by id.
- square
- accept dispute
- manage orders.
- list refunds.
- loyalty
- accept a dispute.
- create payment link
- get order details.
- search catalog objects.
- get payment details.
- locations
- terminal
- webhooks
- get an invoice.
- list payment links.
- batch change inventory
- subscriptions
- refunds
- list catalog objects.
- create a new order.
- bookings
- create order
- cancel payment
- get catalog object
- get dispute
- financial technology
- create an order.
- manage a specific payment.
- list payments
- search subscriptions.
- search orders
- list invoices for a location.
- complete payment
- search all orders.
- apply inventory adjustments.
- payments
- manage invoices.
- list payment refunds.
- merchants
- create a payment.
- complete a payment.
- list disputes
- refund a payment.
- search catalog objects
- create a draft invoice.
- create a payment link.
- get invoice
- get dispute details.
- create subscription
- catalog
- orders
- refund payment
- labor
- inventory
- get payment
- list payments.
- commerce
- list invoices
- checkout
- create refund
- get a single catalog object.
- manage refunds.
- manage catalog items.
- customers
- upsert catalog object
- list invoices.
- gift cards
- list disputes.
- create a checkout payment link.
- list payment disputes.
- point of sale
- invoicing
- create or update a catalog object.
- list payment links
- manage disputes.
- manage payment links.
- create payment
- manage payments.
- manage subscriptions.
- create a subscription.
- list refunds
- get order
- list payments taken by the account.
- cancel a payment.
- ecommerce
- retrieve inventory counts.
- search subscriptions
- disputes
- manage a specific order.
- team
- get details for a specific payment.
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
