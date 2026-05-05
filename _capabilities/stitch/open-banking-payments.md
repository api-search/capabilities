---
api_specs:
- filename: stitch-openapi.yml
  format: yaml
  label: stitch
  slug: stitch
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/stitch/refs/heads/main/openapi/stitch-openapi.yml
categories: []
consumed_apis:
- stitch
description: Unified open banking and payments workflow for African fintech applications. Combines pay-in payment initiation, bank account data access, and outbound disbursements into a single integration covering South Africa and Nigeria. Designed for e-commerce platforms, marketplaces, and financial applications that need to accept payments, access account data, and send payouts.
layout: capability
name: Stitch Open Banking and Payments
operations:
- description: Initiate a Pay By Bank payment for a customer.
  method: POST
  name: initiate-payment
  path: /v1/payments
- description: Get current status of a payment initiation request.
  method: GET
  name: get-payment-status
  path: /v1/payments/{paymentRequestId}
- description: List bank accounts linked by the user.
  method: GET
  name: list-bank-accounts
  path: /v1/bank-accounts
- description: Get transactions for a linked bank account.
  method: GET
  name: get-account-transactions
  path: /v1/bank-accounts/{accountId}/transactions
- description: Create an outbound disbursement to a bank account.
  method: POST
  name: create-disbursement
  path: /v1/disbursements
