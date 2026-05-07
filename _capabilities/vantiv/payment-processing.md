---
categories: []
consumed_apis: []
description: Unified payment processing workflow combining Vantiv's eCommerce CNP API and chargeback management. Designed for merchants processing online card payments, managing refunds, tokenizing card data for recurring billing, and defending chargeback disputes.
layout: capability
name: Vantiv Payment Processing
operations:
- description: Authorize a card and hold funds
  method: POST
  name: create-authorization
  path: /v1/payments/authorizations
- description: Process a card sale (authorize and capture)
  method: POST
  name: create-sale
  path: /v1/payments/sales
- description: Capture an authorized transaction for settlement
  method: POST
  name: create-capture
  path: /v1/payments/captures
- description: Issue a refund to a cardholder
  method: POST
  name: create-credit
  path: /v1/payments/credits
- description: Cancel a pending unsettled transaction
  method: POST
  name: create-void
  path: /v1/payments/voids
- description: Tokenize a card number for secure storage
  method: POST
  name: register-token
  path: /v1/tokens
- description: Process a recurring billing charge
  method: POST
  name: create-recurring-transaction
  path: /v1/payments/recurring
- description: Process an ACH bank payment
  method: POST
  name: create-echeck-sale
  path: /v1/payments/echeck
personas: []
provider_name: Vantiv
provider_slug: vantiv
search_terms:
- ach/echeck payments
- process a card sale (authorize and capture)
- process a recurring billing charge against a stored card token
- create capture
- authorize a credit card payment to verify funds availability
- refund management
- cancel a pending transaction before it settles
- process echeck payment
- create credit
- chargebacks
- capture an authorized transaction for settlement
- ecommerce
- void payment
- vantiv
- create echeck sale
- create authorization
- fintech
- capture payment
- create recurring transaction
- register token
- finance
- tokenize a card number for secure storage
- payment processing
- process an ach/echeck payment using bank account details
- process recurring charge
- process sale
- tokenize card
- create sale
- tokenize a card number for secure storage and future transactions
- authorize a card and hold funds
- capture authorized funds
- issue a refund to a cardholder
- create void
- authorize card
- card authorization management
- payments
- cancel a pending unsettled transaction
- void pending transactions
- process an ach bank payment
- process a complete card sale (authorization and capture in one step)
- capture a previously authorized payment to initiate settlement
- card tokenization via vault
- refund payment
- issue a full or partial refund to a cardholder
- recurring billing transactions
- card sale transactions
- process a recurring billing charge
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vantiv Payment Processing\n  description: Unified payment processing workflow combining Vantiv's eCommerce CNP API and chargeback management. Designed\n    for merchants processing online card payments, managing refunds, tokenizing card data for recurring billing, and defending\n    chargeback disputes.\n  tags:\n  - Vantiv\n  - Payments\n  - Payment Processing\n  - eCommerce\n  - Finance\n  - Chargebacks\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VANTIV_MERCHANT_ID: VANTIV_MERCHANT_ID\n    VANTIV_USERNAME: VANTIV_USERNAME\n    VANTIV_PASSWORD: VANTIV_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: vantiv-cnp\n    baseUri: https://payments.vantivcnp.com/vap/communicator/online\n    description: Vantiv eCommerce payment processing\n    authentication:\n      type: basic\n      username: '{{VANTIV_USERNAME}}'\n      password: '{{VANTIV_PASSWORD}}'\n    resources:\n    - name:\
  \ authorization\n      path: /authorization\n      description: Card authorization transactions\n      operations:\n      - name: create-authorization\n        method: POST\n        description: Authorize a card to verify funds and place a hold\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sale\n      path: /sale\n      description: Combined authorization and capture\n      operations:\n      - name: create-sale\n        method: POST\n        description: Process a card sale (authorize and capture in one step)\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: capture\n      path: /capture\n      description: Capture authorized transactions\n      operations:\n      - name: create-capture\n        method: POST\n        description: Capture a previously authorized transaction for settlement\n        outputRawFormat:\
  \ xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credit\n      path: /credit\n      description: Refund transactions\n      operations:\n      - name: create-credit\n        method: POST\n        description: Issue a refund to a cardholder\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: void\n      path: /void\n      description: Void pending transactions\n      operations:\n      - name: create-void\n        method: POST\n        description: Cancel a pending unsettled transaction\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token\n      path: /registerTokenRequest\n      description: Card tokenization\n      operations:\n      - name: register-token\n        method: POST\n        description: Tokenize a card number via Vantiv Vault\n   \
  \     outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recurring\n      path: /recurringTransaction\n      description: Recurring billing transactions\n      operations:\n      - name: create-recurring-transaction\n        method: POST\n        description: Process a recurring billing charge against a stored token\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: echeck-sale\n      path: /echeckSale\n      description: ACH/eCheck payment processing\n      operations:\n      - name: create-echeck-sale\n        method: POST\n        description: Process an ACH/eCheck bank payment\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vantiv-payments-api\n    description: Unified REST API for\
  \ Vantiv payment processing workflows.\n    resources:\n    - path: /v1/payments/authorizations\n      name: authorizations\n      description: Card authorization management\n      operations:\n      - method: POST\n        name: create-authorization\n        description: Authorize a card and hold funds\n        call: vantiv-cnp.create-authorization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/sales\n      name: sales\n      description: Card sale transactions\n      operations:\n      - method: POST\n        name: create-sale\n        description: Process a card sale (authorize and capture)\n        call: vantiv-cnp.create-sale\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/captures\n      name: captures\n      description: Capture authorized funds\n      operations:\n      - method: POST\n        name: create-capture\n        description: Capture an authorized transaction for settlement\n\
  \        call: vantiv-cnp.create-capture\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/credits\n      name: credits\n      description: Refund management\n      operations:\n      - method: POST\n        name: create-credit\n        description: Issue a refund to a cardholder\n        call: vantiv-cnp.create-credit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/voids\n      name: voids\n      description: Void pending transactions\n      operations:\n      - method: POST\n        name: create-void\n        description: Cancel a pending unsettled transaction\n        call: vantiv-cnp.create-void\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: Card tokenization via Vault\n      operations:\n      - method: POST\n        name: register-token\n        description: Tokenize a card number for secure\
  \ storage\n        call: vantiv-cnp.register-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/recurring\n      name: recurring\n      description: Recurring billing transactions\n      operations:\n      - method: POST\n        name: create-recurring-transaction\n        description: Process a recurring billing charge\n        call: vantiv-cnp.create-recurring-transaction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/echeck\n      name: echeck\n      description: ACH/eCheck payments\n      operations:\n      - method: POST\n        name: create-echeck-sale\n        description: Process an ACH bank payment\n        call: vantiv-cnp.create-echeck-sale\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vantiv-payments-mcp\n    transport: http\n    description: MCP server for AI-assisted payment processing and dispute\
  \ management.\n    tools:\n    - name: authorize-card\n      description: Authorize a credit card payment to verify funds availability\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.create-authorization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-sale\n      description: Process a complete card sale (authorization and capture in one step)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.create-sale\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-payment\n      description: Capture a previously authorized payment to initiate settlement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: vantiv-cnp.create-capture\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refund-payment\n   \
  \   description: Issue a full or partial refund to a cardholder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.create-credit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-payment\n      description: Cancel a pending transaction before it settles\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vantiv-cnp.create-void\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tokenize-card\n      description: Tokenize a card number for secure storage and future transactions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.register-token\n      with:\n        accountNumber: tools.cardNumber\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-recurring-charge\n      description:\
  \ Process a recurring billing charge against a stored card token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.create-recurring-transaction\n      with:\n        token: tools.token\n        amount: tools.amount\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-echeck-payment\n      description: Process an ACH/eCheck payment using bank account details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: vantiv-cnp.create-echeck-sale\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vantiv/refs/heads/main/capabilities/payment-processing.yaml
tags:
- Vantiv
- Payments
- Payment Processing
- eCommerce
- Finance
- Chargebacks
tools:
- description: Authorize a credit card payment to verify funds availability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authorize-card
- description: Process a complete card sale (authorization and capture in one step)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-sale
- description: Capture a previously authorized payment to initiate settlement
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: capture-payment
- description: Issue a full or partial refund to a cardholder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: refund-payment
- description: Cancel a pending transaction before it settles
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: void-payment
- description: Tokenize a card number for secure storage and future transactions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tokenize-card
- description: Process a recurring billing charge against a stored card token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-recurring-charge
- description: Process an ACH/eCheck payment using bank account details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: process-echeck-payment
---
