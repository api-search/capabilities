---
categories: []
consumed_apis: []
description: Unified open banking workflow combining account management, transaction history, balance monitoring, and identity verification through the Teller API. Enables fintech applications, personal finance tools, and lending platforms to access real-time financial data across US banks and credit unions.
layout: capability
name: Teller Open Banking
operations:
- description: List accounts with beneficial owner identity information
  method: GET
  name: list-identity
  path: /v1/identity
- description: List all authorized bank accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get a bank account by ID
  method: GET
  name: get-account
  path: /v1/accounts/{account_id}
- description: Get routing number and account number
  method: GET
  name: get-account-details
  path: /v1/accounts/{account_id}/details
- description: Get available and ledger balances
  method: GET
  name: get-account-balances
  path: /v1/accounts/{account_id}/balances
- description: List transactions with optional date filtering and pagination
  method: GET
  name: list-transactions
  path: /v1/accounts/{account_id}/transactions
- description: Get a transaction by ID
  method: GET
  name: get-transaction
  path: /v1/accounts/{account_id}/transactions/{transaction_id}
- description: List all supported banks and credit unions
  method: GET
  name: list-institutions
  path: /v1/institutions
personas: []
provider_name: Teller
provider_slug: teller
search_terms:
- sensitive account number and routing details
- get account
- transactions
- get a transaction by id
- identity verification
- list institutions
- unified api
- get account details
- get a specific transaction record by id
- list accounts
- get routing number and full account number for a bank account
- get account balances
- get routing number and account number
- single transaction record
- transaction history for a bank account
- list transactions with optional date filtering and pagination
- fintech
- list all authorized bank accounts
- get transaction
- financial data
- list all us financial institutions supported by teller
- list identity
- teller
- get real-time available and ledger balances for a bank account
- list supported institutions
- accounts
- list bank accounts with beneficial owner identity information
- real-time account balance data
- bank accounts accessible via the current enrollment
- account holder identity and ownership information
- single bank account resource
- open banking
- list all supported banks and credit unions
- get available and ledger balances
- banking
- list transactions for a bank account with date range filtering
- list accounts with beneficial owner identity information
- get details for a specific bank account
- get a bank account by id
- list transactions
- list all bank accounts authorized in the current teller enrollment
- supported financial institutions
slug: open-banking
source_filename: open-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Teller Open Banking\n  description: Unified open banking workflow combining account management, transaction history, balance monitoring, and identity\n    verification through the Teller API. Enables fintech applications, personal finance tools, and lending platforms to access\n    real-time financial data across US banks and credit unions.\n  tags:\n  - Accounts\n  - Banking\n  - Financial Data\n  - FinTech\n  - Identity Verification\n  - Open Banking\n  - Teller\n  - Transactions\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELLER_ACCESS_TOKEN: TELLER_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: teller\n    baseUri: https://api.teller.io\n    description: Teller unified banking API for real-time financial data access.\n    authentication:\n      type: bearer\n      token: '{{TELLER_ACCESS_TOKEN}}'\n    resources:\n    - name: identity\n      path: /identity\n   \
  \   description: Account holder identity information\n      operations:\n      - name: list-identity\n        method: GET\n        description: List accounts with owner identity information attached\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: accounts\n      path: /accounts\n      description: Bank account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all authorized bank accounts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get a single bank account by ID\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account-details\n        method: GET\n        description: Get account routing and account numbers\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account-balances\n        method: GET\n        description: Get current available and ledger balances\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /accounts/{account_id}/transactions\n\
  \      description: Account transaction history\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List transactions for an account with optional date filtering\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Maximum transactions to return\n        - name: from_id\n          in: query\n          type: string\n          required: false\n          description: Paginate backward from this transaction ID\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Filter from this ISO 8601 date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter to this ISO 8601 date\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-transaction\n        method: GET\n        description: Get a single transaction by ID\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        - name: transaction_id\n          in: path\n          type: string\n          required: true\n          description: Transaction identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: institutions\n      path: /institutions\n      description: Supported financial institutions\n      operations:\n      - name: list-institutions\n        method: GET\n        description: List all supported financial institutions and their available products\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: teller-open-banking-api\n    description: Unified REST API for open banking data access including accounts, balances, transactions, and identity across\n      US financial institutions.\n    resources:\n    - path: /v1/identity\n      name: identity\n      description: Account holder identity and ownership information\n      operations:\n      - method: GET\n        name: list-identity\n        description: List accounts with beneficial owner identity information\n        call: teller.list-identity\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Bank accounts accessible via the current enrollment\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all authorized bank accounts\n        call: teller.list-accounts\n\
  \        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/accounts/{account_id}\n      name: account\n      description: Single bank account resource\n      operations:\n      - method: GET\n        name: get-account\n        description: Get a bank account by ID\n        call: teller.get-account\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{account_id}/details\n      name: account-details\n      description: Sensitive account number and routing details\n      operations:\n      - method: GET\n        name: get-account-details\n        description: Get routing number and account number\n        call: teller.get-account-details\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{account_id}/balances\n      name: account-balances\n      description:\
  \ Real-time account balance data\n      operations:\n      - method: GET\n        name: get-account-balances\n        description: Get available and ledger balances\n        call: teller.get-account-balances\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{account_id}/transactions\n      name: transactions\n      description: Transaction history for a bank account\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List transactions with optional date filtering and pagination\n        call: teller.list-transactions\n        with:\n          account_id: rest.account_id\n          count: rest.count\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/accounts/{account_id}/transactions/{transaction_id}\n      name: transaction\n    \
  \  description: Single transaction record\n      operations:\n      - method: GET\n        name: get-transaction\n        description: Get a transaction by ID\n        call: teller.get-transaction\n        with:\n          account_id: rest.account_id\n          transaction_id: rest.transaction_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/institutions\n      name: institutions\n      description: Supported financial institutions\n      operations:\n      - method: GET\n        name: list-institutions\n        description: List all supported banks and credit unions\n        call: teller.list-institutions\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: teller-open-banking-mcp\n    transport: http\n    description: MCP server for AI-assisted open banking data access and financial analysis across US banks and credit unions\n      via Teller.\n    tools:\n    - name: list-identity\n\
  \      description: List bank accounts with beneficial owner identity information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.list-identity\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-accounts\n      description: List all bank accounts authorized in the current Teller enrollment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.list-accounts\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-account\n      description: Get details for a specific bank account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.get-account\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-details\n      description: Get routing number and full account number\
  \ for a bank account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.get-account-details\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-balances\n      description: Get real-time available and ledger balances for a bank account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.get-account-balances\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List transactions for a bank account with date range filtering\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.list-transactions\n      with:\n        account_id: tools.account_id\n        count: tools.count\n        start_date: tools.start_date\n\
  \        end_date: tools.end_date\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-transaction\n      description: Get a specific transaction record by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.get-transaction\n      with:\n        account_id: tools.account_id\n        transaction_id: tools.transaction_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supported-institutions\n      description: List all US financial institutions supported by Teller\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: teller.list-institutions\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/teller/refs/heads/main/capabilities/open-banking.yaml
tags:
- Accounts
- Banking
- Financial Data
- FinTech
- Identity Verification
- Open Banking
- Teller
- Transactions
tools:
- description: List bank accounts with beneficial owner identity information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-identity
- description: List all bank accounts authorized in the current Teller enrollment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-accounts
- description: Get details for a specific bank account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account
- description: Get routing number and full account number for a bank account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-details
- description: Get real-time available and ledger balances for a bank account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-balances
- description: List transactions for a bank account with date range filtering
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-transactions
- description: Get a specific transaction record by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-transaction
- description: List all US financial institutions supported by Teller
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-supported-institutions
---
