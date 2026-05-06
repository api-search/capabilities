---
categories: []
consumed_apis: []
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
- push provision a token to a wallet
- fraud detection
- tokenize a payment card via mdes
- bulk tokenization operations
- submit bulk tokenization request
- delete a token
- check card eligibility for digitization
- submit bulk tokenization
- financial services
- click to pay
- token lifecycle management
- check digitization eligibility
- digital payments
- tokenization
- suspend an active token
- enroll issuer click to pay
- tokenize a payment card
- suspend token
- delete token
- register token requestor
- push provisioning to wallets
- credit cards
- digital identity
- open banking
- push provision to wallet
- push provision a token to a digital wallet
- mastercard
- get token details
- payments
- tokenize card
- submit a bulk tokenization request for a card portfolio
- mdes
- push provision
- register a new token requestor
- check if a card is eligible for digitization
- enroll an issuer in click to pay
- pre-digitization eligibility
slug: digital-enablement-and-tokenization
source_filename: digital-enablement-and-tokenization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Digital Enablement and Tokenization\n  description: Unified workflow for digital payment teams and issuer technology to manage card tokenization, MDES digital\n    enablement, Click to Pay enrollment, and push provisioning to digital wallets.\n  tags:\n  - Mastercard\n  - Tokenization\n  - MDES\n  - Digital Payments\n  - Click to Pay\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: mdes-digital\n    baseUri: https://api.mastercard.com/mdes\n    description: Mastercard MDES Digital Enablement API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: tokens\n      path: /tokens\n      description: Token lifecycle management\n\
  \      operations:\n      - name: tokenize\n        method: POST\n        description: Tokenize a payment card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            card: '{{tools.card}}'\n      - name: get-token\n        method: GET\n        description: Get token details\n        inputParameters:\n        - name: token_id\n          in: path\n          type: string\n          required: true\n          description: Token identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-token\n        method: POST\n        description: Suspend a token\n        inputParameters:\n        - name: token_id\n          in: path\n          type: string\n          required: true\n          description: Token identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-token\n        method: DELETE\n        description: Delete a token\n        inputParameters:\n        - name: token_id\n          in: path\n          type: string\n          required: true\n          description: Token identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: mdes-token-connect\n    baseUri: https://api.mastercard.com/mdes/token-connect\n    description: Mastercard MDES Token Connect API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: provisioning\n      path: /provisioning\n      description: Token provisioning operations\n      operations:\n      - name: push-provision\n        method: POST\n        description: Push provision a token to a wallet\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            provisioning: '{{tools.provisioning}}'\n  - type: http\n    namespace: mdes-pre-digitization\n    baseUri: https://api.mastercard.com/mdes/pre-digitization\n    description: Mastercard MDES Pre-Digitization API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: eligibility\n      path: /eligibility\n      description: Pre-digitization eligibility\n      operations:\n      - name: check-eligibility\n        method: POST\n        description: Check card eligibility for digitization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            card: '{{tools.card}}'\n\
  \  - type: http\n    namespace: mdes-bulk-tokenization\n    baseUri: https://api.mastercard.com/mdes/bulk-tokenization\n    description: Mastercard MDES Bulk Tokenization API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: bulk\n      path: /bulk\n      description: Bulk tokenization operations\n      operations:\n      - name: submit-bulk-tokenization\n        method: POST\n        description: Submit a bulk tokenization request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            batch: '{{tools.batch}}'\n  - type: http\n    namespace: token-requestor-id\n    baseUri: https://api.mastercard.com/trid\n    description: Mastercard Token Requestor Identifier API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n\
  \      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: requestors\n      path: /requestors\n      description: Token requestor management\n      operations:\n      - name: register-requestor\n        method: POST\n        description: Register a token requestor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requestor: '{{tools.requestor}}'\n  - type: http\n    namespace: issuer-click-to-pay\n    baseUri: https://api.mastercard.com/click-to-pay/issuers\n    description: Mastercard Issuer Enrollment Click to Pay API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: enrollments\n      path: /enrollments\n      description: Issuer enrollment operations\n      operations:\n      - name: enroll-issuer\n      \
  \  method: POST\n        description: Enroll an issuer in Click to Pay\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            enrollment: '{{tools.enrollment}}'\n  exposes:\n  - type: rest\n    port: 8088\n    namespace: digital-token-api\n    description: Unified REST API for digital enablement and tokenization.\n    resources:\n    - path: /v1/tokens\n      name: tokens\n      description: Token lifecycle management\n      operations:\n      - method: POST\n        name: tokenize-card\n        description: Tokenize a payment card\n        call: mdes-digital.tokenize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/eligibility\n      name: eligibility\n      description: Pre-digitization eligibility\n      operations:\n      - method: POST\n        name: check-digitization-eligibility\n        description:\
  \ Check card eligibility for digitization\n        call: mdes-pre-digitization.check-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk-tokenization\n      name: bulk-tokenization\n      description: Bulk tokenization operations\n      operations:\n      - method: POST\n        name: submit-bulk-tokenization\n        description: Submit bulk tokenization request\n        call: mdes-bulk-tokenization.submit-bulk-tokenization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning\n      name: provisioning\n      description: Push provisioning to wallets\n      operations:\n      - method: POST\n        name: push-provision\n        description: Push provision a token to a wallet\n        call: mdes-token-connect.push-provision\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9098\n    namespace: digital-token-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted digital enablement and tokenization.\n    tools:\n    - name: tokenize-card\n      description: Tokenize a payment card via MDES\n      hints:\n        readOnly: false\n      call: mdes-digital.tokenize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-token-details\n      description: Get token details\n      hints:\n        readOnly: true\n      call: mdes-digital.get-token\n      with:\n        token_id: tools.token_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suspend-token\n      description: Suspend an active token\n      hints:\n        readOnly: false\n      call: mdes-digital.suspend-token\n      with:\n        token_id: tools.token_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-token\n      description: Delete a token\n      hints:\n        readOnly: false\n        destructive: true\n      call: mdes-digital.delete-token\n\
  \      with:\n        token_id: tools.token_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-digitization-eligibility\n      description: Check if a card is eligible for digitization\n      hints:\n        readOnly: true\n      call: mdes-pre-digitization.check-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: push-provision-to-wallet\n      description: Push provision a token to a digital wallet\n      hints:\n        readOnly: false\n      call: mdes-token-connect.push-provision\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-bulk-tokenization\n      description: Submit a bulk tokenization request for a card portfolio\n      hints:\n        readOnly: false\n      call: mdes-bulk-tokenization.submit-bulk-tokenization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-token-requestor\n      description: Register a new token requestor\n\
  \      hints:\n        readOnly: false\n      call: token-requestor-id.register-requestor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-issuer-click-to-pay\n      description: Enroll an issuer in Click to Pay\n      hints:\n        readOnly: false\n      call: issuer-click-to-pay.enroll-issuer\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/digital-enablement-and-tokenization.yaml
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
