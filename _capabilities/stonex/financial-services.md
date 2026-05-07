---
categories: []
consumed_apis: []
description: Unified financial services workflow combining StoneX cross-border payments and institutional clearing operations. Enables financial institutions, corporate treasuries, and institutional traders to execute FX payments, monitor clearing accounts, manage positions, and submit trades through a single integrated interface.
layout: capability
name: StoneX Financial Services
operations:
- description: Initiate a cross-border payment in 140+ currencies.
  method: POST
  name: create-payment
  path: /v1/payments
- description: List payments with status and date filters.
  method: GET
  name: list-payments
  path: /v1/payments
- description: Get details of a specific payment.
  method: GET
  name: get-payment
  path: /v1/payments/{paymentId}
- description: Get indicative FX rates for a currency pair.
  method: GET
  name: get-fx-rates
  path: /v1/fx-rates
- description: List clearing accounts.
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get current positions for a clearing account.
  method: GET
  name: get-account-positions
  path: /v1/accounts/{accountId}/positions
- description: Get cash, margin, and P&L balances.
  method: GET
  name: get-account-balances
  path: /v1/accounts/{accountId}/balances
- description: Submit a trade for clearing and settlement.
  method: POST
  name: submit-trade
  path: /v1/trades
- description: List trades with filters.
  method: GET
  name: list-trades
  path: /v1/trades
- description: List clearing documents.
  method: GET
  name: list-documents
  path: /v1/documents
