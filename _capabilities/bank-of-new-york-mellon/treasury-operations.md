---
categories:
- payments
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
- get the status and details of a bny mellon payment
- list transactions
- get current and available balances for a bny mellon account
- treasury
- analyst executing treasury transactions and reporting
- list bny accounts
- executive managing corporate liquidity and treasury operations
- get account balances
- initiate funds transfer
- wire transfers
- institutional banking
- banking
- initiate payment
- institutional account management and cash positioning
- Corporate Treasurer
- initiate a payment (wire, ach, swift, chips) through bny mellon
- initiate a funds transfer between bny mellon accounts
- bny mellon
- Treasury Analyst
- get payment status
- list transactions for a bny mellon account
- wire, ach, swift, and chips payment execution
- Institutional Client
- payments
- asset servicing
- institutional treasury operations including accounts, payments, and funds transfers
- internal funds transfers and liquidity management
- institutional investor or fund manager using bny custody and treasury services
- list bny mellon treasury accounts for the authenticated client
slug: treasury-operations
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
