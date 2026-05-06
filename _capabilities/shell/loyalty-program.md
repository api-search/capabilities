---
categories: []
consumed_apis: []
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
- get balance
- get points balance
- list rewards catalogue
- list offers
- points
- retrieve shell go+ loyalty account profile and tier information
- oil and gas
- loyalty
- get loyalty account
- enroll a new loyalty program member
- redeem loyalty points for a reward from the shell catalogue
- aviation
- list loyalty transactions
- manage shell go+ loyalty accounts
- redeem points
- retail
- browse available rewards in shell go+ loyalty catalogue
- gas
- get loyalty account details
- enroll loyalty member
- mobility
- fleet management
- list available offers
- get loyalty points earn and redeem transaction history
- list available rewards
- fuel
- list personalized loyalty offers available for a member account
- redeem loyalty points
- renewable energy
- enroll member
- access specific loyalty account
- energy
- loyalty transaction history
- electric vehicle charging
- get current points balance
- manage loyalty offers
- rewards
- lubricants
- get account
- redeem points for a reward
- get current redeemable and pending points balance for a loyalty account
- list transactions
- browse shell rewards catalogue
- enroll a new customer in shell go+ loyalty program
- list rewards
- get loyalty transaction history
- access points balance
slug: loyalty-program
source_filename: loyalty-program.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shell Loyalty Program\n  description: Unified Shell Go+ loyalty program workflow combining account management, points tracking, rewards catalogue,\n    offer assignment, and redemption. Designed for partners integrating Shell loyalty into digital apps and services.\n  tags:\n  - Energy\n  - Loyalty\n  - Points\n  - Retail\n  - Rewards\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHELL_LOYALTY_TOKEN: SHELL_LOYALTY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: shell-loyalty\n    baseUri: https://api.shell.com/loyalty/v1\n    description: Shell Go+ loyalty program API\n    authentication:\n      type: bearer\n      token: '{{SHELL_LOYALTY_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Manage loyalty accounts\n      operations:\n      - name: enroll-account\n        method: POST\n        description: Enroll a new loyalty account\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.first_name}}'\n            lastName: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n            countryCode: '{{tools.country_code}}'\n      - name: get-account\n        method: GET\n        description: Get loyalty account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Loyalty account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-points-balance\n        method: GET\n        description: Get loyalty points balance for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n      \
  \    description: Loyalty account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: redeem-points\n        method: POST\n        description: Redeem loyalty points for a reward\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rewardId: '{{tools.reward_id}}'\n            pointsToRedeem: '{{tools.points_to_redeem}}'\n      - name: list-loyalty-transactions\n        method: GET\n        description: Get loyalty transaction history for an account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Loyalty account ID\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n     \
  \   - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalogue\n      path: /catalogue\n      description: Browse loyalty rewards catalogue\n      operations:\n      - name: list-catalogue\n        method: GET\n        description: List available loyalty rewards\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by reward category\n        - name: countryCode\n          in: query\n          type: string\n          required: false\n          description: Filter by country\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /accounts/{accountId}/offers\n      description:\
  \ Manage loyalty offers\n      operations:\n      - name: list-offers\n        method: GET\n        description: List available offers for a loyalty account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Loyalty account ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: shell-loyalty-program-api\n    description: Unified REST API for Shell Go+ loyalty program integration.\n    resources:\n    - path: /v1/loyalty-accounts\n      name: loyalty-accounts\n      description: Manage Shell Go+ loyalty accounts\n      operations:\n      - method: POST\n        name: enroll-member\n        description: Enroll a new loyalty program member\n        call: shell-loyalty.enroll-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/loyalty-accounts/{id}\n      name: loyalty-account\n      description: Access specific loyalty account\n      operations:\n      - method: GET\n        name: get-account\n        description: Get loyalty account details\n        call: shell-loyalty.get-account\n        with:\n          accountId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty-accounts/{id}/balance\n      name: points-balance\n      description: Access points balance\n      operations:\n      - method: GET\n        name: get-balance\n        description: Get current points balance\n        call: shell-loyalty.get-points-balance\n        with:\n          accountId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty-accounts/{id}/redeem\n      name: redemption\n      description: Redeem loyalty points\n      operations:\n      - method: POST\n        name: redeem-points\n        description: Redeem\
  \ points for a reward\n        call: shell-loyalty.redeem-points\n        with:\n          accountId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty-accounts/{id}/transactions\n      name: loyalty-transactions\n      description: Loyalty transaction history\n      operations:\n      - method: GET\n        name: list-transactions\n        description: Get loyalty transaction history\n        call: shell-loyalty.list-loyalty-transactions\n        with:\n          accountId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rewards\n      name: rewards\n      description: Browse Shell rewards catalogue\n      operations:\n      - method: GET\n        name: list-rewards\n        description: List available rewards\n        call: shell-loyalty.list-catalogue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/loyalty-accounts/{id}/offers\n     \
  \ name: offers\n      description: Manage loyalty offers\n      operations:\n      - method: GET\n        name: list-offers\n        description: List available offers\n        call: shell-loyalty.list-offers\n        with:\n          accountId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: shell-loyalty-program-mcp\n    transport: http\n    description: MCP server for AI-assisted Shell Go+ loyalty program management.\n    tools:\n    - name: enroll-loyalty-member\n      description: Enroll a new customer in Shell Go+ loyalty program\n      hints:\n        readOnly: false\n      call: shell-loyalty.enroll-account\n      with:\n        first_name: tools.first_name\n        last_name: tools.last_name\n        email: tools.email\n        country_code: tools.country_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-loyalty-account\n      description: Retrieve Shell Go+\
  \ loyalty account profile and tier information\n      hints:\n        readOnly: true\n      call: shell-loyalty.get-account\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-points-balance\n      description: Get current redeemable and pending points balance for a loyalty account\n      hints:\n        readOnly: true\n      call: shell-loyalty.get-points-balance\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: redeem-loyalty-points\n      description: Redeem loyalty points for a reward from the Shell catalogue\n      hints:\n        readOnly: false\n      call: shell-loyalty.redeem-points\n      with:\n        reward_id: tools.reward_id\n        points_to_redeem: tools.points_to_redeem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-rewards-catalogue\n      description: Browse available\
  \ rewards in Shell Go+ loyalty catalogue\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shell-loyalty.list-catalogue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-loyalty-transactions\n      description: Get loyalty points earn and redeem transaction history\n      hints:\n        readOnly: true\n      call: shell-loyalty.list-loyalty-transactions\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-available-offers\n      description: List personalized loyalty offers available for a member account\n      hints:\n        readOnly: true\n      call: shell-loyalty.list-offers\n      with:\n        accountId: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
