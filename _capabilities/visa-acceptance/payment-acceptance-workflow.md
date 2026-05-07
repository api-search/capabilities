---
categories: []
consumed_apis: []
description: Workflow capability for the complete payment acceptance lifecycle on the Visa Acceptance platform. Covers merchant payment processing (authorize, capture, refund, void), invoice-based payment collection, and pay-by-link generation for online merchants, ISVs, and AI agents.
layout: capability
name: Visa Acceptance Payment Acceptance Workflow
operations:
- description: Authorize a payment transaction
  method: POST
  name: authorize-payment
  path: /v1/payments
- description: Complete a previously authorized payment
  method: POST
  name: capture-payment
  path: /v1/payments/{paymentId}/captures
- description: Refund a captured payment (partial or full)
  method: POST
  name: refund-payment
  path: /v1/payments/{paymentId}/refunds
- description: Void a payment before it settles
  method: POST
  name: void-payment
  path: /v1/payments/{paymentId}/voids
- description: Release an authorization hold
  method: POST
  name: reverse-authorization
  path: /v1/payments/{paymentId}/reversals
- description: Create an invoice for a customer
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Get invoice details
  method: GET
  name: get-invoice
  path: /v1/invoices/{invoiceId}
- description: Update a draft invoice
  method: PATCH
  name: update-invoice
  path: /v1/invoices/{invoiceId}
- description: Generate a shareable payment link
  method: POST
  name: create-pay-by-link
  path: /v1/pay-by-links
- description: List payment links
  method: GET
  name: list-pay-by-links
  path: /v1/pay-by-links
- description: Get payment link details
  method: GET
  name: get-pay-by-link
  path: /v1/pay-by-links/{linkId}
- description: Cancel a payment link
  method: DELETE
  name: cancel-pay-by-link
  path: /v1/pay-by-links/{linkId}
