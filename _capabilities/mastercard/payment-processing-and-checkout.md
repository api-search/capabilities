---
categories:
- payments
consumed_apis:
- checkout-solutions
- unified-checkout
- cloud-commerce
- contactless-reader
- gateway
- merchant-qr
- installments
description: Unified workflow for merchants and payment processors to manage checkout experiences, process payments, and accept contactless transactions across Mastercard's payment gateway, checkout solutions, and commerce APIs.
layout: capability
name: Mastercard Payment Processing and Checkout
operations:
- description: Create a new checkout session
  method: POST
  name: create-checkout-session
  path: /v1/checkout-sessions
- description: Create a unified checkout session
  method: POST
  name: create-unified-session
  path: /v1/unified-sessions
- description: Process a payment through the gateway
  method: POST
  name: process-payment
  path: /v1/payments
- description: Get payment details
  method: GET
  name: get-payment
  path: /v1/payments
- description: Generate a merchant QR code for payment
  method: POST
  name: generate-qr-code
  path: /v1/qr-payments
- description: Create an installment plan
  method: POST
  name: create-installment-plan
  path: /v1/installment-plans
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- e-commerce
- register a contactless reader device
- get payment details
- buy-now-pay-later installment plans
- create a buy-now-pay-later installment plan
- fraud detection
- process payment
- process a payment through the gateway
- qr code payment acceptance
- merchant
- payment processing
- create unified session
- generate a merchant-presented qr code for payment
- checkout session management
- financial services
- digital identity
- create an installment plan
- retrieve payment transaction details
- generate a merchant qr code for payment
- create installment plan
- process a payment through the mastercard gateway
- unified checkout sessions
- get payment
- create a unified checkout session supporting multiple payment methods
- mastercard
- register contactless reader
- process a cloud commerce transaction
- generate qr code
- process cloud transaction
- checkout
- open banking
- payments
- create a unified checkout session
- create checkout session
- create a new checkout session
- credit cards
- create a new checkout session for a merchant
slug: payment-processing-and-checkout
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Payment Processing and Checkout\"\n  description: \"Unified workflow for merchants and payment processors to manage checkout experiences, process payments, and accept contactless transactions across Mastercard's payment gateway, checkout solutions, and commerce APIs.\"\n  tags:\n    - Mastercard\n    - Payment Processing\n    - Checkout\n    - E-Commerce\n    - Merchant\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: checkout-solutions\n      location: ./shared/checkout-solutions.yaml\n    - import: unified-checkout\n      location: ./shared/unified-checkout-solutions.yaml\n    - import: cloud-commerce\n      location: ./shared/cloud-commerce.yaml\n    - import: contactless-reader\n      location: ./shared/contactless-reader-sdk.yaml\n\
  \    - import: gateway\n      location: ./shared/gateway.yaml\n    - import: merchant-qr\n      location: ./shared/merchant-presented-qr.yaml\n    - import: installments\n      location: ./shared/installments.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: payment-checkout-api\n      description: \"Unified REST API for Mastercard payment processing and checkout workflows.\"\n      resources:\n        - path: /v1/checkout-sessions\n          name: checkout-sessions\n          description: \"Checkout session management\"\n          operations:\n            - method: POST\n              name: create-checkout-session\n              description: \"Create a new checkout session\"\n              call: \"checkout-solutions.initiate-checkout\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/unified-sessions\n          name: unified-sessions\n          description: \"Unified checkout sessions\"\n  \
  \        operations:\n            - method: POST\n              name: create-unified-session\n              description: \"Create a unified checkout session\"\n              call: \"unified-checkout.create-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: \"Payment processing\"\n          operations:\n            - method: POST\n              name: process-payment\n              description: \"Process a payment through the gateway\"\n              call: \"gateway.process-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-payment\n              description: \"Get payment details\"\n              call: \"gateway.get-payment\"\n              with:\n                payment_id: \"rest.payment_id\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n        - path: /v1/qr-payments\n          name: qr-payments\n          description: \"QR code payment acceptance\"\n          operations:\n            - method: POST\n              name: generate-qr-code\n              description: \"Generate a merchant QR code for payment\"\n              call: \"merchant-qr.generate-qr\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/installment-plans\n          name: installment-plans\n          description: \"Buy-now-pay-later installment plans\"\n          operations:\n            - method: POST\n              name: create-installment-plan\n              description: \"Create an installment plan\"\n              call: \"installments.create-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: payment-checkout-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted payment processing and checkout management.\"\n      tools:\n        - name: create-checkout-session\n          description: \"Create a new checkout session for a merchant\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"checkout-solutions.initiate-checkout\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-unified-session\n          description: \"Create a unified checkout session supporting multiple payment methods\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unified-checkout.create-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-payment\n          description: \"Process a payment through the Mastercard gateway\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ false\n          call: \"gateway.process-payment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment-details\n          description: \"Retrieve payment transaction details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"gateway.get-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-qr-code\n          description: \"Generate a merchant-presented QR code for payment\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"merchant-qr.generate-qr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-cloud-transaction\n          description: \"Process a cloud commerce transaction\"\n          hints:\n            readOnly: false\n         \
  \   idempotent: false\n          call: \"cloud-commerce.process-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-contactless-reader\n          description: \"Register a contactless reader device\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"contactless-reader.register-reader\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-installment-plan\n          description: \"Create a buy-now-pay-later installment plan\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"installments.create-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/payment-processing-and-checkout.yaml
tags:
- Mastercard
- Payment Processing
- Checkout
- E-Commerce
- Merchant
tools:
- description: Create a new checkout session for a merchant
  hints:
    idempotent: false
    readOnly: false
  name: create-checkout-session
- description: Create a unified checkout session supporting multiple payment methods
  hints:
    idempotent: false
    readOnly: false
  name: create-unified-session
- description: Process a payment through the Mastercard gateway
  hints:
    idempotent: false
    readOnly: false
  name: process-payment
- description: Retrieve payment transaction details
  hints:
    idempotent: true
    readOnly: true
  name: get-payment-details
- description: Generate a merchant-presented QR code for payment
  hints:
    idempotent: false
    readOnly: false
  name: generate-qr-code
- description: Process a cloud commerce transaction
  hints:
    idempotent: false
    readOnly: false
  name: process-cloud-transaction
- description: Register a contactless reader device
  hints:
    idempotent: false
    readOnly: false
  name: register-contactless-reader
- description: Create a buy-now-pay-later installment plan
  hints:
    idempotent: false
    readOnly: false
  name: create-installment-plan
---
