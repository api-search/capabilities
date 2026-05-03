---
categories: []
consumed_apis:
- wells-fargo-gateway
- wells-fargo-transactions
- wells-fargo-ach
description: Unified treasury management capability combining the Wells Fargo Gateway API, Account Transactions API, and ACH Payments API. Enables commercial banking customers, treasury managers, and ERP systems to manage accounts, initiate payments across multiple rails, monitor transaction activity, and process ACH batch payables and receivables through a single integrated interface.
layout: capability
name: Wells Fargo Commercial Banking Treasury
operations:
- description: List all accounts for the authenticated commercial customer.
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get current and available balances for an account.
  method: GET
  name: get-balances
  path: /v1/accounts/{accountId}/balances
- description: List account transactions via Gateway.
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: List detailed transaction history for an account.
  method: GET
  name: list-account-transactions
  path: /v1/accounts/{accountId}/transactions
- description: List payments initiated through the Gateway.
  method: GET
  name: list-payments
  path: /v1/payments
- description: Initiate a payment via Gateway.
  method: POST
  name: create-payment
  path: /v1/payments
- description: List ACH payments.
  method: GET
  name: list-ach-payments
  path: /v1/ach-payments
- description: Initiate an ACH credit or debit payment.
  method: POST
  name: initiate-ach-payment
  path: /v1/ach-payments
- description: Submit a batch ACH payment file.
  method: POST
  name: submit-ach-batch
  path: /v1/ach-batches
- description: List ACH returns and NOCs.
  method: GET
  name: list-ach-returns
  path: /v1/ach-returns
