---
categories: []
consumed_apis: []
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
- disputes
- cancel payment intent
- retrieve details of a stripe checkout session
- update dispute
- get dispute
- confirm payment intent
- capture authorized funds for a stripe payment intent
- checkout
- individual payment intent
- individual dispute
- create a refund
- fintech
- create a stripe hosted checkout page for payment collection
- get payment intent
- list stripe payment intents with optional filters
- get checkout session
- payment refunds
- list disputes
- capture payment funds
- confirm a stripe payment intent to execute the payment
- financial services
- get details of a specific stripe dispute
- t1
- e-commerce
- create refund
- create a payment intent
- get a payment intent
- payment disputes and chargebacks
- list stripe refunds
- stripe
- list payment intents
- capture payment intent
- create a new stripe payment intent for collecting payment
- list stripe payment disputes (chargebacks)
- refunds
- create checkout session
- manage payment intents for custom payment flows
- get a dispute
- update evidence for a stripe dispute to contest a chargeback
- retrieve a stripe payment intent by id
- create a refund on a stripe charge or payment intent
- create a hosted checkout session
- list refunds
- confirm a payment intent
- list checkout sessions
- cancel an uncaptured stripe payment intent
- payments
- capture authorized payment
- hosted checkout sessions
- create payment intent
- commerce
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stripe Payment Processing\n  description: Unified capability for end-to-end payment processing workflows. Combines Stripe Payment Intents and Checkout\n    APIs to support payment creation, confirmation, capture, refunds, and dispute management. Used by e-commerce platforms,\n    SaaS billing teams, and payment operations engineers.\n  tags:\n  - Stripe\n  - Payments\n  - Checkout\n  - Refunds\n  - Disputes\n  - E-Commerce\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STRIPE_API_KEY: STRIPE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stripe-payment-intents\n    baseUri: https://api.stripe.com\n    description: Stripe Payment Intents API for creating and managing payment flows.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: payment-intents\n      path: /v1/payment_intents\n      description: Payment intent collection\
  \ operations\n      operations:\n      - name: list-payment-intents\n        method: GET\n        description: List all payment intents\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        - name: customer\n          in: query\n          type: string\n          required: false\n          description: Filter by customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-intent\n        method: POST\n        description: Create a new payment intent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            customer: '{{tools.customer}}'\n\
  \    - name: payment-intent-search\n      path: /v1/payment_intents/search\n      description: Search payment intents\n      operations:\n      - name: search-payment-intents\n        method: GET\n        description: Search payment intents by query string\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-intent\n      path: /v1/payment_intents/{intent}\n      description: Individual payment intent operations\n      operations:\n      - name: get-payment-intent\n        method: GET\n        description: Retrieve a payment intent by ID\n        inputParameters:\n        - name: intent\n          in: path\n          type: string\n          required: true\n          description: Payment intent ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-payment-intent\n        method: POST\n        description: Update a payment intent\n        inputParameters:\n        - name: intent\n          in: path\n          type: string\n          required: true\n          description: Payment intent ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-intent-confirm\n      path: /v1/payment_intents/{intent}/confirm\n      description: Confirm a payment intent\n      operations:\n      - name: confirm-payment-intent\n        method: POST\n        description: Confirm a payment intent to execute the payment\n        inputParameters:\n        - name: intent\n          in: path\n          type: string\n          required: true\n          description: Payment intent ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: payment-intent-capture\n      path: /v1/payment_intents/{intent}/capture\n      description: Capture an authorized payment intent\n      operations:\n      - name: capture-payment-intent\n        method: POST\n        description: Capture funds for an authorized payment intent\n        inputParameters:\n        - name: intent\n          in: path\n          type: string\n          required: true\n          description: Payment intent ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-intent-cancel\n      path: /v1/payment_intents/{intent}/cancel\n      description: Cancel a payment intent\n      operations:\n      - name: cancel-payment-intent\n        method: POST\n        description: Cancel a payment intent that has not been captured\n        inputParameters:\n        - name: intent\n          in: path\n          type: string\n          required:\
  \ true\n          description: Payment intent ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-checkout\n    baseUri: https://api.stripe.com\n    description: Stripe Checkout API for hosted and embedded payment pages.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: checkout-sessions\n      path: /v1/checkout/sessions\n      description: Checkout session collection\n      operations:\n      - name: list-checkout-sessions\n        method: GET\n        description: List all checkout sessions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-checkout-session\n\
  \        method: POST\n        description: Create a new checkout session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            success_url: '{{tools.success_url}}'\n            cancel_url: '{{tools.cancel_url}}'\n            mode: '{{tools.mode}}'\n    - name: checkout-session\n      path: /v1/checkout/sessions/{session}\n      description: Individual checkout session\n      operations:\n      - name: get-checkout-session\n        method: GET\n        description: Retrieve a checkout session by ID\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n          description: Checkout session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout-session-expire\n      path: /v1/checkout/sessions/{session}/expire\n\
  \      description: Expire a checkout session\n      operations:\n      - name: expire-checkout-session\n        method: POST\n        description: Expire a checkout session before it naturally expires\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n          description: Checkout session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout-session-line-items\n      path: /v1/checkout/sessions/{session}/line_items\n      description: Line items for a checkout session\n      operations:\n      - name: list-checkout-session-line-items\n        method: GET\n        description: List line items for a checkout session\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n          description: Checkout session ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-refunds\n    baseUri: https://api.stripe.com\n    description: Stripe Refunds API for managing charge reversals.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: refunds\n      path: /v1/refunds\n      description: Refund collection\n      operations:\n      - name: list-refunds\n        method: GET\n        description: List all refunds\n        inputParameters:\n        - name: charge\n          in: query\n          type: string\n          required: false\n          description: Filter by charge ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-refund\n        method: POST\n        description:\
  \ Create a refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            charge: '{{tools.charge}}'\n            amount: '{{tools.amount}}'\n    - name: refund\n      path: /v1/refunds/{refund}\n      description: Individual refund\n      operations:\n      - name: get-refund\n        method: GET\n        description: Retrieve a refund by ID\n        inputParameters:\n        - name: refund\n          in: path\n          type: string\n          required: true\n          description: Refund ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refund-cancel\n      path: /v1/refunds/{refund}/cancel\n      description: Cancel a refund\n      operations:\n      - name: cancel-refund\n        method: POST\n        description: Cancel a pending refund\n        inputParameters:\n\
  \        - name: refund\n          in: path\n          type: string\n          required: true\n          description: Refund ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-disputes\n    baseUri: https://api.stripe.com\n    description: Stripe Disputes API for managing chargebacks.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: disputes\n      path: /v1/disputes\n      description: Dispute collection\n      operations:\n      - name: list-disputes\n        method: GET\n        description: List all disputes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: charge\n          in: query\n          type: string\n          required: false\n          description: Filter by charge ID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute\n      path: /v1/disputes/{dispute}\n      description: Individual dispute\n      operations:\n      - name: get-dispute\n        method: GET\n        description: Retrieve a dispute by ID\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dispute\n        method: POST\n        description: Update dispute evidence\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: dispute-close\n      path: /v1/disputes/{dispute}/close\n      description: Close a dispute\n      operations:\n      - name: close-dispute\n        method: POST\n        description: Close a dispute by accepting the chargeback\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n          description: Dispute ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stripe-payment-processing-api\n    description: Unified REST API for Stripe payment processing workflows.\n    resources:\n    - path: /v1/payment-intents\n      name: payment-intents\n      description: Manage payment intents for custom payment flows\n      operations:\n      - method: GET\n        name: list-payment-intents\n        description: List payment intents\n        call: stripe-payment-intents.list-payment-intents\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment-intent\n        description: Create a payment intent\n        call: stripe-payment-intents.create-payment-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-intents/{intent}\n      name: payment-intent\n      description: Individual payment intent\n      operations:\n      - method: GET\n        name: get-payment-intent\n        description: Get a payment intent\n        call: stripe-payment-intents.get-payment-intent\n        with:\n          intent: rest.intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-intents/{intent}/confirm\n      name: payment-intent-confirm\n      description: Confirm a payment intent\n      operations:\n      - method: POST\n        name: confirm-payment-intent\n        description: Confirm payment intent\n        call: stripe-payment-intents.confirm-payment-intent\n\
  \        with:\n          intent: rest.intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-intents/{intent}/capture\n      name: payment-intent-capture\n      description: Capture payment funds\n      operations:\n      - method: POST\n        name: capture-payment-intent\n        description: Capture authorized payment\n        call: stripe-payment-intents.capture-payment-intent\n        with:\n          intent: rest.intent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checkout-sessions\n      name: checkout-sessions\n      description: Hosted checkout sessions\n      operations:\n      - method: GET\n        name: list-checkout-sessions\n        description: List checkout sessions\n        call: stripe-checkout.list-checkout-sessions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-checkout-session\n        description:\
  \ Create a hosted checkout session\n        call: stripe-checkout.create-checkout-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refunds\n      name: refunds\n      description: Payment refunds\n      operations:\n      - method: GET\n        name: list-refunds\n        description: List refunds\n        call: stripe-refunds.list-refunds\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-refund\n        description: Create a refund\n        call: stripe-refunds.create-refund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disputes\n      name: disputes\n      description: Payment disputes and chargebacks\n      operations:\n      - method: GET\n        name: list-disputes\n        description: List disputes\n        call: stripe-disputes.list-disputes\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/disputes/{dispute}\n      name: dispute\n      description: Individual dispute\n      operations:\n      - method: GET\n        name: get-dispute\n        description: Get a dispute\n        call: stripe-disputes.get-dispute\n        with:\n          dispute: rest.dispute\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: stripe-payment-processing-mcp\n    transport: http\n    description: MCP server for AI-assisted Stripe payment processing workflows.\n    tools:\n    - name: list-payment-intents\n      description: List Stripe payment intents with optional filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stripe-payment-intents.list-payment-intents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment-intent\n      description: Create a new Stripe payment intent for collecting payment\n      hints:\n        readOnly: false\n\
  \        destructive: false\n      call: stripe-payment-intents.create-payment-intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payment-intent\n      description: Retrieve a Stripe payment intent by ID\n      hints:\n        readOnly: true\n      call: stripe-payment-intents.get-payment-intent\n      with:\n        intent: tools.intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: confirm-payment-intent\n      description: Confirm a Stripe payment intent to execute the payment\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-payment-intents.confirm-payment-intent\n      with:\n        intent: tools.intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-payment-intent\n      description: Capture authorized funds for a Stripe payment intent\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-payment-intents.capture-payment-intent\n\
  \      with:\n        intent: tools.intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-payment-intent\n      description: Cancel an uncaptured Stripe payment intent\n      hints:\n        readOnly: false\n        destructive: true\n      call: stripe-payment-intents.cancel-payment-intent\n      with:\n        intent: tools.intent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-checkout-session\n      description: Create a Stripe hosted checkout page for payment collection\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-checkout.create-checkout-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-checkout-session\n      description: Retrieve details of a Stripe checkout session\n      hints:\n        readOnly: true\n      call: stripe-checkout.get-checkout-session\n      with:\n        session: tools.session\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-refund\n      description: Create a refund on a Stripe charge or payment intent\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-refunds.create-refund\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-refunds\n      description: List Stripe refunds\n      hints:\n        readOnly: true\n      call: stripe-refunds.list-refunds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-disputes\n      description: List Stripe payment disputes (chargebacks)\n      hints:\n        readOnly: true\n      call: stripe-disputes.list-disputes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dispute\n      description: Get details of a specific Stripe dispute\n      hints:\n        readOnly: true\n      call: stripe-disputes.get-dispute\n      with:\n        dispute: tools.dispute\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: update-dispute\n      description: Update evidence for a Stripe dispute to contest a chargeback\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-disputes.update-dispute\n      with:\n        dispute: tools.dispute\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