personas: []
provider_name: Stitch
provider_slug: stitch
search_terms:
- get current status of a payment initiation request.
- fintech
- open banking
- initiate payment
- payment initiation requests.
- financial data
- payment status retrieval.
- send an outbound payment disbursement to a beneficiary bank account. use for marketplace payouts, refunds, or mass payments.
- africa
- linked user bank accounts.
- check the status of a payment initiation request (pending, complete, cancelled, or error). use to poll for payment completion.
- initiate a pay by bank payment for a customer.
- retrieve transaction history for a linked bank account. supports relay-style cursor pagination via first/after parameters.
- nigeria
- get account transactions
- payments
- create disbursement
- list bank accounts linked by the user.
- unified api
- south africa
- outbound payment disbursements.
- bank account transactions.
- get transactions for a linked bank account.
- list bank accounts linked by the user. use to show available accounts for payment or data analysis.
- get payment status
- list bank accounts
- initiate a pay by bank payment in south africa or nigeria. returns a payment url to redirect the customer for bank authorization.
- create an outbound disbursement to a bank account.
slug: open-banking-payments
source_filename: open-banking-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Stitch Open Banking and Payments\n  description: >-\n    Unified open banking and payments workflow for African fintech applications.\n    Combines pay-in payment initiation, bank account data access, and outbound\n    disbursements into a single integration covering South Africa and Nigeria.\n    Designed for e-commerce platforms, marketplaces, and financial applications\n    that need to accept payments, access account data, and send payouts.\n  tags:\n    - Africa\n    - Open Banking\n    - Payments\n    - Financial Data\n    - South Africa\n    - Nigeria\n    - Fintech\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STITCH_CLIENT_ID: STITCH_CLIENT_ID\n      STITCH_CLIENT_SECRET: STITCH_CLIENT_SECRET\n      STITCH_ACCESS_TOKEN: STITCH_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: stitch\n      location: ./shared/stitch.yaml\n\n  exposes:\n    - type: rest\n     \
  \ port: 8080\n      namespace: open-banking-api\n      description: >-\n        Unified REST API for African open banking payments, account data,\n        and disbursements via Stitch.\n      resources:\n        - path: /v1/payments\n          name: payments\n          description: Payment initiation requests.\n          operations:\n            - method: POST\n              name: initiate-payment\n              description: Initiate a Pay By Bank payment for a customer.\n              call: \"stitch.initiate-payment\"\n              with:\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n                payerReference: \"rest.payerReference\"\n                beneficiaryReference: \"rest.beneficiaryReference\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/{paymentRequestId}\n          name: payment\n          description: Payment status retrieval.\n          operations:\n\
  \            - method: GET\n              name: get-payment-status\n              description: Get current status of a payment initiation request.\n              call: \"stitch.get-payment-status\"\n              with:\n                paymentRequestId: \"rest.paymentRequestId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bank-accounts\n          name: bank-accounts\n          description: Linked user bank accounts.\n          operations:\n            - method: GET\n              name: list-bank-accounts\n              description: List bank accounts linked by the user.\n              call: \"stitch.list-bank-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bank-accounts/{accountId}/transactions\n          name: transactions\n          description: Bank account transactions.\n          operations:\n            - method: GET\n\
  \              name: get-account-transactions\n              description: Get transactions for a linked bank account.\n              call: \"stitch.get-account-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n                first: \"rest.first\"\n                after: \"rest.after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/disbursements\n          name: disbursements\n          description: Outbound payment disbursements.\n          operations:\n            - method: POST\n              name: create-disbursement\n              description: Create an outbound disbursement to a bank account.\n              call: \"stitch.create-disbursement\"\n              with:\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n                beneficiaryAccountNumber: \"rest.beneficiaryAccountNumber\"\n                beneficiaryBankId: \"rest.beneficiaryBankId\"\
  \n                reference: \"rest.reference\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: open-banking-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted African open banking operations including\n        payment initiation, account data retrieval, and payout management.\n      tools:\n        - name: initiate-payment\n          description: >-\n            Initiate a Pay By Bank payment in South Africa or Nigeria.\n            Returns a payment URL to redirect the customer for bank authorization.\n          hints:\n            readOnly: false\n          call: \"stitch.initiate-payment\"\n          with:\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            payerReference: \"tools.payerReference\"\n            beneficiaryReference: \"tools.beneficiaryReference\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n\n        - name: get-payment-status\n          description: >-\n            Check the status of a payment initiation request (Pending, Complete,\n            Cancelled, or Error). Use to poll for payment completion.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stitch.get-payment-status\"\n          with:\n            paymentRequestId: \"tools.paymentRequestId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bank-accounts\n          description: >-\n            List bank accounts linked by the user. Use to show available\n            accounts for payment or data analysis.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stitch.list-bank-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account-transactions\n\
  \          description: >-\n            Retrieve transaction history for a linked bank account. Supports\n            Relay-style cursor pagination via first/after parameters.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stitch.get-account-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n            first: \"tools.first\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-disbursement\n          description: >-\n            Send an outbound payment disbursement to a beneficiary bank account.\n            Use for marketplace payouts, refunds, or mass payments.\n          hints:\n            readOnly: false\n          call: \"stitch.create-disbursement\"\n          with:\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            beneficiaryAccountNumber: \"tools.beneficiaryAccountNumber\"\
  \n            beneficiaryBankId: \"tools.beneficiaryBankId\"\n            reference: \"tools.reference\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stitch/refs/heads/main/capabilities/open-banking-payments.yaml
tags:
- Africa
- Open Banking
- Payments
- Financial Data
- South Africa
- Nigeria
- Fintech
tools:
- description: Initiate a Pay By Bank payment in South Africa or Nigeria. Returns a payment URL to redirect the customer for bank authorization.
  hints:
    readOnly: false
  name: initiate-payment
- description: Check the status of a payment initiation request (Pending, Complete, Cancelled, or Error). Use to poll for payment completion.
  hints:
    idempotent: true
    readOnly: true
  name: get-payment-status
- description: List bank accounts linked by the user. Use to show available accounts for payment or data analysis.
  hints:
    idempotent: true
    readOnly: true
  name: list-bank-accounts
- description: Retrieve transaction history for a linked bank account. Supports Relay-style cursor pagination via first/after parameters.
  hints:
    idempotent: true
    readOnly: true
  name: get-account-transactions
- description: Send an outbound payment disbursement to a beneficiary bank account. Use for marketplace payouts, refunds, or mass payments.
  hints:
    readOnly: false
  name: create-disbursement
---
