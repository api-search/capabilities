---
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
- list bank of america cashpro accounts for the authenticated client
- finance
- list statements
- get account balances
- corporate treasury operations including account management, payments, and reporting
- payments
- list available bank of america account statements
- payment management
- Treasury Analyst
- executive responsible for corporate cash and liquidity management
- analyst managing day-to-day treasury operations and reporting
- list transactions for a bank of america account within a date range
- system integration connecting erp/tms to bank of america cashpro apis
- initiate payment
- get the current status of a bank of america payment
- list bofa accounts
- Corporate Treasurer
- payment initiation and tracking across 350+ payment types
- get payment status
- list cashpro accounts
- initiate a payment
- treasury
- account management
- corporate banking
- cashpro
- initiate a payment through bank of america cashpro (supports 350+ payment types)
- get current and available balances for a cashpro account
- ERP Integration
- corporate cash management, balance reporting, and liquidity
- banking
- list accounts
- list account transactions
- bank of america
slug: treasury-banking
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
