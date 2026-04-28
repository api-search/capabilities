---
categories: []
consumed_apis:
- bny-treasury
description: BNY Mellon treasury operations workflow for institutional clients covering account management, balance reporting, payment initiation, funds transfers, and transaction history. Integrates with TMS and ERP platforms for automated treasury operations.
layout: capability
name: BNY Mellon Treasury Operations
operations: []
personas: []
provider_name: BNY Mellon
provider_slug: bank-of-new-york-mellon
search_terms:
- internal funds transfers and liquidity management
- list bny accounts
- institutional investor or fund manager using bny custody and treasury services
- get the status and details of a bny mellon payment
- initiate a funds transfer between bny mellon accounts
- asset servicing
- list transactions
- banking
- payments
- get current and available balances for a bny mellon account
- get account balances
- analyst executing treasury transactions and reporting
- initiate funds transfer
- list bny mellon treasury accounts for the authenticated client
- bny mellon
- list transactions for a bny mellon account
- treasury
- institutional banking
- Institutional Client
- institutional account management and cash positioning
- initiate a payment (wire, ach, swift, chips) through bny mellon
- wire, ach, swift, and chips payment execution
- initiate payment
- executive managing corporate liquidity and treasury operations
- get payment status
- Treasury Analyst
- institutional treasury operations including accounts, payments, and funds transfers
- wire transfers
- Corporate Treasurer
slug: treasury-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"BNY Mellon Treasury Operations\"\n  description: >-\n    BNY Mellon treasury operations workflow for institutional clients covering account\n    management, balance reporting, payment initiation, funds transfers, and transaction\n    history. Integrates with TMS and ERP platforms for automated treasury operations.\n  tags:\n    - BNY Mellon\n    - Treasury\n    - Payments\n    - Institutional Banking\n    - Wire Transfers\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BNY_CLIENT_ID: BNY_CLIENT_ID\n      BNY_CLIENT_SECRET: BNY_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: bny-treasury\n      location: ./shared/treasury-services-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9080\n      namespace: bny-treasury-mcp\n      transport: http\n      description: \"MCP server for AI-assisted BNY Mellon treasury operations.\"\n      tools:\n        - name: list-bny-accounts\n\
  \          description: List BNY Mellon treasury accounts for the authenticated client\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bny-treasury.listAccounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balances\n          description: Get current and available balances for a BNY Mellon account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bny-treasury.getAccountBalances\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: List transactions for a BNY Mellon account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bny-treasury.listTransactions\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: initiate-payment\n          description: Initiate a payment (wire, ACH, SWIFT, CHIPS) through BNY Mellon\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bny-treasury.initiatePayment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment-status\n          description: Get the status and details of a BNY Mellon payment\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bny-treasury.getPayment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-funds-transfer\n          description: Initiate a funds transfer between BNY Mellon accounts\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bny-treasury.initiateFundsTransfer\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bank-of-new-york-mellon/refs/heads/main/capabilities/treasury-operations.yaml
tags:
- BNY Mellon
- Treasury
- Payments
- Institutional Banking
- Wire Transfers
tools:
- description: List BNY Mellon treasury accounts for the authenticated client
  hints:
    openWorld: false
    readOnly: true
  name: list-bny-accounts
- description: Get current and available balances for a BNY Mellon account
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balances
- description: List transactions for a BNY Mellon account
  hints:
    openWorld: false
    readOnly: true
  name: list-transactions
- description: Initiate a payment (wire, ACH, SWIFT, CHIPS) through BNY Mellon
  hints:
    openWorld: false
    readOnly: false
  name: initiate-payment
- description: Get the status and details of a BNY Mellon payment
  hints:
    openWorld: false
    readOnly: true
  name: get-payment-status
- description: Initiate a funds transfer between BNY Mellon accounts
  hints:
    openWorld: false
    readOnly: false
  name: initiate-funds-transfer
---
