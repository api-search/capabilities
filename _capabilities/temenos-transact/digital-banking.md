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
- list customers
- get account balance information
- cancel a pending payment order
- get account
- list accounts
- list available currencies
- get account details by id
- digital banking
- get customer details
- cancel payment order
- get account details
- payments
- submit a payment order
- register a new payment beneficiary
- get account balances
- list banking products from the catalog
- create a customer
- financial services
- list deposits
- list loans
- initiate a fund transfer between accounts
- list debit and credit cards
- enterprise
- temenos
- list customer accounts with optional filters
- transaction history
- get customer
- account balances
- list loan arrangements
- validate iban
- create customer
- get customer accounts
- account management
- customer management
- fund transfers
- validate an iban and resolve bank details
- get fund transfer
- account details
- list deposit arrangements
- create fund transfer
- list payment orders
- create payment order
- list cards
- get transaction history for an account
- payment operations
- banking
- list accounts for a customer
- list payment beneficiaries
- get transaction history
- create a payment order
- list customer accounts
- initiate a fund transfer
- fintech
- create beneficiary
- list products
- get account transactions
- core banking
- get fund transfer status and details
- list beneficiaries
- list currencies
- create a new customer
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
