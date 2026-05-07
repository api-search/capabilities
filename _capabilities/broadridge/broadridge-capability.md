---
categories: []
consumed_apis: []
description: The Broadridge Wealth Management API provides access to account activity, balances, positions, and transaction data for wealth management platforms. REST APIs enable broker-dealers and RIAs to integrate Broadridge back-office clearing and custody data into front-office wealth management applications.
layout: capability
name: Broadridge Wealth Management API
operations:
- description: List accounts
  method: GET
  name: listaccounts
  path: /wealth/v1/accounts
- description: Get account details
  method: GET
  name: getaccount
  path: /wealth/v1/accounts/{accountNumber}
- description: Get account balances
  method: GET
  name: getaccountbalances
  path: /wealth/v1/accounts/{accountNumber}/balances
- description: Get account positions
  method: GET
  name: getaccountpositions
  path: /wealth/v1/accounts/{accountNumber}/positions
- description: Get account transactions
  method: GET
  name: getaccounttransactions
  path: /wealth/v1/accounts/{accountNumber}/transactions
- description: Get account performance
  method: GET
  name: getaccountperformance
  path: /wealth/v1/accounts/{accountNumber}/performance
personas: []
provider_name: broadridge
provider_slug: broadridge
search_terms:
- get account performance
- listaccounts
- get account balances
- getaccount
- getaccountbalances
- broadridge
- getaccountperformance
- get account details
- get account positions
- getaccounttransactions
- api
- get account transactions
- list accounts
- getaccountpositions
slug: broadridge-capability
source_filename: broadridge-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Broadridge Wealth Management API\n  description: The Broadridge Wealth Management API provides access to account activity, balances, positions, and transaction\n    data for wealth management platforms. REST APIs enable broker-dealers and RIAs to integrate Broadridge back-office clearing\n    and custody data into front-office wealth management applications.\n  tags:\n  - Broadridge\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: broadridge\n    baseUri: https://api.broadridge.example.com\n    description: Broadridge Wealth Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BROADRIDGE_TOKEN}}'\n    resources:\n    - name: wealth-v1-accounts\n      path: /wealth/v1/accounts\n      operations:\n      - name: listaccounts\n        method: GET\n        description: List accounts\n        inputParameters:\n        - name: accountType\n    \
  \      in: query\n          type: string\n          description: Filter by account type\n        - name: status\n          in: query\n          type: string\n        - name: repId\n          in: query\n          type: string\n          description: Filter by registered representative ID\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wealth-v1-accounts-accountnumber\n      path: /wealth/v1/accounts/{accountNumber}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Get account details\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n          description: Account number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: wealth-v1-accounts-accountnumber-balances\n      path: /wealth/v1/accounts/{accountNumber}/balances\n      operations:\n      - name: getaccountbalances\n        method: GET\n        description: Get account balances\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n        - name: asOfDate\n          in: query\n          type: string\n          description: Get balances as of a specific date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wealth-v1-accounts-accountnumber-positions\n      path: /wealth/v1/accounts/{accountNumber}/positions\n      operations:\n      - name: getaccountpositions\n        method: GET\n        description: Get account positions\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n    \
  \      required: true\n        - name: asOfDate\n          in: query\n          type: string\n        - name: assetClass\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wealth-v1-accounts-accountnumber-transactions\n      path: /wealth/v1/accounts/{accountNumber}/transactions\n      operations:\n      - name: getaccounttransactions\n        method: GET\n        description: Get account transactions\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n        - name: toDate\n          in: query\n          type: string\n        - name: transactionType\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: pageSize\n\
  \          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wealth-v1-accounts-accountnumber-performance\n      path: /wealth/v1/accounts/{accountNumber}/performance\n      operations:\n      - name: getaccountperformance\n        method: GET\n        description: Get account performance\n        inputParameters:\n        - name: accountNumber\n          in: path\n          type: string\n          required: true\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n        - name: toDate\n          in: query\n          type: string\n        - name: benchmark\n          in: query\n          type: string\n          description: Benchmark ticker symbol for comparison\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n\
  \    port: 8080\n    namespace: broadridge-rest\n    description: REST adapter for Broadridge Wealth Management API.\n    resources:\n    - path: /wealth/v1/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: List accounts\n        call: broadridge.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wealth/v1/accounts/{accountNumber}\n      name: getaccount\n      operations:\n      - method: GET\n        name: getaccount\n        description: Get account details\n        call: broadridge.getaccount\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wealth/v1/accounts/{accountNumber}/balances\n      name: getaccountbalances\n      operations:\n      - method: GET\n        name: getaccountbalances\n        description: Get account balances\n        call: broadridge.getaccountbalances\n\
  \        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wealth/v1/accounts/{accountNumber}/positions\n      name: getaccountpositions\n      operations:\n      - method: GET\n        name: getaccountpositions\n        description: Get account positions\n        call: broadridge.getaccountpositions\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wealth/v1/accounts/{accountNumber}/transactions\n      name: getaccounttransactions\n      operations:\n      - method: GET\n        name: getaccounttransactions\n        description: Get account transactions\n        call: broadridge.getaccounttransactions\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wealth/v1/accounts/{accountNumber}/performance\n      name:\
  \ getaccountperformance\n      operations:\n      - method: GET\n        name: getaccountperformance\n        description: Get account performance\n        call: broadridge.getaccountperformance\n        with:\n          accountNumber: rest.accountNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: broadridge-mcp\n    transport: http\n    description: MCP adapter for Broadridge Wealth Management API for AI agent use.\n    tools:\n    - name: listaccounts\n      description: List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadridge.listaccounts\n      with:\n        accountType: tools.accountType\n        status: tools.status\n        repId: tools.repId\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: accountType\n        type: string\n        description: Filter by account type\n      - name:\
  \ status\n        type: string\n        description: status\n      - name: repId\n        type: string\n        description: Filter by registered representative ID\n      - name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccount\n      description: Get account details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadridge.getaccount\n      with:\n        accountNumber: tools.accountNumber\n      inputParameters:\n      - name: accountNumber\n        type: string\n        description: Account number\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountbalances\n      description: Get account balances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n \
  \     call: broadridge.getaccountbalances\n      with:\n        accountNumber: tools.accountNumber\n        asOfDate: tools.asOfDate\n      inputParameters:\n      - name: accountNumber\n        type: string\n        description: accountNumber\n        required: true\n      - name: asOfDate\n        type: string\n        description: Get balances as of a specific date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountpositions\n      description: Get account positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadridge.getaccountpositions\n      with:\n        accountNumber: tools.accountNumber\n        asOfDate: tools.asOfDate\n        assetClass: tools.assetClass\n      inputParameters:\n      - name: accountNumber\n        type: string\n        description: accountNumber\n        required: true\n      - name: asOfDate\n        type: string\n        description: asOfDate\n      -\
  \ name: assetClass\n        type: string\n        description: assetClass\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccounttransactions\n      description: Get account transactions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadridge.getaccounttransactions\n      with:\n        accountNumber: tools.accountNumber\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        transactionType: tools.transactionType\n        page: tools.page\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: accountNumber\n        type: string\n        description: accountNumber\n        required: true\n      - name: fromDate\n        type: string\n        description: fromDate\n        required: true\n      - name: toDate\n        type: string\n        description: toDate\n      - name: transactionType\n        type: string\n        description: transactionType\n      -\
  \ name: page\n        type: integer\n        description: page\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountperformance\n      description: Get account performance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadridge.getaccountperformance\n      with:\n        accountNumber: tools.accountNumber\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        benchmark: tools.benchmark\n      inputParameters:\n      - name: accountNumber\n        type: string\n        description: accountNumber\n        required: true\n      - name: fromDate\n        type: string\n        description: fromDate\n        required: true\n      - name: toDate\n        type: string\n        description: toDate\n      - name: benchmark\n        type: string\n        description: Benchmark ticker symbol for comparison\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BROADRIDGE_TOKEN: BROADRIDGE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/broadridge/refs/heads/main/capabilities/broadridge-capability.yaml
tags:
- Broadridge
- API
tools:
- description: List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Get account details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Get account balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbalances
- description: Get account positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountpositions
- description: Get account transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccounttransactions
- description: Get account performance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountperformance
---
