---
categories: []
consumed_apis: []
description: End-to-end payment processing on Shift4. Combines charges, refunds, checkout sessions, and disputes for e-commerce and merchant operations workflows.
layout: capability
name: Shift4 Payment Processing
operations:
- description: ''
  method: GET
  name: list-charges
  path: /charges
- description: ''
  method: POST
  name: create-charge
  path: /charges
- description: ''
  method: POST
  name: capture-charge
  path: /charges/{charge}/capture
- description: ''
  method: POST
  name: create-refund
  path: /refunds
- description: ''
  method: POST
  name: create-checkout-session
  path: /checkout/sessions
- description: ''
  method: GET
  name: list-disputes
  path: /disputes
personas: []
provider_name: Shift4 Payments
provider_slug: shift4-payments
search_terms:
- list shift4 disputes.
- e-commerce
- create checkout session
- commerce
- refund a shift4 charge.
- capture a previously authorized shift4 charge.
- list disputes
- create a shift4 hosted checkout session.
- capture charge
- create refund
- refunds
- shift4
- disputes
- checkout
- payments
- create charge
- create a shift4 charge against a card or token.
- list charges
- fintech
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shift4 Payment Processing\n  description: End-to-end payment processing on Shift4. Combines charges, refunds, checkout sessions, and disputes for e-commerce\n    and merchant operations workflows.\n  tags:\n  - Shift4\n  - Payments\n  - Checkout\n  - Refunds\n  - Disputes\n  - E-Commerce\n  created: '2026-05-05'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHIFT4_API_KEY: SHIFT4_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: shift4-charges\n    baseUri: https://api.shift4.com\n    description: Shift4 Charges API for processing card and payment-method charges.\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: charges\n      path: /charges\n      description: Charges collection.\n      operations:\n      - name: list-charges\n        method: GET\n        description: List charges.\n        inputParameters:\n        - name:\
  \ limit\n          in: query\n          type: integer\n          required: false\n        - name: startingAfter\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-charge\n        method: POST\n        description: Create a new charge.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            card: '{{tools.card}}'\n            description: '{{tools.description}}'\n    - name: charge\n      path: /charges/{charge}\n      description: Individual charge resource.\n      operations:\n      - name: get-charge\n        method: GET\n        description: Retrieve a charge by ID.\n        inputParameters:\n    \
  \    - name: charge\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-charge\n        method: POST\n        description: Update a charge.\n        inputParameters:\n        - name: charge\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-capture\n      path: /charges/{charge}/capture\n      description: Capture an authorized charge.\n      operations:\n      - name: capture-charge\n        method: POST\n        description: Capture a previously authorized charge.\n        inputParameters:\n        - name: charge\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  - type: http\n    namespace: shift4-refunds\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: refunds\n      path: /refunds\n      operations:\n      - name: list-refunds\n        method: GET\n        description: List refunds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-refund\n        method: POST\n        description: Refund a charge.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            chargeId: '{{tools.chargeId}}'\n            amount: '{{tools.amount}}'\n            reason: '{{tools.reason}}'\n    - name: refund\n      path: /refunds/{refund}\n      operations:\n      - name: get-refund\n\
  \        method: GET\n        description: Retrieve a refund by ID.\n        inputParameters:\n        - name: refund\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: shift4-checkout\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: checkout-sessions\n      path: /checkout/sessions\n      operations:\n      - name: create-checkout-session\n        method: POST\n        description: Create a checkout session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: checkout-session\n      path: /checkout/sessions/{session}\n      operations:\n      - name: get-checkout-session\n        method: GET\n        description:\
  \ Retrieve a checkout session by ID.\n        inputParameters:\n        - name: session\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-links\n      path: /payment-links\n      operations:\n      - name: create-payment-link\n        method: POST\n        description: Create a payment link.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-link\n      path: /payment-links/{link}\n      operations:\n      - name: get-payment-link\n        method: GET\n        description: Retrieve a payment link by ID.\n        inputParameters:\n        - name: link\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  - type: http\n    namespace: shift4-disputes\n    baseUri: https://api.shift4.com\n    authentication:\n      type: basic\n      username: '{{SHIFT4_API_KEY}}'\n      password: ''\n    resources:\n    - name: disputes\n      path: /disputes\n      operations:\n      - name: list-disputes\n        method: GET\n        description: List disputes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dispute\n      path: /disputes/{dispute}\n      operations:\n      - name: get-dispute\n        method: GET\n        description: Retrieve a dispute by ID.\n        inputParameters:\n        - name: dispute\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fraud-warnings\n      path: /fraud-warnings\n      operations:\n      -\
  \ name: list-fraud-warnings\n        method: GET\n        description: List fraud warnings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shift4-payment-processing-api\n    description: Unified REST surface for Shift4 payment workflows.\n    resources:\n    - path: /charges\n      name: charges\n      operations:\n      - method: GET\n        name: list-charges\n        call: shift4-charges.list-charges\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-charge\n        call: shift4-charges.create-charge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charges/{charge}/capture\n      name: charge-capture\n      operations:\n      - method: POST\n        name: capture-charge\n        call: shift4-charges.capture-charge\n        with:\n         \
  \ charge: rest.charge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /refunds\n      name: refunds\n      operations:\n      - method: POST\n        name: create-refund\n        call: shift4-refunds.create-refund\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /checkout/sessions\n      name: checkout-sessions\n      operations:\n      - method: POST\n        name: create-checkout-session\n        call: shift4-checkout.create-checkout-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /disputes\n      name: disputes\n      operations:\n      - method: GET\n        name: list-disputes\n        call: shift4-disputes.list-disputes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: shift4-payment-processing-mcp\n    transport: http\n    description: MCP surface for AI-assisted Shift4 payment workflows.\n\
  \    tools:\n    - name: create-charge\n      description: Create a Shift4 charge against a card or token.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-charges.create-charge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-charge\n      description: Capture a previously authorized Shift4 charge.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-charges.capture-charge\n      with:\n        charge: tools.charge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-refund\n      description: Refund a Shift4 charge.\n      hints:\n        readOnly: false\n        destructive: false\n      call: shift4-refunds.create-refund\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-checkout-session\n      description: Create a Shift4 hosted checkout session.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n      call: shift4-checkout.create-checkout-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-disputes\n      description: List Shift4 disputes.\n      hints:\n        readOnly: true\n      call: shift4-disputes.list-disputes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shift4-payments/refs/heads/main/capabilities/payment-processing.yaml
tags:
- Shift4
- Payments
- Checkout
- Refunds
- Disputes
- E-Commerce
tools:
- description: Create a Shift4 charge against a card or token.
  hints:
    destructive: false
    readOnly: false
  name: create-charge
- description: Capture a previously authorized Shift4 charge.
  hints:
    destructive: false
    readOnly: false
  name: capture-charge
- description: Refund a Shift4 charge.
  hints:
    destructive: false
    readOnly: false
  name: create-refund
- description: Create a Shift4 hosted checkout session.
  hints:
    destructive: false
    readOnly: false
  name: create-checkout-session
- description: List Shift4 disputes.
  hints:
    readOnly: true
  name: list-disputes
---
