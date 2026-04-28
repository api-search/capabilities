---
categories: []
consumed_apis:
- card-issuance
- traditional-fulfillment
- bin-lookup
- automatic-billing-updater
- payment-account-mgmt
- payment-account-ref
- account-catalog
- universal-spec
- account-validation
description: Unified workflow for issuers and card managers to handle card issuance, fulfillment, BIN lookups, billing updates, payment account management, and account catalog services.
layout: capability
name: Mastercard Card and Account Management
operations:
- description: Issue a new card
  method: POST
  name: issue-card
  path: /v1/cards
- description: Look up BIN information
  method: POST
  name: lookup-bin
  path: /v1/bins
- description: Request updated card credentials
  method: POST
  name: get-billing-updates
  path: /v1/billing-updates
- description: Manage a payment account
  method: POST
  name: manage-account
  path: /v1/accounts
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- get card details
- fraud detection
- look up bin information for a card
- issue a new card
- automatic billing updates
- account management
- digital identity
- open banking
- card issuance and management
- create fulfillment order
- manage a payment account lifecycle
- get account catalog
- request updated card credentials for card-on-file
- bin lookup
- manage a payment account
- submit pan-related event for account level management
- issue card
- retrieve account catalog data
- create a physical card fulfillment order
- issue a new mastercard card
- look up bin information
- list bins
- request updated card credentials
- financial services
- get payment account reference
- query payment account reference to link tokens to accounts
- payments
- manage account
- issuers
- validate account
- payment account management
- manage payment account
- credit cards
- list available mastercard bins
- submit pan event
- card management
- validate account details
- mastercard
- get billing updates
- lookup bin
slug: card-and-account-management
tags:
- Mastercard
- Card Management
- Account Management
- Issuers
tools:
- description: Issue a new Mastercard card
  hints:
    readOnly: false
  name: issue-card
- description: Get card details
  hints:
    readOnly: true
  name: get-card-details
- description: Create a physical card fulfillment order
  hints:
    readOnly: false
  name: create-fulfillment-order
- description: Look up BIN information for a card
  hints:
    readOnly: true
  name: lookup-bin
- description: List available Mastercard BINs
  hints:
    idempotent: true
    readOnly: true
  name: list-bins
- description: Request updated card credentials for card-on-file
  hints:
    readOnly: true
  name: get-billing-updates
- description: Manage a payment account lifecycle
  hints:
    readOnly: false
  name: manage-payment-account
- description: Query payment account reference to link tokens to accounts
  hints:
    readOnly: true
  name: get-payment-account-reference
- description: Validate account details
  hints:
    readOnly: true
  name: validate-account
- description: Retrieve account catalog data
  hints:
    idempotent: true
    readOnly: true
  name: get-account-catalog
- description: Submit PAN-related event for account level management
  hints:
    readOnly: false
  name: submit-pan-event
---
