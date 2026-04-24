---
consumed_apis:
- mdes-digital
- mdes-token-connect
- mdes-pre-digitization
- mdes-bulk-tokenization
- token-requestor-id
- issuer-click-to-pay
description: Unified workflow for digital payment teams and issuer technology to manage card tokenization, MDES digital enablement, Click to Pay enrollment, and push provisioning to digital wallets.
layout: capability
name: Mastercard Digital Enablement and Tokenization
operations:
- description: Tokenize a payment card
  method: POST
  name: tokenize-card
  path: /v1/tokens
- description: Check card eligibility for digitization
  method: POST
  name: check-digitization-eligibility
  path: /v1/eligibility
- description: Submit bulk tokenization request
  method: POST
  name: submit-bulk-tokenization
  path: /v1/bulk-tokenization
- description: Push provision a token to a wallet
  method: POST
  name: push-provision
  path: /v1/provisioning
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- tokenize card
- bulk tokenization operations
- submit a bulk tokenization request for a card portfolio
- push provision
- suspend an active token
- submit bulk tokenization
- check if a card is eligible for digitization
- mdes
- digital payments
- payments
- enroll an issuer in click to pay
- get token details
- digital identity
- register a new token requestor
- credit cards
- check digitization eligibility
- push provision a token to a wallet
- push provision a token to a digital wallet
- push provision to wallet
- token lifecycle management
- fraud detection
- click to pay
- mastercard
- tokenization
- enroll issuer click to pay
- register token requestor
- tokenize a payment card via mdes
- delete token
- delete a token
- suspend token
- pre-digitization eligibility
- push provisioning to wallets
- financial services
- check card eligibility for digitization
- open banking
- tokenize a payment card
- submit bulk tokenization request
slug: digital-enablement-and-tokenization
tags:
- Mastercard
- Tokenization
- MDES
- Digital Payments
- Click to Pay
tools:
- description: Tokenize a payment card via MDES
  hints:
    readOnly: false
  name: tokenize-card
- description: Get token details
  hints:
    readOnly: true
  name: get-token-details
- description: Suspend an active token
  hints:
    readOnly: false
  name: suspend-token
- description: Delete a token
  hints:
    destructive: true
    readOnly: false
  name: delete-token
- description: Check if a card is eligible for digitization
  hints:
    readOnly: true
  name: check-digitization-eligibility
- description: Push provision a token to a digital wallet
  hints:
    readOnly: false
  name: push-provision-to-wallet
- description: Submit a bulk tokenization request for a card portfolio
  hints:
    readOnly: false
  name: submit-bulk-tokenization
- description: Register a new token requestor
  hints:
    readOnly: false
  name: register-token-requestor
- description: Enroll an issuer in Click to Pay
  hints:
    readOnly: false
  name: enroll-issuer-click-to-pay
---