personas: []
provider_name: wells-fargo
provider_slug: wells-fargo
search_terms:
- list ach payments
- initiate an ach credit or debit payment.
- list ach payments.
- list payments
- search detailed transaction history for a wells fargo account (up to 180 days). supports ach, wire, rtp, and fednow transaction types.
- commercial banking
- gateway payment management.
- get real-time ledger and available balance for a wells fargo account.
- initiate ach payment
- ach return and noc management.
- get ach payment status
- list all accounts for the authenticated commercial customer.
- cancel ach payment
- list ach returns and notifications of change (noc) for monitoring payment exceptions.
- get account balance
- list ach returns
- list account transactions
- list transactions
- financial services
- open banking
- create payment
- ach batch file processing.
- get balances
- real-time account balance information.
- submit a batch ach payment file with multiple credit or debit transactions.
- banking
- submit ach batch
- commercial bank account management.
- cancel a pending ach payment before it is submitted to the ach network.
- list commercial accounts
- list account transactions via gateway.
- payments
- list gateway payments
- detailed transaction reporting (up to 180 days).
- list payment history from the wells fargo gateway platform.
- initiate a payment via gateway.
- search transactions
- list detailed transaction history for an account.
- submit a batch ach payment file.
- list accounts
- list ach payment history and status.
- list payments initiated through the gateway.
- ach payment initiation and tracking.
- get current status and settlement details of an ach payment.
- account transaction history (gateway).
- ach
- get current and available balances for an account.
- list ach returns and nocs.
- initiate a single ach credit or debit payment via wells fargo. supports ccd, ctx, ppd, and web transaction codes.
- get full detail for a specific wells fargo transaction.
- get transaction detail
- initiate gateway payment
- treasury management
- initiate a payment via wells fargo gateway (supports intelligent routing to rtp/fednow/ach).
- list all wells fargo commercial bank accounts for the authenticated customer.
slug: commercial-banking-treasury
source_filename: commercial-banking-treasury.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Wells Fargo Commercial Banking Treasury\"\n  description: >-\n    Unified treasury management capability combining the Wells Fargo Gateway API,\n    Account Transactions API, and ACH Payments API. Enables commercial banking\n    customers, treasury managers, and ERP systems to manage accounts, initiate\n    payments across multiple rails, monitor transaction activity, and process\n    ACH batch payables and receivables through a single integrated interface.\n  tags:\n    - Banking\n    - Financial Services\n    - Treasury Management\n    - Commercial Banking\n    - Payments\n    - ACH\n    - Open Banking\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WELLS_FARGO_GATEWAY_TOKEN: WELLS_FARGO_GATEWAY_TOKEN\n      WELLS_FARGO_TRANSACTIONS_TOKEN: WELLS_FARGO_TRANSACTIONS_TOKEN\n      WELLS_FARGO_ACH_TOKEN: WELLS_FARGO_ACH_TOKEN\n\ncapability:\n  consumes:\n    - import: wells-fargo-gateway\n\
  \      location: ./shared/gateway-api.yaml\n    - import: wells-fargo-transactions\n      location: ./shared/account-transactions-api.yaml\n    - import: wells-fargo-ach\n      location: ./shared/ach-payments-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wells-fargo-treasury-api\n      description: \"Unified REST API for Wells Fargo commercial banking treasury management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Commercial bank account management.\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all accounts for the authenticated commercial customer.\"\n              call: \"wells-fargo-transactions.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/balances\n          name: balances\n          description: \"Real-time\
  \ account balance information.\"\n          operations:\n            - method: GET\n              name: get-balances\n              description: \"Get current and available balances for an account.\"\n              call: \"wells-fargo-transactions.get-account-balances\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions\n          name: transactions\n          description: \"Account transaction history (Gateway).\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List account transactions via Gateway.\"\n              call: \"wells-fargo-gateway.list-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/transactions\n\
  \          name: account-transactions\n          description: \"Detailed transaction reporting (up to 180 days).\"\n          operations:\n            - method: GET\n              name: list-account-transactions\n              description: \"List detailed transaction history for an account.\"\n              call: \"wells-fargo-transactions.list-account-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments\n          name: payments\n          description: \"Gateway payment management.\"\n          operations:\n            - method: GET\n              name: list-payments\n              description: \"List payments initiated through the Gateway.\"\n              call: \"wells-fargo-gateway.list-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n\
  \              name: create-payment\n              description: \"Initiate a payment via Gateway.\"\n              call: \"wells-fargo-gateway.create-payment\"\n              with:\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n                recipient_account: \"rest.recipientAccount\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ach-payments\n          name: ach-payments\n          description: \"ACH payment initiation and tracking.\"\n          operations:\n            - method: GET\n              name: list-ach-payments\n              description: \"List ACH payments.\"\n              call: \"wells-fargo-ach.list-ach-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: initiate-ach-payment\n              description:\
  \ \"Initiate an ACH credit or debit payment.\"\n              call: \"wells-fargo-ach.initiate-ach-payment\"\n              with:\n                debit_account_id: \"rest.debitAccountId\"\n                amount: \"rest.amount\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ach-batches\n          name: ach-batches\n          description: \"ACH batch file processing.\"\n          operations:\n            - method: POST\n              name: submit-ach-batch\n              description: \"Submit a batch ACH payment file.\"\n              call: \"wells-fargo-ach.submit-ach-batch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ach-returns\n          name: ach-returns\n          description: \"ACH return and NOC management.\"\n          operations:\n            - method: GET\n              name: list-ach-returns\n              description:\
  \ \"List ACH returns and NOCs.\"\n              call: \"wells-fargo-ach.list-ach-returns\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wells-fargo-treasury-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Wells Fargo commercial banking treasury management.\"\n      tools:\n        - name: list-commercial-accounts\n          description: \"List all Wells Fargo commercial bank accounts for the authenticated customer.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-transactions.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account-balance\n          description: \"Get real-time ledger and available balance for a Wells Fargo account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n  \
  \        call: \"wells-fargo-transactions.get-account-balances\"\n          with:\n            accountId: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-transactions\n          description: \"Search detailed transaction history for a Wells Fargo account (up to 180 days). Supports ACH, Wire, RTP, and FedNow transaction types.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-transactions.list-account-transactions\"\n          with:\n            accountId: \"tools.account_id\"\n            startDate: \"tools.start_date\"\n            endDate: \"tools.end_date\"\n            transactionType: \"tools.transaction_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-transaction-detail\n          description: \"Get full detail for a specific Wells Fargo transaction.\"\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-transactions.get-transaction-detail\"\n          with:\n            accountId: \"tools.account_id\"\n            transactionId: \"tools.transaction_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: initiate-gateway-payment\n          description: \"Initiate a payment via Wells Fargo Gateway (supports intelligent routing to RTP/FedNow/ACH).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wells-fargo-gateway.create-payment\"\n          with:\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            recipient_account: \"tools.recipient_account\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-gateway-payments\n   \
  \       description: \"List payment history from the Wells Fargo Gateway platform.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-gateway.list-payments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: initiate-ach-payment\n          description: \"Initiate a single ACH credit or debit payment via Wells Fargo. Supports CCD, CTX, PPD, and WEB transaction codes.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wells-fargo-ach.initiate-ach-payment\"\n          with:\n            debit_account_id: \"tools.debit_account_id\"\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            credit_account_number: \"tools.credit_account_number\"\n            credit_routing_number: \"tools.credit_routing_number\"\n            receiver_name: \"tools.receiver_name\"\n \
  \           same_day: \"tools.same_day_ach\"\n            effective_date: \"tools.effective_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ach-payments\n          description: \"List ACH payment history and status.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-ach.list-ach-payments\"\n          with:\n            startDate: \"tools.start_date\"\n            endDate: \"tools.end_date\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-ach-payment-status\n          description: \"Get current status and settlement details of an ACH payment.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-ach.get-ach-payment\"\n          with:\n            paymentId: \"tools.payment_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-ach-payment\n          description: \"Cancel a pending ACH payment before it is submitted to the ACH network.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wells-fargo-ach.cancel-ach-payment\"\n          with:\n            paymentId: \"tools.payment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-ach-batch\n          description: \"Submit a batch ACH payment file with multiple credit or debit transactions.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wells-fargo-ach.submit-ach-batch\"\n          with:\n            company_name: \"tools.company_name\"\n            effective_date: \"tools.effective_date\"\n            transactions: \"tools.transactions\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-ach-returns\n          description: \"List ACH returns and Notifications of Change (NOC) for monitoring payment exceptions.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wells-fargo-ach.list-ach-returns\"\n          with:\n            startDate: \"tools.start_date\"\n            endDate: \"tools.end_date\"\n            returnType: \"tools.return_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wells-fargo/refs/heads/main/capabilities/commercial-banking-treasury.yaml
