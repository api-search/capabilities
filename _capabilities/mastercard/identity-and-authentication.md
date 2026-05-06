---
categories:
- identity-access
consumed_apis: []
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
- kyc
- verify a consumer identity
- fraud detection
- create consent
- get transaction insights
- identity
- get account identity insights
- get account insights
- financial services
- submit trust verification
- get identity intelligence insights for a transaction
- authentication consent management
- verify a consumer identity using mastercard id
- get identity insights for a transaction
- initiate strong customer authentication
- submit identity verification as a trust provider
- get authentication consent status
- credit cards
- verify identity
- get consent status
- digital identity
- get identity intelligence insights for an account
- open banking
- identity insights for transactions
- authentication
- mastercard
- identity verification
- get transaction identity insights
- create auth consent
- payments
- initiate authentication
- identity insights for accounts
- create an authentication consent request
- create authentication consent
- verification
- get identity insights for an account
slug: identity-and-authentication
source_filename: identity-and-authentication.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Identity and Authentication\n  description: Unified workflow for identity managers and compliance teams to verify identities, manage authentication consent,\n    and leverage identity intelligence for fraud prevention across Mastercard's identity services.\n  tags:\n  - Mastercard\n  - Identity\n  - Authentication\n  - Verification\n  - KYC\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: id-verification\n    baseUri: https://api.mastercard.com/id/verification\n    description: Mastercard ID Verification API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: verifications\n      path: /verifications\n      description:\
  \ Identity verification operations\n      operations:\n      - name: verify-identity\n        method: POST\n        description: Verify a consumer identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identity: '{{tools.identity}}'\n  - type: http\n    namespace: id-trust-providers\n    baseUri: https://api.mastercard.com/id/trust-providers\n    description: Mastercard ID for Trust Providers API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: trust-services\n      path: /trust-services\n      description: Trust provider operations\n      operations:\n      - name: submit-verification\n        method: POST\n        description: Submit identity verification as a trust provider\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            verification: '{{tools.verification}}'\n  - type: http\n    namespace: id-identity-providers\n    baseUri: https://api.mastercard.com/id/identity-providers\n    description: Mastercard ID for Identity Providers API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: identity-services\n      path: /identity-services\n      description: Identity provider operations\n      operations:\n      - name: provide-identity\n        method: POST\n        description: Provide identity data as an identity provider\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identity: '{{tools.identity}}'\n  - type: http\n\
  \    namespace: authentication-consent\n    baseUri: https://api.mastercard.com/authentication/consent\n    description: Mastercard Authentication Consent API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: consents\n      path: /consents\n      description: Consent management\n      operations:\n      - name: create-consent\n        method: POST\n        description: Create an authentication consent request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            consent: '{{tools.consent}}'\n      - name: get-consent\n        method: GET\n        description: Retrieve consent status\n        inputParameters:\n        - name: consent_id\n          in: path\n          type: string\n          required: true\n          description: Consent\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: authentication-facilitator\n    baseUri: https://api.mastercard.com/authentication/facilitator\n    description: Mastercard Authentication Facilitator API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: authentications\n      path: /authentications\n      description: Authentication facilitation\n      operations:\n      - name: initiate-authentication\n        method: POST\n        description: Initiate a strong customer authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            authentication: '{{tools.authentication}}'\n  - type: http\n    namespace:\
  \ identity-insights-accounts\n    baseUri: https://api.mastercard.com/idinsights/accounts\n    description: Mastercard Identity Insights for Accounts API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: account-insights\n      path: /insights\n      description: Account identity insights\n      operations:\n      - name: get-account-insights\n        method: POST\n        description: Get identity insights for an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: identity-insights-transactions\n    baseUri: https://api.mastercard.com/idinsights/transactions\n    description: Mastercard Identity Insights for Transactions API\n    authentication:\n      type: oauth1\n\
  \      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transaction-insights\n      path: /insights\n      description: Transaction identity insights\n      operations:\n      - name: get-transaction-insights\n        method: POST\n        description: Get identity insights for a transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: identity-auth-api\n    description: Unified REST API for Mastercard identity and authentication workflows.\n    resources:\n    - path: /v1/verifications\n      name: verifications\n      description: Identity verification\n      operations:\n      - method: POST\n        name: verify-identity\n        description: Verify a consumer identity\n\
  \        call: id-verification.verify-identity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consents\n      name: consents\n      description: Authentication consent management\n      operations:\n      - method: POST\n        name: create-consent\n        description: Create authentication consent\n        call: authentication-consent.create-consent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account-insights\n      name: account-insights\n      description: Identity insights for accounts\n      operations:\n      - method: POST\n        name: get-account-insights\n        description: Get identity insights for an account\n        call: identity-insights-accounts.get-account-insights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transaction-insights\n      name: transaction-insights\n      description: Identity insights for transactions\n      operations:\n\
  \      - method: POST\n        name: get-transaction-insights\n        description: Get identity insights for a transaction\n        call: identity-insights-transactions.get-transaction-insights\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: identity-auth-mcp\n    transport: http\n    description: MCP server for AI-assisted identity verification and authentication.\n    tools:\n    - name: verify-identity\n      description: Verify a consumer identity using Mastercard ID\n      hints:\n        readOnly: true\n      call: id-verification.verify-identity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-auth-consent\n      description: Create an authentication consent request\n      hints:\n        readOnly: false\n      call: authentication-consent.create-consent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-consent-status\n      description:\
  \ Get authentication consent status\n      hints:\n        readOnly: true\n      call: authentication-consent.get-consent\n      with:\n        consent_id: tools.consent_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-authentication\n      description: Initiate strong customer authentication\n      hints:\n        readOnly: false\n      call: authentication-facilitator.initiate-authentication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-identity-insights\n      description: Get identity intelligence insights for an account\n      hints:\n        readOnly: true\n      call: identity-insights-accounts.get-account-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction-identity-insights\n      description: Get identity intelligence insights for a transaction\n      hints:\n        readOnly: true\n      call: identity-insights-transactions.get-transaction-insights\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-trust-verification\n      description: Submit identity verification as a trust provider\n      hints:\n        readOnly: false\n      call: id-trust-providers.submit-verification\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
