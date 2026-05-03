---
categories: []
consumed_apis:
- bofa-cashpro
description: Bank of America CashPro treasury banking workflow for corporate clients covering account management, balance reporting, payment initiation, and statement access. Integrates with TMS and ERP platforms for automated treasury operations.
layout: capability
name: Bank of America CashPro Treasury Banking
operations:
- description: List CashPro accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Initiate a payment
  method: POST
  name: initiate-payment
  path: /v1/payments
personas: []
provider_name: Bank of America
provider_slug: bank-of-america
search_terms:
- executive responsible for corporate cash and liquidity management
- bank of america
- account management
- initiate a payment through bank of america cashpro (supports 350+ payment types)
- list bank of america cashpro accounts for the authenticated client
- list account transactions
- list available bank of america account statements
- ERP Integration
- Corporate Treasurer
- payment initiation and tracking across 350+ payment types
- banking
- cashpro
- Treasury Analyst
- corporate cash management, balance reporting, and liquidity
- list bofa accounts
- payments
- analyst managing day-to-day treasury operations and reporting
- get payment status
- get current and available balances for a cashpro account
- list accounts
- treasury
- initiate a payment
- list statements
- payment management
- finance
- get account balances
- list cashpro accounts
- initiate payment
- corporate banking
- system integration connecting erp/tms to bank of america cashpro apis
- corporate treasury operations including account management, payments, and reporting
- list transactions for a bank of america account within a date range
- get the current status of a bank of america payment
slug: treasury-banking
source_filename: treasury-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Bank of America CashPro Treasury Banking\"\n  description: >-\n    Bank of America CashPro treasury banking workflow for corporate clients covering\n    account management, balance reporting, payment initiation, and statement access.\n    Integrates with TMS and ERP platforms for automated treasury operations.\n  tags:\n    - Bank of America\n    - CashPro\n    - Treasury\n    - Payments\n    - Corporate Banking\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BOFA_CLIENT_ID: BOFA_CLIENT_ID\n      BOFA_CLIENT_SECRET: BOFA_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: bofa-cashpro\n      location: ./shared/cashpro-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: bofa-treasury-api\n      description: \"Unified REST API for Bank of America CashPro treasury operations.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n\
  \          description: Account management\n          operations:\n            - method: GET\n              name: list-accounts\n              description: List CashPro accounts\n              call: \"bofa-cashpro.listAccounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: Payment management\n          operations:\n            - method: POST\n              name: initiate-payment\n              description: Initiate a payment\n              call: \"bofa-cashpro.initiatePayment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: bofa-treasury-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Bank of America treasury management.\"\n      tools:\n        - name: list-bofa-accounts\n          description: List Bank of America CashPro\
  \ accounts for the authenticated client\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bofa-cashpro.listAccounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balances\n          description: Get current and available balances for a CashPro account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bofa-cashpro.getAccountBalances\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-account-transactions\n          description: List transactions for a Bank of America account within a date range\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bofa-cashpro.listTransactions\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: initiate-payment\n          description: Initiate a payment through Bank of America CashPro (supports 350+ payment types)\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"bofa-cashpro.initiatePayment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment-status\n          description: Get the current status of a Bank of America payment\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bofa-cashpro.getPayment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-statements\n          description: List available Bank of America account statements\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"bofa-cashpro.listStatements\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bank-of-america/refs/heads/main/capabilities/treasury-banking.yaml
tags:
- Bank of America
- CashPro
- Treasury
- Payments
- Corporate Banking
tools:
- description: List Bank of America CashPro accounts for the authenticated client
  hints:
    openWorld: false
    readOnly: true
  name: list-bofa-accounts
- description: Get current and available balances for a CashPro account
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balances
- description: List transactions for a Bank of America account within a date range
  hints:
    openWorld: false
    readOnly: true
  name: list-account-transactions
- description: Initiate a payment through Bank of America CashPro (supports 350+ payment types)
  hints:
    openWorld: false
    readOnly: false
  name: initiate-payment
- description: Get the current status of a Bank of America payment
  hints:
    openWorld: false
    readOnly: true
  name: get-payment-status
- description: List available Bank of America account statements
  hints:
    openWorld: false
    readOnly: true
  name: list-statements
---
