---
categories: []
consumed_apis:
- stripe-payment-intents
- stripe-checkout
- stripe-refunds
- stripe-disputes
description: Unified capability for end-to-end payment processing workflows. Combines Stripe Payment Intents and Checkout APIs to support payment creation, confirmation, capture, refunds, and dispute management. Used by e-commerce platforms, SaaS billing teams, and payment operations engineers.
layout: capability
name: Stripe Payment Processing
operations:
- description: List payment intents
  method: GET
  name: list-payment-intents
  path: /v1/payment-intents
- description: Create a payment intent
  method: POST
  name: create-payment-intent
  path: /v1/payment-intents
- description: Get a payment intent
  method: GET
  name: get-payment-intent
  path: /v1/payment-intents/{intent}
- description: Confirm payment intent
  method: POST
  name: confirm-payment-intent
  path: /v1/payment-intents/{intent}/confirm
- description: Capture authorized payment
  method: POST
  name: capture-payment-intent
  path: /v1/payment-intents/{intent}/capture
- description: List checkout sessions
  method: GET
  name: list-checkout-sessions
  path: /v1/checkout-sessions
- description: Create a hosted checkout session
  method: POST
  name: create-checkout-session
  path: /v1/checkout-sessions
- description: List refunds
  method: GET
  name: list-refunds
  path: /v1/refunds
- description: Create a refund
  method: POST
  name: create-refund
  path: /v1/refunds
- description: List disputes
  method: GET
  name: list-disputes
  path: /v1/disputes
- description: Get a dispute
  method: GET
  name: get-dispute
  path: /v1/disputes/{dispute}
personas: []
provider_name: Stripe
provider_slug: stripe
search_terms:
- t1
- capture authorized funds for a stripe payment intent
- capture payment intent
- get details of a specific stripe dispute
- create refund
- stripe
- individual dispute
- create a stripe hosted checkout page for payment collection
- e-commerce
- individual payment intent
- update evidence for a stripe dispute to contest a chargeback
- create checkout session
- capture authorized payment
- update dispute
- financial services
- get payment intent
- manage payment intents for custom payment flows
- get a dispute
- cancel an uncaptured stripe payment intent
- create a refund on a stripe charge or payment intent
- retrieve details of a stripe checkout session
- refunds
- payments
- list disputes
- list payment intents
- list refunds
- confirm a stripe payment intent to execute the payment
- create a refund
- commerce
- confirm payment intent
- capture payment funds
- list checkout sessions
- create a hosted checkout session
- create a payment intent
- payment disputes and chargebacks
- get a payment intent
- disputes
- list stripe payment intents with optional filters
- payment refunds
- get checkout session
- get dispute
- list stripe refunds
- list stripe payment disputes (chargebacks)
- fintech
- confirm a payment intent
- cancel payment intent
- create a new stripe payment intent for collecting payment
- hosted checkout sessions
- create payment intent
- checkout
- retrieve a stripe payment intent by id
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stripe Payment Processing\"\n  description: >-\n    Unified capability for end-to-end payment processing workflows. Combines Stripe Payment Intents\n    and Checkout APIs to support payment creation, confirmation, capture, refunds, and dispute management.\n    Used by e-commerce platforms, SaaS billing teams, and payment operations engineers.\n  tags:\n    - Stripe\n    - Payments\n    - Checkout\n    - Refunds\n    - Disputes\n    - E-Commerce\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STRIPE_API_KEY: STRIPE_API_KEY\n\ncapability:\n  consumes:\n    - import: stripe-payment-intents\n      location: ./shared/payment-intents.yaml\n    - import: stripe-checkout\n      location: ./shared/checkout.yaml\n    - import: stripe-refunds\n      location: ./shared/refunds.yaml\n    - import: stripe-disputes\n      location: ./shared/disputes.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: stripe-payment-processing-api\n      description: \"Unified REST API for Stripe payment processing workflows.\"\n      resources:\n        - path: /v1/payment-intents\n          name: payment-intents\n          description: \"Manage payment intents for custom payment flows\"\n          operations:\n            - method: GET\n              name: list-payment-intents\n              description: \"List payment intents\"\n              call: \"stripe-payment-intents.list-payment-intents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment-intent\n              description: \"Create a payment intent\"\n              call: \"stripe-payment-intents.create-payment-intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payment-intents/{intent}\n          name: payment-intent\n\
  \          description: \"Individual payment intent\"\n          operations:\n            - method: GET\n              name: get-payment-intent\n              description: \"Get a payment intent\"\n              call: \"stripe-payment-intents.get-payment-intent\"\n              with:\n                intent: \"rest.intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payment-intents/{intent}/confirm\n          name: payment-intent-confirm\n          description: \"Confirm a payment intent\"\n          operations:\n            - method: POST\n              name: confirm-payment-intent\n              description: \"Confirm payment intent\"\n              call: \"stripe-payment-intents.confirm-payment-intent\"\n              with:\n                intent: \"rest.intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payment-intents/{intent}/capture\n\
  \          name: payment-intent-capture\n          description: \"Capture payment funds\"\n          operations:\n            - method: POST\n              name: capture-payment-intent\n              description: \"Capture authorized payment\"\n              call: \"stripe-payment-intents.capture-payment-intent\"\n              with:\n                intent: \"rest.intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/checkout-sessions\n          name: checkout-sessions\n          description: \"Hosted checkout sessions\"\n          operations:\n            - method: GET\n              name: list-checkout-sessions\n              description: \"List checkout sessions\"\n              call: \"stripe-checkout.list-checkout-sessions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-checkout-session\n        \
  \      description: \"Create a hosted checkout session\"\n              call: \"stripe-checkout.create-checkout-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/refunds\n          name: refunds\n          description: \"Payment refunds\"\n          operations:\n            - method: GET\n              name: list-refunds\n              description: \"List refunds\"\n              call: \"stripe-refunds.list-refunds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-refund\n              description: \"Create a refund\"\n              call: \"stripe-refunds.create-refund\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes\n          name: disputes\n          description: \"Payment disputes and chargebacks\"\n          operations:\n\
  \            - method: GET\n              name: list-disputes\n              description: \"List disputes\"\n              call: \"stripe-disputes.list-disputes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/{dispute}\n          name: dispute\n          description: \"Individual dispute\"\n          operations:\n            - method: GET\n              name: get-dispute\n              description: \"Get a dispute\"\n              call: \"stripe-disputes.get-dispute\"\n              with:\n                dispute: \"rest.dispute\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: stripe-payment-processing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Stripe payment processing workflows.\"\n      tools:\n        - name: list-payment-intents\n          description: \"List\
  \ Stripe payment intents with optional filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stripe-payment-intents.list-payment-intents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-payment-intent\n          description: \"Create a new Stripe payment intent for collecting payment\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-payment-intents.create-payment-intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment-intent\n          description: \"Retrieve a Stripe payment intent by ID\"\n          hints:\n            readOnly: true\n          call: \"stripe-payment-intents.get-payment-intent\"\n          with:\n            intent: \"tools.intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: confirm-payment-intent\n          description: \"Confirm a Stripe payment intent to execute the payment\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-payment-intents.confirm-payment-intent\"\n          with:\n            intent: \"tools.intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: capture-payment-intent\n          description: \"Capture authorized funds for a Stripe payment intent\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-payment-intents.capture-payment-intent\"\n          with:\n            intent: \"tools.intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-payment-intent\n          description: \"Cancel an uncaptured Stripe payment intent\"\n          hints:\n            readOnly: false\n            destructive: true\n\
  \          call: \"stripe-payment-intents.cancel-payment-intent\"\n          with:\n            intent: \"tools.intent\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-checkout-session\n          description: \"Create a Stripe hosted checkout page for payment collection\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-checkout.create-checkout-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-checkout-session\n          description: \"Retrieve details of a Stripe checkout session\"\n          hints:\n            readOnly: true\n          call: \"stripe-checkout.get-checkout-session\"\n          with:\n            session: \"tools.session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-refund\n          description: \"Create a refund\
  \ on a Stripe charge or payment intent\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-refunds.create-refund\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-refunds\n          description: \"List Stripe refunds\"\n          hints:\n            readOnly: true\n          call: \"stripe-refunds.list-refunds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-disputes\n          description: \"List Stripe payment disputes (chargebacks)\"\n          hints:\n            readOnly: true\n          call: \"stripe-disputes.list-disputes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dispute\n          description: \"Get details of a specific Stripe dispute\"\n          hints:\n            readOnly: true\n          call: \"stripe-disputes.get-dispute\"\n\
  \          with:\n            dispute: \"tools.dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-dispute\n          description: \"Update evidence for a Stripe dispute to contest a chargeback\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-disputes.update-dispute\"\n          with:\n            dispute: \"tools.dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stripe/refs/heads/main/capabilities/payment-processing.yaml
