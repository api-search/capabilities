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
- initiate a payment
- list available bank of america account statements
- get the current status of a bank of america payment
- bank of america
- banking
- corporate treasury operations including account management, payments, and reporting
- payment management
- executive responsible for corporate cash and liquidity management
- finance
- corporate cash management, balance reporting, and liquidity
- system integration connecting erp/tms to bank of america cashpro apis
- get current and available balances for a cashpro account
- list bank of america cashpro accounts for the authenticated client
- list bofa accounts
- initiate payment
- corporate banking
- list account transactions
- cashpro
- list accounts
- list transactions for a bank of america account within a date range
- Treasury Analyst
- account management
- get payment status
- ERP Integration
- payment initiation and tracking across 350+ payment types
- payments
- initiate a payment through bank of america cashpro (supports 350+ payment types)
- list statements
- list cashpro accounts
- Corporate Treasurer
- treasury
- get account balances
- analyst managing day-to-day treasury operations and reporting
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
