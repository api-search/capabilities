---
categories: []
consumed_apis: []
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
- casino game catalog
- player information
- developer building casino platform features using the betsolutions api
- withdraw funds
- player fund deposits, withdrawals, and balance operations
- player profile and account information
- wallet
- get the complete list of available betsolutions casino games with rtp and product metadata
- get player
- online casino operator integrating betsolutions into their gaming platform
- casino
- list casino games
- withdraw funds from a casino player's wallet account
- get player wallet balance
- deposit funds to a casino player's wallet account for game play
- get profile and account information for a casino player
- Platform Developer
- get player balance
- get the complete casino game catalog
- betting
- retrieve current wallet balance for a player
- gaming
- withdraw funds from a player's casino wallet
- Casino Operator
- get player profile and account information
- slots
- wallet management, game catalog, and player operations for casino operators
- casinos
- gambling
- sports betting
- get player profile
- table games
- deposit funds
- get the current wallet balance for a casino player
- withdraw funds from player wallet
- deposit funds to a player's casino wallet
- available casino games and product metadata
- list games
- betsolutions
- deposit funds to player wallet
slug: casino-platform
source_filename: casino-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BetSolutions Casino Platform\n  description: Unified casino platform workflow combining wallet management, player profile, and game catalog operations.\n    Designed for casino operators and developers integrating BetSolutions into their gaming platforms. Provides complete coverage\n    of player wallet operations (transfer and seamless modes), game discovery, and player data retrieval in a single workflow.\n  tags:\n  - BetSolutions\n  - Casino\n  - Gaming\n  - Wallet\n  - Slots\n  - Table Games\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BETSOLUTIONS_MERCHANT_ID: BETSOLUTIONS_MERCHANT_ID\n    BETSOLUTIONS_SECRET_KEY: BETSOLUTIONS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: betsolutions-wallet\n    baseUri: https://api.betsolutions.com/v1\n    description: BetSolutions Casino API for wallet management and game integration.\n    authentication:\n      type: apikey\n\
  \      key: hash\n      value: '{{BETSOLUTIONS_HASH}}'\n      placement: query\n    resources:\n    - name: wallet\n      path: /wallet\n      description: Wallet operations for casino players\n      operations:\n      - name: authenticate-player\n        method: GET\n        description: Authenticate a player and generate a private token\n        inputParameters:\n        - name: merchantId\n          in: query\n          type: string\n          required: true\n          description: Merchant unique identifier\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: Public player token\n        - name: hash\n          in: query\n          type: string\n          required: true\n          description: SHA-256 authentication hash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deposit-funds\n        method: POST\n        description:\
  \ Deposit funds to a player's wallet (transfer mode)\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            playerId: '{{tools.playerId}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            transactionId: '{{tools.transactionId}}'\n            hash: '{{tools.hash}}'\n      - name: withdraw-funds\n        method: POST\n        description: Withdraw funds from a player's wallet (transfer mode)\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            playerId: '{{tools.playerId}}'\n            amount: '{{tools.amount}}'\n\
  \            currency: '{{tools.currency}}'\n            transactionId: '{{tools.transactionId}}'\n            hash: '{{tools.hash}}'\n      - name: get-balance\n        method: POST\n        description: Retrieve a player's current wallet balance\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            playerId: '{{tools.playerId}}'\n            hash: '{{tools.hash}}'\n    - name: game\n      path: /game\n      description: Game management and listing\n      operations:\n      - name: get-game-list\n        method: POST\n        description: Retrieve available games with product metadata\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            merchantId: '{{tools.merchantId}}'\n            hash: '{{tools.hash}}'\n    - name: player\n      path: /player\n      description: Player information retrieval\n      operations:\n      - name: get-player-info\n        method: POST\n        description: Get player profile details\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantId: '{{tools.merchantId}}'\n            playerId: '{{tools.playerId}}'\n            hash: '{{tools.hash}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: casino-platform-api\n    description: Unified REST API for BetSolutions casino platform operations.\n    resources:\n    - path: /v1/wallet/balance\n      name: balance\n      description: Get player wallet balance\n      operations:\n      - method: POST\n        name: get-player-balance\n\
  \        description: Retrieve current wallet balance for a player\n        call: betsolutions-wallet.get-balance\n        with:\n          merchantId: rest.merchantId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/wallet/deposit\n      name: deposit\n      description: Deposit funds to player wallet\n      operations:\n      - method: POST\n        name: deposit-funds\n        description: Deposit funds to a player's casino wallet\n        call: betsolutions-wallet.deposit-funds\n        with:\n          merchantId: rest.merchantId\n          playerId: rest.playerId\n          amount: rest.amount\n          currency: rest.currency\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/wallet/withdraw\n      name: withdraw\n      description: Withdraw funds from player wallet\n      operations:\n      - method: POST\n        name:\
  \ withdraw-funds\n        description: Withdraw funds from a player's casino wallet\n        call: betsolutions-wallet.withdraw-funds\n        with:\n          merchantId: rest.merchantId\n          playerId: rest.playerId\n          amount: rest.amount\n          currency: rest.currency\n          transactionId: rest.transactionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/games\n      name: games\n      description: Casino game catalog\n      operations:\n      - method: GET\n        name: list-games\n        description: Get the complete casino game catalog\n        call: betsolutions-wallet.get-game-list\n        with:\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}\n      name: player\n      description: Player information\n      operations:\n      - method: GET\n        name: get-player\n        description: Get player profile and account\
  \ information\n        call: betsolutions-wallet.get-player-info\n        with:\n          playerId: rest.playerId\n          merchantId: rest.merchantId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: casino-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted BetSolutions casino platform management.\n    tools:\n    - name: get-player-balance\n      description: Get the current wallet balance for a casino player\n      hints:\n        readOnly: true\n        openWorld: false\n      call: betsolutions-wallet.get-balance\n      with:\n        merchantId: tools.merchantId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deposit-funds\n      description: Deposit funds to a casino player's wallet account for game play\n      hints:\n        readOnly: false\n        destructive: false\n      call: betsolutions-wallet.deposit-funds\n\
  \      with:\n        merchantId: tools.merchantId\n        playerId: tools.playerId\n        amount: tools.amount\n        currency: tools.currency\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: withdraw-funds\n      description: Withdraw funds from a casino player's wallet account\n      hints:\n        readOnly: false\n        destructive: false\n      call: betsolutions-wallet.withdraw-funds\n      with:\n        merchantId: tools.merchantId\n        playerId: tools.playerId\n        amount: tools.amount\n        currency: tools.currency\n        transactionId: tools.transactionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-casino-games\n      description: Get the complete list of available BetSolutions casino games with RTP and product metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: betsolutions-wallet.get-game-list\n      with:\n\
  \        merchantId: tools.merchantId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-profile\n      description: Get profile and account information for a casino player\n      hints:\n        readOnly: true\n        openWorld: false\n      call: betsolutions-wallet.get-player-info\n      with:\n        merchantId: tools.merchantId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
