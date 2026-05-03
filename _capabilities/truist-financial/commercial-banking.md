---
categories: []
consumed_apis:
- truist-commercial-accounts
- truist-commercial-transactions
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
- get details for a specific commercial transaction.
- get details for a specific commercial account transaction including ach trace numbers, wire reference numbers, and check numbers.
- individual commercial transaction
- accounts
- commercial banking
- list commercial transactions
- retrieve commercial account transactions with filtering by date range and payment type (ach, wire, check, book transfer).
- get commercial account balances
- individual commercial account
- get consolidated balance summary across all commercial accounts.
- consolidated commercial account balance summary
- get commercial account
- commercial deposit accounts
- financial services
- open banking
- wire transfer
- get a consolidated balance summary across all commercial accounts for the organization.
- banking
- list commercial accounts
- payments
- transactions
- get ledger, available, collected, and float balances for a commercial account. used for daily balance reporting and intraday cash position monitoring.
- commercial account transaction history
- get details for a specific commercial deposit account.
- list commercial transactions including ach, wires, and checks.
- get details for a specific commercial account.
- ach
- treasury
- get commercial transaction
- commercial account balance data
- get commercial account summary
- fortune 500
- personal banking
- list all commercial deposit accounts for the organization.
- get ledger, available, collected, and float balances for a commercial account.
slug: commercial-banking
source_filename: commercial-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Truist Commercial Banking\"\n  description: >-\n    Unified commercial banking capability combining commercial account management and\n    transaction retrieval. Used by treasury teams, ERP integrations, and corporate\n    finance applications to manage commercial deposit accounts, retrieve real-time\n    balances, and access complete transaction history including ACH, wire transfers,\n    and check payments for cash flow reconciliation and treasury management.\n  tags:\n    - Banking\n    - Commercial Banking\n    - Treasury\n    - Accounts\n    - Transactions\n    - Payments\n    - ACH\n    - Wire Transfer\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRUIST_COMMERCIAL_OAUTH2_TOKEN: TRUIST_COMMERCIAL_OAUTH2_TOKEN\n\ncapability:\n  consumes:\n    - import: truist-commercial-accounts\n      location: ./shared/commercial-accounts.yaml\n    - import: truist-commercial-transactions\n\
  \      location: ./shared/commercial-transactions.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: truist-commercial-banking-api\n      description: \"Unified REST API for commercial banking account management and transaction reporting.\"\n      resources:\n        - path: /v1/commercial/accounts\n          name: commercial-accounts\n          description: \"Commercial deposit accounts\"\n          operations:\n            - method: GET\n              name: list-commercial-accounts\n              description: \"List all commercial deposit accounts for the organization.\"\n              call: \"truist-commercial-accounts.list-commercial-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commercial/accounts/summary\n          name: commercial-account-summary\n          description: \"Consolidated commercial account balance summary\"\n          operations:\n            - method: GET\n\
  \              name: get-commercial-account-summary\n              description: \"Get consolidated balance summary across all commercial accounts.\"\n              call: \"truist-commercial-accounts.get-commercial-account-summary\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commercial/accounts/{accountId}\n          name: commercial-account\n          description: \"Individual commercial account\"\n          operations:\n            - method: GET\n              name: get-commercial-account\n              description: \"Get details for a specific commercial account.\"\n              call: \"truist-commercial-accounts.get-commercial-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commercial/accounts/{accountId}/balances\n          name: commercial-account-balances\n\
  \          description: \"Commercial account balance data\"\n          operations:\n            - method: GET\n              name: get-commercial-account-balances\n              description: \"Get ledger, available, collected, and float balances for a commercial account.\"\n              call: \"truist-commercial-accounts.get-commercial-account-balances\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commercial/accounts/{accountId}/transactions\n          name: commercial-transactions\n          description: \"Commercial account transaction history\"\n          operations:\n            - method: GET\n              name: list-commercial-transactions\n              description: \"List commercial transactions including ACH, wires, and checks.\"\n              call: \"truist-commercial-transactions.list-commercial-transactions\"\n              with:\n\
  \                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commercial/accounts/{accountId}/transactions/{transactionId}\n          name: commercial-transaction\n          description: \"Individual commercial transaction\"\n          operations:\n            - method: GET\n              name: get-commercial-transaction\n              description: \"Get details for a specific commercial transaction.\"\n              call: \"truist-commercial-transactions.get-commercial-transaction\"\n              with:\n                accountId: \"rest.accountId\"\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: truist-commercial-banking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted commercial banking, treasury\
  \ management, and cash flow analysis.\"\n      tools:\n        - name: list-commercial-accounts\n          description: \"List all commercial deposit accounts for the organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-accounts.list-commercial-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commercial-account\n          description: \"Get details for a specific commercial deposit account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-accounts.get-commercial-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commercial-account-balances\n          description: \"Get ledger, available, collected, and float balances for a commercial account. Used for\
  \ daily balance reporting and intraday cash position monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-accounts.get-commercial-account-balances\"\n          with:\n            accountId: \"tools.accountId\"\n            asOfDate: \"tools.asOfDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commercial-account-summary\n          description: \"Get a consolidated balance summary across all commercial accounts for the organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-accounts.get-commercial-account-summary\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commercial-transactions\n          description: \"Retrieve commercial account transactions with\
  \ filtering by date range and payment type (ACH, wire, check, book transfer).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-transactions.list-commercial-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n            transactionType: \"tools.transactionType\"\n            debitCreditIndicator: \"tools.debitCreditIndicator\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commercial-transaction\n          description: \"Get details for a specific commercial account transaction including ACH trace numbers, wire reference numbers, and check numbers.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truist-commercial-transactions.get-commercial-transaction\"\n          with:\n            accountId: \"tools.accountId\"\
  \n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
