---
categories: []
consumed_apis: []
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
- list direct debit mandates
- get account
- transactions
- create customer
- payment order management
- cloud banking
- wealth management
- get customer details
- create a standing order
- get account details
- list banking accounts for a customer
- list accounts
- create a new banking customer
- single account operations
- list customer accounts
- get current balances for a bank account
- list recurring standing orders
- account balance information
- digital banking
- get account balances
- customers
- list standing orders
- fintech
- list direct debits
- create account
- account transaction history
- create a payment order
- financial services
- customer account management
- list payment orders
- create payment order
- direct debit mandates
- get customer
- accounts
- create standing order
- single customer operations
- list customers
- list account transactions
- create a new account arrangement
- create a new customer
- open banking
- banking
- payments
- customer management
- get details for a specific bank account
- set up a new recurring standing order
- list transaction history for a bank account
- list transactions
- create a new banking account arrangement
- recurring standing orders
- list banking customers
- get balances
- create a new payment order (sepa, swift, domestic)
- core banking
slug: core-banking
source_filename: core-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Temenos Core Banking\n  description: Unified core banking workflow combining Transact and Payments APIs for account management, customer operations,\n    and payment processing. Used by retail and corporate banking teams to manage the complete customer banking lifecycle.\n  tags:\n  - Banking\n  - Core Banking\n  - Accounts\n  - Payments\n  - Customers\n  - Transactions\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMENOS_TRANSACT_TOKEN: TEMENOS_TRANSACT_TOKEN\n    TEMENOS_PAYMENTS_TOKEN: TEMENOS_PAYMENTS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: transact\n    baseUri: https://api.temenos.com/transact/v1\n    description: Temenos Transact core banking API\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_TRANSACT_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /holdings/accounts\n      description: Customer account arrangements\n      operations:\n\
  \      - name: list-accounts\n        method: GET\n        description: List customer accounts with optional filtering\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter accounts by customer identifier\n        - name: accountType\n          in: query\n          type: string\n          required: false\n          description: Filter by account type (CURRENT, SAVINGS, DEPOSIT, LOAN)\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page\n        - name: page_start\n          in: query\n          type: integer\n          required: false\n          description: Starting record number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new\
  \ account arrangement\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            accountType: '{{tools.accountType}}'\n            currency: '{{tools.currency}}'\n            productId: '{{tools.productId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-detail\n      path: /holdings/accounts/{accountId}\n      description: Single account operations\n      operations:\n      - name: get-account\n        method: GET\n        description: Get account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update account\
  \ arrangement\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-balances\n      path: /holdings/accounts/{accountId}/balances\n      description: Account balance information\n      operations:\n      - name: get-account-balances\n        method: GET\n        description: Get account balances\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-transactions\n      path:\
  \ /holdings/accounts/{accountId}/transactions\n      description: Account transaction history\n      operations:\n      - name: list-account-transactions\n        method: GET\n        description: List account transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /party/customers\n      description: Customer management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        \
  \  description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create new customer\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            customerType: '{{tools.customerType}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-detail\n      path: /party/customers/{customerId}\n      description: Single customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get customer details\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Unique\
  \ customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-orders\n      path: /order/paymentOrders\n      description: Payment order management\n      operations:\n      - name: list-payment-orders\n        method: GET\n        description: List payment orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-order\n        method: POST\n        description: Create payment order\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            creditAccountId: '{{tools.creditAccountId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n\
  \            paymentType: '{{tools.paymentType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: payments\n    baseUri: https://api.temenos.com/payments/v1\n    description: Temenos Payments API for multi-type payment processing\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_PAYMENTS_TOKEN}}'\n    resources:\n    - name: payment-orders\n      path: /paymentOrders\n      description: Payment order initiation and management\n      operations:\n      - name: list-payment-orders\n        method: GET\n        description: List payment orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: paymentType\n          in: query\n          type: string\n          required: false\n          description: Filter by payment type\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-order\n        method: POST\n        description: Initiate a payment order\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            paymentType: '{{tools.paymentType}}'\n            beneficiary: '{{tools.beneficiary}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-payments\n      path: /bulkPayments\n      description: Bulk payment file processing\n      operations:\n      - name: list-bulk-payments\n        method: GET\n        description: List bulk payment batches\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bulk-payment\n        method: POST\n        description: Create a bulk payment batch\n        body:\n          type: json\n          data:\n            batchReference: '{{tools.batchReference}}'\n            debitAccountId: '{{tools.debitAccountId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: standing-orders\n      path: /standingOrders\n      description: Recurring payment standing orders\n      operations:\n      - name: list-standing-orders\n        method: GET\n        description: List standing orders\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-standing-order\n        method: POST\n        description: Create a standing order\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            amount: '{{tools.amount}}'\n            frequency: '{{tools.frequency}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: direct-debits\n      path: /directDebits\n      description: Direct debit mandate management\n      operations:\n      - name: list-direct-debits\n        method: GET\n        description: List direct debit mandates\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: core-banking-api\n    description: Unified REST API for Temenos core banking operations.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Customer account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List customer accounts\n        call: transact.list-accounts\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create a new account arrangement\n        call: transact.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account-detail\n      description: Single account operations\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account details\n\
  \        call: transact.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/balances\n      name: account-balances\n      description: Account balance information\n      operations:\n      - method: GET\n        name: get-balances\n        description: Get account balances\n        call: transact.get-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: account-transactions\n      description: Account transaction history\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List account transactions\n        call: transact.list-account-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/customers\n      name: customers\n      description: Customer management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List customers\n        call: transact.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer\n        call: transact.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer-detail\n      description: Single customer operations\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get customer details\n        call: transact.get-customer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-orders\n      name: payment-orders\n      description: Payment\
  \ order management\n      operations:\n      - method: GET\n        name: list-payment-orders\n        description: List payment orders\n        call: payments.list-payment-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment-order\n        description: Create a payment order\n        call: payments.create-payment-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/standing-orders\n      name: standing-orders\n      description: Recurring standing orders\n      operations:\n      - method: GET\n        name: list-standing-orders\n        description: List standing orders\n        call: payments.list-standing-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-standing-order\n        description: Create a standing order\n        call: payments.create-standing-order\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/direct-debits\n      name: direct-debits\n      description: Direct debit mandates\n      operations:\n      - method: GET\n        name: list-direct-debits\n        description: List direct debit mandates\n        call: payments.list-direct-debits\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: core-banking-mcp\n    transport: http\n    description: MCP server for AI-assisted core banking operations.\n    tools:\n    - name: list-accounts\n      description: List banking accounts for a customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.list-accounts\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get details for a specific bank account\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: transact.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balances\n      description: Get current balances for a bank account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.get-account-balances\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-account-transactions\n      description: List transaction history for a bank account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.list-account-transactions\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-account\n      description: Create a new banking account arrangement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ transact.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List banking customers\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get customer details\n      hints:\n        readOnly: true\n        openWorld: false\n      call: transact.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new banking customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: transact.create-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-orders\n      description: List payment orders\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: payments.list-payment-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment-order\n      description: Create a new payment order (SEPA, SWIFT, domestic)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: payments.create-payment-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-standing-orders\n      description: List recurring standing orders\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payments.list-standing-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-standing-order\n      description: Set up a new recurring standing order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: payments.create-standing-order\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: list-direct-debits\n      description: List direct debit mandates\n      hints:\n        readOnly: true\n        openWorld: false\n      call: payments.list-direct-debits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
