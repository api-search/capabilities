---
categories: []
consumed_apis:
- tsys-gateway
description: Unified workflow capability for merchant payment processing combining the TSYS Payment Gateway for transaction authorization, capture, void, and refund operations. Designed for merchants, ISVs, and payment facilitators requiring a complete card acceptance workflow.
layout: capability
name: TSYS Payment Processing
operations:
- description: List payment transactions
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Get transaction status
  method: GET
  name: get-transaction
  path: /v1/transactions/{transactionId}
personas: []
provider_name: Total System Services
provider_slug: total-system-services
search_terms:
- individual transaction
- get transaction status
- capture a previously authorized payment
- card issuing
- authorize a card payment without capturing funds
- authorize payment
- transaction management
- process sale
- merchant services
- list transactions
- financial services
- capture payment
- list merchant transactions with optional date and status filters
- payments
- transactions
- process a full or partial refund for a settled transaction
- get transaction
- void payment
- credit card
- refund payment
- void an authorized or captured payment before settlement
- look up the status and details of a specific transaction
- fintech
- list payment transactions
- process a complete card sale (authorization + capture)
- payment processing
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TSYS Payment Processing\"\n  description: \"Unified workflow capability for merchant payment processing combining the TSYS Payment Gateway for transaction authorization, capture, void, and refund operations. Designed for merchants, ISVs, and payment facilitators requiring a complete card acceptance workflow.\"\n  tags:\n    - Payments\n    - Payment Processing\n    - Merchant Services\n    - Transactions\n    - Credit Card\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TSYS_API_KEY: TSYS_API_KEY\n\ncapability:\n  consumes:\n    - import: tsys-gateway\n      location: ./shared/payment-gateway.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tsys-payments-api\n      description: \"Unified REST API for TSYS merchant payment processing.\"\n      resources:\n        - path: /v1/transactions\n          name: transactions\n          description: \"Transaction\
  \ management\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List payment transactions\"\n              call: \"tsys-gateway.list-transactions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions/{transactionId}\n          name: transaction\n          description: \"Individual transaction\"\n          operations:\n            - method: GET\n              name: get-transaction\n              description: \"Get transaction status\"\n              call: \"tsys-gateway.get-transaction\"\n              with:\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tsys-payments-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TSYS payment processing workflows.\"\
  \n      tools:\n        - name: authorize-payment\n          description: \"Authorize a card payment without capturing funds\"\n          hints:\n            readOnly: false\n          call: \"tsys-gateway.authorize-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-sale\n          description: \"Process a complete card sale (authorization + capture)\"\n          hints:\n            readOnly: false\n          call: \"tsys-gateway.process-sale\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: capture-payment\n          description: \"Capture a previously authorized payment\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tsys-gateway.capture-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: void-payment\n          description: \"Void an authorized or captured payment before settlement\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tsys-gateway.void-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refund-payment\n          description: \"Process a full or partial refund for a settled transaction\"\n          hints:\n            readOnly: false\n          call: \"tsys-gateway.refund-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-transaction\n          description: \"Look up the status and details of a specific transaction\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"tsys-gateway.get-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: \"List merchant transactions with optional date and status filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsys-gateway.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/total-system-services/refs/heads/main/capabilities/payment-processing.yaml
tags:
- Payments
- Payment Processing
- Merchant Services
- Transactions
- Credit Card
tools:
- description: Authorize a card payment without capturing funds
  hints:
    readOnly: false
  name: authorize-payment
- description: Process a complete card sale (authorization + capture)
  hints:
    readOnly: false
  name: process-sale
- description: Capture a previously authorized payment
  hints:
    idempotent: true
    readOnly: false
  name: capture-payment
- description: Void an authorized or captured payment before settlement
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: void-payment
- description: Process a full or partial refund for a settled transaction
  hints:
    readOnly: false
  name: refund-payment
- description: Look up the status and details of a specific transaction
  hints:
    idempotent: true
    readOnly: true
  name: get-transaction
- description: List merchant transactions with optional date and status filters
  hints:
    openWorld: true
    readOnly: true
  name: list-transactions
---
