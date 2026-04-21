---
consumed_apis:
- affirm-checkout
- affirm-transactions
- affirm-disputes
- affirm-promos
description: Unified workflow capability for managing the full Affirm BNPL payment lifecycle — from initiating checkout sessions through transaction authorization, capture, refund, and dispute resolution. Used by merchant engineers and payment operations teams.
layout: capability
name: Affirm Payment Management
operations:
- description: Create an Affirm checkout session.
  method: POST
  name: store-checkout
  path: /v1/checkouts
- description: Read a checkout session.
  method: GET
  name: read-checkout
  path: /v1/checkouts/{token}
- description: List all transactions.
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Authorize a transaction.
  method: POST
  name: authorize-transaction
  path: /v1/transactions
- description: Capture a transaction.
  method: POST
  name: capture-transaction
  path: /v1/transactions/{id}/capture
- description: Refund a transaction.
  method: POST
  name: refund-transaction
  path: /v1/transactions/{id}/refund
- description: List all disputes.
  method: GET
  name: list-disputes
  path: /v1/disputes
- description: Get dispute details.
  method: GET
  name: get-dispute
  path: /v1/disputes/{dispute_id}
- description: Get promotional financing terms.
  method: GET
  name: get-promo
  path: /v1/promos
personas:
- description: Backend developer integrating Affirm BNPL into a merchant's e-commerce checkout.
  id: merchant-engineer
  name: Merchant Engineer
- description: Merchant operations team member managing transaction reconciliation and dispute resolution.
  id: payment-ops
  name: Payment Operations
provider_name: affirm
provider_slug: affirm
search_terms:
- store checkout
- submit dispute evidence
- merchant operations team member managing transaction reconciliation and dispute resolution.
- displaying financing terms and promotional messaging to customers.
- refund a captured transaction.
- read an affirm checkout session by token.
- handling of customer chargebacks and disputes.
- list all disputes.
- read checkout
- list transactions
- list disputes
- list all transactions.
- capture transaction
- submit evidence to contest an affirm payment dispute.
- get affirm promotional financing terms and messaging for a purchase amount.
- list all affirm payment disputes for a merchant.
- create an affirm checkout session.
- transactions
- refund a transaction.
- get details of a specific affirm payment dispute.
- checkout
- payment ops
- void transaction
- full bnpl payment lifecycle from checkout through capture, refund, and dispute management.
- payments
- merchant engineer
- refund a captured affirm transaction partially or fully.
- dispute management.
- get dispute
- authorization, capture, void, and refund of payment transactions.
- get promotional financing terms.
- promotional messaging.
- affirm
- specific dispute operations.
- backend developer integrating affirm bnpl into a merchant's e-commerce checkout.
- capture a transaction.
- initiation and management of customer financing sessions.
- authorize transaction
- capture an authorized transaction.
- buy now pay later
- checkout session management.
- get promo
- list all affirm payment transactions for reconciliation.
- create an affirm bnpl checkout session for a customer purchase.
- authorize an affirm transaction using a checkout token.
- get promo messaging
- authorize a transaction.
- get dispute details.
- capture an authorized affirm transaction to collect funds.
- read a checkout session.
- refund transaction
- disputes
- void an authorized affirm transaction before capture.
- retrieve or update a checkout session.
- payment transaction management.
slug: payment-management
tags:
- Affirm
- Payments
- Buy Now Pay Later
- Checkout
- Transactions
- Disputes
tools:
- description: Create an Affirm BNPL checkout session for a customer purchase.
  hints:
    destructive: false
    readOnly: false
  name: store-checkout
- description: Read an Affirm checkout session by token.
  hints:
    destructive: false
    readOnly: true
  name: read-checkout
- description: List all Affirm payment transactions for reconciliation.
  hints:
    destructive: false
    readOnly: true
  name: list-transactions
- description: Authorize an Affirm transaction using a checkout token.
  hints:
    destructive: false
    readOnly: false
  name: authorize-transaction
- description: Capture an authorized Affirm transaction to collect funds.
  hints:
    destructive: false
    readOnly: false
  name: capture-transaction
- description: Refund a captured Affirm transaction partially or fully.
  hints:
    destructive: true
    readOnly: false
  name: refund-transaction
- description: Void an authorized Affirm transaction before capture.
  hints:
    destructive: true
    readOnly: false
  name: void-transaction
- description: List all Affirm payment disputes for a merchant.
  hints:
    destructive: false
    readOnly: true
  name: list-disputes
- description: Get details of a specific Affirm payment dispute.
  hints:
    destructive: false
    readOnly: true
  name: get-dispute
- description: Submit evidence to contest an Affirm payment dispute.
  hints:
    destructive: false
    readOnly: false
  name: submit-dispute-evidence
- description: Get Affirm promotional financing terms and messaging for a purchase amount.
  hints:
    destructive: false
    readOnly: true
  name: get-promo-messaging
---
