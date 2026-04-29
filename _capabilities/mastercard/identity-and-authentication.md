---
categories:
- identity-access
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
- digital identity
- verify a consumer identity
- create authentication consent
- identity
- verification
- create consent
- get identity insights for a transaction
- initiate authentication
- identity insights for accounts
- initiate strong customer authentication
- financial services
- get transaction insights
- get authentication consent status
- get transaction identity insights
- get consent status
- open banking
- authentication
- get identity intelligence insights for an account
- identity verification
- submit identity verification as a trust provider
- get identity insights for an account
- create auth consent
- create an authentication consent request
- authentication consent management
- payments
- fraud detection
- get account insights
- credit cards
- verify identity
- verify a consumer identity using mastercard id
- identity insights for transactions
- kyc
- mastercard
- submit trust verification
- get identity intelligence insights for a transaction
- get account identity insights
slug: identity-and-authentication
source_filename: identity-and-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Identity and Authentication\"\n  description: \"Unified workflow for identity managers and compliance teams to verify identities, manage authentication consent, and leverage identity intelligence for fraud prevention across Mastercard's identity services.\"\n  tags:\n    - Mastercard\n    - Identity\n    - Authentication\n    - Verification\n    - KYC\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: id-verification\n      location: ./shared/id-verification.yaml\n    - import: id-trust-providers\n      location: ./shared/id-for-trust-providers.yaml\n    - import: id-identity-providers\n      location: ./shared/id-for-identity-providers.yaml\n    - import: authentication-consent\n      location: ./shared/authentication-consent.yaml\n\
  \    - import: authentication-facilitator\n      location: ./shared/authentication-facilitator.yaml\n    - import: identity-insights-accounts\n      location: ./shared/identity-insights-accounts.yaml\n    - import: identity-insights-transactions\n      location: ./shared/identity-insights-transactions.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: identity-auth-api\n      description: \"Unified REST API for Mastercard identity and authentication workflows.\"\n      resources:\n        - path: /v1/verifications\n          name: verifications\n          description: \"Identity verification\"\n          operations:\n            - method: POST\n              name: verify-identity\n              description: \"Verify a consumer identity\"\n              call: \"id-verification.verify-identity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consents\n          name: consents\n          description:\
  \ \"Authentication consent management\"\n          operations:\n            - method: POST\n              name: create-consent\n              description: \"Create authentication consent\"\n              call: \"authentication-consent.create-consent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account-insights\n          name: account-insights\n          description: \"Identity insights for accounts\"\n          operations:\n            - method: POST\n              name: get-account-insights\n              description: \"Get identity insights for an account\"\n              call: \"identity-insights-accounts.get-account-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transaction-insights\n          name: transaction-insights\n          description: \"Identity insights for transactions\"\n          operations:\n            - method:\
  \ POST\n              name: get-transaction-insights\n              description: \"Get identity insights for a transaction\"\n              call: \"identity-insights-transactions.get-transaction-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: identity-auth-mcp\n      transport: http\n      description: \"MCP server for AI-assisted identity verification and authentication.\"\n      tools:\n        - name: verify-identity\n          description: \"Verify a consumer identity using Mastercard ID\"\n          hints:\n            readOnly: true\n          call: \"id-verification.verify-identity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-auth-consent\n          description: \"Create an authentication consent request\"\n          hints:\n            readOnly: false\n          call: \"authentication-consent.create-consent\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-consent-status\n          description: \"Get authentication consent status\"\n          hints:\n            readOnly: true\n          call: \"authentication-consent.get-consent\"\n          with:\n            consent_id: \"tools.consent_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-authentication\n          description: \"Initiate strong customer authentication\"\n          hints:\n            readOnly: false\n          call: \"authentication-facilitator.initiate-authentication\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-identity-insights\n          description: \"Get identity intelligence insights for an account\"\n          hints:\n            readOnly: true\n          call: \"identity-insights-accounts.get-account-insights\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-transaction-identity-insights\n          description: \"Get identity intelligence insights for a transaction\"\n          hints:\n            readOnly: true\n          call: \"identity-insights-transactions.get-transaction-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-trust-verification\n          description: \"Submit identity verification as a trust provider\"\n          hints:\n            readOnly: false\n          call: \"id-trust-providers.submit-verification\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/identity-and-authentication.yaml
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
