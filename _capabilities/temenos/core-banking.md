---
categories: []
consumed_apis:
- transact
- payments
description: Unified core banking workflow combining Transact and Payments APIs for account management, customer operations, and payment processing. Used by retail and corporate banking teams to manage the complete customer banking lifecycle.
layout: capability
name: Temenos Core Banking
operations:
- description: List customer accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new account arrangement
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get account details
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Get account balances
  method: GET
  name: get-balances
  path: /v1/accounts/{accountId}/balances
- description: List account transactions
  method: GET
  name: list-transactions
  path: /v1/accounts/{accountId}/transactions
- description: List customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get customer details
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: List payment orders
  method: GET
  name: list-payment-orders
  path: /v1/payment-orders
- description: Create a payment order
  method: POST
  name: create-payment-order
  path: /v1/payment-orders
- description: List standing orders
  method: GET
  name: list-standing-orders
  path: /v1/standing-orders
- description: Create a standing order
  method: POST
  name: create-standing-order
  path: /v1/standing-orders
- description: List direct debit mandates
  method: GET
  name: list-direct-debits
  path: /v1/direct-debits
personas: []
provider_name: Temenos
provider_slug: temenos
search_terms:
- create a standing order
- direct debit mandates
- core banking
- customer account management
- list transaction history for a bank account
- create a new payment order (sepa, swift, domestic)
- list customers
- create standing order
- get account
- get account details
- list accounts
- create a new account arrangement
- fintech
- account transaction history
- open banking
- recurring standing orders
- get balances
- create payment order
- create a new banking account arrangement
- single customer operations
- list customer accounts
- account balance information
- create account
- set up a new recurring standing order
- accounts
- payment order management
- customers
- wealth management
- create a new banking customer
- list direct debit mandates
- get customer
- payments
- list payment orders
- banking
- list transactions
- create a new customer
- get current balances for a bank account
- list recurring standing orders
- cloud banking
- get customer details
- list direct debits
- list standing orders
- single account operations
- digital banking
- create customer
- list banking accounts for a customer
- get details for a specific bank account
- transactions
- list banking customers
- financial services
- customer management
- create a payment order
- list account transactions
- get account balances
slug: core-banking
source_filename: core-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Temenos Core Banking\"\n  description: \"Unified core banking workflow combining Transact and Payments APIs for account management, customer operations, and payment processing. Used by retail and corporate banking teams to manage the complete customer banking lifecycle.\"\n  tags:\n    - Banking\n    - Core Banking\n    - Accounts\n    - Payments\n    - Customers\n    - Transactions\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\n      TEMENOS_PAYMENTS_TOKEN: TEMENOS_PAYMENTS_TOKEN\n\ncapability:\n  consumes:\n    - import: transact\n      location: ./shared/transact.yaml\n    - import: payments\n      location: ./shared/payments.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: core-banking-api\n      description: \"Unified REST API for Temenos core banking operations.\"\n      resources:\n        - path:\
  \ /v1/accounts\n          name: accounts\n          description: \"Customer account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List customer accounts\"\n              call: \"transact.list-accounts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new account arrangement\"\n              call: \"transact.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}\n          name: account-detail\n          description: \"Single account operations\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get account details\"\n\
  \              call: \"transact.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/balances\n          name: account-balances\n          description: \"Account balance information\"\n          operations:\n            - method: GET\n              name: get-balances\n              description: \"Get account balances\"\n              call: \"transact.get-account-balances\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/transactions\n          name: account-transactions\n          description: \"Account transaction history\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List account\
  \ transactions\"\n              call: \"transact.list-account-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers\n          name: customers\n          description: \"Customer management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers\"\n              call: \"transact.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer\"\n              call: \"transact.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}\n          name: customer-detail\n          description:\
  \ \"Single customer operations\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get customer details\"\n              call: \"transact.get-customer\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payment-orders\n          name: payment-orders\n          description: \"Payment order management\"\n          operations:\n            - method: GET\n              name: list-payment-orders\n              description: \"List payment orders\"\n              call: \"payments.list-payment-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment-order\n              description: \"Create a payment order\"\n              call: \"payments.create-payment-order\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/standing-orders\n          name: standing-orders\n          description: \"Recurring standing orders\"\n          operations:\n            - method: GET\n              name: list-standing-orders\n              description: \"List standing orders\"\n              call: \"payments.list-standing-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-standing-order\n              description: \"Create a standing order\"\n              call: \"payments.create-standing-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/direct-debits\n          name: direct-debits\n          description: \"Direct debit mandates\"\n          operations:\n            - method: GET\n              name: list-direct-debits\n\
  \              description: \"List direct debit mandates\"\n              call: \"payments.list-direct-debits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: core-banking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted core banking operations.\"\n      tools:\n        - name: list-accounts\n          description: \"List banking accounts for a customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.list-accounts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Get details for a specific bank account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.get-account\"\n          with:\n  \
  \          accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-balances\n          description: \"Get current balances for a bank account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.get-account-balances\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-account-transactions\n          description: \"List transaction history for a bank account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.list-account-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-account\n          description: \"Create a new banking account arrangement\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"transact.create-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customers\n          description: \"List banking customers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get customer details\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"transact.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new banking customer\"\n          hints:\n    \
  \        readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"transact.create-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payment-orders\n          description: \"List payment orders\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payments.list-payment-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-payment-order\n          description: \"Create a new payment order (SEPA, SWIFT, domestic)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"payments.create-payment-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-standing-orders\n          description: \"List recurring standing orders\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"payments.list-standing-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-standing-order\n          description: \"Set up a new recurring standing order\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"payments.create-standing-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-direct-debits\n          description: \"List direct debit mandates\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"payments.list-direct-debits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/temenos/refs/heads/main/capabilities/core-banking.yaml
tags:
- Banking
- Core Banking
- Accounts
- Payments
- Customers
- Transactions
tools:
- description: List banking accounts for a customer
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Get details for a specific bank account
  hints:
    openWorld: false
    readOnly: true
  name: get-account
- description: Get current balances for a bank account
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balances
- description: List transaction history for a bank account
  hints:
    openWorld: false
    readOnly: true
  name: list-account-transactions
- description: Create a new banking account arrangement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-account
- description: List banking customers
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Get customer details
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Create a new banking customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: List payment orders
  hints:
    openWorld: false
    readOnly: true
  name: list-payment-orders
- description: Create a new payment order (SEPA, SWIFT, domestic)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-payment-order
- description: List recurring standing orders
  hints:
    openWorld: false
    readOnly: true
  name: list-standing-orders
- description: Set up a new recurring standing order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-standing-order
- description: List direct debit mandates
  hints:
    openWorld: false
    readOnly: true
  name: list-direct-debits
---
