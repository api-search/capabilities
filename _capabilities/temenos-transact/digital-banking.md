---
categories:
- payments
consumed_apis:
- core-banking
description: Unified digital banking capability combining account management, customer operations, payment processing, deposits, loans, and reference data for retail and corporate banking applications. Used by digital banking developers and fintech integration teams.
layout: capability
name: Temenos Digital Banking
operations:
- description: List customer accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get account details
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Get account balances
  method: GET
  name: get-account-balances
  path: /v1/accounts/{accountId}/balances
- description: Get transaction history
  method: GET
  name: get-account-transactions
  path: /v1/accounts/{accountId}/transactions
- description: List customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: List payment orders
  method: GET
  name: list-payment-orders
  path: /v1/payments
- description: Create a payment order
  method: POST
  name: create-payment-order
  path: /v1/payments
- description: Initiate a fund transfer
  method: POST
  name: create-fund-transfer
  path: /v1/transfers
personas: []
provider_name: Temenos Transact
provider_slug: temenos-transact
search_terms:
- get transaction history for an account
- customer management
- list debit and credit cards
- core banking
- list payment beneficiaries
- account balances
- validate an iban and resolve bank details
- payment operations
- get account balances
- validate iban
- get fund transfer status and details
- list customer accounts
- account management
- payments
- list banking products from the catalog
- list available currencies
- get transaction history
- get customer accounts
- list payment orders
- list customer accounts with optional filters
- initiate a fund transfer
- get account balance information
- transaction history
- list customers
- cancel a pending payment order
- account details
- get account details by id
- register a new payment beneficiary
- list deposits
- list products
- digital banking
- list cards
- create a customer
- fund transfers
- fintech
- banking
- get account
- temenos
- get customer details
- get customer
- get account details
- list accounts for a customer
- get fund transfer
- list deposit arrangements
- create beneficiary
- initiate a fund transfer between accounts
- create fund transfer
- list loan arrangements
- financial services
- list loans
- create a new customer
- list accounts
- create a payment order
- list currencies
- create payment order
- get account transactions
- cancel payment order
- list beneficiaries
- enterprise
- create customer
- submit a payment order
slug: digital-banking
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Temenos Digital Banking\"\n  description: \"Unified digital banking capability combining account management, customer operations, payment processing, deposits, loans, and reference data for retail and corporate banking applications. Used by digital banking developers and fintech integration teams.\"\n  tags:\n    - Temenos\n    - Digital Banking\n    - Core Banking\n    - Payments\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      TEMENOS_BEARER_TOKEN: TEMENOS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: core-banking\n      location: ./shared/core-banking.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: digital-banking-api\n      description: \"Unified REST API for digital banking operations.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n    \
  \        - method: GET\n              name: list-accounts\n              description: \"List customer accounts\"\n              call: \"core-banking.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}\n          name: account-details\n          description: \"Account details\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get account details\"\n              call: \"core-banking.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}/balances\n          name: account-balances\n          description: \"Account balances\"\n          operations:\n            - method: GET\n              name: get-account-balances\n              description: \"Get account\
  \ balances\"\n              call: \"core-banking.get-account-balances\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}/transactions\n          name: account-transactions\n          description: \"Transaction history\"\n          operations:\n            - method: GET\n              name: get-account-transactions\n              description: \"Get transaction history\"\n              call: \"core-banking.get-account-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: \"Customer management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers\"\
  \n              call: \"core-banking.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a customer\"\n              call: \"core-banking.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: \"Payment operations\"\n          operations:\n            - method: GET\n              name: list-payment-orders\n              description: \"List payment orders\"\n              call: \"core-banking.list-payment-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment-order\n              description: \"Create a payment order\"\n              call: \"core-banking.create-payment-order\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transfers\n          name: transfers\n          description: \"Fund transfers\"\n          operations:\n            - method: POST\n              name: create-fund-transfer\n              description: \"Initiate a fund transfer\"\n              call: \"core-banking.create-fund-transfer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: digital-banking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted digital banking operations.\"\n      tools:\n        - name: list-accounts\n          description: \"List customer accounts with optional filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"core-banking.list-accounts\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n        - name: get-account\n          description: \"Get account details by ID\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balances\n          description: \"Get account balance information\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-account-balances\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-transactions\n          description: \"Get transaction history for an account\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-account-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: \"List customers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"core-banking.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get customer details\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer\"\n          call: \"core-banking.create-customer\"\n          with:\n            shortName: \"tools.shortName\"\n            customerMnemonic: \"tools.customerMnemonic\"\n            sectorId: \"tools.sectorId\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n        - name: get-customer-accounts\n          description: \"List accounts for a customer\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-customer-accounts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-fund-transfer\n          description: \"Initiate a fund transfer between accounts\"\n          call: \"core-banking.create-fund-transfer\"\n          with:\n            debitAccountId: \"tools.debitAccountId\"\n            creditAccountId: \"tools.creditAccountId\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fund-transfer\n          description: \"Get fund transfer status and details\"\n          hints:\n            readOnly: true\n          call: \"core-banking.get-fund-transfer\"\
  \n          with:\n            transferId: \"tools.transferId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payment-orders\n          description: \"List payment orders\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"core-banking.list-payment-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-payment-order\n          description: \"Submit a payment order\"\n          call: \"core-banking.create-payment-order\"\n          with:\n            debitAccountId: \"tools.debitAccountId\"\n            debitAmount: \"tools.debitAmount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-payment-order\n          description: \"Cancel a pending payment order\"\n          hints:\n            destructive: true\n          call: \"core-banking.cancel-payment-order\"\
  \n          with:\n            paymentOrderId: \"tools.paymentOrderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deposits\n          description: \"List deposit arrangements\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-deposits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-loans\n          description: \"List loan arrangements\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-loans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-beneficiaries\n          description: \"List payment beneficiaries\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-beneficiaries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-beneficiary\n\
  \          description: \"Register a new payment beneficiary\"\n          call: \"core-banking.create-beneficiary\"\n          with:\n            customerId: \"tools.customerId\"\n            beneficiaryName: \"tools.beneficiaryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: \"List banking products from the catalog\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-currencies\n          description: \"List available currencies\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-currencies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-iban\n          description: \"Validate an IBAN and resolve bank details\"\n          hints:\n     \
  \       readOnly: true\n          call: \"core-banking.validate-iban\"\n          with:\n            iban: \"tools.iban\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cards\n          description: \"List debit and credit cards\"\n          hints:\n            readOnly: true\n          call: \"core-banking.list-cards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/temenos-transact/refs/heads/main/capabilities/digital-banking.yaml
