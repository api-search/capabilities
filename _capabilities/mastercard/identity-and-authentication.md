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
- get account insights
- get transaction identity insights
- financial services
- authentication
- submit identity verification as a trust provider
- get identity insights for an account
- credit cards
- submit trust verification
- identity insights for accounts
- identity insights for transactions
- create auth consent
- verify a consumer identity using mastercard id
- identity
- identity verification
- verify identity
- mastercard
- initiate strong customer authentication
- verification
- get identity intelligence insights for a transaction
- initiate authentication
- create consent
- get transaction insights
- create an authentication consent request
- create authentication consent
- get consent status
- authentication consent management
- get identity insights for a transaction
- get authentication consent status
- digital identity
- payments
- open banking
- get identity intelligence insights for an account
- kyc
- fraud detection
- verify a consumer identity
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
