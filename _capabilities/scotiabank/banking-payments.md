---
api_specs:
- filename: scotiabank-tranxact-openapi.yml
  format: yaml
  label: scotiabank-tranxact
  slug: scotiabank-tranxact
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/scotiabank/refs/heads/main/openapi/scotiabank-tranxact-openapi.yml
categories: []
consumed_apis:
- scotiabank-tranxact
description: Unified capability for banking and payments workflows using Scotiabank's Scotia TranXact APIs. Enables corporate treasury teams, ERP systems, and financial applications to initiate wire payments, send real-time INTERAC transfers, manage EFT batches, retrieve account balances and transaction history, and track payment status.
layout: capability
name: Scotiabank Banking and Payments
operations:
- description: Initiate a domestic or international wire transfer
  method: POST
  name: initiate-wire-payment
  path: /v1/payments/wire
- description: Get wire payment status
  method: GET
  name: get-wire-payment
  path: /v1/payments/wire
- description: Send real-time payment via INTERAC e-Transfer
  method: POST
  name: initiate-realtime-payment
  path: /v1/payments/realtime
- description: Create and submit EFT payment
  method: POST
  name: create-eft-payment
  path: /v1/payments/eft
- description: List eligible deposit accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get current or prior-day balance
  method: GET
  name: get-account-balance
  path: /v1/accounts/{account_id}/balance
- description: List account transactions (up to 2 years)
  method: GET
  name: list-transactions
  path: /v1/accounts/{account_id}/transactions
- description: Validate account number and ownership
  method: POST
  name: validate-account
  path: /v1/accounts/validate
- description: Track wire payment by UETR
  method: GET
  name: track-payment
  path: /v1/payments/track/{reference_id}
