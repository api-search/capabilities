---
categories: []
consumed_apis:
- send-funding
- send-p2p
- send-disbursements
- send-account-info
- send-account-verification
- cross-border
- direct-services
- account-validation
- currency-conversion
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
- create cross border payment
- digital identity
- funding transactions
- validate account
- payments
- create a disbursement
- create a funding transaction
- create a funding transaction via mastercard send
- open banking
- verify send account
- create a cross-border international payment
- create a cross-border payment
- get account info
- process a direct service transaction
- currency conversion rates
- cross-border payment processing
- create a person-to-person transfer
- get conversion rate
- fraud detection
- verify account eligibility for mastercard send
- create a person-to-person money transfer
- p2p transfers
- process direct transaction
- create funding
- create disbursement
- disbursements
- mastercard send
- credit cards
- disbursement transactions
- money transfer
- get currency conversion rate
- get account information for a send recipient
- financial services
- create p2p transfer
- mastercard
- get currency conversion rate for cross-border transactions
- cross-border
- validate account details before transfer
- create a disbursement to send money to a recipient
slug: money-transfer-and-disbursements
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Money Transfer and Disbursements\"\n  description: \"Unified workflow for fintech developers and payment processors to manage real-time money transfers, P2P payments, disbursements, and cross-border services through Mastercard Send and related APIs.\"\n  tags:\n    - Mastercard\n    - Money Transfer\n    - Disbursements\n    - Cross-Border\n    - Mastercard Send\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: send-funding\n      location: ./shared/send-funding.yaml\n    - import: send-p2p\n      location: ./shared/send-person-to-person.yaml\n    - import: send-disbursements\n      location: ./shared/send-disbursements.yaml\n    - import: send-account-info\n      location: ./shared/send-account-info.yaml\n    - import: send-account-verification\n\
  \      location: ./shared/send-account-verification.yaml\n    - import: cross-border\n      location: ./shared/cross-border-services.yaml\n    - import: direct-services\n      location: ./shared/direct-services.yaml\n    - import: account-validation\n      location: ./shared/account-validation.yaml\n    - import: currency-conversion\n      location: ./shared/currency-conversion.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: money-transfer-api\n      description: \"Unified REST API for Mastercard money transfer and disbursement workflows.\"\n      resources:\n        - path: /v1/funding\n          name: funding\n          description: \"Funding transactions\"\n          operations:\n            - method: POST\n              name: create-funding\n              description: \"Create a funding transaction\"\n              call: \"send-funding.create-funding\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    \
  \    - path: /v1/transfers\n          name: transfers\n          description: \"P2P transfers\"\n          operations:\n            - method: POST\n              name: create-p2p-transfer\n              description: \"Create a person-to-person transfer\"\n              call: \"send-p2p.create-p2p-transfer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disbursements\n          name: disbursements\n          description: \"Disbursement transactions\"\n          operations:\n            - method: POST\n              name: create-disbursement\n              description: \"Create a disbursement\"\n              call: \"send-disbursements.create-disbursement\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cross-border-payments\n          name: cross-border-payments\n          description: \"Cross-border payment processing\"\n          operations:\n\
  \            - method: POST\n              name: create-cross-border-payment\n              description: \"Create a cross-border payment\"\n              call: \"cross-border.create-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/conversion-rates\n          name: conversion-rates\n          description: \"Currency conversion rates\"\n          operations:\n            - method: GET\n              name: get-conversion-rate\n              description: \"Get currency conversion rate\"\n              call: \"currency-conversion.get-conversion-rate\"\n              with:\n                fxDate: \"rest.fxDate\"\n                transCurr: \"rest.transCurr\"\n                crdhldBillCurr: \"rest.crdhldBillCurr\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: money-transfer-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted money transfer and disbursement operations.\"\n      tools:\n        - name: create-funding\n          description: \"Create a funding transaction via Mastercard Send\"\n          hints:\n            readOnly: false\n          call: \"send-funding.create-funding\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-p2p-transfer\n          description: \"Create a person-to-person money transfer\"\n          hints:\n            readOnly: false\n          call: \"send-p2p.create-p2p-transfer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-disbursement\n          description: \"Create a disbursement to send money to a recipient\"\n          hints:\n            readOnly: false\n          call: \"send-disbursements.create-disbursement\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: verify-send-account\n          description: \"Verify account eligibility for Mastercard Send\"\n          hints:\n            readOnly: true\n          call: \"send-account-verification.verify-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-info\n          description: \"Get account information for a Send recipient\"\n          hints:\n            readOnly: true\n          call: \"send-account-info.get-account-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-account\n          description: \"Validate account details before transfer\"\n          hints:\n            readOnly: true\n          call: \"account-validation.validate-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cross-border-payment\n          description: \"Create a cross-border international\
  \ payment\"\n          hints:\n            readOnly: false\n          call: \"cross-border.create-payment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-conversion-rate\n          description: \"Get currency conversion rate for cross-border transactions\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"currency-conversion.get-conversion-rate\"\n          with:\n            fxDate: \"tools.fxDate\"\n            transCurr: \"tools.transCurr\"\n            crdhldBillCurr: \"tools.crdhldBillCurr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-direct-transaction\n          description: \"Process a direct service transaction\"\n          hints:\n            readOnly: false\n          call: \"direct-services.process-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
