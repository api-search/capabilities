---
categories: []
consumed_apis:
- mastercom
- processing-core
- ethoca-consumer-clarity
- currency-conversion
description: Unified workflow for dispute managers and back-office teams to manage chargebacks, retrieval requests, transaction processing, and settlement through Mastercom and processing APIs.
layout: capability
name: Mastercard Disputes and Settlement
operations:
- description: Create a chargeback
  method: POST
  name: create-chargeback
  path: /v1/chargebacks
- description: Retrieve chargebacks
  method: GET
  name: get-chargebacks
  path: /v1/chargebacks
- description: Create a retrieval request
  method: POST
  name: create-retrieval
  path: /v1/retrievals
- description: Look up transaction details for dispute resolution
  method: POST
  name: lookup-transaction-clarity
  path: /v1/transaction-clarity
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- mastercom
- retrieve chargebacks
- chargeback management
- create retrieval request
- financial services
- create a chargeback
- retrieve chargebacks from mastercom
- authorize transaction
- lookup transaction for dispute
- get settlement rate
- open banking
- authorize a transaction through core processing
- create a retrieval request in mastercom
- look up transaction details to aid dispute resolution
- fraud detection
- get chargebacks
- lookup transaction clarity
- look up transaction details for dispute resolution
- transaction clarity for dispute resolution
- create a chargeback in mastercom
- chargebacks
- create a retrieval request
- create chargeback
- payments
- mastercard
- disputes
- create retrieval
- retrieval request management
- digital identity
- settlement
- credit cards
- get currency conversion rate for settlement
slug: disputes-and-settlement
tags:
- Mastercard
- Disputes
- Chargebacks
- Settlement
- Mastercom
tools:
- description: Create a chargeback in Mastercom
  hints:
    readOnly: false
  name: create-chargeback
- description: Retrieve chargebacks from Mastercom
  hints:
    readOnly: true
  name: get-chargebacks
- description: Create a retrieval request in Mastercom
  hints:
    readOnly: false
  name: create-retrieval-request
- description: Look up transaction details to aid dispute resolution
  hints:
    readOnly: true
  name: lookup-transaction-for-dispute
- description: Authorize a transaction through core processing
  hints:
    readOnly: false
  name: authorize-transaction
- description: Get currency conversion rate for settlement
  hints:
    idempotent: true
    readOnly: true
  name: get-settlement-rate
---
