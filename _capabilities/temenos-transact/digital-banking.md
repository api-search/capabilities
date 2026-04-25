---
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
- get customer accounts
- list customer accounts
- enterprise
- list customers
- get transaction history for an account
- payment operations
- cancel a pending payment order
- initiate a fund transfer between accounts
- validate an iban and resolve bank details
- get account balance information
- get account
- list accounts for a customer
- initiate a fund transfer
- fintech
- register a new payment beneficiary
- create a customer
- fund transfers
- customer management
- list products
- temenos
- create a payment order
- account balances
- create a new customer
- create payment order
- get account balances
- get fund transfer
- get account details by id
- financial services
- account management
- core banking
- list customer accounts with optional filters
- list currencies
- get account transactions
- list payment orders
- list loan arrangements
- list beneficiaries
- digital banking
- get transaction history
- cancel payment order
- create beneficiary
- create fund transfer
- list banking products from the catalog
- list deposit arrangements
- validate iban
- list cards
- get fund transfer status and details
- get account details
- banking
- payments
- get customer details
- list available currencies
- account details
- list deposits
- submit a payment order
- list loans
- create customer
- get customer
- transaction history
- list payment beneficiaries
- list debit and credit cards
- list accounts
slug: digital-banking
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