tags:
- Stripe
- Payments
- Checkout
- Refunds
- Disputes
- E-Commerce
tools:
- description: List Stripe payment intents with optional filters
  hints:
    openWorld: true
    readOnly: true
  name: list-payment-intents
- description: Create a new Stripe payment intent for collecting payment
  hints:
    destructive: false
    readOnly: false
  name: create-payment-intent
- description: Retrieve a Stripe payment intent by ID
  hints:
    readOnly: true
  name: get-payment-intent
- description: Confirm a Stripe payment intent to execute the payment
  hints:
    destructive: false
    readOnly: false
  name: confirm-payment-intent
- description: Capture authorized funds for a Stripe payment intent
  hints:
    destructive: false
    readOnly: false
  name: capture-payment-intent
- description: Cancel an uncaptured Stripe payment intent
  hints:
    destructive: true
    readOnly: false
  name: cancel-payment-intent
- description: Create a Stripe hosted checkout page for payment collection
  hints:
    destructive: false
    readOnly: false
  name: create-checkout-session
- description: Retrieve details of a Stripe checkout session
  hints:
    readOnly: true
  name: get-checkout-session
- description: Create a refund on a Stripe charge or payment intent
  hints:
    destructive: false
    readOnly: false
  name: create-refund
- description: List Stripe refunds
  hints:
    readOnly: true
  name: list-refunds
- description: List Stripe payment disputes (chargebacks)
  hints:
    readOnly: true
  name: list-disputes
- description: Get details of a specific Stripe dispute
  hints:
    readOnly: true
  name: get-dispute
- description: Update evidence for a Stripe dispute to contest a chargeback
  hints:
    destructive: false
    readOnly: false
  name: update-dispute
---
