---
categories: []
consumed_apis:
- tsys-issuing
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
- card issuing
- file a dispute for a specific card transaction
- create cardholder account
- dispute management
- get spending limits and restrictions for a card
- get transaction history for a specific card
- create a new cardholder account in the card program
- issue card
- create a new account
- merchant services
- financial services
- individual account
- spending controls
- get account
- payments
- list transaction disputes in the card program
- list disputes
- list cardholder accounts
- create account
- cardholder account management
- cards for an account
- list all cardholder accounts in the card program
- get account details
- list accounts
- file dispute
- disputes
- issue a new card
- file a dispute
- get card spending controls
- list all cards associated with a cardholder account
- issue a new physical or virtual payment card for an account
- get details for a specific cardholder account including balance
- fintech
- cardholder management
- list account cards
- create dispute
- payment processing
- get card transactions
slug: card-issuing
source_filename: card-issuing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TSYS Card Issuing\"\n  description: \"Workflow capability for financial institutions and fintechs to manage card programs via the TSYS Issuing Platform. Covers cardholder onboarding, card issuance, spending controls, transaction monitoring, and dispute management.\"\n  tags:\n    - Card Issuing\n    - Cardholder Management\n    - Fintech\n    - Spending Controls\n    - Disputes\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TSYS_ISSUING_TOKEN: TSYS_ISSUING_TOKEN\n\ncapability:\n  consumes:\n    - import: tsys-issuing\n      location: ./shared/issuing-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: tsys-issuing-api\n      description: \"Unified REST API for TSYS card issuing program management.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Cardholder account management\"\n          operations:\n\
  \            - method: GET\n              name: list-accounts\n              description: \"List cardholder accounts\"\n              call: \"tsys-issuing.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new account\"\n              call: \"tsys-issuing.create-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}\n          name: account\n          description: \"Individual account\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get account details\"\n              call: \"tsys-issuing.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/accounts/{accountId}/cards\n          name: account-cards\n          description: \"Cards for an account\"\n          operations:\n            - method: GET\n              name: list-account-cards\n              description: \"List account cards\"\n              call: \"tsys-issuing.list-account-cards\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: issue-card\n              description: \"Issue a new card\"\n              call: \"tsys-issuing.issue-card\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes\n          name: disputes\n          description: \"Dispute management\"\n          operations:\n            - method: GET\n              name:\
  \ list-disputes\n              description: \"List disputes\"\n              call: \"tsys-issuing.list-disputes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dispute\n              description: \"File a dispute\"\n              call: \"tsys-issuing.create-dispute\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: tsys-issuing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TSYS card program management.\"\n      tools:\n        - name: list-accounts\n          description: \"List all cardholder accounts in the card program\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsys-issuing.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ create-cardholder-account\n          description: \"Create a new cardholder account in the card program\"\n          hints:\n            readOnly: false\n          call: \"tsys-issuing.create-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: \"Get details for a specific cardholder account including balance\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tsys-issuing.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-account-cards\n          description: \"List all cards associated with a cardholder account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsys-issuing.list-account-cards\"\n          with:\n            accountId: \"tools.accountId\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: issue-card\n          description: \"Issue a new physical or virtual payment card for an account\"\n          hints:\n            readOnly: false\n          call: \"tsys-issuing.issue-card\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-card-spending-controls\n          description: \"Get spending limits and restrictions for a card\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tsys-issuing.get-card-controls\"\n          with:\n            cardId: \"tools.cardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-card-transactions\n          description: \"Get transaction history for a specific card\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"tsys-issuing.list-card-transactions\"\n          with:\n            cardId: \"tools.cardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-disputes\n          description: \"List transaction disputes in the card program\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tsys-issuing.list-disputes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: file-dispute\n          description: \"File a dispute for a specific card transaction\"\n          hints:\n            readOnly: false\n          call: \"tsys-issuing.create-dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
