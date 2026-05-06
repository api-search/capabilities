---
categories: []
consumed_apis: []
description: 'Workflow capability for open banking payment operations via TrueLayer. Covers the full payment lifecycle: creating payments and mandates, handling payouts, processing refunds, and monitoring merchant account balances and transactions across UK and EU open banking rails. Used by fintech developers, payment teams, and financial platforms.'
layout: capability
name: TrueLayer Open Banking Payments
operations:
- description: Create a new open banking payment
  method: POST
  name: create-payment
  path: /v1/payments
- description: Get payment status
  method: GET
  name: get-payment
  path: /v1/payments/{id}
- description: Create a refund for a payment
  method: POST
  name: create-refund
  path: /v1/payments/{id}/refunds
- description: List refunds for a payment
  method: GET
  name: list-payment-refunds
  path: /v1/payments/{id}/refunds
- description: Create a VRP mandate
  method: POST
  name: create-mandate
  path: /v1/mandates
- description: Get mandate details
  method: GET
  name: get-mandate
  path: /v1/mandates/{id}
- description: Revoke a VRP mandate
  method: DELETE
  name: revoke-mandate
  path: /v1/mandates/{id}
- description: Create a payout
  method: POST
  name: create-payout
  path: /v1/payouts
- description: Get payout status
  method: GET
  name: get-payout
  path: /v1/payouts/{id}
- description: List merchant accounts
  method: GET
  name: list-merchant-accounts
  path: /v1/merchant-accounts
- description: Get merchant account and balance
  method: GET
  name: get-merchant-account
  path: /v1/merchant-accounts/{id}
- description: List merchant account transactions
  method: GET
  name: list-merchant-account-transactions
  path: /v1/merchant-accounts/{id}/transactions