personas: []
provider_name: StoneX
provider_slug: stonex
search_terms:
- list clearing accounts.
- payments get fx rates
- institutional clearing accounts.
- submit trade
- submit a trade for clearing and settlement.
- clearing documents.
- get fx rates
- get cash, margin, and p&l balances.
- get indicative fx exchange rates for a currency pair. use for pre-payment rate discovery or treasury rate monitoring.
- list clearing documents including trade confirmations and statements. use for compliance, audit, or client reporting.
- get indicative fx rates for a currency pair.
- list clearing documents.
- futures
- list trades with account, status, and date filters. use for trade reconciliation, settlement monitoring, or reporting.
- list trades with filters.
- list accounts
- list cross-border payments with status and date filters. use to monitor payment pipeline, reconcile transactions, or generate reports.
- get account balances
- clearing get balances
- create payment
- foreign exchange rate queries.
- get payment
- account position data.
- trade submission and management.
- list payments with status and date filters.
- get details of a specific payment.
- finance
- payments create payment
- get details and current status of a specific payment.
- get current open positions for a clearing account. use for risk management, p&l monitoring, or portfolio reporting.
- financial services
- trading
- payments list payments
- fx
- institutional
- get account positions
- get current positions for a clearing account.
- list trades
- payments get payment
- clearing
- initiate a cross-border payment through stonex in 140+ currencies. use for corporate treasury fx payments, international supplier payments, or global settlements.
- list institutional clearing accounts. use to discover available accounts for trading or reporting.
- clearing get positions
- clearing list trades
- submit a trade for clearing and settlement through stonex. use for programmatic trade entry or algorithmic trading workflows.
- initiate a cross-border payment in 140+ currencies.
- cross-border payment initiation and tracking.
- payments
- clearing list documents
- list documents
- clearing list accounts
- individual payment operations.
- account balance data.
- clearing submit trade
- risk management
- list payments
- get cash, margin, and p&l balances for a clearing account. use for margin monitoring, risk management, or daily reconciliation.
slug: financial-services
source_filename: financial-services.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StoneX Financial Services\n  description: Unified financial services workflow combining StoneX cross-border payments and institutional clearing operations.\n    Enables financial institutions, corporate treasuries, and institutional traders to execute FX payments, monitor clearing\n    accounts, manage positions, and submit trades through a single integrated interface.\n  tags:\n  - Finance\n  - Financial Services\n  - Payments\n  - Clearing\n  - Trading\n  - FX\n  - Institutional\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STONEX_PAYMENTS_CLIENT_ID: STONEX_PAYMENTS_CLIENT_ID\n    STONEX_PAYMENTS_CLIENT_SECRET: STONEX_PAYMENTS_CLIENT_SECRET\n    STONEX_PAYMENTS_ACCESS_TOKEN: STONEX_PAYMENTS_ACCESS_TOKEN\n    STONEX_CLEARING_CLIENT_ID: STONEX_CLEARING_CLIENT_ID\n    STONEX_CLEARING_CLIENT_SECRET: STONEX_CLEARING_CLIENT_SECRET\n    STONEX_CLEARING_ACCESS_TOKEN: STONEX_CLEARING_ACCESS_TOKEN\n\
  capability:\n  consumes:\n  - type: http\n    namespace: stonex-payments\n    baseUri: https://fx-api.payments.stonex.com\n    description: StoneX Payments API for cross-border payments and FX rates.\n    authentication:\n      type: bearer\n      token: '{{STONEX_PAYMENTS_ACCESS_TOKEN}}'\n    resources:\n    - name: payments\n      path: /payments\n      description: Cross-border payment creation and management.\n      operations:\n      - name: create-payment\n        method: POST\n        description: Initiate a cross-border payment in local currency.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            sell_currency: '{{tools.sell_currency}}'\n            buy_currency: '{{tools.buy_currency}}'\n            beneficiary:\n              name: '{{tools.beneficiary_name}}'\n              country: '{{tools.beneficiary_country}}'\n              account_number: '{{tools.account_number}}'\n              bank_code: '{{tools.bank_code}}'\n\
  \            payment_reference: '{{tools.payment_reference}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-payments\n        method: GET\n        description: List payments with optional status and date filters.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by payment status.\n        - name: currency\n          in: query\n          type: string\n          required: false\n          description: Filter by currency (ISO 4217).\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter.\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: End date filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: payment\n      path: /payments/{paymentId}\n      description: Individual payment retrieval.\n      operations:\n      - name: get-payment\n        method: GET\n        description: Get details of a specific payment by ID.\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Payment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fx-rates\n      path: /rates\n      description: Foreign exchange rates.\n      operations:\n      - name: get-fx-rates\n        method: GET\n        description: Get indicative FX rates for a currency pair.\n        inputParameters:\n        - name: sell_currency\n          in: query\n          type: string\n          required: true\n          description: Source currency (ISO 4217).\n        - name: buy_currency\n\
  \          in: query\n          type: string\n          required: true\n          description: Destination currency (ISO 4217).\n        - name: amount\n          in: query\n          type: number\n          required: false\n          description: Amount to convert.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stonex-clearing\n    baseUri: https://api.clearing.stonex.com\n    description: StoneX Clearing API for institutional account and trade management.\n    authentication:\n      type: bearer\n      token: '{{STONEX_CLEARING_ACCESS_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Clearing account management.\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List clearing accounts accessible to the client.\n        inputParameters:\n        - name: page\n          in: query\n          type:\
  \ integer\n          required: false\n          description: Page number.\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account\n      path: /accounts/{accountId}\n      description: Individual account operations.\n      operations:\n      - name: get-account\n        method: GET\n        description: Get details of a specific clearing account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-positions\n      path: /accounts/{accountId}/positions\n      description: Account position data.\n  \
  \    operations:\n      - name: get-account-positions\n        method: GET\n        description: Get current positions for a clearing account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-balances\n      path: /accounts/{accountId}/balances\n      description: Account balance data.\n      operations:\n      - name: get-account-balances\n        method: GET\n        description: Get cash, margin, and P&L balances for an account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: trades\n      path: /trades\n      description: Trade submission and listing.\n      operations:\n      - name: submit-trade\n        method: POST\n        description: Submit a trade for clearing and settlement.\n        body:\n          type: json\n          data:\n            account_id: '{{tools.account_id}}'\n            symbol: '{{tools.symbol}}'\n            side: '{{tools.side}}'\n            quantity: '{{tools.quantity}}'\n            price: '{{tools.price}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-trades\n        method: GET\n        description: List trades with optional account and status filters.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: false\n          description: Filter by account.\n        - name: status\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by status.\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter.\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: End date filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      description: Clearing document management.\n      operations:\n      - name: list-documents\n        method: GET\n        description: List clearing documents.\n        inputParameters:\n        - name: account_id\n          in: query\n          type: string\n          required: false\n          description: Filter by account.\n        - name: document_type\n          in: query\n          type: string\n          required: false\n          description: Filter by document type.\n        - name:\
  \ from_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter.\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: End date filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stonex-financial-api\n    description: Unified REST API for StoneX cross-border payments, FX rates, clearing accounts, position management, and\n      trade operations.\n    resources:\n    - path: /v1/payments\n      name: payments\n      description: Cross-border payment initiation and tracking.\n      operations:\n      - method: POST\n        name: create-payment\n        description: Initiate a cross-border payment in 140+ currencies.\n        call: stonex-payments.create-payment\n        with:\n          amount: rest.amount\n          sell_currency:\
  \ rest.sell_currency\n          buy_currency: rest.buy_currency\n          beneficiary_name: rest.beneficiary_name\n          account_number: rest.account_number\n          bank_code: rest.bank_code\n          payment_reference: rest.payment_reference\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-payments\n        description: List payments with status and date filters.\n        call: stonex-payments.list-payments\n        with:\n          status: rest.status\n          currency: rest.currency\n          from_date: rest.from_date\n          to_date: rest.to_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}\n      name: payment\n      description: Individual payment operations.\n      operations:\n      - method: GET\n        name: get-payment\n        description: Get details of a specific payment.\n        call: stonex-payments.get-payment\n        with:\n\
  \          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fx-rates\n      name: fx-rates\n      description: Foreign exchange rate queries.\n      operations:\n      - method: GET\n        name: get-fx-rates\n        description: Get indicative FX rates for a currency pair.\n        call: stonex-payments.get-fx-rates\n        with:\n          sell_currency: rest.sell_currency\n          buy_currency: rest.buy_currency\n          amount: rest.amount\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: clearing-accounts\n      description: Institutional clearing accounts.\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List clearing accounts.\n        call: stonex-clearing.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/positions\n      name:\
  \ positions\n      description: Account position data.\n      operations:\n      - method: GET\n        name: get-account-positions\n        description: Get current positions for a clearing account.\n        call: stonex-clearing.get-account-positions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/balances\n      name: balances\n      description: Account balance data.\n      operations:\n      - method: GET\n        name: get-account-balances\n        description: Get cash, margin, and P&L balances.\n        call: stonex-clearing.get-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trades\n      name: trades\n      description: Trade submission and management.\n      operations:\n      - method: POST\n        name: submit-trade\n        description: Submit a trade\
  \ for clearing and settlement.\n        call: stonex-clearing.submit-trade\n        with:\n          account_id: rest.account_id\n          symbol: rest.symbol\n          side: rest.side\n          quantity: rest.quantity\n          price: rest.price\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-trades\n        description: List trades with filters.\n        call: stonex-clearing.list-trades\n        with:\n          account_id: rest.account_id\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents\n      name: documents\n      description: Clearing documents.\n      operations:\n      - method: GET\n        name: list-documents\n        description: List clearing documents.\n        call: stonex-clearing.list-documents\n        with:\n          account_id: rest.account_id\n          document_type: rest.document_type\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: stonex-financial-mcp\n    transport: http\n    description: MCP server for AI-assisted financial operations including FX payment processing, account monitoring, position\n      management, and trade execution.\n    tools:\n    - name: payments-create-payment\n      description: Initiate a cross-border payment through StoneX in 140+ currencies. Use for corporate treasury FX payments,\n        international supplier payments, or global settlements.\n      hints:\n        readOnly: false\n      call: stonex-payments.create-payment\n      with:\n        amount: tools.amount\n        sell_currency: tools.sell_currency\n        buy_currency: tools.buy_currency\n        beneficiary_name: tools.beneficiary_name\n        account_number: tools.account_number\n        bank_code: tools.bank_code\n        payment_reference: tools.payment_reference\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: payments-list-payments\n      description: List cross-border payments with status and date filters. Use to monitor payment pipeline, reconcile transactions,\n        or generate reports.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-payments.list-payments\n      with:\n        status: tools.status\n        currency: tools.currency\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: payments-get-payment\n      description: Get details and current status of a specific payment.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-payments.get-payment\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: payments-get-fx-rates\n      description: Get indicative FX exchange rates for a currency pair. Use for pre-payment rate discovery or\
  \ treasury rate\n        monitoring.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-payments.get-fx-rates\n      with:\n        sell_currency: tools.sell_currency\n        buy_currency: tools.buy_currency\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearing-list-accounts\n      description: List institutional clearing accounts. Use to discover available accounts for trading or reporting.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-clearing.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearing-get-positions\n      description: Get current open positions for a clearing account. Use for risk management, P&L monitoring, or portfolio\n        reporting.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-clearing.get-account-positions\n      with:\n        accountId: tools.accountId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearing-get-balances\n      description: Get cash, margin, and P&L balances for a clearing account. Use for margin monitoring, risk management,\n        or daily reconciliation.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-clearing.get-account-balances\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearing-submit-trade\n      description: Submit a trade for clearing and settlement through StoneX. Use for programmatic trade entry or algorithmic\n        trading workflows.\n      hints:\n        readOnly: false\n      call: stonex-clearing.submit-trade\n      with:\n        account_id: tools.account_id\n        symbol: tools.symbol\n        side: tools.side\n        quantity: tools.quantity\n        price: tools.price\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: clearing-list-trades\n      description: List trades with account, status, and date filters. Use for trade reconciliation, settlement monitoring,\n        or reporting.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-clearing.list-trades\n      with:\n        account_id: tools.account_id\n        status: tools.status\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clearing-list-documents\n      description: List clearing documents including trade confirmations and statements. Use for compliance, audit, or client\n        reporting.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stonex-clearing.list-documents\n      with:\n        account_id: tools.account_id\n        document_type: tools.document_type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stonex/refs/heads/main/capabilities/financial-services.yaml
tags:
- Finance
- Financial Services
- Payments
- Clearing
- Trading
- FX
- Institutional
tools:
- description: Initiate a cross-border payment through StoneX in 140+ currencies. Use for corporate treasury FX payments, international supplier payments, or global settlements.
  hints:
    readOnly: false
  name: payments-create-payment
- description: List cross-border payments with status and date filters. Use to monitor payment pipeline, reconcile transactions, or generate reports.
  hints:
    idempotent: true
    readOnly: true
  name: payments-list-payments
- description: Get details and current status of a specific payment.
  hints:
    idempotent: true
    readOnly: true
  name: payments-get-payment
- description: Get indicative FX exchange rates for a currency pair. Use for pre-payment rate discovery or treasury rate monitoring.
  hints:
    idempotent: true
    readOnly: true
  name: payments-get-fx-rates
- description: List institutional clearing accounts. Use to discover available accounts for trading or reporting.
  hints:
    idempotent: true
    readOnly: true
  name: clearing-list-accounts
- description: Get current open positions for a clearing account. Use for risk management, P&L monitoring, or portfolio reporting.
  hints:
    idempotent: true
    readOnly: true
  name: clearing-get-positions
- description: Get cash, margin, and P&L balances for a clearing account. Use for margin monitoring, risk management, or daily reconciliation.
  hints:
    idempotent: true
    readOnly: true
  name: clearing-get-balances
- description: Submit a trade for clearing and settlement through StoneX. Use for programmatic trade entry or algorithmic trading workflows.
  hints:
    readOnly: false
  name: clearing-submit-trade
- description: List trades with account, status, and date filters. Use for trade reconciliation, settlement monitoring, or reporting.
  hints:
    idempotent: true
    readOnly: true
  name: clearing-list-trades
- description: List clearing documents including trade confirmations and statements. Use for compliance, audit, or client reporting.
  hints:
    idempotent: true
    readOnly: true
  name: clearing-list-documents
---