tags:
- Temenos
- Digital Banking
- Core Banking
- Payments
tools:
- description: List customer accounts with optional filters
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Get account details by ID
  hints:
    readOnly: true
  name: get-account
- description: Get account balance information
  hints:
    readOnly: true
  name: get-account-balances
- description: Get transaction history for an account
  hints:
    readOnly: true
  name: get-account-transactions
- description: List customers
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get customer details
  hints:
    readOnly: true
  name: get-customer
- description: Create a new customer
  hints: {}
  name: create-customer
- description: List accounts for a customer
  hints:
    readOnly: true
  name: get-customer-accounts
- description: Initiate a fund transfer between accounts
  hints: {}
  name: create-fund-transfer
- description: Get fund transfer status and details
  hints:
    readOnly: true
  name: get-fund-transfer
- description: List payment orders
  hints:
    openWorld: true
    readOnly: true
  name: list-payment-orders
- description: Submit a payment order
  hints: {}
  name: create-payment-order
- description: Cancel a pending payment order
  hints:
    destructive: true
  name: cancel-payment-order
- description: List deposit arrangements
  hints:
    readOnly: true
  name: list-deposits
- description: List loan arrangements
  hints:
    readOnly: true
  name: list-loans
- description: List payment beneficiaries
  hints:
    readOnly: true
  name: list-beneficiaries
- description: Register a new payment beneficiary
  hints: {}
  name: create-beneficiary
- description: List banking products from the catalog
  hints:
    readOnly: true
  name: list-products
- description: List available currencies
  hints:
    readOnly: true
  name: list-currencies
- description: Validate an IBAN and resolve bank details
  hints:
    readOnly: true
  name: validate-iban
- description: List debit and credit cards
  hints:
    readOnly: true
  name: list-cards
---
