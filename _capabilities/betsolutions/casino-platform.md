---
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
- withdraw funds
- deposit funds to a player's casino wallet
- list games
- retrieve current wallet balance for a player
- get the complete casino game catalog
- Casino Operator
- developer building casino platform features using the betsolutions api
- slots
- get player profile and account information
- player profile and account information
- get player
- wallet
- wallet management, game catalog, and player operations for casino operators
- casinos
- Platform Developer
- gaming
- available casino games and product metadata
- get profile and account information for a casino player
- betting
- online casino operator integrating betsolutions into their gaming platform
- get player balance
- betsolutions
- list casino games
- gambling
- get player wallet balance
- get player profile
- casino game catalog
- withdraw funds from a casino player's wallet account
- withdraw funds from player wallet
- table games
- deposit funds to a casino player's wallet account for game play
- casino
- get the complete list of available betsolutions casino games with rtp and product metadata
- get the current wallet balance for a casino player
- deposit funds
- player fund deposits, withdrawals, and balance operations
- deposit funds to player wallet
- sports betting
- withdraw funds from a player's casino wallet
- player information
slug: casino-platform
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
