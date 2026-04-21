---
consumed_apis:
- community-pass-identity
- community-pass-payments
description: Unified workflow for development organizations and financial inclusion teams to manage digital identities, process payments, and deliver services through the Community Pass ecosystem in underserved communities.
layout: capability
name: Mastercard Community Pass and Financial Inclusion
operations:
- description: Create a digital identity
  method: POST
  name: create-identity
  path: /v1/identities
- description: Process a Community Pass payment
  method: POST
  name: process-payment
  path: /v1/payments
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- open banking
- create identity
- fraud detection
- payments
- process payment
- credit cards
- financial services
- create digital identity
- process community payment
- process a payment in the community pass ecosystem
- create a digital identity
- digital identity management
- digital identity
- mastercard
- community pass
- financial inclusion
- create a digital identity in the community pass ecosystem
- verify digital identity
- verify a digital identity
- process a community pass payment
- community pass payments
slug: community-pass-and-inclusion
tags:
- Mastercard
- Community Pass
- Financial Inclusion
- Digital Identity
tools:
- description: Create a digital identity in the Community Pass ecosystem
  hints:
    readOnly: false
  name: create-digital-identity
- description: Verify a digital identity
  hints:
    readOnly: true
  name: verify-digital-identity
- description: Process a payment in the Community Pass ecosystem
  hints:
    readOnly: false
  name: process-community-payment
---