personas: []
provider_name: Scotiabank
provider_slug: scotiabank
search_terms:
- send real-time payment via interac e-transfer
- canada
- initiate wire transfer
- create and submit eft payment
- create eft payment
- list accounts
- send interac payment
- get current or prior-day account balance including opening and closing balances.
- initiate realtime payment
- account transaction history
- validate account number and ownership
- open banking
- get wire payment status
- validate a scotiabank account number format and check ownership match likelihood.
- finance
- list enriched transaction history for an account (up to 2 years). returns transaction date, amount, credit/debit indicator, and description.
- initiate a domestic or international wire transfer (cad or usd). powered by swift gpi for real-time tracking.
- list eligible deposit accounts
- initiate wire payment
- account balance retrieval
- get current or prior-day balance
- payment status tracking
- get wire payment
- get the current status of a wire payment by payment id
- track wire payment
- bank account management
- validate bank account
- payments
- wire payment initiation and tracking
- initiate a domestic or international wire transfer
- banking
- real-time interac e-transfer payments
- get account balance
- list transactions
- track the real-time status of a wire payment using its unique end-to-end transaction reference (uetr).
- track payment
- eft
- electronic funds transfer management
- account validation
- send a real-time business payment via interac e-transfer (up to $25,000). recipient receives payment at their email address.
- list account transactions (up to 2 years)
- validate account
- list bank accounts
- list all eligible scotiabank deposit accounts for the customer
- interac
- create and submit an electronic funds transfer (eft) payment for debit or credit transactions.
- treasury management
- wire transfer
- list account transactions
- track wire payment by uetr
slug: banking-payments
source_filename: banking-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Scotiabank Banking and Payments\"\n  description: >-\n    Unified capability for banking and payments workflows using Scotiabank's\n    Scotia TranXact APIs. Enables corporate treasury teams, ERP systems, and\n    financial applications to initiate wire payments, send real-time INTERAC\n    transfers, manage EFT batches, retrieve account balances and transaction\n    history, and track payment status.\n  tags:\n    - Banking\n    - Payments\n    - Wire Transfer\n    - EFT\n    - INTERAC\n    - Treasury Management\n    - Canada\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCOTIABANK_CLIENT_ID: SCOTIABANK_CLIENT_ID\n      SCOTIABANK_CLIENT_SECRET: SCOTIABANK_CLIENT_SECRET\n      SCOTIABANK_ACCESS_TOKEN: SCOTIABANK_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: scotiabank-tranxact\n      location: ./shared/scotiabank-tranxact.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: scotiabank-banking-api\n      description: \"Unified REST API for Scotiabank banking and payment operations.\"\n      resources:\n        - path: /v1/payments/wire\n          name: wire-payments\n          description: Wire payment initiation and tracking\n          operations:\n            - method: POST\n              name: initiate-wire-payment\n              description: Initiate a domestic or international wire transfer\n              call: \"scotiabank-tranxact.initiate-wire-payment\"\n              with:\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-wire-payment\n              description: Get wire payment status\n              call: \"scotiabank-tranxact.get-wire-payment\"\n              with:\n                payment_id: \"rest.payment_id\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/realtime\n          name: realtime-payments\n          description: Real-time INTERAC e-Transfer payments\n          operations:\n            - method: POST\n              name: initiate-realtime-payment\n              description: Send real-time payment via INTERAC e-Transfer\n              call: \"scotiabank-tranxact.initiate-realtime-payment\"\n              with:\n                amount: \"rest.amount\"\n                recipient_email: \"rest.recipient_email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/eft\n          name: eft-payments\n          description: Electronic Funds Transfer management\n          operations:\n            - method: POST\n              name: create-eft-payment\n              description: Create and submit EFT payment\n              call: \"scotiabank-tranxact.create-eft-payment\"\
  \n              with:\n                amount: \"rest.amount\"\n                payment_type: \"rest.payment_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts\n          name: accounts\n          description: Bank account management\n          operations:\n            - method: GET\n              name: list-accounts\n              description: List eligible deposit accounts\n              call: \"scotiabank-tranxact.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{account_id}/balance\n          name: account-balance\n          description: Account balance retrieval\n          operations:\n            - method: GET\n              name: get-account-balance\n              description: Get current or prior-day balance\n              call: \"scotiabank-tranxact.get-account-balance\"\n              with:\n\
  \                account_id: \"rest.account_id\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{account_id}/transactions\n          name: transactions\n          description: Account transaction history\n          operations:\n            - method: GET\n              name: list-transactions\n              description: List account transactions (up to 2 years)\n              call: \"scotiabank-tranxact.list-transactions\"\n              with:\n                account_id: \"rest.account_id\"\n                from_date: \"rest.from_date\"\n                to_date: \"rest.to_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/validate\n          name: account-validation\n          description: Account validation\n          operations:\n            - method: POST\n              name:\
  \ validate-account\n              description: Validate account number and ownership\n              call: \"scotiabank-tranxact.validate-account\"\n              with:\n                account_number: \"rest.account_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments/track/{reference_id}\n          name: payment-tracking\n          description: Payment status tracking\n          operations:\n            - method: GET\n              name: track-payment\n              description: Track wire payment by UETR\n              call: \"scotiabank-tranxact.track-payment\"\n              with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: scotiabank-banking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted banking and payment\
  \ workflows with Scotiabank.\"\n      tools:\n        - name: initiate-wire-transfer\n          description: >-\n            Initiate a domestic or international wire transfer (CAD or USD).\n            Powered by SWIFT GPI for real-time tracking.\n          hints:\n            readOnly: false\n          call: \"scotiabank-tranxact.initiate-wire-payment\"\n          with:\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            debit_account: \"tools.debit_account\"\n            credit_account: \"tools.credit_account\"\n            remittance_information: \"tools.remittance_information\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-wire-payment-status\n          description: Get the current status of a wire payment by payment ID\n          hints:\n            readOnly: true\n          call: \"scotiabank-tranxact.get-wire-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: send-interac-payment\n          description: >-\n            Send a real-time business payment via INTERAC e-Transfer (up to $25,000).\n            Recipient receives payment at their email address.\n          hints:\n            readOnly: false\n          call: \"scotiabank-tranxact.initiate-realtime-payment\"\n          with:\n            amount: \"tools.amount\"\n            recipient_email: \"tools.recipient_email\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-eft-payment\n          description: >-\n            Create and submit an Electronic Funds Transfer (EFT) payment\n            for debit or credit transactions.\n          hints:\n            readOnly: false\n          call: \"scotiabank-tranxact.create-eft-payment\"\n          with:\n            payment_type: \"\
  tools.payment_type\"\n            amount: \"tools.amount\"\n            effective_date: \"tools.effective_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bank-accounts\n          description: List all eligible Scotiabank deposit accounts for the customer\n          hints:\n            readOnly: true\n          call: \"scotiabank-tranxact.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account-balance\n          description: >-\n            Get current or prior-day account balance including opening\n            and closing balances.\n          hints:\n            readOnly: true\n          call: \"scotiabank-tranxact.get-account-balance\"\n          with:\n            account_id: \"tools.account_id\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-account-transactions\n\
  \          description: >-\n            List enriched transaction history for an account (up to 2 years).\n            Returns transaction date, amount, credit/debit indicator, and description.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scotiabank-tranxact.list-transactions\"\n          with:\n            account_id: \"tools.account_id\"\n            from_date: \"tools.from_date\"\n            to_date: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: validate-bank-account\n          description: >-\n            Validate a Scotiabank account number format and check\n            ownership match likelihood.\n          hints:\n            readOnly: true\n          call: \"scotiabank-tranxact.validate-account\"\n          with:\n            account_number: \"tools.account_number\"\n            account_holder_name: \"tools.account_holder_name\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: track-wire-payment\n          description: >-\n            Track the real-time status of a wire payment using its\n            Unique End-to-End Transaction Reference (UETR).\n          hints:\n            readOnly: true\n          call: \"scotiabank-tranxact.track-payment\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scotiabank/refs/heads/main/capabilities/banking-payments.yaml
tags:
- Banking
- Payments
- Wire Transfer
- EFT
- INTERAC
- Treasury Management
- Canada
tools:
- description: Initiate a domestic or international wire transfer (CAD or USD). Powered by SWIFT GPI for real-time tracking.
  hints:
    readOnly: false
  name: initiate-wire-transfer
- description: Get the current status of a wire payment by payment ID
  hints:
    readOnly: true
  name: get-wire-payment-status
- description: Send a real-time business payment via INTERAC e-Transfer (up to $25,000). Recipient receives payment at their email address.
  hints:
    readOnly: false
  name: send-interac-payment
- description: Create and submit an Electronic Funds Transfer (EFT) payment for debit or credit transactions.
  hints:
    readOnly: false
  name: create-eft-payment
- description: List all eligible Scotiabank deposit accounts for the customer
  hints:
    readOnly: true
  name: list-bank-accounts
- description: Get current or prior-day account balance including opening and closing balances.
  hints:
    readOnly: true
  name: get-account-balance
- description: List enriched transaction history for an account (up to 2 years). Returns transaction date, amount, credit/debit indicator, and description.
  hints:
    openWorld: true
    readOnly: true
  name: list-account-transactions
- description: Validate a Scotiabank account number format and check ownership match likelihood.
  hints:
    readOnly: true
  name: validate-bank-account
- description: Track the real-time status of a wire payment using its Unique End-to-End Transaction Reference (UETR).
  hints:
    readOnly: true
  name: track-wire-payment
---
