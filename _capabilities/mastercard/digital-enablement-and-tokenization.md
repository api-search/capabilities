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
- submit bulk tokenization
- tokenization
- click to pay
- fraud detection
- tokenize a payment card
- digital payments
- submit bulk tokenization request
- mdes
- payments
- push provisioning to wallets
- suspend token
- check card eligibility for digitization
- digital identity
- submit a bulk tokenization request for a card portfolio
- check if a card is eligible for digitization
- push provision a token to a digital wallet
- credit cards
- push provision
- token lifecycle management
- pre-digitization eligibility
- bulk tokenization operations
- suspend an active token
- register a new token requestor
- mastercard
- delete a token
- financial services
- check digitization eligibility
- enroll an issuer in click to pay
- push provision to wallet
- delete token
- get token details
- register token requestor
- open banking
- push provision a token to a wallet
- enroll issuer click to pay
- tokenize a payment card via mdes
- tokenize card
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
