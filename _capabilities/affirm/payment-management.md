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
- authorization, capture, void, and refund of payment transactions.
- create an affirm bnpl checkout session for a customer purchase.
- get promotional financing terms.
- list all disputes.
- payment ops
- initiation and management of customer financing sessions.
- transactions
- handling of customer chargebacks and disputes.
- authorize an affirm transaction using a checkout token.
- read checkout
- merchant operations team member managing transaction reconciliation and dispute resolution.
- disputes
- void an authorized affirm transaction before capture.
- create an affirm checkout session.
- retrieve or update a checkout session.
- capture an authorized affirm transaction to collect funds.
- list all affirm payment transactions for reconciliation.
- capture an authorized transaction.
- get details of a specific affirm payment dispute.
- refund transaction
- get promo
- refund a transaction.
- refund a captured transaction.
- full bnpl payment lifecycle from checkout through capture, refund, and dispute management.
- specific dispute operations.
- payment transaction management.
- list transactions
- submit dispute evidence
- refund a captured affirm transaction partially or fully.
- list disputes
- authorize transaction
- merchant engineer
- authorize a transaction.
- get promo messaging
- payments
- list all affirm payment disputes for a merchant.
- displaying financing terms and promotional messaging to customers.
- promotional messaging.
- capture transaction
- submit evidence to contest an affirm payment dispute.
- capture a transaction.
- affirm
- backend developer integrating affirm bnpl into a merchant's e-commerce checkout.
- get dispute details.
- buy now pay later
- void transaction
- read a checkout session.
- dispute management.
- store checkout
- list all transactions.
- get dispute
- checkout session management.
- checkout
- read an affirm checkout session by token.
- get affirm promotional financing terms and messaging for a purchase amount.
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