personas: []
provider_name: Visa Acceptance
provider_slug: visa-acceptance
search_terms:
- release an authorization hold
- release an authorization hold without completing the payment
- payment links
- invoice management
- refund a captured payment (partial or full)
- update a draft invoice
- get pay by link
- visa
- cancel a payment before it settles to release funds back to the customer
- generate a shareable payment link to collect a payment
- digital wallets
- invoice access by id
- void payment
- cancel a payment link
- get the status and details of a specific invoice
- authorize a payment to place a hold on customer funds
- generate a shareable payment link
- fintech
- authorize payment
- void a payment before it settles
- reverse authorization holds
- get invoice details
- capture payment
- complete a payment by capturing previously authorized funds
- refund captured payments
- refund a customer for a captured payment (partial or full)
- cancel an active payment link so it can no longer accept payments
- create invoice
- payment authorization and sale
- get payment link details
- e-commerce
- credit cards
- authorize a payment transaction
- payment link management
- list pay by links
- update invoice
- list payment links filtered by status
- invoicing
- payment link access by id
- create an invoice for a customer
- create an invoice with line items and due date for a customer
- payments
- capture authorized payments
- reverse authorization
- list invoices
- list payment links
- void payments before settlement
- get invoice
- create pay by link
- cancel pay by link
- refund payment
- complete a previously authorized payment
- list invoices filtered by status (created, sent, paid, etc.)
slug: payment-acceptance-workflow
source_filename: payment-acceptance-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Visa Acceptance Payment Acceptance Workflow\n  description: Workflow capability for the complete payment acceptance lifecycle on the Visa Acceptance platform. Covers merchant\n    payment processing (authorize, capture, refund, void), invoice-based payment collection, and pay-by-link generation for\n    online merchants, ISVs, and AI agents.\n  tags:\n  - Credit Cards\n  - E-Commerce\n  - Fintech\n  - Invoicing\n  - Payment Links\n  - Payments\n  - Visa\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VISA_ACCEPTANCE_JWT_TOKEN: VISA_ACCEPTANCE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: visa-acceptance-payments\n    baseUri: https://apitest.visaacceptance.com\n    description: Visa Acceptance Payments REST API\n    authentication:\n      type: bearer\n      token: '{{VISA_ACCEPTANCE_JWT_TOKEN}}'\n    resources:\n    - name: payments\n      path: /pts/v2/payments\n      description:\
  \ Payment authorization and sale\n      operations:\n      - name: authorize-payment\n        method: POST\n        description: Authorize a payment transaction\n        inputParameters:\n        - name: capture\n          in: body\n          type: boolean\n          required: false\n          description: Combine auth and capture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-captures\n      path: /pts/v2/payments/{paymentId}/captures\n      description: Capture a previously authorized payment\n      operations:\n      - name: capture-payment\n        method: POST\n        description: Capture a previously authorized payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Payment ID from authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: payment-refunds\n      path: /pts/v2/payments/{paymentId}/refunds\n      description: Refund a captured payment\n      operations:\n      - name: refund-payment\n        method: POST\n        description: Refund a captured payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Payment ID to refund\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-voids\n      path: /pts/v2/payments/{paymentId}/voids\n      description: Void a payment before settlement\n      operations:\n      - name: void-payment\n        method: POST\n        description: Void a payment transaction\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Payment ID to void\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-reversals\n      path: /pts/v2/payments/{paymentId}/reversals\n      description: Reverse an authorization\n      operations:\n      - name: reverse-authorization\n        method: POST\n        description: Reverse an authorization to release held funds\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Authorization payment ID to reverse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /pts/v2/invoices\n      description: Invoice creation and management\n      operations:\n      - name: create-invoice\n        method: POST\n        description: Create an invoice for payment collection\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: list-invoices\n        method: GET\n        description: List invoices with optional status filter\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by invoice status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice-by-id\n      path: /pts/v2/invoices/{invoiceId}\n      description: Invoice management by ID\n      operations:\n      - name: get-invoice\n        method: GET\n        description: Get invoice details by ID\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-invoice\n        method: PATCH\n        description: Update a draft invoice\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: paybylinks\n      path: /pts/v2/paybylinks\n      description: Payment link creation and management\n      operations:\n      - name: create-pay-by-link\n        method: POST\n        description: Generate a shareable payment link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-pay-by-links\n        method: GET\n        description: List payment links with optional status\
  \ filter\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by link status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: paybylink-by-id\n      path: /pts/v2/paybylinks/{linkId}\n      description: Payment link management by ID\n      operations:\n      - name: get-pay-by-link\n        method: GET\n        description: Get payment link details\n        inputParameters:\n        - name: linkId\n          in: path\n          type: string\n          required: true\n          description: Payment link ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-pay-by-link\n        method: DELETE\n        description: Cancel an active payment link\n        inputParameters:\n        - name: linkId\n         \
  \ in: path\n          type: string\n          required: true\n          description: Payment link ID to cancel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: payment-acceptance-api\n    description: Unified REST API for the Visa Acceptance payment lifecycle.\n    resources:\n    - path: /v1/payments\n      name: payments\n      description: Payment authorization and sale\n      operations:\n      - method: POST\n        name: authorize-payment\n        description: Authorize a payment transaction\n        call: visa-acceptance-payments.authorize-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}/captures\n      name: payment-captures\n      description: Capture authorized payments\n      operations:\n      - method: POST\n        name: capture-payment\n        description: Complete\
  \ a previously authorized payment\n        call: visa-acceptance-payments.capture-payment\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}/refunds\n      name: payment-refunds\n      description: Refund captured payments\n      operations:\n      - method: POST\n        name: refund-payment\n        description: Refund a captured payment (partial or full)\n        call: visa-acceptance-payments.refund-payment\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}/voids\n      name: payment-voids\n      description: Void payments before settlement\n      operations:\n      - method: POST\n        name: void-payment\n        description: Void a payment before it settles\n        call: visa-acceptance-payments.void-payment\n        with:\n          paymentId: rest.paymentId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}/reversals\n      name: payment-reversals\n      description: Reverse authorization holds\n      operations:\n      - method: POST\n        name: reverse-authorization\n        description: Release an authorization hold\n        call: visa-acceptance-payments.reverse-authorization\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: POST\n        name: create-invoice\n        description: Create an invoice for a customer\n        call: visa-acceptance-payments.create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-invoices\n        description: List invoices\n        call: visa-acceptance-payments.list-invoices\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}\n      name: invoice-by-id\n      description: Invoice access by ID\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Get invoice details\n        call: visa-acceptance-payments.get-invoice\n        with:\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-invoice\n        description: Update a draft invoice\n        call: visa-acceptance-payments.update-invoice\n        with:\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pay-by-links\n      name: pay-by-links\n      description: Payment link management\n      operations:\n      - method: POST\n        name: create-pay-by-link\n        description: Generate a shareable payment link\n        call: visa-acceptance-payments.create-pay-by-link\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-pay-by-links\n        description: List payment links\n        call: visa-acceptance-payments.list-pay-by-links\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pay-by-links/{linkId}\n      name: pay-by-link-by-id\n      description: Payment link access by ID\n      operations:\n      - method: GET\n        name: get-pay-by-link\n        description: Get payment link details\n        call: visa-acceptance-payments.get-pay-by-link\n        with:\n          linkId: rest.linkId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-pay-by-link\n        description: Cancel a payment link\n        call: visa-acceptance-payments.cancel-pay-by-link\n        with:\n          linkId: rest.linkId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: payment-acceptance-mcp\n    transport: http\n    description: MCP server for AI-assisted payment acceptance and invoice management.\n    tools:\n    - name: authorize-payment\n      description: Authorize a payment to place a hold on customer funds\n      hints:\n        readOnly: false\n        idempotent: false\n      call: visa-acceptance-payments.authorize-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-payment\n      description: Complete a payment by capturing previously authorized funds\n      hints:\n        readOnly: false\n        idempotent: true\n      call: visa-acceptance-payments.capture-payment\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: refund-payment\n      description: Refund a customer for a captured payment (partial or full)\n      hints:\n        readOnly: false\n        idempotent: false\n   \
  \   call: visa-acceptance-payments.refund-payment\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-payment\n      description: Cancel a payment before it settles to release funds back to the customer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: visa-acceptance-payments.void-payment\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reverse-authorization\n      description: Release an authorization hold without completing the payment\n      hints:\n        readOnly: false\n        idempotent: true\n      call: visa-acceptance-payments.reverse-authorization\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create an invoice with line items and due date for\
  \ a customer\n      hints:\n        readOnly: false\n        idempotent: false\n      call: visa-acceptance-payments.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List invoices filtered by status (CREATED, SENT, PAID, etc.)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visa-acceptance-payments.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Get the status and details of a specific invoice\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visa-acceptance-payments.get-invoice\n      with:\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pay-by-link\n      description: Generate a shareable payment link to collect a payment\n      hints:\n        readOnly: false\n        idempotent: false\n      call:\
  \ visa-acceptance-payments.create-pay-by-link\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pay-by-links\n      description: List payment links filtered by status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visa-acceptance-payments.list-pay-by-links\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-pay-by-link\n      description: Cancel an active payment link so it can no longer accept payments\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: visa-acceptance-payments.cancel-pay-by-link\n      with:\n        linkId: tools.linkId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/visa-acceptance/refs/heads/main/capabilities/payment-acceptance-workflow.yaml
