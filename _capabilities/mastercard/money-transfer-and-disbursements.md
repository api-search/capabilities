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
- create a person-to-person transfer
- create a cross-border payment
- p2p transfers
- financial services
- verify account eligibility for mastercard send
- verify send account
- create funding
- credit cards
- create a disbursement
- create p2p transfer
- create a funding transaction
- money transfer
- create a funding transaction via mastercard send
- create a person-to-person money transfer
- get currency conversion rate for cross-border transactions
- process direct transaction
- get account information for a send recipient
- get currency conversion rate
- validate account
- get conversion rate
- funding transactions
- mastercard
- disbursements
- cross-border
- get account info
- process a direct service transaction
- currency conversion rates
- mastercard send
- validate account details before transfer
- create disbursement
- digital identity
- payments
- open banking
- fraud detection
- create a cross-border international payment
- disbursement transactions
- cross-border payment processing
- create cross border payment
- create a disbursement to send money to a recipient
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
