---
categories: []
consumed_apis: []
description: Unified personal and small business banking capability combining account management and transaction history. Used by fintech developers, personal finance management applications, and account aggregation platforms to give consumers and small business owners a complete view of their Truist banking data.
layout: capability
name: Truist Personal Banking
operations:
- description: List all personal and small business deposit accounts.
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get details for a specific personal or small business account.
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Get current and available balances for an account.
  method: GET
  name: get-account-balances
  path: /v1/accounts/{accountId}/balances
- description: List transactions for a personal or small business account.
  method: GET
  name: list-transactions
  path: /v1/accounts/{accountId}/transactions
- description: Get details for a specific account transaction.
  method: GET
  name: get-transaction
  path: /v1/accounts/{accountId}/transactions/{transactionId}
personas: []
provider_name: Truist Financial
provider_slug: truist-financial
search_terms:
- get account
- transactions
- personal banking
- commercial banking
- list accounts
- list all personal and small business deposit accounts.
- account balance information
- individual account details
- get account balances
- personal and small business deposit accounts
- get details for a specific personal or small business account.
- get transaction
- individual transaction details
- get details for a specific personal account transaction.
- account transaction history
- small business
- financial services
- accounts
- get details for a specific personal or small business deposit account.
- get details for a specific account transaction.
- retrieve transaction history for a personal account with date range and status filtering.
- open banking
- get current and available balances for an account.
- list all personal and small business deposit accounts for the authenticated client.
- banking
- payments
- list transactions for a personal or small business account.
- list transactions
- get current and available balances for a personal or small business account.
- fortune 500
slug: personal-banking
source_filename: personal-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Truist Personal Banking\n  description: Unified personal and small business banking capability combining account management and transaction history.\n    Used by fintech developers, personal finance management applications, and account aggregation platforms to give consumers\n    and small business owners a complete view of their Truist banking data.\n  tags:\n  - Banking\n  - Personal Banking\n  - Small Business\n  - Accounts\n  - Transactions\n  - Open Banking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUIST_OAUTH2_TOKEN: TRUIST_OAUTH2_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: truist-personal-accounts\n    baseUri: https://api.truist.com/v1\n    description: Personal and small business account information API.\n    authentication:\n      type: bearer\n      token: '{{TRUIST_OAUTH2_TOKEN}}'\n    resources:\n    - name: personal-accounts\n      path: /personal/accounts\n\
  \      description: Personal and small business deposit accounts\n      operations:\n      - name: list-personal-accounts\n        method: GET\n        description: Retrieve a list of personal and small business deposit accounts for the authenticated client.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: personal-account\n      path: /personal/accounts/{accountId}\n      description: Individual personal account details\n      operations:\n      - name: get-personal-account\n        method: GET\n        description: Retrieve details for a specific personal or small business deposit account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ personal-account-balances\n      path: /personal/accounts/{accountId}/balances\n      description: Personal account balance information\n      operations:\n      - name: get-personal-account-balances\n        method: GET\n        description: Retrieve current and available balances for a personal or small business account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: truist-personal-transactions\n    baseUri: https://api.truist.com/v1\n    description: Personal and small business transaction history API.\n    authentication:\n      type: bearer\n      token: '{{TRUIST_OAUTH2_TOKEN}}'\n    resources:\n    - name: personal-transactions\n      path: /personal/accounts/{accountId}/transactions\n      description:\
  \ Personal account transaction history\n      operations:\n      - name: list-personal-transactions\n        method: GET\n        description: Retrieve posted and pending transactions for a personal or small business account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD)\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by POSTED, PENDING, or ALL\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of transactions\n      \
  \  - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: personal-transaction\n      path: /personal/accounts/{accountId}/transactions/{transactionId}\n      description: Individual transaction details\n      operations:\n      - name: get-personal-transaction\n        method: GET\n        description: Retrieve details for a specific transaction on a personal or small business account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Unique transaction identifier\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: truist-personal-banking-api\n    description: Unified REST API for personal and small business banking data.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Personal and small business deposit accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all personal and small business deposit accounts.\n        call: truist-personal-accounts.list-personal-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account\n      description: Individual account details\n      operations:\n      - method: GET\n        name: get-account\n        description: Get details for a specific personal or small business account.\n        call: truist-personal-accounts.get-personal-account\n        with:\n          accountId: rest.accountId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/balances\n      name: account-balances\n      description: Account balance information\n      operations:\n      - method: GET\n        name: get-account-balances\n        description: Get current and available balances for an account.\n        call: truist-personal-accounts.get-personal-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: transactions\n      description: Account transaction history\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List transactions for a personal or small business account.\n        call: truist-personal-transactions.list-personal-transactions\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions/{transactionId}\n      name: transaction\n      description: Individual transaction details\n      operations:\n      - method: GET\n        name: get-transaction\n        description: Get details for a specific account transaction.\n        call: truist-personal-transactions.get-personal-transaction\n        with:\n          accountId: rest.accountId\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: truist-personal-banking-mcp\n    transport: http\n    description: MCP server for AI-assisted personal banking data access and financial management.\n    tools:\n    - name: list-accounts\n      description: List all personal and small business deposit accounts for the authenticated client.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-personal-accounts.list-personal-accounts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get details for a specific personal or small business deposit account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-personal-accounts.get-personal-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balances\n      description: Get current and available balances for a personal or small business account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-personal-accounts.get-personal-account-balances\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: Retrieve transaction history for a personal account with date range and status filtering.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: truist-personal-transactions.list-personal-transactions\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        status: tools.status\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction\n      description: Get details for a specific personal account transaction.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-personal-transactions.get-personal-transaction\n      with:\n        accountId: tools.accountId\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/truist-financial/refs/heads/main/capabilities/personal-banking.yaml
tags:
- Banking
- Personal Banking
- Small Business
- Accounts
- Transactions
- Open Banking
tools:
- description: List all personal and small business deposit accounts for the authenticated client.
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Get details for a specific personal or small business deposit account.
  hints:
    openWorld: false
    readOnly: true
  name: get-account
- description: Get current and available balances for a personal or small business account.
  hints:
    openWorld: false
    readOnly: true
  name: get-account-balances
- description: Retrieve transaction history for a personal account with date range and status filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-transactions
- description: Get details for a specific personal account transaction.
  hints:
    openWorld: false
    readOnly: true
  name: get-transaction
---
