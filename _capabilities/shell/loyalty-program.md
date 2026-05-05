---
categories: []
consumed_apis:
- shell-loyalty
description: Unified Shell Go+ loyalty program workflow combining account management, points tracking, rewards catalogue, offer assignment, and redemption. Designed for partners integrating Shell loyalty into digital apps and services.
layout: capability
name: Shell Loyalty Program
operations:
- description: Enroll a new loyalty program member
  method: POST
  name: enroll-member
  path: /v1/loyalty-accounts
- description: Get loyalty account details
  method: GET
  name: get-account
  path: /v1/loyalty-accounts/{id}
- description: Get current points balance
  method: GET
  name: get-balance
  path: /v1/loyalty-accounts/{id}/balance
- description: Redeem points for a reward
  method: POST
  name: redeem-points
  path: /v1/loyalty-accounts/{id}/redeem
- description: Get loyalty transaction history
  method: GET
  name: list-transactions
  path: /v1/loyalty-accounts/{id}/transactions
- description: List available rewards
  method: GET
  name: list-rewards
  path: /v1/rewards
- description: List available offers
  method: GET
  name: list-offers
  path: /v1/loyalty-accounts/{id}/offers
personas: []
provider_name: Shell
provider_slug: shell
search_terms:
- list rewards catalogue
- get loyalty account
- renewable energy
- list loyalty transactions
- list rewards
- list available rewards
- get points balance
- enroll member
- get account
- loyalty transaction history
- manage shell go+ loyalty accounts
- redeem loyalty points
- list offers
- enroll loyalty member
- get loyalty transaction history
- redeem loyalty points for a reward from the shell catalogue
- browse available rewards in shell go+ loyalty catalogue
- mobility
- list personalized loyalty offers available for a member account
- gas
- manage loyalty offers
- list available offers
- electric vehicle charging
- enroll a new loyalty program member
- get loyalty account details
- access points balance
- get current points balance
- loyalty
- redeem points for a reward
- get loyalty points earn and redeem transaction history
- get balance
- redeem points
- oil and gas
- fuel
- retail
- points
- enroll a new customer in shell go+ loyalty program
- list transactions
- rewards
- lubricants
- get current redeemable and pending points balance for a loyalty account
- browse shell rewards catalogue
- energy
- access specific loyalty account
- retrieve shell go+ loyalty account profile and tier information
- aviation
- fleet management
slug: loyalty-program
source_filename: loyalty-program.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shell Loyalty Program\"\n  description: >-\n    Unified Shell Go+ loyalty program workflow combining account management,\n    points tracking, rewards catalogue, offer assignment, and redemption.\n    Designed for partners integrating Shell loyalty into digital apps and services.\n  tags:\n    - Energy\n    - Loyalty\n    - Points\n    - Retail\n    - Rewards\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHELL_LOYALTY_TOKEN: SHELL_LOYALTY_TOKEN\n\ncapability:\n  consumes:\n    - import: shell-loyalty\n      location: ./shared/loyalty.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: shell-loyalty-program-api\n      description: \"Unified REST API for Shell Go+ loyalty program integration.\"\n      resources:\n        - path: /v1/loyalty-accounts\n          name: loyalty-accounts\n          description: \"Manage Shell Go+ loyalty accounts\"\n       \
  \   operations:\n            - method: POST\n              name: enroll-member\n              description: \"Enroll a new loyalty program member\"\n              call: \"shell-loyalty.enroll-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/loyalty-accounts/{id}\n          name: loyalty-account\n          description: \"Access specific loyalty account\"\n          operations:\n            - method: GET\n              name: get-account\n              description: \"Get loyalty account details\"\n              call: \"shell-loyalty.get-account\"\n              with:\n                accountId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/loyalty-accounts/{id}/balance\n          name: points-balance\n          description: \"Access points balance\"\n          operations:\n            - method: GET\n              name: get-balance\n\
  \              description: \"Get current points balance\"\n              call: \"shell-loyalty.get-points-balance\"\n              with:\n                accountId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/loyalty-accounts/{id}/redeem\n          name: redemption\n          description: \"Redeem loyalty points\"\n          operations:\n            - method: POST\n              name: redeem-points\n              description: \"Redeem points for a reward\"\n              call: \"shell-loyalty.redeem-points\"\n              with:\n                accountId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/loyalty-accounts/{id}/transactions\n          name: loyalty-transactions\n          description: \"Loyalty transaction history\"\n          operations:\n            - method: GET\n              name: list-transactions\n\
  \              description: \"Get loyalty transaction history\"\n              call: \"shell-loyalty.list-loyalty-transactions\"\n              with:\n                accountId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rewards\n          name: rewards\n          description: \"Browse Shell rewards catalogue\"\n          operations:\n            - method: GET\n              name: list-rewards\n              description: \"List available rewards\"\n              call: \"shell-loyalty.list-catalogue\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/loyalty-accounts/{id}/offers\n          name: offers\n          description: \"Manage loyalty offers\"\n          operations:\n            - method: GET\n              name: list-offers\n              description: \"List available offers\"\n              call: \"shell-loyalty.list-offers\"\
  \n              with:\n                accountId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: shell-loyalty-program-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Shell Go+ loyalty program management.\"\n      tools:\n        - name: enroll-loyalty-member\n          description: \"Enroll a new customer in Shell Go+ loyalty program\"\n          hints:\n            readOnly: false\n          call: \"shell-loyalty.enroll-account\"\n          with:\n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n            email: \"tools.email\"\n            country_code: \"tools.country_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-loyalty-account\n          description: \"Retrieve Shell Go+ loyalty account profile and tier information\"\n    \
  \      hints:\n            readOnly: true\n          call: \"shell-loyalty.get-account\"\n          with:\n            accountId: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-points-balance\n          description: \"Get current redeemable and pending points balance for a loyalty account\"\n          hints:\n            readOnly: true\n          call: \"shell-loyalty.get-points-balance\"\n          with:\n            accountId: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: redeem-loyalty-points\n          description: \"Redeem loyalty points for a reward from the Shell catalogue\"\n          hints:\n            readOnly: false\n          call: \"shell-loyalty.redeem-points\"\n          with:\n            reward_id: \"tools.reward_id\"\n            points_to_redeem: \"tools.points_to_redeem\"\n          outputParameters:\n  \
  \          - type: object\n              mapping: \"$.\"\n        - name: list-rewards-catalogue\n          description: \"Browse available rewards in Shell Go+ loyalty catalogue\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shell-loyalty.list-catalogue\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-loyalty-transactions\n          description: \"Get loyalty points earn and redeem transaction history\"\n          hints:\n            readOnly: true\n          call: \"shell-loyalty.list-loyalty-transactions\"\n          with:\n            accountId: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-available-offers\n          description: \"List personalized loyalty offers available for a member account\"\n          hints:\n            readOnly: true\n          call: \"shell-loyalty.list-offers\"\
  \n          with:\n            accountId: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shell/refs/heads/main/capabilities/loyalty-program.yaml
tags:
- Energy
- Loyalty
- Points
- Retail
- Rewards
tools:
- description: Enroll a new customer in Shell Go+ loyalty program
  hints:
    readOnly: false
  name: enroll-loyalty-member
- description: Retrieve Shell Go+ loyalty account profile and tier information
  hints:
    readOnly: true
  name: get-loyalty-account
- description: Get current redeemable and pending points balance for a loyalty account
  hints:
    readOnly: true
  name: get-points-balance
- description: Redeem loyalty points for a reward from the Shell catalogue
  hints:
    readOnly: false
  name: redeem-loyalty-points
- description: Browse available rewards in Shell Go+ loyalty catalogue
  hints:
    openWorld: true
    readOnly: true
  name: list-rewards-catalogue
- description: Get loyalty points earn and redeem transaction history
  hints:
    readOnly: true
  name: list-loyalty-transactions
- description: List personalized loyalty offers available for a member account
  hints:
    readOnly: true
  name: list-available-offers
---
