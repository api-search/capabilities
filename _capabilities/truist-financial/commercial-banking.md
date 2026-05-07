---
categories: []
consumed_apis: []
description: Unified commercial banking capability combining commercial account management and transaction retrieval. Used by treasury teams, ERP integrations, and corporate finance applications to manage commercial deposit accounts, retrieve real-time balances, and access complete transaction history including ACH, wire transfers, and check payments for cash flow reconciliation and treasury management.
layout: capability
name: Truist Commercial Banking
operations:
- description: List all commercial deposit accounts for the organization.
  method: GET
  name: list-commercial-accounts
  path: /v1/commercial/accounts
- description: Get consolidated balance summary across all commercial accounts.
  method: GET
  name: get-commercial-account-summary
  path: /v1/commercial/accounts/summary
- description: Get details for a specific commercial account.
  method: GET
  name: get-commercial-account
  path: /v1/commercial/accounts/{accountId}
- description: Get ledger, available, collected, and float balances for a commercial account.
  method: GET
  name: get-commercial-account-balances
  path: /v1/commercial/accounts/{accountId}/balances
- description: List commercial transactions including ACH, wires, and checks.
  method: GET
  name: list-commercial-transactions
  path: /v1/commercial/accounts/{accountId}/transactions
- description: Get details for a specific commercial transaction.
  method: GET
  name: get-commercial-transaction
  path: /v1/commercial/accounts/{accountId}/transactions/{transactionId}