tags:
- Banking
- Financial Services
- Treasury Management
- Commercial Banking
- Payments
- ACH
- Open Banking
tools:
- description: List all Wells Fargo commercial bank accounts for the authenticated customer.
  hints:
    openWorld: false
    readOnly: true
  name: list-commercial-accounts
- description: Get real-time ledger and available balance for a Wells Fargo account.
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balance
- description: Search detailed transaction history for a Wells Fargo account (up to 180 days). Supports ACH, Wire, RTP, and FedNow transaction types.
  hints:
    openWorld: false
    readOnly: true
  name: search-transactions
- description: Get full detail for a specific Wells Fargo transaction.
  hints:
    openWorld: false
    readOnly: true
  name: get-transaction-detail
- description: Initiate a payment via Wells Fargo Gateway (supports intelligent routing to RTP/FedNow/ACH).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiate-gateway-payment
- description: List payment history from the Wells Fargo Gateway platform.
  hints:
    openWorld: false
    readOnly: true
  name: list-gateway-payments
- description: Initiate a single ACH credit or debit payment via Wells Fargo. Supports CCD, CTX, PPD, and WEB transaction codes.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiate-ach-payment
- description: List ACH payment history and status.
  hints:
    openWorld: false
    readOnly: true
  name: list-ach-payments
- description: Get current status and settlement details of an ACH payment.
  hints:
    openWorld: false
    readOnly: true
  name: get-ach-payment-status
- description: Cancel a pending ACH payment before it is submitted to the ACH network.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-ach-payment
- description: Submit a batch ACH payment file with multiple credit or debit transactions.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-ach-batch
- description: List ACH returns and Notifications of Change (NOC) for monitoring payment exceptions.
  hints:
    openWorld: false
    readOnly: true
  name: list-ach-returns
---
