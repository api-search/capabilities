---
consumed_apis:
- send-funding
- send-p2p
- send-disbursements
- send-account-info
- send-account-verification
- cross-border
- direct-services
- account-validation
- currency-conversion
description: Unified workflow for fintech developers and payment processors to manage real-time money transfers, P2P payments, disbursements, and cross-border services through Mastercard Send and related APIs.
layout: capability
name: Mastercard Money Transfer and Disbursements
operations:
- description: Create a funding transaction
  method: POST
  name: create-funding
  path: /v1/funding
- description: Create a person-to-person transfer
  method: POST
  name: create-p2p-transfer
  path: /v1/transfers
- description: Create a disbursement
  method: POST
  name: create-disbursement
  path: /v1/disbursements
- description: Create a cross-border payment
  method: POST
  name: create-cross-border-payment
  path: /v1/cross-border-payments
- description: Get currency conversion rate
  method: GET
  name: get-conversion-rate
  path: /v1/conversion-rates
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- open banking
- p2p transfers
- create cross border payment
- disbursement transactions
- get currency conversion rate
- fraud detection
- funding transactions
- create a disbursement to send money to a recipient
- validate account
- payments
- get account information for a send recipient
- create disbursement
- verify account eligibility for mastercard send
- mastercard send
- credit cards
- financial services
- disbursements
- create a funding transaction
- get currency conversion rate for cross-border transactions
- create a person-to-person transfer
- get conversion rate
- cross-border payment processing
- create a funding transaction via mastercard send
- process direct transaction
- money transfer
- create funding
- create a cross-border payment
- digital identity
- create a disbursement
- mastercard
- cross-border
- get account info
- process a direct service transaction
- validate account details before transfer
- verify send account
- create p2p transfer
- create a cross-border international payment
- create a person-to-person money transfer
- currency conversion rates
slug: money-transfer-and-disbursements
tags:
- Mastercard
- Money Transfer
- Disbursements
- Cross-Border
- Mastercard Send
tools:
- description: Create a funding transaction via Mastercard Send
  hints:
    readOnly: false
  name: create-funding
- description: Create a person-to-person money transfer
  hints:
    readOnly: false
  name: create-p2p-transfer
- description: Create a disbursement to send money to a recipient
  hints:
    readOnly: false
  name: create-disbursement
- description: Verify account eligibility for Mastercard Send
  hints:
    readOnly: true
  name: verify-send-account
- description: Get account information for a Send recipient
  hints:
    readOnly: true
  name: get-account-info
- description: Validate account details before transfer
  hints:
    readOnly: true
  name: validate-account
- description: Create a cross-border international payment
  hints:
    readOnly: false
  name: create-cross-border-payment
- description: Get currency conversion rate for cross-border transactions
  hints:
    idempotent: true
    readOnly: true
  name: get-conversion-rate
- description: Process a direct service transaction
  hints:
    readOnly: false
  name: process-direct-transaction
---