personas: []
provider_name: TrueLayer
provider_slug: truelayer
search_terms:
- create a variable recurring payment (vrp) mandate. authorizes future payments within defined constraints (limits, frequency).
- get merchant account
- get payout status
- uk banking
- get payout
- create an open banking bank-transfer payment via truelayer. supports pay-ins to merchant accounts and single payments to external accounts. requires amount in minor units (pence/cents).
- data api
- variable recurring payment mandates
- financial services
- payouts
- payment lifecycle management
- get merchant account and balance
- revoke a vrp mandate
- create a payout
- merchant account management
- list refunds for a payment
- vrp
- revoke an active vrp mandate
- create a payout from merchant account to a user or external account
- get merchant account details and current balance
- get mandate details
- list transactions for a merchant account with date filters
- get the current status and details of a payment
- get payment status
- create a vrp mandate
- create payout
- create refund
- open banking
- refunds
- eu banking
- create a refund for a payment
- get payment
- list all truelayer merchant accounts with balances
- create a new open banking payment
- list payment refunds
- truelayer
- psd2
- merchant accounts
- payments
- get mandate
- merchant account payouts
- list merchant account transactions
- create mandate
- initiate a refund for a completed payment
- create payment
- get vrp mandate status and details
- list all refunds for a specific payment
- revoke mandate
- list merchant accounts
slug: open-banking-payments
source_filename: open-banking-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TrueLayer Open Banking Payments\n  description: 'Workflow capability for open banking payment operations via TrueLayer. Covers the full payment lifecycle:\n    creating payments and mandates, handling payouts, processing refunds, and monitoring merchant account balances and transactions\n    across UK and EU open banking rails. Used by fintech developers, payment teams, and financial platforms.'\n  tags:\n  - TrueLayer\n  - Open Banking\n  - Payments\n  - VRP\n  - Payouts\n  - Refunds\n  - Merchant Accounts\n  - UK Banking\n  - EU Banking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUELAYER_ACCESS_TOKEN: TRUELAYER_ACCESS_TOKEN\n    TRUELAYER_SIGNING_KEY: TRUELAYER_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: truelayer-payments\n    baseUri: https://api.truelayer.com\n    description: TrueLayer Payments API v3\n    authentication:\n      type: bearer\n      token:\
  \ '{{TRUELAYER_ACCESS_TOKEN}}'\n    resources:\n    - name: payments\n      path: /v3/payments\n      description: Payment creation and management\n      operations:\n      - name: create-payment\n        method: POST\n        description: Create a new bank payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount_in_minor: '{{tools.amount_in_minor}}'\n            currency: '{{tools.currency}}'\n            payment_method: '{{tools.payment_method}}'\n            user: '{{tools.user}}'\n            metadata: '{{tools.metadata}}'\n    - name: payment\n      path: /v3/payments/{id}\n      description: Individual payment operations\n      operations:\n      - name: get-payment\n        method: GET\n        description: Get payment status and details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n \
  \         required: true\n          description: Payment UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-refunds\n      path: /v3/payments/{id}/refunds\n      description: Refund management for payments\n      operations:\n      - name: create-refund\n        method: POST\n        description: Create a refund for a payment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount_in_minor: '{{tools.amount_in_minor}}'\n            reference: '{{tools.reference}}'\n      - name: list-payment-refunds\n        method: GET\n        description: List refunds for a payment\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mandates\n      path: /v3/mandates\n      description: VRP mandate management\n      operations:\n      - name: create-mandate\n        method: POST\n        description: Create a VRP mandate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mandate: '{{tools.mandate}}'\n            currency: '{{tools.currency}}'\n            user: '{{tools.user}}'\n            constraints: '{{tools.constraints}}'\n    - name: mandate\n      path: /v3/mandates/{id}\n      description: Individual mandate operations\n      operations:\n      - name: get-mandate\n        method: GET\n        description: Get mandate by ID\n        inputParameters:\n        - name: id\n        \
  \  in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoke-mandate\n        method: DELETE\n        description: Revoke a VRP mandate\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payouts\n      path: /v3/payouts\n      description: Merchant account payouts\n      operations:\n      - name: create-payout\n        method: POST\n        description: Create a payout from merchant account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchant_account_id: '{{tools.merchant_account_id}}'\n \
  \           amount_in_minor: '{{tools.amount_in_minor}}'\n            currency: '{{tools.currency}}'\n            beneficiary: '{{tools.beneficiary}}'\n    - name: payout\n      path: /v3/payouts/{id}\n      description: Individual payout status\n      operations:\n      - name: get-payout\n        method: GET\n        description: Get payout status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: merchant-accounts\n      path: /v3/merchant-accounts\n      description: Merchant account management\n      operations:\n      - name: list-merchant-accounts\n        method: GET\n        description: List all merchant accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: merchant-account\n     \
  \ path: /v3/merchant-accounts/{id}\n      description: Individual merchant account\n      operations:\n      - name: get-merchant-account\n        method: GET\n        description: Get merchant account and balance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: merchant-account-transactions\n      path: /v3/merchant-accounts/{id}/transactions\n      description: Merchant account transaction history\n      operations:\n      - name: list-merchant-account-transactions\n        method: GET\n        description: List merchant account transactions\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: from\n          in: query\n          type: string\n          required: false\n        - name: to\n          in:\
  \ query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: truelayer-open-banking-api\n    description: Unified REST API for TrueLayer open banking payment operations.\n    resources:\n    - path: /v1/payments\n      name: payments\n      description: Payment lifecycle management\n      operations:\n      - method: POST\n        name: create-payment\n        description: Create a new open banking payment\n        call: truelayer-payments.create-payment\n        with:\n          amount_in_minor: rest.amount_in_minor\n          currency: rest.currency\n          payment_method: rest.payment_method\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{id}\n      name: payment\n      operations:\n      - method: GET\n        name: get-payment\n\
  \        description: Get payment status\n        call: truelayer-payments.get-payment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{id}/refunds\n      name: payment-refunds\n      operations:\n      - method: POST\n        name: create-refund\n        description: Create a refund for a payment\n        call: truelayer-payments.create-refund\n        with:\n          id: rest.id\n          amount_in_minor: rest.amount_in_minor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-payment-refunds\n        description: List refunds for a payment\n        call: truelayer-payments.list-payment-refunds\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mandates\n      name: mandates\n      description: Variable recurring payment mandates\n      operations:\n    \
  \  - method: POST\n        name: create-mandate\n        description: Create a VRP mandate\n        call: truelayer-payments.create-mandate\n        with:\n          mandate: rest.mandate\n          currency: rest.currency\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mandates/{id}\n      name: mandate\n      operations:\n      - method: GET\n        name: get-mandate\n        description: Get mandate details\n        call: truelayer-payments.get-mandate\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: revoke-mandate\n        description: Revoke a VRP mandate\n        call: truelayer-payments.revoke-mandate\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payouts\n      name: payouts\n      description: Merchant account payouts\n      operations:\n\
  \      - method: POST\n        name: create-payout\n        description: Create a payout\n        call: truelayer-payments.create-payout\n        with:\n          merchant_account_id: rest.merchant_account_id\n          amount_in_minor: rest.amount_in_minor\n          currency: rest.currency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payouts/{id}\n      name: payout\n      operations:\n      - method: GET\n        name: get-payout\n        description: Get payout status\n        call: truelayer-payments.get-payout\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/merchant-accounts\n      name: merchant-accounts\n      description: Merchant account management\n      operations:\n      - method: GET\n        name: list-merchant-accounts\n        description: List merchant accounts\n        call: truelayer-payments.list-merchant-accounts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/merchant-accounts/{id}\n      name: merchant-account\n      operations:\n      - method: GET\n        name: get-merchant-account\n        description: Get merchant account and balance\n        call: truelayer-payments.get-merchant-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/merchant-accounts/{id}/transactions\n      name: merchant-account-transactions\n      operations:\n      - method: GET\n        name: list-merchant-account-transactions\n        description: List merchant account transactions\n        call: truelayer-payments.list-merchant-account-transactions\n        with:\n          id: rest.id\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: truelayer-open-banking-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted open banking payment operations via TrueLayer.\n    tools:\n    - name: create-payment\n      description: Create an open banking bank-transfer payment via TrueLayer. Supports pay-ins to merchant accounts and single\n        payments to external accounts. Requires amount in minor units (pence/cents).\n      hints:\n        readOnly: false\n      call: truelayer-payments.create-payment\n      with:\n        amount_in_minor: tools.amount_in_minor\n        currency: tools.currency\n        payment_method: tools.payment_method\n        user: tools.user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payment\n      description: Get the current status and details of a payment\n      hints:\n        readOnly: true\n        idempotent: true\n      call: truelayer-payments.get-payment\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-refund\n      description:\
  \ Initiate a refund for a completed payment\n      hints:\n        readOnly: false\n      call: truelayer-payments.create-refund\n      with:\n        id: tools.id\n        amount_in_minor: tools.amount_in_minor\n        reference: tools.reference\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-refunds\n      description: List all refunds for a specific payment\n      hints:\n        readOnly: true\n      call: truelayer-payments.list-payment-refunds\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mandate\n      description: Create a Variable Recurring Payment (VRP) mandate. Authorizes future payments within defined constraints\n        (limits, frequency).\n      hints:\n        readOnly: false\n      call: truelayer-payments.create-mandate\n      with:\n        mandate: tools.mandate\n        currency: tools.currency\n        user: tools.user\n        constraints:\
  \ tools.constraints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-mandate\n      description: Get VRP mandate status and details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: truelayer-payments.get-mandate\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-mandate\n      description: Revoke an active VRP mandate\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: truelayer-payments.revoke-mandate\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payout\n      description: Create a payout from merchant account to a user or external account\n      hints:\n        readOnly: false\n      call: truelayer-payments.create-payout\n      with:\n        merchant_account_id: tools.merchant_account_id\n        amount_in_minor: tools.amount_in_minor\n\
  \        currency: tools.currency\n        beneficiary: tools.beneficiary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payout\n      description: Get payout status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: truelayer-payments.get-payout\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-merchant-accounts\n      description: List all TrueLayer merchant accounts with balances\n      hints:\n        readOnly: true\n      call: truelayer-payments.list-merchant-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-merchant-account\n      description: Get merchant account details and current balance\n      hints:\n        readOnly: true\n        idempotent: true\n      call: truelayer-payments.get-merchant-account\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-merchant-account-transactions\n      description: List transactions for a merchant account with date filters\n      hints:\n        readOnly: true\n      call: truelayer-payments.list-merchant-account-transactions\n      with:\n        id: tools.id\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/truelayer/refs/heads/main/capabilities/open-banking-payments.yaml
