---
consumed_apis:
- id-verification
- id-trust-providers
- id-identity-providers
- authentication-consent
- authentication-facilitator
- identity-insights-accounts
- identity-insights-transactions
description: Unified workflow for identity managers and compliance teams to verify identities, manage authentication consent, and leverage identity intelligence for fraud prevention across Mastercard's identity services.
layout: capability
name: Mastercard Identity and Authentication
operations:
- description: Verify a consumer identity
  method: POST
  name: verify-identity
  path: /v1/verifications
- description: Create authentication consent
  method: POST
  name: create-consent
  path: /v1/consents
- description: Get identity insights for an account
  method: POST
  name: get-account-insights
  path: /v1/account-insights
- description: Get identity insights for a transaction
  method: POST
  name: get-transaction-insights
  path: /v1/transaction-insights
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- get account identity insights
- credit cards
- digital identity
- create authentication consent
- get transaction identity insights
- open banking
- submit trust verification
- submit identity verification as a trust provider
- kyc
- verify identity
- create an authentication consent request
- create auth consent
- identity insights for transactions
- authentication
- get identity intelligence insights for an account
- create consent
- initiate authentication
- verify a consumer identity using mastercard id
- get consent status
- identity verification
- financial services
- get authentication consent status
- mastercard
- get account insights
- authentication consent management
- get transaction insights
- get identity insights for a transaction
- identity
- payments
- get identity intelligence insights for a transaction
- verification
- fraud detection
- verify a consumer identity
- initiate strong customer authentication
- identity insights for accounts
- get identity insights for an account
slug: identity-and-authentication
tags:
- Mastercard
- Identity
- Authentication
- Verification
- KYC
tools:
- description: Verify a consumer identity using Mastercard ID
  hints:
    readOnly: true
  name: verify-identity
- description: Create an authentication consent request
  hints:
    readOnly: false
  name: create-auth-consent
- description: Get authentication consent status
  hints:
    readOnly: true
  name: get-consent-status
- description: Initiate strong customer authentication
  hints:
    readOnly: false
  name: initiate-authentication
- description: Get identity intelligence insights for an account
  hints:
    readOnly: true
  name: get-account-identity-insights
- description: Get identity intelligence insights for a transaction
  hints:
    readOnly: true
  name: get-transaction-identity-insights
- description: Submit identity verification as a trust provider
  hints:
    readOnly: false
  name: submit-trust-verification
---
