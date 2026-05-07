---
categories: []
consumed_apis: []
description: Workflow capability for financial institutions and fintechs to manage card programs via the TSYS Issuing Platform. Covers cardholder onboarding, card issuance, spending controls, transaction monitoring, and dispute management.
layout: capability
name: TSYS Card Issuing
operations:
- description: List cardholder accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new account
  method: POST
  name: create-account
  path: /v1/accounts
- description: Get account details
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: List account cards
  method: GET
  name: list-account-cards
  path: /v1/accounts/{accountId}/cards
- description: Issue a new card
  method: POST
  name: issue-card
  path: /v1/accounts/{accountId}/cards
- description: List disputes
  method: GET
  name: list-disputes
  path: /v1/disputes
- description: File a dispute
  method: POST
  name: create-dispute
  path: /v1/disputes
personas: []
provider_name: Total System Services
provider_slug: total-system-services
search_terms:
- disputes
- get account
- create cardholder account
- get card transactions
- spending controls
- cardholder account management
- file a dispute for a specific card transaction
- create dispute
- list all cardholder accounts in the card program
- get spending limits and restrictions for a card
- issue a new physical or virtual payment card for an account
- get account details
- list accounts
- cards for an account
- card issuing
- fintech
- cardholder management
- get details for a specific cardholder account including balance
- file a dispute
- list disputes
- create a new account
- create account
- payment processing
- financial services
- dispute management
- file dispute
- create a new cardholder account in the card program
- issue card
- merchant services
- issue a new card
- list transaction disputes in the card program
- list all cards associated with a cardholder account
- payments
- list account cards
- get transaction history for a specific card
- individual account
- list cardholder accounts
- get card spending controls
slug: card-issuing
source_filename: card-issuing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TSYS Card Issuing\n  description: Workflow capability for financial institutions and fintechs to manage card programs via the TSYS Issuing Platform.\n    Covers cardholder onboarding, card issuance, spending controls, transaction monitoring, and dispute management.\n  tags:\n  - Card Issuing\n  - Cardholder Management\n  - Fintech\n  - Spending Controls\n  - Disputes\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TSYS_ISSUING_TOKEN: TSYS_ISSUING_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tsys-issuing\n    baseUri: https://issuing.api.tsys.com/v1\n    description: TSYS Issuing Platform API for card program management\n    authentication:\n      type: bearer\n      token: '{{TSYS_ISSUING_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Cardholder account management\n      operations:\n      - name: list-accounts\n        method: GET\n\
  \        description: List all cardholder accounts\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new cardholder account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cardholder: '{{tools.cardholder}}'\n            creditLimit: '{{tools.creditLimit}}'\n    - name: account\n      path: /accounts/{accountId}\n      description: Individual account operations\n      operations:\n      - name: get-account\n\
  \        method: GET\n        description: Get cardholder account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-cards\n      path: /accounts/{accountId}/cards\n      description: Cards for an account\n      operations:\n      - name: list-account-cards\n        method: GET\n        description: List all cards for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: issue-card\n        method: POST\n        description: Issue a new card for an account\n \
  \       inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            network: '{{tools.network}}'\n    - name: card-transactions\n      path: /cards/{cardId}/transactions\n      description: Card transaction history\n      operations:\n      - name: list-card-transactions\n        method: GET\n        description: Get transaction history for a card\n        inputParameters:\n        - name: cardId\n          in: path\n          type: string\n          required: true\n          description: Card identifier\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date\n        - name: endDate\n  \
  \        in: query\n          type: string\n          required: false\n          description: End date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: card-controls\n      path: /cards/{cardId}/controls\n      description: Card spending controls\n      operations:\n      - name: get-card-controls\n        method: GET\n        description: Get spending controls for a card\n        inputParameters:\n        - name: cardId\n          in: path\n          type: string\n          required: true\n          description: Card identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: disputes\n      path: /disputes\n      description: Transaction dispute management\n      operations:\n      - name: list-disputes\n        method: GET\n        description: List transaction disputes\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dispute\n        method: POST\n        description: File a transaction dispute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            transactionId: '{{tools.transactionId}}'\n            reason: '{{tools.reason}}'\n            amount: '{{tools.amount}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: tsys-issuing-api\n    description: Unified REST API for TSYS card issuing program management.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Cardholder account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List cardholder accounts\n        call: tsys-issuing.list-accounts\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-account\n        description: Create a new account\n        call: tsys-issuing.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account\n      description: Individual account\n      operations:\n      - method: GET\n        name: get-account\n        description: Get account details\n        call: tsys-issuing.get-account\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/cards\n      name: account-cards\n      description: Cards for an account\n      operations:\n      - method: GET\n        name: list-account-cards\n        description: List account cards\n        call: tsys-issuing.list-account-cards\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: issue-card\n        description: Issue a new card\n        call: tsys-issuing.issue-card\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/disputes\n      name: disputes\n      description: Dispute management\n      operations:\n      - method: GET\n        name: list-disputes\n        description: List disputes\n        call: tsys-issuing.list-disputes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dispute\n        description: File a dispute\n        call: tsys-issuing.create-dispute\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: tsys-issuing-mcp\n    transport: http\n    description: MCP server for AI-assisted TSYS card program management.\n    tools:\n    - name: list-accounts\n      description: List all cardholder accounts in\
  \ the card program\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsys-issuing.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cardholder-account\n      description: Create a new cardholder account in the card program\n      hints:\n        readOnly: false\n      call: tsys-issuing.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get details for a specific cardholder account including balance\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tsys-issuing.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-account-cards\n      description: List all cards associated with a cardholder account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsys-issuing.list-account-cards\n      with:\n\
  \        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: issue-card\n      description: Issue a new physical or virtual payment card for an account\n      hints:\n        readOnly: false\n      call: tsys-issuing.issue-card\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card-spending-controls\n      description: Get spending limits and restrictions for a card\n      hints:\n        readOnly: true\n        idempotent: true\n      call: tsys-issuing.get-card-controls\n      with:\n        cardId: tools.cardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card-transactions\n      description: Get transaction history for a specific card\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsys-issuing.list-card-transactions\n      with:\n        cardId: tools.cardId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-disputes\n      description: List transaction disputes in the card program\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tsys-issuing.list-disputes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: file-dispute\n      description: File a dispute for a specific card transaction\n      hints:\n        readOnly: false\n      call: tsys-issuing.create-dispute\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/total-system-services/refs/heads/main/capabilities/card-issuing.yaml
tags:
- Card Issuing
- Cardholder Management
- Fintech
- Spending Controls
- Disputes
tools:
- description: List all cardholder accounts in the card program
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Create a new cardholder account in the card program
  hints:
    readOnly: false
  name: create-cardholder-account
- description: Get details for a specific cardholder account including balance
  hints:
    idempotent: true
    readOnly: true
  name: get-account
- description: List all cards associated with a cardholder account
  hints:
    openWorld: true
    readOnly: true
  name: list-account-cards
- description: Issue a new physical or virtual payment card for an account
  hints:
    readOnly: false
  name: issue-card
- description: Get spending limits and restrictions for a card
  hints:
    idempotent: true
    readOnly: true
  name: get-card-spending-controls
- description: Get transaction history for a specific card
  hints:
    openWorld: true
    readOnly: true
  name: get-card-transactions
- description: List transaction disputes in the card program
  hints:
    openWorld: true
    readOnly: true
  name: list-disputes
- description: File a dispute for a specific card transaction
  hints:
    readOnly: false
  name: file-dispute
---
