---
categories: []
consumed_apis:
- betsolutions-wallet
description: Unified casino platform workflow combining wallet management, player profile, and game catalog operations. Designed for casino operators and developers integrating BetSolutions into their gaming platforms. Provides complete coverage of player wallet operations (transfer and seamless modes), game discovery, and player data retrieval in a single workflow.
layout: capability
name: BetSolutions Casino Platform
operations:
- description: Retrieve current wallet balance for a player
  method: POST
  name: get-player-balance
  path: /v1/wallet/balance
- description: Deposit funds to a player's casino wallet
  method: POST
  name: deposit-funds
  path: /v1/wallet/deposit
- description: Withdraw funds from a player's casino wallet
  method: POST
  name: withdraw-funds
  path: /v1/wallet/withdraw
- description: Get the complete casino game catalog
  method: GET
  name: list-games
  path: /v1/games
- description: Get player profile and account information
  method: GET
  name: get-player
  path: /v1/players/{playerId}
personas: []
provider_name: BetSolutions
provider_slug: betsolutions
search_terms:
- deposit funds to player wallet
- Platform Developer
- withdraw funds from a casino player's wallet account
- get player profile
- get profile and account information for a casino player
- get player wallet balance
- get the current wallet balance for a casino player
- betting
- get the complete casino game catalog
- player profile and account information
- casinos
- betsolutions
- sports betting
- get the complete list of available betsolutions casino games with rtp and product metadata
- developer building casino platform features using the betsolutions api
- get player
- withdraw funds
- available casino games and product metadata
- player information
- casino game catalog
- retrieve current wallet balance for a player
- withdraw funds from a player's casino wallet
- online casino operator integrating betsolutions into their gaming platform
- deposit funds to a casino player's wallet account for game play
- withdraw funds from player wallet
- slots
- player fund deposits, withdrawals, and balance operations
- deposit funds to a player's casino wallet
- list games
- Casino Operator
- get player balance
- gambling
- casino
- list casino games
- wallet management, game catalog, and player operations for casino operators
- get player profile and account information
- deposit funds
- table games
- wallet
- gaming
slug: casino-platform
source_filename: casino-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"BetSolutions Casino Platform\"\n  description: >-\n    Unified casino platform workflow combining wallet management, player profile,\n    and game catalog operations. Designed for casino operators and developers\n    integrating BetSolutions into their gaming platforms. Provides complete\n    coverage of player wallet operations (transfer and seamless modes), game\n    discovery, and player data retrieval in a single workflow.\n  tags:\n    - BetSolutions\n    - Casino\n    - Gaming\n    - Wallet\n    - Slots\n    - Table Games\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BETSOLUTIONS_MERCHANT_ID: BETSOLUTIONS_MERCHANT_ID\n      BETSOLUTIONS_SECRET_KEY: BETSOLUTIONS_SECRET_KEY\n\ncapability:\n  consumes:\n    - import: betsolutions-wallet\n      location: ./shared/wallet-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: casino-platform-api\n  \
  \    description: \"Unified REST API for BetSolutions casino platform operations.\"\n      resources:\n        - path: /v1/wallet/balance\n          name: balance\n          description: \"Get player wallet balance\"\n          operations:\n            - method: POST\n              name: get-player-balance\n              description: \"Retrieve current wallet balance for a player\"\n              call: \"betsolutions-wallet.get-balance\"\n              with:\n                merchantId: \"rest.merchantId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/wallet/deposit\n          name: deposit\n          description: \"Deposit funds to player wallet\"\n          operations:\n            - method: POST\n              name: deposit-funds\n              description: \"Deposit funds to a player's casino wallet\"\n              call: \"betsolutions-wallet.deposit-funds\"\n  \
  \            with:\n                merchantId: \"rest.merchantId\"\n                playerId: \"rest.playerId\"\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/wallet/withdraw\n          name: withdraw\n          description: \"Withdraw funds from player wallet\"\n          operations:\n            - method: POST\n              name: withdraw-funds\n              description: \"Withdraw funds from a player's casino wallet\"\n              call: \"betsolutions-wallet.withdraw-funds\"\n              with:\n                merchantId: \"rest.merchantId\"\n                playerId: \"rest.playerId\"\n                amount: \"rest.amount\"\n                currency: \"rest.currency\"\n                transactionId: \"rest.transactionId\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n        - path: /v1/games\n          name: games\n          description: \"Casino game catalog\"\n          operations:\n            - method: GET\n              name: list-games\n              description: \"Get the complete casino game catalog\"\n              call: \"betsolutions-wallet.get-game-list\"\n              with:\n                merchantId: \"rest.merchantId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}\n          name: player\n          description: \"Player information\"\n          operations:\n            - method: GET\n              name: get-player\n              description: \"Get player profile and account information\"\n              call: \"betsolutions-wallet.get-player-info\"\n              with:\n                playerId: \"rest.playerId\"\n                merchantId: \"rest.merchantId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: casino-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted BetSolutions casino platform management.\"\n      tools:\n        - name: get-player-balance\n          description: \"Get the current wallet balance for a casino player\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"betsolutions-wallet.get-balance\"\n          with:\n            merchantId: \"tools.merchantId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deposit-funds\n          description: \"Deposit funds to a casino player's wallet account for game play\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"betsolutions-wallet.deposit-funds\"\n          with:\n            merchantId:\
  \ \"tools.merchantId\"\n            playerId: \"tools.playerId\"\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: withdraw-funds\n          description: \"Withdraw funds from a casino player's wallet account\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"betsolutions-wallet.withdraw-funds\"\n          with:\n            merchantId: \"tools.merchantId\"\n            playerId: \"tools.playerId\"\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-casino-games\n          description: \"Get the complete list of available BetSolutions casino games with RTP and product\
  \ metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"betsolutions-wallet.get-game-list\"\n          with:\n            merchantId: \"tools.merchantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-profile\n          description: \"Get profile and account information for a casino player\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"betsolutions-wallet.get-player-info\"\n          with:\n            merchantId: \"tools.merchantId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/betsolutions/refs/heads/main/capabilities/casino-platform.yaml
tags:
- BetSolutions
- Casino
- Gaming
- Wallet
- Slots
- Table Games
tools:
- description: Get the current wallet balance for a casino player
  hints:
    openWorld: false
    readOnly: true
  name: get-player-balance
- description: Deposit funds to a casino player's wallet account for game play
  hints:
    destructive: false
    readOnly: false
  name: deposit-funds
- description: Withdraw funds from a casino player's wallet account
  hints:
    destructive: false
    readOnly: false
  name: withdraw-funds
- description: Get the complete list of available BetSolutions casino games with RTP and product metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-casino-games
- description: Get profile and account information for a casino player
  hints:
    openWorld: false
    readOnly: true
  name: get-player-profile
---
