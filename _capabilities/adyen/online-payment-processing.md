---
categories:
- payments
consumed_apis: []
description: 'Unified capability for accepting and managing online payments. Combines the Checkout API and Payments API to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. Primary persona: Developer or Merchant Platform Engineer.'
layout: capability
name: Adyen Online Payment Processing
operations:
- description: Create a checkout session.
  method: POST
  name: create-checkout-session
  path: /v1/sessions
- description: List available payment methods.
  method: POST
  name: list-payment-methods
  path: /v1/payment-methods
- description: Create a payment via Checkout API.
  method: POST
  name: create-payment
  path: /v1/payments
- description: Authorise a payment.
  method: POST
  name: authorise-payment
  path: /v1/payments/authorise
- description: Capture an authorised payment.
  method: POST
  name: capture-payment
  path: /v1/payments/capture
- description: Refund a payment.
  method: POST
  name: refund-payment
  path: /v1/payments/{paymentPspReference}/refunds
- description: Cancel an authorised payment.
  method: POST
  name: cancel-payment
  path: /v1/payments/cancel
personas: []
provider_name: Adyen
provider_slug: adyen
search_terms:
- cancel an authorised payment before capture.
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- refund completed payments.
- initiate and manage payments.
- online payments
- authorise a payment via classic payments api.
- capture a previously authorised payment.
- marketplace and platform fund management.
- checkout
- cancel payment
- list available payment methods for a shopper based on their context.
- adyen
- get available payment methods for a shopper.
- list available payment methods.
- create payment
- fintech
- capture payment
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- capture authorised payments.
- cancel authorised payments.
- chargeback and dispute handling.
- authorise a payment.
- create a checkout session.
- cancel an authorised payment.
- create checkout sessions for hosted payment flows.
- refund a payment.
- authorise a payment via classic adyen payments api.
- e-commerce
- refund a completed payment using its psp reference.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- list payment methods
- online and in-person payment acceptance.
- builds payment integrations using adyen apis and sdks.
- financial services
- authorise payment
- create an adyen checkout session for hosted payment flows.
- manages merchant accounts, terminals, and dispute responses.
- create checkout session
- create a payment via checkout api.
- payments
- builds marketplace and fintech platforms using adyen balance platform.
- initiate a payment via adyen checkout api.
- capture an authorised payment.
- refund payment
- merchant account and balance platform configuration.
slug: online-payment-processing
source_filename: online-payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adyen Online Payment Processing\n  description: 'Unified capability for accepting and managing online payments. Combines the Checkout API and Payments API\n    to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation,\n    refunds, and cancellations. Primary persona: Developer or Merchant Platform Engineer.'\n  tags:\n  - Adyen\n  - Payments\n  - Checkout\n  - Online Payments\n  - E-Commerce\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADYEN_API_KEY: ADYEN_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: checkout\n    baseUri: https://checkout-test.adyen.com/v71\n    description: Adyen Checkout API for initiating and managing online payments.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{ADYEN_API_KEY}}'\n      placement: header\n    resources:\n    - name: payments\n\
  \      path: /payments\n      description: Initiate and manage payment transactions.\n      operations:\n      - name: create-payment\n        method: POST\n        description: Submit a payment request for the selected payment method.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-sessions\n      path: /sessions\n      description: Create and manage checkout sessions.\n      operations:\n      - name: create-session\n        method: POST\n        description: Create a payment session for checkout.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-methods\n      path: /paymentMethods\n      description: Retrieve available payment methods for a shopper.\n      operations:\n      - name: list-payment-methods\n        method: POST\n        description: Get a list of available payment methods based\
  \ on the transaction and shopper context.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds\n      path: /payments/{paymentPspReference}/refunds\n      description: Refund payments.\n      operations:\n      - name: refund-payment\n        method: POST\n        description: Refund a payment using the PSP reference.\n        inputParameters:\n        - name: paymentPspReference\n          in: path\n          type: string\n          required: true\n          description: The PSP reference of the payment to refund.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cancels\n      path: /cancels\n      description: Cancel authorised payments.\n      operations:\n      - name: cancel-payment\n        method: POST\n        description: Cancel an authorised payment.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: payments\n    baseUri: https://pal-test.adyen.com/pal/servlet/Payment/v68\n    description: Adyen classic Payment API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{ADYEN_API_KEY}}'\n      placement: header\n    resources:\n    - name: authorise\n      path: /authorise\n      description: Authorise a payment.\n      operations:\n      - name: authorise-payment\n        method: POST\n        description: Authorise a payment request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: capture\n      path: /capture\n      description: Capture an authorised payment.\n      operations:\n      - name: capture-payment\n        method: POST\n        description: Capture a previously authorised payment.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: refund\n      path: /refund\n      description: Refund a payment.\n      operations:\n      - name: refund-payment\n        method: POST\n        description: Refund a captured payment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cancel\n      path: /cancel\n      description: Cancel an authorised payment.\n      operations:\n      - name: cancel-payment\n        method: POST\n        description: Cancel an authorised payment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: adyen-online-payments-api\n    description: Unified REST API for Adyen online payment processing workflows.\n    resources:\n    - path: /v1/sessions\n      name: checkout-sessions\n      description: Create checkout sessions\
  \ for hosted payment flows.\n      operations:\n      - method: POST\n        name: create-checkout-session\n        description: Create a checkout session.\n        call: checkout.create-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-methods\n      name: payment-methods\n      description: Get available payment methods for a shopper.\n      operations:\n      - method: POST\n        name: list-payment-methods\n        description: List available payment methods.\n        call: checkout.list-payment-methods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Initiate and manage payments.\n      operations:\n      - method: POST\n        name: create-payment\n        description: Create a payment via Checkout API.\n        call: checkout.create-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/authorise\n\
  \      name: authorise\n      description: Authorise a payment via classic Payments API.\n      operations:\n      - method: POST\n        name: authorise-payment\n        description: Authorise a payment.\n        call: payments.authorise-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/capture\n      name: capture\n      description: Capture authorised payments.\n      operations:\n      - method: POST\n        name: capture-payment\n        description: Capture an authorised payment.\n        call: payments.capture-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentPspReference}/refunds\n      name: refunds\n      description: Refund completed payments.\n      operations:\n      - method: POST\n        name: refund-payment\n        description: Refund a payment.\n        call: checkout.refund-payment\n        with:\n          paymentPspReference: rest.paymentPspReference\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/cancel\n      name: cancels\n      description: Cancel authorised payments.\n      operations:\n      - method: POST\n        name: cancel-payment\n        description: Cancel an authorised payment.\n        call: checkout.cancel-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: adyen-online-payments-mcp\n    transport: http\n    description: MCP server for AI-assisted Adyen online payment processing.\n    tools:\n    - name: create-checkout-session\n      description: Create an Adyen checkout session for hosted payment flows.\n      hints:\n        readOnly: false\n        destructive: false\n      call: checkout.create-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-methods\n      description: List available payment methods for a shopper based on their context.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n      call: checkout.list-payment-methods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment\n      description: Initiate a payment via Adyen Checkout API.\n      hints:\n        readOnly: false\n        destructive: false\n      call: checkout.create-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorise-payment\n      description: Authorise a payment via classic Adyen Payments API.\n      hints:\n        readOnly: false\n        destructive: false\n      call: payments.authorise-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-payment\n      description: Capture a previously authorised payment.\n      hints:\n        readOnly: false\n        destructive: false\n      call: payments.capture-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refund-payment\n\
  \      description: Refund a completed payment using its PSP reference.\n      hints:\n        readOnly: false\n        destructive: false\n      call: checkout.refund-payment\n      with:\n        paymentPspReference: tools.paymentPspReference\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-payment\n      description: Cancel an authorised payment before capture.\n      hints:\n        readOnly: false\n        destructive: true\n      call: checkout.cancel-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adyen/refs/heads/main/capabilities/online-payment-processing.yaml
tags:
- Adyen
- Payments
- Checkout
- Online Payments
- E-Commerce
tools:
- description: Create an Adyen checkout session for hosted payment flows.
  hints:
    destructive: false
    readOnly: false
  name: create-checkout-session
- description: List available payment methods for a shopper based on their context.
  hints:
    destructive: false
    readOnly: true
  name: list-payment-methods
- description: Initiate a payment via Adyen Checkout API.
  hints:
    destructive: false
    readOnly: false
  name: create-payment
- description: Authorise a payment via classic Adyen Payments API.
  hints:
    destructive: false
    readOnly: false
  name: authorise-payment
- description: Capture a previously authorised payment.
  hints:
    destructive: false
    readOnly: false
  name: capture-payment
- description: Refund a completed payment using its PSP reference.
  hints:
    destructive: false
    readOnly: false
  name: refund-payment
- description: Cancel an authorised payment before capture.
  hints:
    destructive: true
    readOnly: false
  name: cancel-payment
---