tags:
- Credit Cards
- E-Commerce
- Fintech
- Invoicing
- Payment Links
- Payments
- Visa
tools:
- description: Authorize a payment to place a hold on customer funds
  hints:
    idempotent: false
    readOnly: false
  name: authorize-payment
- description: Complete a payment by capturing previously authorized funds
  hints:
    idempotent: true
    readOnly: false
  name: capture-payment
- description: Refund a customer for a captured payment (partial or full)
  hints:
    idempotent: false
    readOnly: false
  name: refund-payment
- description: Cancel a payment before it settles to release funds back to the customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: void-payment
- description: Release an authorization hold without completing the payment
  hints:
    idempotent: true
    readOnly: false
  name: reverse-authorization
- description: Create an invoice with line items and due date for a customer
  hints:
    idempotent: false
    readOnly: false
  name: create-invoice
- description: List invoices filtered by status (CREATED, SENT, PAID, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-invoices
- description: Get the status and details of a specific invoice
  hints:
    idempotent: true
    readOnly: true
  name: get-invoice
- description: Generate a shareable payment link to collect a payment
  hints:
    idempotent: false
    readOnly: false
  name: create-pay-by-link
- description: List payment links filtered by status
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-by-links
- description: Cancel an active payment link so it can no longer accept payments
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-pay-by-link
---