personas: []
provider_name: Truist Financial
provider_slug: truist-financial
search_terms:
- get commercial account balances
- transactions
- ach
- get commercial account summary
- treasury
- commercial banking
- get details for a specific commercial account.
- commercial account balance data
- get consolidated balance summary across all commercial accounts.
- personal banking
- get details for a specific commercial deposit account.
- individual commercial account
- get commercial transaction
- commercial account transaction history
- retrieve commercial account transactions with filtering by date range and payment type (ach, wire, check, book transfer).
- commercial deposit accounts
- financial services
- list all commercial deposit accounts for the organization.
- list commercial transactions including ach, wires, and checks.
- accounts
- get details for a specific commercial account transaction including ach trace numbers, wire reference numbers, and check numbers.
- consolidated commercial account balance summary
- get details for a specific commercial transaction.
- open banking
- get a consolidated balance summary across all commercial accounts for the organization.
- banking
- payments
- list commercial transactions
- get commercial account
- get ledger, available, collected, and float balances for a commercial account.
- fortune 500
- individual commercial transaction
- get ledger, available, collected, and float balances for a commercial account. used for daily balance reporting and intraday cash position monitoring.
- wire transfer
- list commercial accounts
slug: commercial-banking
source_filename: commercial-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Truist Commercial Banking\n  description: Unified commercial banking capability combining commercial account management and transaction retrieval. Used\n    by treasury teams, ERP integrations, and corporate finance applications to manage commercial deposit accounts, retrieve\n    real-time balances, and access complete transaction history including ACH, wire transfers, and check payments for cash\n    flow reconciliation and treasury management.\n  tags:\n  - Banking\n  - Commercial Banking\n  - Treasury\n  - Accounts\n  - Transactions\n  - Payments\n  - ACH\n  - Wire Transfer\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUIST_COMMERCIAL_OAUTH2_TOKEN: TRUIST_COMMERCIAL_OAUTH2_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: truist-commercial-accounts\n    baseUri: https://api.truist.com/v1\n    description: Commercial banking account information API.\n    authentication:\n\
  \      type: bearer\n      token: '{{TRUIST_COMMERCIAL_OAUTH2_TOKEN}}'\n    resources:\n    - name: commercial-accounts\n      path: /commercial/accounts\n      description: Commercial deposit accounts\n      operations:\n      - name: list-commercial-accounts\n        method: GET\n        description: Retrieve a list of commercial deposit accounts for the authenticated organization.\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Filter accounts by customer/organization identifier\n        - name: accountType\n          in: query\n          type: string\n          required: false\n          description: Filter by account type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commercial-account\n      path: /commercial/accounts/{accountId}\n      description: Individual commercial account details\n\
  \      operations:\n      - name: get-commercial-account\n        method: GET\n        description: Retrieve details for a specific commercial deposit account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commercial-account-balances\n      path: /commercial/accounts/{accountId}/balances\n      description: Commercial account balance data\n      operations:\n      - name: get-commercial-account-balances\n        method: GET\n        description: Retrieve current and available balances for a commercial deposit account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: asOfDate\n        \
  \  in: query\n          type: string\n          required: false\n          description: Balance as of date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commercial-account-summary\n      path: /commercial/accounts/summary\n      description: Consolidated commercial account summary\n      operations:\n      - name: get-commercial-account-summary\n        method: GET\n        description: Retrieve a consolidated balance summary across all commercial accounts.\n        inputParameters:\n        - name: customerId\n          in: query\n          type: string\n          required: false\n          description: Customer/organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: truist-commercial-transactions\n    baseUri: https://api.truist.com/v1\n    description:\
  \ Commercial banking transaction history API.\n    authentication:\n      type: bearer\n      token: '{{TRUIST_COMMERCIAL_OAUTH2_TOKEN}}'\n    resources:\n    - name: commercial-transactions\n      path: /commercial/accounts/{accountId}/transactions\n      description: Commercial account transaction history\n      operations:\n      - name: list-commercial-transactions\n        method: GET\n        description: Retrieve commercial account transactions including ACH, wires, and checks.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD)\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD)\n        - name: transactionType\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter by ACH, WIRE, CHECK, BOOK_TRANSFER, FEE, INTEREST, or ALL\n        - name: debitCreditIndicator\n          in: query\n          type: string\n          required: false\n          description: Filter by DEBIT or CREDIT\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of transactions\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: commercial-transaction\n      path: /commercial/accounts/{accountId}/transactions/{transactionId}\n      description: Individual commercial transaction details\n      operations:\n      - name: get-commercial-transaction\n        method: GET\n        description: Retrieve\
  \ details for a specific commercial account transaction.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: transactionId\n          in: path\n          type: string\n          required: true\n          description: Unique transaction identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: truist-commercial-banking-api\n    description: Unified REST API for commercial banking account management and transaction reporting.\n    resources:\n    - path: /v1/commercial/accounts\n      name: commercial-accounts\n      description: Commercial deposit accounts\n      operations:\n      - method: GET\n        name: list-commercial-accounts\n        description: List all commercial deposit accounts for the organization.\n\
  \        call: truist-commercial-accounts.list-commercial-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commercial/accounts/summary\n      name: commercial-account-summary\n      description: Consolidated commercial account balance summary\n      operations:\n      - method: GET\n        name: get-commercial-account-summary\n        description: Get consolidated balance summary across all commercial accounts.\n        call: truist-commercial-accounts.get-commercial-account-summary\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commercial/accounts/{accountId}\n      name: commercial-account\n      description: Individual commercial account\n      operations:\n      - method: GET\n        name: get-commercial-account\n        description: Get details for a specific commercial account.\n        call: truist-commercial-accounts.get-commercial-account\n        with:\n          accountId: rest.accountId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commercial/accounts/{accountId}/balances\n      name: commercial-account-balances\n      description: Commercial account balance data\n      operations:\n      - method: GET\n        name: get-commercial-account-balances\n        description: Get ledger, available, collected, and float balances for a commercial account.\n        call: truist-commercial-accounts.get-commercial-account-balances\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commercial/accounts/{accountId}/transactions\n      name: commercial-transactions\n      description: Commercial account transaction history\n      operations:\n      - method: GET\n        name: list-commercial-transactions\n        description: List commercial transactions including ACH, wires, and checks.\n        call: truist-commercial-transactions.list-commercial-transactions\n\
  \        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commercial/accounts/{accountId}/transactions/{transactionId}\n      name: commercial-transaction\n      description: Individual commercial transaction\n      operations:\n      - method: GET\n        name: get-commercial-transaction\n        description: Get details for a specific commercial transaction.\n        call: truist-commercial-transactions.get-commercial-transaction\n        with:\n          accountId: rest.accountId\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: truist-commercial-banking-mcp\n    transport: http\n    description: MCP server for AI-assisted commercial banking, treasury management, and cash flow analysis.\n    tools:\n    - name: list-commercial-accounts\n      description: List all commercial deposit accounts\
  \ for the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-accounts.list-commercial-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commercial-account\n      description: Get details for a specific commercial deposit account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-accounts.get-commercial-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commercial-account-balances\n      description: Get ledger, available, collected, and float balances for a commercial account. Used for daily balance reporting\n        and intraday cash position monitoring.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-accounts.get-commercial-account-balances\n      with:\n        accountId: tools.accountId\n        asOfDate:\
  \ tools.asOfDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commercial-account-summary\n      description: Get a consolidated balance summary across all commercial accounts for the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-accounts.get-commercial-account-summary\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commercial-transactions\n      description: Retrieve commercial account transactions with filtering by date range and payment type (ACH, wire, check,\n        book transfer).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-transactions.list-commercial-transactions\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        transactionType: tools.transactionType\n        debitCreditIndicator:\
  \ tools.debitCreditIndicator\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commercial-transaction\n      description: Get details for a specific commercial account transaction including ACH trace numbers, wire reference numbers,\n        and check numbers.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truist-commercial-transactions.get-commercial-transaction\n      with:\n        accountId: tools.accountId\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/truist-financial/refs/heads/main/capabilities/commercial-banking.yaml
tags:
- Banking
- Commercial Banking
- Treasury
- Accounts
- Transactions
- Payments
- ACH
- Wire Transfer
tools:
- description: List all commercial deposit accounts for the organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-commercial-accounts
- description: Get details for a specific commercial deposit account.
  hints:
    openWorld: false
    readOnly: true
  name: get-commercial-account
- description: Get ledger, available, collected, and float balances for a commercial account. Used for daily balance reporting and intraday cash position monitoring.
  hints:
    openWorld: false
    readOnly: true
  name: get-commercial-account-balances
- description: Get a consolidated balance summary across all commercial accounts for the organization.
  hints:
    openWorld: false
    readOnly: true
  name: get-commercial-account-summary
- description: Retrieve commercial account transactions with filtering by date range and payment type (ACH, wire, check, book transfer).
  hints:
    openWorld: false
    readOnly: true
  name: list-commercial-transactions
- description: Get details for a specific commercial account transaction including ACH trace numbers, wire reference numbers, and check numbers.
  hints:
    openWorld: false
    readOnly: true
  name: get-commercial-transaction
---
