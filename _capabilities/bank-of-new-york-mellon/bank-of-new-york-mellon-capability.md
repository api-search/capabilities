---
categories: []
consumed_apis: []
description: The BNY Mellon Treasury Services API enables corporate clients to programmatically initiate and track payments, access account balances and transaction history, manage wire transfers, and retrieve reporting data. The API is available via the BNY Mellon Marketplace (marketplace.bnymellon.com) and supports global treasury operations across multiple currencies and payment rails.
layout: capability
name: BNY Mellon Treasury Services API
operations:
- description: List Accounts
  method: GET
  name: listaccounts
  path: /accounts
- description: Get Account
  method: GET
  name: getaccount
  path: /accounts/{accountId}
- description: Get Account Balances
  method: GET
  name: getaccountbalances
  path: /accounts/{accountId}/balances
- description: List Transactions
  method: GET
  name: listtransactions
  path: /accounts/{accountId}/transactions
- description: Initiate Payment
  method: POST
  name: initiatepayment
  path: /payments
- description: List Payments
  method: GET
  name: listpayments
  path: /payments
- description: Get Payment
  method: GET
  name: getpayment
  path: /payments/{paymentId}
- description: Initiate Funds Transfer
  method: POST
  name: initiatefundstransfer
  path: /funds-transfers
- description: Get Funds Transfer
  method: GET
  name: getfundstransfer
  path: /funds-transfers/{transferId}
