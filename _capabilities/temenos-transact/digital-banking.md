---
categories:
- payments
consumed_apis: []
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
- create fund transfer
- payment operations
- account management
- account details
- get account details
- list deposit arrangements
- list payment orders
- initiate a fund transfer between accounts
- get customer
- create beneficiary
- temenos
- financial services
- get account balances
- register a new payment beneficiary
- account balances
- get fund transfer
- create a new customer
- list banking products from the catalog
- get account balance information
- list available currencies
- customer management
- list currencies
- validate an iban and resolve bank details
- fund transfers
- enterprise
- core banking
- cancel payment order
- get transaction history
- get customer details
- get fund transfer status and details
- transaction history
- cancel a pending payment order
- list customer accounts with optional filters
- list accounts for a customer
- initiate a fund transfer
- list deposits
- list loan arrangements
- list payment beneficiaries
- list loans
- create customer
- list cards
- create a payment order
- list beneficiaries
- list customer accounts
- payments
- get customer accounts
- create a customer
- list customers
- validate iban
- create payment order
- get account transactions
- list products
- get account details by id
- list accounts
- digital banking
- submit a payment order
- get account
- get transaction history for an account
- banking
- list debit and credit cards
- fintech
slug: digital-banking
source_filename: digital-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Temenos Digital Banking\n  description: Unified digital banking capability combining account management, customer operations, payment processing, deposits,\n    loans, and reference data for retail and corporate banking applications. Used by digital banking developers and fintech\n    integration teams.\n  tags:\n  - Temenos\n  - Digital Banking\n  - Core Banking\n  - Payments\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMENOS_BEARER_TOKEN: TEMENOS_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: core-banking\n    baseUri: https://api.temenos.com/api/v1.0.0\n    description: Temenos Transact Core Banking API for accounts, customers, payments, deposits, loans, and reference data.\n    authentication:\n      type: bearer\n      token: '{{TEMENOS_BEARER_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /holdings/accounts\n      description: Customer account management\n\
  \      operations:\n      - name: list-accounts\n        method: GET\n        description: Retrieve a list of customer accounts\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter by customer identifier\n        - name: accountType\n          in: query\n          type: string\n          required: false\n          description: Filter by account type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Retrieve account details by ID\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PUT\n        description: Update an existing account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountName: '{{tools.accountName}}'\n      - name: get-account-balances\n        method: GET\n        description: Retrieve balance information for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: get-account-transactions\n        method: GET\n        description: Retrieve transaction history for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /party/customers\n      description: Customer profile management\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve a list of customers\n        inputParameters:\n\
  \        - name: customerName\n          in: query\n          type: string\n          required: false\n          description: Filter by customer name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            shortName: '{{tools.shortName}}'\n            customerMnemonic: '{{tools.customerMnemonic}}'\n            sectorId: '{{tools.sectorId}}'\n      - name: get-customer\n        method: GET\n        description: Retrieve customer details\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PUT\n        description: Update customer details\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerNames: '{{tools.customerNames}}'\n      - name: get-customer-accounts\n        method: GET\n        description: Retrieve accounts for a customer\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: payments\n      path: /order\n      description: Payment processing operations\n      operations:\n      - name: create-fund-transfer\n        method: POST\n        description: Initiate a fund transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            creditAccountId: '{{tools.creditAccountId}}'\n            amount: '{{tools.amount}}'\n      - name: get-fund-transfer\n        method: GET\n        description: Get fund transfer details\n        inputParameters:\n        - name: transferId\n          in: path\n          type: string\n          required: true\n          description: Transfer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-payment-orders\n \
  \       method: GET\n        description: List payment orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-order\n        method: POST\n        description: Create a payment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            debitAccountId: '{{tools.debitAccountId}}'\n            debitAmount: '{{tools.debitAmount}}'\n      - name: get-payment-order\n        method: GET\n        description: Get payment order details\n        inputParameters:\n        - name: paymentOrderId\n          in: path\n          type: string\n          required: true\n          description: Payment order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ cancel-payment-order\n        method: POST\n        description: Cancel a payment order\n        inputParameters:\n        - name: paymentOrderId\n          in: path\n          type: string\n          required: true\n          description: Payment order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-standing-orders\n        method: GET\n        description: List standing orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-standing-order\n        method: POST\n        description: Create a standing order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.accountId}}'\n            amount: '{{tools.amount}}'\n     \
  \       frequency: '{{tools.frequency}}'\n    - name: deposits\n      path: /holdings/deposits\n      description: Deposit arrangement management\n      operations:\n      - name: list-deposits\n        method: GET\n        description: List deposit arrangements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deposit\n        method: GET\n        description: Get deposit details\n        inputParameters:\n        - name: depositId\n          in: path\n          type: string\n          required: true\n          description: Deposit identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: loans\n      path: /holdings/loans\n      description: Loan arrangement management\n      operations:\n      - name: list-loans\n        method: GET\n        description: List loan arrangements\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-loan\n        method: GET\n        description: Get loan details\n        inputParameters:\n        - name: loanId\n          in: path\n          type: string\n          required: true\n          description: Loan identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: beneficiaries\n      path: /party/beneficiaries\n      description: Payment beneficiary management\n      operations:\n      - name: list-beneficiaries\n        method: GET\n        description: List registered beneficiaries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-beneficiary\n        method: POST\n        description: Register a new beneficiary\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            beneficiaryName: '{{tools.beneficiaryName}}'\n    - name: products\n      path: /product/products\n      description: Product catalog\n      operations:\n      - name: list-products\n        method: GET\n        description: List banking products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reference\n      path: /reference\n      description: Reference data\n      operations:\n      - name: list-currencies\n        method: GET\n        description: List available currencies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-countries\n        method: GET\n        description: List available countries\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-iban\n        method: GET\n        description: Validate an IBAN\n        inputParameters:\n        - name: iban\n          in: path\n          type: string\n          required: true\n          description: IBAN to validate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /holdings/cards\n      description: Card management\n      operations:\n      - name: list-cards\n        method: GET\n        description: List debit and credit cards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-card\n        method: GET\n        description: Get card details\n        inputParameters:\n        - name: cardId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Card identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: digital-banking-api\n    description: Unified REST API for digital banking operations.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List customer accounts\n        call: core-banking.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account-details\n      description: Account details\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account details\n        call: core-banking.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/balances\n      name: account-balances\n      description: Account balances\n      operations:\n      - method: GET\n        name: get-account-balances\n        description: Get account balances\n        call: core-banking.get-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: account-transactions\n      description: Transaction history\n      operations:\n      - method: GET\n        name: get-account-transactions\n        description: Get transaction history\n        call: core-banking.get-account-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer management\n      operations:\n      - method: GET\n\
  \        name: list-customers\n        description: List customers\n        call: core-banking.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a customer\n        call: core-banking.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Payment operations\n      operations:\n      - method: GET\n        name: list-payment-orders\n        description: List payment orders\n        call: core-banking.list-payment-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment-order\n        description: Create a payment order\n        call: core-banking.create-payment-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transfers\n      name: transfers\n \
  \     description: Fund transfers\n      operations:\n      - method: POST\n        name: create-fund-transfer\n        description: Initiate a fund transfer\n        call: core-banking.create-fund-transfer\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: digital-banking-mcp\n    transport: http\n    description: MCP server for AI-assisted digital banking operations.\n    tools:\n    - name: list-accounts\n      description: List customer accounts with optional filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: core-banking.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get account details by ID\n      hints:\n        readOnly: true\n      call: core-banking.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balances\n\
  \      description: Get account balance information\n      hints:\n        readOnly: true\n      call: core-banking.get-account-balances\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-transactions\n      description: Get transaction history for an account\n      hints:\n        readOnly: true\n      call: core-banking.get-account-transactions\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List customers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: core-banking.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get customer details\n      hints:\n        readOnly: true\n      call: core-banking.get-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer\n      call: core-banking.create-customer\n      with:\n        shortName: tools.shortName\n        customerMnemonic: tools.customerMnemonic\n        sectorId: tools.sectorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer-accounts\n      description: List accounts for a customer\n      hints:\n        readOnly: true\n      call: core-banking.get-customer-accounts\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-fund-transfer\n      description: Initiate a fund transfer between accounts\n      call: core-banking.create-fund-transfer\n      with:\n        debitAccountId: tools.debitAccountId\n        creditAccountId: tools.creditAccountId\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: get-fund-transfer\n      description: Get fund transfer status and details\n      hints:\n        readOnly: true\n      call: core-banking.get-fund-transfer\n      with:\n        transferId: tools.transferId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-orders\n      description: List payment orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: core-banking.list-payment-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment-order\n      description: Submit a payment order\n      call: core-banking.create-payment-order\n      with:\n        debitAccountId: tools.debitAccountId\n        debitAmount: tools.debitAmount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-payment-order\n      description: Cancel a pending payment order\n      hints:\n        destructive: true\n      call: core-banking.cancel-payment-order\n\
  \      with:\n        paymentOrderId: tools.paymentOrderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deposits\n      description: List deposit arrangements\n      hints:\n        readOnly: true\n      call: core-banking.list-deposits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-loans\n      description: List loan arrangements\n      hints:\n        readOnly: true\n      call: core-banking.list-loans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-beneficiaries\n      description: List payment beneficiaries\n      hints:\n        readOnly: true\n      call: core-banking.list-beneficiaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-beneficiary\n      description: Register a new payment beneficiary\n      call: core-banking.create-beneficiary\n      with:\n        customerId: tools.customerId\n        beneficiaryName: tools.beneficiaryName\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: List banking products from the catalog\n      hints:\n        readOnly: true\n      call: core-banking.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-currencies\n      description: List available currencies\n      hints:\n        readOnly: true\n      call: core-banking.list-currencies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-iban\n      description: Validate an IBAN and resolve bank details\n      hints:\n        readOnly: true\n      call: core-banking.validate-iban\n      with:\n        iban: tools.iban\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cards\n      description: List debit and credit cards\n      hints:\n        readOnly: true\n      call: core-banking.list-cards\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n"
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