tags:
- TrueLayer
- Open Banking
- Payments
- VRP
- Payouts
- Refunds
- Merchant Accounts
- UK Banking
- EU Banking
tools:
- description: Create an open banking bank-transfer payment via TrueLayer. Supports pay-ins to merchant accounts and single payments to external accounts. Requires amount in minor units (pence/cents).
  hints:
    readOnly: false
  name: create-payment
- description: Get the current status and details of a payment
  hints:
    idempotent: true
    readOnly: true
  name: get-payment
- description: Initiate a refund for a completed payment
  hints:
    readOnly: false
  name: create-refund
- description: List all refunds for a specific payment
  hints:
    readOnly: true
  name: list-payment-refunds
- description: Create a Variable Recurring Payment (VRP) mandate. Authorizes future payments within defined constraints (limits, frequency).
  hints:
    readOnly: false
  name: create-mandate
- description: Get VRP mandate status and details
  hints:
    idempotent: true
    readOnly: true
  name: get-mandate
- description: Revoke an active VRP mandate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-mandate
- description: Create a payout from merchant account to a user or external account
  hints:
    readOnly: false
  name: create-payout
- description: Get payout status
  hints:
    idempotent: true
    readOnly: true
  name: get-payout
- description: List all TrueLayer merchant accounts with balances
  hints:
    readOnly: true
  name: list-merchant-accounts
- description: Get merchant account details and current balance
  hints:
    idempotent: true
    readOnly: true
  name: get-merchant-account
- description: List transactions for a merchant account with date filters
  hints:
    readOnly: true
  name: list-merchant-account-transactions
---
