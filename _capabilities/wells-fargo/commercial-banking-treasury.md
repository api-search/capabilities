---
categories: []
consumed_apis: []
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
- search transactions
- initiate ach payment
- list gateway payments
- get account balance
- get transaction detail
- list ach returns and notifications of change (noc) for monitoring payment exceptions.
- ach return and noc management.
- list commercial accounts
- list payments initiated through the gateway.
- list ach returns and nocs.
- financial services
- gateway payment management.
- get full detail for a specific wells fargo transaction.
- list all wells fargo commercial bank accounts for the authenticated customer.
- list payment history from the wells fargo gateway platform.
- initiate a payment via gateway.
- list detailed transaction history for an account.
- list ach payment history and status.
- list ach payments.
- cancel a pending ach payment before it is submitted to the ach network.
- treasury management
- list ach payments
- list all accounts for the authenticated commercial customer.
- commercial banking
- list payments
- list account transactions via gateway.
- initiate an ach credit or debit payment.
- cancel ach payment
- commercial bank account management.
- get real-time ledger and available balance for a wells fargo account.
- get current and available balances for an account.
- open banking
- detailed transaction reporting (up to 180 days).
- account transaction history (gateway).
- list account transactions
- search detailed transaction history for a wells fargo account (up to 180 days). supports ach, wire, rtp, and fednow transaction types.
- real-time account balance information.
- ach batch file processing.
- payments
- initiate gateway payment
- submit ach batch
- list ach returns
- get current status and settlement details of an ach payment.
- submit a batch ach payment file.
- initiate a single ach credit or debit payment via wells fargo. supports ccd, ctx, ppd, and web transaction codes.
- list accounts
- submit a batch ach payment file with multiple credit or debit transactions.
- get balances
- create payment
- ach payment initiation and tracking.
- list transactions
- ach
- banking
- get ach payment status
- initiate a payment via wells fargo gateway (supports intelligent routing to rtp/fednow/ach).
slug: commercial-banking-treasury
source_filename: commercial-banking-treasury.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wells Fargo Commercial Banking Treasury\n  description: Unified treasury management capability combining the Wells Fargo Gateway API, Account Transactions API, and\n    ACH Payments API. Enables commercial banking customers, treasury managers, and ERP systems to manage accounts, initiate\n    payments across multiple rails, monitor transaction activity, and process ACH batch payables and receivables through a\n    single integrated interface.\n  tags:\n  - Banking\n  - Financial Services\n  - Treasury Management\n  - Commercial Banking\n  - Payments\n  - ACH\n  - Open Banking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WELLS_FARGO_GATEWAY_TOKEN: WELLS_FARGO_GATEWAY_TOKEN\n    WELLS_FARGO_TRANSACTIONS_TOKEN: WELLS_FARGO_TRANSACTIONS_TOKEN\n    WELLS_FARGO_ACH_TOKEN: WELLS_FARGO_ACH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wells-fargo-gateway\n    baseUri: https://api.wellsfargo.com\n\
  \    description: Wells Fargo Gateway open banking API.\n    authentication:\n      type: bearer\n      token: '{{WELLS_FARGO_GATEWAY_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Account information and balances.\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List accounts for the authenticated commercial customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /payments\n      description: Payment initiation and management.\n      operations:\n      - name: list-payments\n        method: GET\n        description: List payments initiated through the Gateway.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment\n        method: POST\n        description: Initiate a new payment.\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            recipientAccount: '{{tools.recipient_account}}'\n            description: '{{tools.description}}'\n    - name: transactions\n      path: /transactions\n      description: Transaction history retrieval.\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List transactions for a specified account.\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: true\n          description: Account identifier.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter.\n        - name: endDate\n          in: query\n          type: string\n    \
  \      required: false\n          description: End date filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wells-fargo-transactions\n    baseUri: https://api.wellsfargo.com\n    description: Wells Fargo Account Transactions API for treasury reporting.\n    authentication:\n      type: bearer\n      token: '{{WELLS_FARGO_TRANSACTIONS_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /v3/accounts\n      description: Account information.\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List accounts for the authenticated customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-balances\n      path: /v3/accounts/{accountId}/balances\n      description: Real-time account balance information.\n      operations:\n      - name: get-account-balances\n\
  \        method: GET\n        description: Get current and available balances for an account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Wells Fargo account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-transactions\n      path: /v3/accounts/{accountId}/transactions\n      description: Transaction history for an account.\n      operations:\n      - name: list-account-transactions\n        method: GET\n        description: List transactions for an account (up to 180 days).\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Wells Fargo account ID.\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD).\n\
  \        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD).\n        - name: transactionType\n          in: query\n          type: string\n          required: false\n          description: Transaction type filter (ACH, WIRE, RTP, CHECK, FED_NOW).\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-transaction-detail\n        method: GET\n        description: Get details for a specific transaction.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Wells Fargo account ID.\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Unique transaction ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wells-fargo-ach\n    baseUri: https://api.wellsfargo.com\n    description: Wells Fargo ACH Payments API.\n    authentication:\n      type: bearer\n      token: '{{WELLS_FARGO_ACH_TOKEN}}'\n    resources:\n    - name: ach-payments\n      path: /v2/ach/payments\n      description: ACH payment initiation and management.\n      operations:\n      - name: initiate-ach-payment\n        method: POST\n        description: Initiate a single ACH credit or debit transaction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            debitAccountId:\
  \ '{{tools.debit_account_id}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            creditAccountNumber: '{{tools.credit_account_number}}'\n            creditRoutingNumber: '{{tools.credit_routing_number}}'\n            creditAccountType: '{{tools.credit_account_type}}'\n            transactionCode: '{{tools.transaction_code}}'\n            receiverName: '{{tools.receiver_name}}'\n            addendaInformation: '{{tools.addenda}}'\n            sameDayAch: '{{tools.same_day}}'\n            effectiveDate: '{{tools.effective_date}}'\n      - name: list-ach-payments\n        method: GET\n        description: List ACH payments.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter.\n        - name: status\n\
  \          in: query\n          type: string\n          required: false\n          description: Status filter.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Page size.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ach-payment\n        method: GET\n        description: Get ACH payment status and details.\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: ACH payment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-ach-payment\n        method: DELETE\n        description: Cancel a pending ACH payment.\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required:\
  \ true\n          description: ACH payment ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ach-batches\n      path: /v2/ach/batches\n      description: Batch ACH payment file submission.\n      operations:\n      - name: submit-ach-batch\n        method: POST\n        description: Submit a batch ACH payment file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            companyName: '{{tools.company_name}}'\n            effectiveDate: '{{tools.effective_date}}'\n            transactions: '{{tools.transactions}}'\n    - name: ach-returns\n      path: /v2/ach/returns\n      description: ACH return and NOC processing.\n      operations:\n      - name: list-ach-returns\n        method: GET\n        description: List ACH returns and NOCs.\n        inputParameters:\n\
  \        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date.\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date.\n        - name: returnType\n          in: query\n          type: string\n          required: false\n          description: Return type (RETURN or NOC).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wells-fargo-treasury-api\n    description: Unified REST API for Wells Fargo commercial banking treasury management.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Commercial bank account management.\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all accounts for the authenticated commercial customer.\n    \
  \    call: wells-fargo-transactions.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/balances\n      name: balances\n      description: Real-time account balance information.\n      operations:\n      - method: GET\n        name: get-balances\n        description: Get current and available balances for an account.\n        call: wells-fargo-transactions.get-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Account transaction history (Gateway).\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List account transactions via Gateway.\n        call: wells-fargo-gateway.list-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: account-transactions\n      description: Detailed transaction reporting (up to 180 days).\n      operations:\n      - method: GET\n        name: list-account-transactions\n        description: List detailed transaction history for an account.\n        call: wells-fargo-transactions.list-account-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Gateway payment management.\n      operations:\n      - method: GET\n        name: list-payments\n        description: List payments initiated through the Gateway.\n        call: wells-fargo-gateway.list-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment\n        description: Initiate a payment via Gateway.\n        call: wells-fargo-gateway.create-payment\n\
  \        with:\n          amount: rest.amount\n          currency: rest.currency\n          recipient_account: rest.recipientAccount\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ach-payments\n      name: ach-payments\n      description: ACH payment initiation and tracking.\n      operations:\n      - method: GET\n        name: list-ach-payments\n        description: List ACH payments.\n        call: wells-fargo-ach.list-ach-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: initiate-ach-payment\n        description: Initiate an ACH credit or debit payment.\n        call: wells-fargo-ach.initiate-ach-payment\n        with:\n          debit_account_id: rest.debitAccountId\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ach-batches\n      name: ach-batches\n    \
  \  description: ACH batch file processing.\n      operations:\n      - method: POST\n        name: submit-ach-batch\n        description: Submit a batch ACH payment file.\n        call: wells-fargo-ach.submit-ach-batch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ach-returns\n      name: ach-returns\n      description: ACH return and NOC management.\n      operations:\n      - method: GET\n        name: list-ach-returns\n        description: List ACH returns and NOCs.\n        call: wells-fargo-ach.list-ach-returns\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wells-fargo-treasury-mcp\n    transport: http\n    description: MCP server for AI-assisted Wells Fargo commercial banking treasury management.\n    tools:\n    - name: list-commercial-accounts\n      description: List all Wells Fargo commercial bank accounts for the authenticated customer.\n      hints:\n     \
  \   readOnly: true\n        openWorld: false\n      call: wells-fargo-transactions.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balance\n      description: Get real-time ledger and available balance for a Wells Fargo account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-transactions.get-account-balances\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-transactions\n      description: Search detailed transaction history for a Wells Fargo account (up to 180 days). Supports ACH, Wire, RTP,\n        and FedNow transaction types.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-transactions.list-account-transactions\n      with:\n        accountId: tools.account_id\n        startDate: tools.start_date\n        endDate: tools.end_date\n        transactionType:\
  \ tools.transaction_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction-detail\n      description: Get full detail for a specific Wells Fargo transaction.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-transactions.get-transaction-detail\n      with:\n        accountId: tools.account_id\n        transactionId: tools.transaction_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-gateway-payment\n      description: Initiate a payment via Wells Fargo Gateway (supports intelligent routing to RTP/FedNow/ACH).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wells-fargo-gateway.create-payment\n      with:\n        amount: tools.amount\n        currency: tools.currency\n        recipient_account: tools.recipient_account\n        description: tools.description\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-gateway-payments\n      description: List payment history from the Wells Fargo Gateway platform.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-gateway.list-payments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiate-ach-payment\n      description: Initiate a single ACH credit or debit payment via Wells Fargo. Supports CCD, CTX, PPD, and WEB transaction\n        codes.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wells-fargo-ach.initiate-ach-payment\n      with:\n        debit_account_id: tools.debit_account_id\n        amount: tools.amount\n        currency: tools.currency\n        credit_account_number: tools.credit_account_number\n        credit_routing_number: tools.credit_routing_number\n        receiver_name: tools.receiver_name\n        same_day: tools.same_day_ach\n        effective_date: tools.effective_date\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ach-payments\n      description: List ACH payment history and status.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-ach.list-ach-payments\n      with:\n        startDate: tools.start_date\n        endDate: tools.end_date\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ach-payment-status\n      description: Get current status and settlement details of an ACH payment.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-ach.get-ach-payment\n      with:\n        paymentId: tools.payment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-ach-payment\n      description: Cancel a pending ACH payment before it is submitted to the ACH network.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: wells-fargo-ach.cancel-ach-payment\n      with:\n        paymentId: tools.payment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-ach-batch\n      description: Submit a batch ACH payment file with multiple credit or debit transactions.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wells-fargo-ach.submit-ach-batch\n      with:\n        company_name: tools.company_name\n        effective_date: tools.effective_date\n        transactions: tools.transactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ach-returns\n      description: List ACH returns and Notifications of Change (NOC) for monitoring payment exceptions.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: wells-fargo-ach.list-ach-returns\n      with:\n        startDate: tools.start_date\n        endDate: tools.end_date\n        returnType:\
  \ tools.return_type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
