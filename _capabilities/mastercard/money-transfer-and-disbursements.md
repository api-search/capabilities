---
categories: []
consumed_apis: []
description: Unified workflow for fintech developers and payment processors to manage real-time money transfers, P2P payments, disbursements, and cross-border services through Mastercard Send and related APIs.
layout: capability
name: Mastercard Money Transfer and Disbursements
operations:
- description: Create a funding transaction
  method: POST
  name: create-funding
  path: /v1/funding
- description: Create a person-to-person transfer
  method: POST
  name: create-p2p-transfer
  path: /v1/transfers
- description: Create a disbursement
  method: POST
  name: create-disbursement
  path: /v1/disbursements
- description: Create a cross-border payment
  method: POST
  name: create-cross-border-payment
  path: /v1/cross-border-payments
- description: Get currency conversion rate
  method: GET
  name: get-conversion-rate
  path: /v1/conversion-rates
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- cross-border
- verify account eligibility for mastercard send
- fraud detection
- get conversion rate
- create a disbursement to send money to a recipient
- create a funding transaction via mastercard send
- create disbursement
- mastercard send
- create a person-to-person transfer
- financial services
- create a cross-border payment
- disbursements
- get currency conversion rate for cross-border transactions
- process direct transaction
- validate account details before transfer
- disbursement transactions
- get currency conversion rate
- create funding
- get account information for a send recipient
- validate account
- credit cards
- process a direct service transaction
- create p2p transfer
- cross-border payment processing
- funding transactions
- digital identity
- open banking
- create a cross-border international payment
- money transfer
- get account info
- mastercard
- create a funding transaction
- currency conversion rates
- payments
- create a disbursement
- p2p transfers
- verify send account
- create cross border payment
- create a person-to-person money transfer
slug: money-transfer-and-disbursements
source_filename: money-transfer-and-disbursements.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Money Transfer and Disbursements\n  description: Unified workflow for fintech developers and payment processors to manage real-time money transfers, P2P payments,\n    disbursements, and cross-border services through Mastercard Send and related APIs.\n  tags:\n  - Mastercard\n  - Money Transfer\n  - Disbursements\n  - Cross-Border\n  - Mastercard Send\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: send-funding\n    baseUri: https://api.mastercard.com/send/v1/partners\n    description: Mastercard Send Funding API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: funding\n      path: /funding\n      description:\
  \ Funding transactions\n      operations:\n      - name: create-funding\n        method: POST\n        description: Create a funding transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            funding: '{{tools.funding}}'\n      - name: get-funding-status\n        method: GET\n        description: Get funding transaction status\n        inputParameters:\n        - name: transfer_id\n          in: path\n          type: string\n          required: true\n          description: Transfer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: send-p2p\n    baseUri: https://api.mastercard.com/send/v1/partners\n    description: Mastercard Send Person to Person API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n\
  \      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transfers\n      path: /transfers\n      description: P2P transfer operations\n      operations:\n      - name: create-p2p-transfer\n        method: POST\n        description: Create a person-to-person transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transfer: '{{tools.transfer}}'\n  - type: http\n    namespace: send-disbursements\n    baseUri: https://api.mastercard.com/send/v1/partners\n    description: Mastercard Send Disbursements API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: disbursements\n      path: /disbursements\n      description: Disbursement operations\n      operations:\n      - name: create-disbursement\n        method: POST\n\
  \        description: Create a disbursement transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            disbursement: '{{tools.disbursement}}'\n  - type: http\n    namespace: send-account-info\n    baseUri: https://api.mastercard.com/send/v1/partners\n    description: Mastercard Send Account Information Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Account information\n      operations:\n      - name: get-account-info\n        method: POST\n        description: Retrieve account information for a Send recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n        \
  \  type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: send-account-verification\n    baseUri: https://api.mastercard.com/send/v1/partners\n    description: Mastercard Send Account Verification Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: verifications\n      path: /verifications\n      description: Account verification\n      operations:\n      - name: verify-account\n        method: POST\n        description: Verify an account for Send eligibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: cross-border\n    baseUri: https://api.mastercard.com/cross-border\n    description: Mastercard Cross-Border\
  \ Services API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: payments\n      path: /payments\n      description: Cross-border payment operations\n      operations:\n      - name: create-payment\n        method: POST\n        description: Create a cross-border payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payment: '{{tools.payment}}'\n      - name: get-payment-status\n        method: GET\n        description: Get cross-border payment status\n        inputParameters:\n        - name: payment_id\n          in: path\n          type: string\n          required: true\n          description: Payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n  - type: http\n    namespace: direct-services\n    baseUri: https://api.mastercard.com/direct-services\n    description: Mastercard Direct Services API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      description: Direct service transactions\n      operations:\n      - name: process-transaction\n        method: POST\n        description: Process a direct service transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  - type: http\n    namespace: account-validation\n    baseUri: https://api.mastercard.com/account-validation\n    description: Mastercard Account Validation API\n    authentication:\n      type: oauth1\n\
  \      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: validations\n      path: /validations\n      description: Account validation operations\n      operations:\n      - name: validate-account\n        method: POST\n        description: Validate an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n  - type: http\n    namespace: currency-conversion\n    baseUri: https://api.mastercard.com/settlement/currencyrate\n    description: Mastercard Currency Conversion API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: rates\n      path: /rates\n      description: Currency conversion rates\n      operations:\n      - name: get-conversion-rate\n\
  \        method: GET\n        description: Get currency conversion rate\n        inputParameters:\n        - name: fxDate\n          in: query\n          type: string\n          required: true\n          description: Date for the conversion rate\n        - name: transCurr\n          in: query\n          type: string\n          required: true\n          description: Transaction currency\n        - name: crdhldBillCurr\n          in: query\n          type: string\n          required: true\n          description: Cardholder billing currency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: money-transfer-api\n    description: Unified REST API for Mastercard money transfer and disbursement workflows.\n    resources:\n    - path: /v1/funding\n      name: funding\n      description: Funding transactions\n      operations:\n      - method: POST\n        name:\
  \ create-funding\n        description: Create a funding transaction\n        call: send-funding.create-funding\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transfers\n      name: transfers\n      description: P2P transfers\n      operations:\n      - method: POST\n        name: create-p2p-transfer\n        description: Create a person-to-person transfer\n        call: send-p2p.create-p2p-transfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disbursements\n      name: disbursements\n      description: Disbursement transactions\n      operations:\n      - method: POST\n        name: create-disbursement\n        description: Create a disbursement\n        call: send-disbursements.create-disbursement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cross-border-payments\n      name: cross-border-payments\n      description: Cross-border payment processing\n\
  \      operations:\n      - method: POST\n        name: create-cross-border-payment\n        description: Create a cross-border payment\n        call: cross-border.create-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/conversion-rates\n      name: conversion-rates\n      description: Currency conversion rates\n      operations:\n      - method: GET\n        name: get-conversion-rate\n        description: Get currency conversion rate\n        call: currency-conversion.get-conversion-rate\n        with:\n          fxDate: rest.fxDate\n          transCurr: rest.transCurr\n          crdhldBillCurr: rest.crdhldBillCurr\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: money-transfer-mcp\n    transport: http\n    description: MCP server for AI-assisted money transfer and disbursement operations.\n    tools:\n    - name: create-funding\n      description: Create a funding\
  \ transaction via Mastercard Send\n      hints:\n        readOnly: false\n      call: send-funding.create-funding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-p2p-transfer\n      description: Create a person-to-person money transfer\n      hints:\n        readOnly: false\n      call: send-p2p.create-p2p-transfer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-disbursement\n      description: Create a disbursement to send money to a recipient\n      hints:\n        readOnly: false\n      call: send-disbursements.create-disbursement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-send-account\n      description: Verify account eligibility for Mastercard Send\n      hints:\n        readOnly: true\n      call: send-account-verification.verify-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-info\n      description: Get\
  \ account information for a Send recipient\n      hints:\n        readOnly: true\n      call: send-account-info.get-account-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-account\n      description: Validate account details before transfer\n      hints:\n        readOnly: true\n      call: account-validation.validate-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cross-border-payment\n      description: Create a cross-border international payment\n      hints:\n        readOnly: false\n      call: cross-border.create-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-conversion-rate\n      description: Get currency conversion rate for cross-border transactions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: currency-conversion.get-conversion-rate\n      with:\n        fxDate: tools.fxDate\n        transCurr: tools.transCurr\n\
  \        crdhldBillCurr: tools.crdhldBillCurr\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-direct-transaction\n      description: Process a direct service transaction\n      hints:\n        readOnly: false\n      call: direct-services.process-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/money-transfer-and-disbursements.yaml
tags:
- Mastercard
- Money Transfer
- Disbursements
- Cross-Border
- Mastercard Send
tools:
- description: Create a funding transaction via Mastercard Send
  hints:
    readOnly: false
  name: create-funding
- description: Create a person-to-person money transfer
  hints:
    readOnly: false
  name: create-p2p-transfer
- description: Create a disbursement to send money to a recipient
  hints:
    readOnly: false
  name: create-disbursement
- description: Verify account eligibility for Mastercard Send
  hints:
    readOnly: true
  name: verify-send-account
- description: Get account information for a Send recipient
  hints:
    readOnly: true
  name: get-account-info
- description: Validate account details before transfer
  hints:
    readOnly: true
  name: validate-account
- description: Create a cross-border international payment
  hints:
    readOnly: false
  name: create-cross-border-payment
- description: Get currency conversion rate for cross-border transactions
  hints:
    idempotent: true
    readOnly: true
  name: get-conversion-rate
- description: Process a direct service transaction
  hints:
    readOnly: false
  name: process-direct-transaction
---