personas: []
provider_name: BNY Mellon
provider_slug: bank-of-new-york-mellon
search_terms:
- get account
- analyst executing treasury transactions and reporting
- getaccount
- getaccountbalances
- institutional banking
- new
- treasury
- api
- asset servicing
- list accounts
- executive managing corporate liquidity and treasury operations
- get account balances
- getfundstransfer
- Corporate Treasurer
- wire, ach, swift, and chips payment execution
- get payment
- mellon
- bank
- institutional account management and cash positioning
- wire transfers
- listtransactions
- institutional investor or fund manager using bny custody and treasury services
- institutional treasury operations including accounts, payments, and funds transfers
- internal funds transfers and liquidity management
- of
- york
- initiate funds transfer
- initiatepayment
- initiate payment
- listaccounts
- banking
- payments
- getpayment
- initiatefundstransfer
- list transactions
- get funds transfer
- Treasury Analyst
- listpayments
- list payments
- Institutional Client
slug: bank-of-new-york-mellon-capability
source_filename: bank-of-new-york-mellon-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BNY Mellon Treasury Services API\n  description: The BNY Mellon Treasury Services API enables corporate clients to programmatically initiate and track payments,\n    access account balances and transaction history, manage wire transfers, and retrieve reporting data. The API is available\n    via the BNY Mellon Marketplace (marketplace.bnymellon.com) and supports global treasury operations across multiple currencies\n    and payment rails.\n  tags:\n  - Bank\n  - Of\n  - New\n  - York\n  - Mellon\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bank-of-new-york-mellon\n    baseUri: https://api.bnymellon.com/treasury/v4\n    description: BNY Mellon Treasury Services API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BANK_OF_NEW_YORK_MELLON_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: listaccounts\n\
  \        method: GET\n        description: List Accounts\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n          description: Filter accounts by currency (ISO 4217)\n        - name: accountType\n          in: query\n          type: string\n          description: Filter by account type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountId}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get Account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-balances\n      path: /accounts/{accountId}/balances\n\
  \      operations:\n      - name: getaccountbalances\n        method: GET\n        description: Get Account Balances\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: balanceType\n          in: query\n          type: string\n          description: Balance type filter (current, available, intraday)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid-transactions\n      path: /accounts/{accountId}/transactions\n      operations:\n      - name: listtransactions\n        method: GET\n        description: List Transactions\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: fromDate\n          in: query\n          type: string\n\
  \          description: Start date (ISO 8601)\n        - name: toDate\n          in: query\n          type: string\n          description: End date (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /payments\n      operations:\n      - name: initiatepayment\n        method: POST\n        description: Initiate Payment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listpayments\n        method: GET\n        description: List Payments\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Payment status filter\n        - name: fromDate\n          in: query\n          type: string\n          description: Start date\
  \ filter\n        - name: toDate\n          in: query\n          type: string\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-paymentid\n      path: /payments/{paymentId}\n      operations:\n      - name: getpayment\n        method: GET\n        description: Get Payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funds-transfers\n      path: /funds-transfers\n      operations:\n      - name: initiatefundstransfer\n        method: POST\n        description: Initiate Funds Transfer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: funds-transfers-transferid\n      path: /funds-transfers/{transferId}\n      operations:\n      - name: getfundstransfer\n        method: GET\n        description: Get Funds Transfer\n        inputParameters:\n        - name: transferId\n          in: path\n          type: string\n          required: true\n          description: Funds transfer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bank-of-new-york-mellon-rest\n    description: REST adapter for BNY Mellon Treasury Services API.\n    resources:\n    - path: /accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: List Accounts\n        call: bank-of-new-york-mellon.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}\n\
  \      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get Account\n        call: bank-of-new-york-mellon.getaccount\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/balances\n      name: getaccountbalances\n      operations:\n      - method: GET\n        name: getaccountbalances\n        description: Get Account Balances\n        call: bank-of-new-york-mellon.getaccountbalances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{accountId}/transactions\n      name: listtransactions\n      operations:\n      - method: GET\n        name: listtransactions\n        description: List Transactions\n        call: bank-of-new-york-mellon.listtransactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /payments\n      name: initiatepayment\n      operations:\n      - method: POST\n        name: initiatepayment\n        description: Initiate Payment\n        call: bank-of-new-york-mellon.initiatepayment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments\n      name: listpayments\n      operations:\n      - method: GET\n        name: listpayments\n        description: List Payments\n        call: bank-of-new-york-mellon.listpayments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /payments/{paymentId}\n      name: getpayment\n      operations:\n      - method: GET\n        name: getpayment\n        description: Get Payment\n        call: bank-of-new-york-mellon.getpayment\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funds-transfers\n      name: initiatefundstransfer\n\
  \      operations:\n      - method: POST\n        name: initiatefundstransfer\n        description: Initiate Funds Transfer\n        call: bank-of-new-york-mellon.initiatefundstransfer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /funds-transfers/{transferId}\n      name: getfundstransfer\n      operations:\n      - method: GET\n        name: getfundstransfer\n        description: Get Funds Transfer\n        call: bank-of-new-york-mellon.getfundstransfer\n        with:\n          transferId: rest.transferId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bank-of-new-york-mellon-mcp\n    transport: http\n    description: MCP adapter for BNY Mellon Treasury Services API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: List Accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.listaccounts\n\
  \      with:\n        currency: tools.currency\n        accountType: tools.accountType\n      inputParameters:\n      - name: currency\n        type: string\n        description: Filter accounts by currency (ISO 4217)\n      - name: accountType\n        type: string\n        description: Filter by account type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Get Account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.getaccount\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: Account identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountbalances\n      description: Get Account Balances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n    \
  \  call: bank-of-new-york-mellon.getaccountbalances\n      with:\n        accountId: tools.accountId\n        balanceType: tools.balanceType\n      inputParameters:\n      - name: accountId\n        type: string\n        description: Account identifier\n        required: true\n      - name: balanceType\n        type: string\n        description: Balance type filter (current, available, intraday)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransactions\n      description: List Transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.listtransactions\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        limit: tools.limit\n      inputParameters:\n      - name: accountId\n        type: string\n        description: Account identifier\n        required: true\n      - name: fromDate\n        type: string\n\
  \        description: Start date (ISO 8601)\n      - name: toDate\n        type: string\n        description: End date (ISO 8601)\n      - name: limit\n        type: integer\n        description: Page size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiatepayment\n      description: Initiate Payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bank-of-new-york-mellon.initiatepayment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpayments\n      description: List Payments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.listpayments\n      with:\n        status: tools.status\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: status\n        type: string\n        description: Payment status filter\n      - name: fromDate\n\
  \        type: string\n        description: Start date filter\n      - name: toDate\n        type: string\n        description: End date filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpayment\n      description: Get Payment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.getpayment\n      with:\n        paymentId: tools.paymentId\n      inputParameters:\n      - name: paymentId\n        type: string\n        description: Payment identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: initiatefundstransfer\n      description: Initiate Funds Transfer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bank-of-new-york-mellon.initiatefundstransfer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfundstransfer\n      description:\
  \ Get Funds Transfer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: bank-of-new-york-mellon.getfundstransfer\n      with:\n        transferId: tools.transferId\n      inputParameters:\n      - name: transferId\n        type: string\n        description: Funds transfer identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BANK_OF_NEW_YORK_MELLON_TOKEN: BANK_OF_NEW_YORK_MELLON_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bank-of-new-york-mellon/refs/heads/main/capabilities/bank-of-new-york-mellon-capability.yaml
tags:
- Bank
- Of
- New
- York
- Mellon
- API
tools:
- description: List Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Get Account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Get Account Balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbalances
- description: List Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransactions
- description: Initiate Payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiatepayment
- description: List Payments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpayments
- description: Get Payment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpayment
- description: Initiate Funds Transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiatefundstransfer
- description: Get Funds Transfer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfundstransfer
---
