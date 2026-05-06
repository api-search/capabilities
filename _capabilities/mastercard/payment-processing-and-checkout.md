---
categories:
- payments
consumed_apis: []
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
- fraud detection
- process a payment through the gateway
- generate a merchant qr code for payment
- create a unified checkout session supporting multiple payment methods
- generate qr code
- create an installment plan
- process a cloud commerce transaction
- financial services
- process cloud transaction
- create a unified checkout session
- get payment details
- unified checkout sessions
- e-commerce
- create a new checkout session for a merchant
- create checkout session
- generate a merchant-presented qr code for payment
- create unified session
- credit cards
- create installment plan
- digital identity
- retrieve payment transaction details
- open banking
- checkout session management
- process payment
- get payment
- buy-now-pay-later installment plans
- checkout
- register contactless reader
- mastercard
- create a new checkout session
- payments
- create a buy-now-pay-later installment plan
- register a contactless reader device
- process a payment through the mastercard gateway
- merchant
- qr code payment acceptance
- payment processing
slug: payment-processing-and-checkout
source_filename: payment-processing-and-checkout.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Payment Processing and Checkout\n  description: Unified workflow for merchants and payment processors to manage checkout experiences, process payments, and\n    accept contactless transactions across Mastercard's payment gateway, checkout solutions, and commerce APIs.\n  tags:\n  - Mastercard\n  - Payment Processing\n  - Checkout\n  - E-Commerce\n  - Merchant\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: checkout-solutions\n    baseUri: https://api.mastercard.com/checkout\n    description: Mastercard Checkout Solutions API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: checkout\n      path: /checkout\n   \
  \   description: Checkout operations\n      operations:\n      - name: initiate-checkout\n        method: POST\n        description: Initiate a checkout session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            checkout: '{{tools.checkout}}'\n      - name: get-checkout-status\n        method: GET\n        description: Get checkout session status\n        inputParameters:\n        - name: session_id\n          in: path\n          type: string\n          required: true\n          description: Checkout session identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: unified-checkout\n    baseUri: https://api.mastercard.com/unified-checkout\n    description: Mastercard Unified Checkout Solutions API\n    authentication:\n      type: oauth1\n\
  \      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: sessions\n      path: /sessions\n      description: Unified checkout session management\n      operations:\n      - name: create-session\n        method: POST\n        description: Create a unified checkout session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            session: '{{tools.session}}'\n  - type: http\n    namespace: cloud-commerce\n    baseUri: https://api.mastercard.com/cloud-commerce\n    description: Mastercard Cloud Commerce API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: transactions\n      path: /transactions\n      description: Cloud commerce transactions\n      operations:\n      -\
  \ name: process-transaction\n        method: POST\n        description: Process a cloud commerce transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transaction: '{{tools.transaction}}'\n  - type: http\n    namespace: contactless-reader\n    baseUri: https://api.mastercard.com/contactless-reader\n    description: Mastercard Contactless Reader SDK API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: readers\n      path: /readers\n      description: Contactless reader management\n      operations:\n      - name: register-reader\n        method: POST\n        description: Register a contactless reader device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n        body:\n          type: json\n          data:\n            reader: '{{tools.reader}}'\n  - type: http\n    namespace: gateway\n    baseUri: https://api.mastercard.com/gateway\n    description: Mastercard Gateway API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: payments\n      path: /payments\n      description: Payment processing\n      operations:\n      - name: process-payment\n        method: POST\n        description: Process a payment transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payment: '{{tools.payment}}'\n      - name: get-payment\n        method: GET\n        description: Retrieve payment transaction details\n        inputParameters:\n        - name: payment_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: merchant-qr\n    baseUri: https://api.mastercard.com/merchant-qr\n    description: Mastercard Merchant Presented QR API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: qr-codes\n      path: /qr-codes\n      description: QR code management\n      operations:\n      - name: generate-qr\n        method: POST\n        description: Generate a merchant QR code for payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            qr: '{{tools.qr}}'\n  - type: http\n    namespace: installments\n\
  \    baseUri: https://api.mastercard.com/installments\n    description: Mastercard Installments API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: plans\n      path: /plans\n      description: Installment plan management\n      operations:\n      - name: create-plan\n        method: POST\n        description: Create an installment plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            plan: '{{tools.plan}}'\n      - name: get-plan\n        method: GET\n        description: Get installment plan details\n        inputParameters:\n        - name: plan_id\n          in: path\n          type: string\n          required: true\n          description: Plan identifier\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: payment-checkout-api\n    description: Unified REST API for Mastercard payment processing and checkout workflows.\n    resources:\n    - path: /v1/checkout-sessions\n      name: checkout-sessions\n      description: Checkout session management\n      operations:\n      - method: POST\n        name: create-checkout-session\n        description: Create a new checkout session\n        call: checkout-solutions.initiate-checkout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/unified-sessions\n      name: unified-sessions\n      description: Unified checkout sessions\n      operations:\n      - method: POST\n        name: create-unified-session\n        description: Create a unified checkout session\n        call: unified-checkout.create-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/payments\n      name: payments\n      description: Payment processing\n      operations:\n      - method: POST\n        name: process-payment\n        description: Process a payment through the gateway\n        call: gateway.process-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-payment\n        description: Get payment details\n        call: gateway.get-payment\n        with:\n          payment_id: rest.payment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/qr-payments\n      name: qr-payments\n      description: QR code payment acceptance\n      operations:\n      - method: POST\n        name: generate-qr-code\n        description: Generate a merchant QR code for payment\n        call: merchant-qr.generate-qr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installment-plans\n      name: installment-plans\n      description:\
  \ Buy-now-pay-later installment plans\n      operations:\n      - method: POST\n        name: create-installment-plan\n        description: Create an installment plan\n        call: installments.create-plan\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: payment-checkout-mcp\n    transport: http\n    description: MCP server for AI-assisted payment processing and checkout management.\n    tools:\n    - name: create-checkout-session\n      description: Create a new checkout session for a merchant\n      hints:\n        readOnly: false\n        idempotent: false\n      call: checkout-solutions.initiate-checkout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-unified-session\n      description: Create a unified checkout session supporting multiple payment methods\n      hints:\n        readOnly: false\n        idempotent: false\n      call: unified-checkout.create-session\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-payment\n      description: Process a payment through the Mastercard gateway\n      hints:\n        readOnly: false\n        idempotent: false\n      call: gateway.process-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payment-details\n      description: Retrieve payment transaction details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: gateway.get-payment\n      with:\n        payment_id: tools.payment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generate-qr-code\n      description: Generate a merchant-presented QR code for payment\n      hints:\n        readOnly: false\n        idempotent: false\n      call: merchant-qr.generate-qr\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-cloud-transaction\n      description: Process a cloud commerce transaction\n\
  \      hints:\n        readOnly: false\n        idempotent: false\n      call: cloud-commerce.process-transaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-contactless-reader\n      description: Register a contactless reader device\n      hints:\n        readOnly: false\n        idempotent: false\n      call: contactless-reader.register-reader\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-installment-plan\n      description: Create a buy-now-pay-later installment plan\n      hints:\n        readOnly: false\n        idempotent: false\n      call: installments.create-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
