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
- list casino games
- gambling
- available casino games and product metadata
- list games
- wallet management, game catalog, and player operations for casino operators
- get the complete list of available betsolutions casino games with rtp and product metadata
- betting
- retrieve current wallet balance for a player
- get player wallet balance
- deposit funds to player wallet
- deposit funds to a casino player's wallet account for game play
- get player balance
- deposit funds
- table games
- player information
- withdraw funds from a player's casino wallet
- get player profile
- deposit funds to a player's casino wallet
- player profile and account information
- online casino operator integrating betsolutions into their gaming platform
- casino game catalog
- get player
- get profile and account information for a casino player
- sports betting
- betsolutions
- slots
- get player profile and account information
- gaming
- wallet
- casino
- withdraw funds
- casinos
- get the complete casino game catalog
- developer building casino platform features using the betsolutions api
- withdraw funds from player wallet
- Casino Operator
- player fund deposits, withdrawals, and balance operations
- Platform Developer
- withdraw funds from a casino player's wallet account
- get the current wallet balance for a casino player
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
