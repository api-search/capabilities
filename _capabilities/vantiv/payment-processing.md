---
api_specs:
- filename: vantiv-cnp-openapi.yml
  format: yaml
  label: vantiv-cnp
  slug: vantiv-cnp
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vantiv/refs/heads/main/openapi/vantiv-cnp-openapi.yml
categories: []
consumed_apis:
- vantiv-cnp
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
- capture a previously authorized payment to initiate settlement
- tokenize a card number for secure storage and future transactions
- process an ach/echeck payment using bank account details
- tokenize a card number for secure storage
- process a recurring billing charge against a stored card token
- create recurring transaction
- process a complete card sale (authorization and capture in one step)
- process echeck payment
- card authorization management
- authorize card
- vantiv
- register token
- create capture
- process sale
- tokenize card
- capture an authorized transaction for settlement
- chargebacks
- authorize a card and hold funds
- cancel a pending unsettled transaction
- capture payment
- issue a full or partial refund to a cardholder
- recurring billing transactions
- card tokenization via vault
- create authorization
- create credit
- process a recurring billing charge
- payments
- card sale transactions
- finance
- authorize a credit card payment to verify funds availability
- process a card sale (authorize and capture)
- capture authorized funds
- create void
- process an ach bank payment
- void payment
- ach/echeck payments
- refund management
- void pending transactions
- refund payment
- ecommerce
- process recurring charge
- issue a refund to a cardholder
- create sale
- create echeck sale
- fintech
- cancel a pending transaction before it settles
- payment processing
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vantiv Payment Processing\"\n  description: >-\n    Unified payment processing workflow combining Vantiv's eCommerce CNP API and chargeback\n    management. Designed for merchants processing online card payments, managing refunds,\n    tokenizing card data for recurring billing, and defending chargeback disputes.\n  tags:\n    - Vantiv\n    - Payments\n    - Payment Processing\n    - eCommerce\n    - Finance\n    - Chargebacks\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VANTIV_MERCHANT_ID: VANTIV_MERCHANT_ID\n      VANTIV_USERNAME: VANTIV_USERNAME\n      VANTIV_PASSWORD: VANTIV_PASSWORD\n\ncapability:\n  consumes:\n    - import: vantiv-cnp\n      location: ./shared/vantiv-cnp.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vantiv-payments-api\n      description: \"Unified REST API for Vantiv payment processing workflows.\"\n      resources:\n  \
  \      - path: /v1/payments/authorizations\n          name: authorizations\n          description: \"Card authorization management\"\n          operations:\n            - method: POST\n              name: create-authorization\n              description: \"Authorize a card and hold funds\"\n              call: \"vantiv-cnp.create-authorization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/sales\n          name: sales\n          description: \"Card sale transactions\"\n          operations:\n            - method: POST\n              name: create-sale\n              description: \"Process a card sale (authorize and capture)\"\n              call: \"vantiv-cnp.create-sale\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/captures\n          name: captures\n          description: \"Capture authorized funds\"\n          operations:\n\
  \            - method: POST\n              name: create-capture\n              description: \"Capture an authorized transaction for settlement\"\n              call: \"vantiv-cnp.create-capture\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/credits\n          name: credits\n          description: \"Refund management\"\n          operations:\n            - method: POST\n              name: create-credit\n              description: \"Issue a refund to a cardholder\"\n              call: \"vantiv-cnp.create-credit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/voids\n          name: voids\n          description: \"Void pending transactions\"\n          operations:\n            - method: POST\n              name: create-void\n              description: \"Cancel a pending unsettled transaction\"\n              call: \"\
  vantiv-cnp.create-void\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens\n          name: tokens\n          description: \"Card tokenization via Vault\"\n          operations:\n            - method: POST\n              name: register-token\n              description: \"Tokenize a card number for secure storage\"\n              call: \"vantiv-cnp.register-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/recurring\n          name: recurring\n          description: \"Recurring billing transactions\"\n          operations:\n            - method: POST\n              name: create-recurring-transaction\n              description: \"Process a recurring billing charge\"\n              call: \"vantiv-cnp.create-recurring-transaction\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/payments/echeck\n          name: echeck\n          description: \"ACH/eCheck payments\"\n          operations:\n            - method: POST\n              name: create-echeck-sale\n              description: \"Process an ACH bank payment\"\n              call: \"vantiv-cnp.create-echeck-sale\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vantiv-payments-mcp\n      transport: http\n      description: \"MCP server for AI-assisted payment processing and dispute management.\"\n      tools:\n        - name: authorize-card\n          description: \"Authorize a credit card payment to verify funds availability\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.create-authorization\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: process-sale\n          description: \"Process a complete card sale (authorization and capture in one step)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.create-sale\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: capture-payment\n          description: \"Capture a previously authorized payment to initiate settlement\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"vantiv-cnp.create-capture\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: refund-payment\n          description: \"Issue a full or partial refund to a cardholder\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.create-credit\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: void-payment\n          description: \"Cancel a pending transaction before it settles\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vantiv-cnp.create-void\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tokenize-card\n          description: \"Tokenize a card number for secure storage and future transactions\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.register-token\"\n          with:\n            accountNumber: \"tools.cardNumber\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-recurring-charge\n          description: \"Process a recurring\
  \ billing charge against a stored card token\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.create-recurring-transaction\"\n          with:\n            token: \"tools.token\"\n            amount: \"tools.amount\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: process-echeck-payment\n          description: \"Process an ACH/eCheck payment using bank account details\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"vantiv-cnp.create-echeck-sale\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
