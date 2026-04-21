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
- verify account eligibility for mastercard send
- currency conversion rates
- fraud detection
- process direct transaction
- get account info
- mastercard
- create a funding transaction via mastercard send
- create a person-to-person transfer
- create a person-to-person money transfer
- credit cards
- cross-border payment processing
- create disbursement
- get currency conversion rate
- process a direct service transaction
- disbursements
- financial services
- create a cross-border payment
- create a cross-border international payment
- disbursement transactions
- funding transactions
- create cross border payment
- create a disbursement to send money to a recipient
- get currency conversion rate for cross-border transactions
- cross-border
- money transfer
- open banking
- verify send account
- get conversion rate
- create a funding transaction
- create funding
- p2p transfers
- create a disbursement
- validate account
- create p2p transfer
- mastercard send
- payments
- validate account details before transfer
- get account information for a send recipient
- digital identity
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
