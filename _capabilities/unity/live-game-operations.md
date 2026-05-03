---
categories: []
consumed_apis:
- unity-economy
- unity-cloud-save
- unity-leaderboards
description: Unified capability for Unity live game operations combining Economy, Cloud Save, Leaderboards, and Remote Config APIs. Enables game economy management, player progression, competitive ranking, and real-time configuration for live service games.
layout: capability
name: Unity Live Game Operations
operations:
- description: Get All Currency Balances for a Player
  method: GET
  name: get-currency-balances
  path: /v1/players/{playerId}/currencies
- description: Add Currency to Player Balance
  method: POST
  name: add-currency
  path: /v1/players/{playerId}/currencies/{currencyId}/add
- description: Get Player Item Inventory
  method: GET
  name: get-inventory
  path: /v1/players/{playerId}/inventory
- description: Purchase a Virtual Item
  method: POST
  name: purchase-item
  path: /v1/players/{playerId}/purchases/virtual
- description: Get Player Game Save Data
  method: GET
  name: get-save-data
  path: /v1/players/{playerId}/save-data
- description: Save Player Game Progress
  method: POST
  name: save-data
  path: /v1/players/{playerId}/save-data
- description: List All Leaderboards
  method: GET
  name: list-leaderboards
  path: /v1/leaderboards
- description: Get Top Leaderboard Scores
  method: GET
  name: get-top-scores
  path: /v1/leaderboards/{leaderboardId}/scores
- description: Submit Player Score to Leaderboard
  method: POST
  name: submit-score
  path: /v1/leaderboards/{leaderboardId}/scores/players/{playerId}
- description: Get Player Score and Rank
  method: GET
  name: get-player-rank
  path: /v1/leaderboards/{leaderboardId}/scores/players/{playerId}
personas: []
provider_name: Unity
provider_slug: unity
search_terms:
- list all game leaderboards
- remote config
- purchase a virtual item
- game leaderboard management
- get currency balances
- get player game save data
- get a player's current rank and score on a leaderboard
- leaderboard score data
- add virtual currency to a player's balance
- save player game progress and state to the cloud
- cloud save
- submit leaderboard score
- add player currency
- deduct virtual currency from a player's balance
- list all leaderboards
- live ops
- virtual item purchases
- purchase item
- purchase virtual item
- economy
- game development
- save data
- get the top scores from a leaderboard
- submit a player's score to a leaderboard
- submit score
- game operations
- submit player score to leaderboard
- game services
- cloud gaming
- unity
- get player score and rank
- get player currencies
- get save data
- list leaderboards
- get all currency balances for a player
- retrieve a player's saved game progress and state
- purchase an in-game item using virtual currency
- player virtual currency balance management
- get player rank
- save player game progress
- get top scores
- player game save data
- add currency
- leaderboards
- add currency to player balance
- player-specific leaderboard score
- get inventory
- get player item inventory
- get all items in a player's inventory
- get player inventory
- deduct player currency
- get top leaderboard scores
- save player progress
- player item inventory
- get all virtual currency balances for a player
- get player progress
- multiplayer
- real-time 3d
slug: live-game-operations
source_filename: live-game-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unity Live Game Operations\"\n  description: \"Unified capability for Unity live game operations combining Economy, Cloud Save, Leaderboards, and Remote Config APIs. Enables game economy management, player progression, competitive ranking, and real-time configuration for live service games.\"\n  tags:\n    - Unity\n    - Live Ops\n    - Economy\n    - Leaderboards\n    - Cloud Save\n    - Remote Config\n    - Game Operations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNITY_ECONOMY_TOKEN: UNITY_ECONOMY_TOKEN\n      UNITY_CLOUD_SAVE_TOKEN: UNITY_CLOUD_SAVE_TOKEN\n      UNITY_LEADERBOARDS_TOKEN: UNITY_LEADERBOARDS_TOKEN\n\ncapability:\n  consumes:\n    - import: unity-economy\n      location: ./shared/economy.yaml\n    - import: unity-cloud-save\n      location: ./shared/cloud-save.yaml\n    - import: unity-leaderboards\n      location: ./shared/leaderboards.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: unity-live-ops-api\n      description: \"Unified REST API for Unity live game operations including economy, player data, and rankings.\"\n      resources:\n        - path: /v1/players/{playerId}/currencies\n          name: player-currencies\n          description: \"Player virtual currency balance management\"\n          operations:\n            - method: GET\n              name: get-currency-balances\n              description: \"Get All Currency Balances for a Player\"\n              call: \"unity-economy.get-player-currency-balances\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}/currencies/{currencyId}/add\n          name: add-currency\n          description: \"Add currency\
  \ to player balance\"\n          operations:\n            - method: POST\n              name: add-currency\n              description: \"Add Currency to Player Balance\"\n              call: \"unity-economy.increment-currency-balance\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                playerId: \"rest.playerId\"\n                currencyId: \"rest.currencyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}/inventory\n          name: player-inventory\n          description: \"Player item inventory\"\n          operations:\n            - method: GET\n              name: get-inventory\n              description: \"Get Player Item Inventory\"\n              call: \"unity-economy.get-player-inventory\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\
  \n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}/purchases/virtual\n          name: virtual-purchases\n          description: \"Virtual item purchases\"\n          operations:\n            - method: POST\n              name: purchase-item\n              description: \"Purchase a Virtual Item\"\n              call: \"unity-economy.make-virtual-purchase\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}/save-data\n          name: player-save-data\n          description: \"Player game save data\"\n          operations:\n            - method: GET\n              name: get-save-data\n              description:\
  \ \"Get Player Game Save Data\"\n              call: \"unity-cloud-save.get-player-data\"\n              with:\n                projectId: \"rest.projectId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: save-data\n              description: \"Save Player Game Progress\"\n              call: \"unity-cloud-save.set-player-data\"\n              with:\n                projectId: \"rest.projectId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leaderboards\n          name: leaderboards\n          description: \"Game leaderboard management\"\n          operations:\n            - method: GET\n              name: list-leaderboards\n              description: \"List All Leaderboards\"\n              call: \"unity-leaderboards.list-leaderboards\"\
  \n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leaderboards/{leaderboardId}/scores\n          name: leaderboard-scores\n          description: \"Leaderboard score data\"\n          operations:\n            - method: GET\n              name: get-top-scores\n              description: \"Get Top Leaderboard Scores\"\n              call: \"unity-leaderboards.get-leaderboard-scores\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                leaderboardId: \"rest.leaderboardId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leaderboards/{leaderboardId}/scores/players/{playerId}\n          name: player-leaderboard-score\n          description:\
  \ \"Player-specific leaderboard score\"\n          operations:\n            - method: POST\n              name: submit-score\n              description: \"Submit Player Score to Leaderboard\"\n              call: \"unity-leaderboards.add-player-score\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                leaderboardId: \"rest.leaderboardId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-player-rank\n              description: \"Get Player Score and Rank\"\n              call: \"unity-leaderboards.get-player-score\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                leaderboardId: \"rest.leaderboardId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: unity-live-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Unity live game operations management.\"\n      tools:\n        # Economy tools\n        - name: get-player-currencies\n          description: \"Get all virtual currency balances for a player\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-economy.get-player-currency-balances\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-player-currency\n          description: \"Add virtual currency to a player's balance\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-economy.increment-currency-balance\"\
  \n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            playerId: \"tools.playerId\"\n            currencyId: \"tools.currencyId\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: deduct-player-currency\n          description: \"Deduct virtual currency from a player's balance\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-economy.decrement-currency-balance\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            playerId: \"tools.playerId\"\n            currencyId: \"tools.currencyId\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-inventory\n          description: \"Get all items in a player's\
  \ inventory\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-economy.get-player-inventory\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: purchase-virtual-item\n          description: \"Purchase an in-game item using virtual currency\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-economy.make-virtual-purchase\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            playerId: \"tools.playerId\"\n            purchase_id: \"tools.purchase_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Cloud Save tools\n        - name: get-player-progress\n   \
  \       description: \"Retrieve a player's saved game progress and state\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-cloud-save.get-player-data\"\n          with:\n            projectId: \"tools.projectId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: save-player-progress\n          description: \"Save player game progress and state to the cloud\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"unity-cloud-save.set-player-data\"\n          with:\n            projectId: \"tools.projectId\"\n            playerId: \"tools.playerId\"\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Leaderboard tools\n        - name: list-leaderboards\n          description: \"List all game leaderboards\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"unity-leaderboards.list-leaderboards\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-scores\n          description: \"Get the top scores from a leaderboard\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unity-leaderboards.get-leaderboard-scores\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            leaderboardId: \"tools.leaderboardId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-leaderboard-score\n          description: \"Submit a player's score to a leaderboard\"\n          hints:\n            readOnly: false\n            idempotent: true\n     \
  \     call: \"unity-leaderboards.add-player-score\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            leaderboardId: \"tools.leaderboardId\"\n            playerId: \"tools.playerId\"\n            score: \"tools.score\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-rank\n          description: \"Get a player's current rank and score on a leaderboard\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-leaderboards.get-player-score\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            leaderboardId: \"tools.leaderboardId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unity/refs/heads/main/capabilities/live-game-operations.yaml
tags:
- Unity
- Live Ops
- Economy
- Leaderboards
- Cloud Save
- Remote Config
- Game Operations
tools:
- description: Get all virtual currency balances for a player
  hints:
    openWorld: false
    readOnly: true
  name: get-player-currencies
- description: Add virtual currency to a player's balance
  hints:
    idempotent: false
    readOnly: false
  name: add-player-currency
- description: Deduct virtual currency from a player's balance
  hints:
    idempotent: false
    readOnly: false
  name: deduct-player-currency
- description: Get all items in a player's inventory
  hints:
    openWorld: false
    readOnly: true
  name: get-player-inventory
- description: Purchase an in-game item using virtual currency
  hints:
    idempotent: false
    readOnly: false
  name: purchase-virtual-item
- description: Retrieve a player's saved game progress and state
  hints:
    openWorld: false
    readOnly: true
  name: get-player-progress
- description: Save player game progress and state to the cloud
  hints:
    idempotent: true
    readOnly: false
  name: save-player-progress
- description: List all game leaderboards
  hints:
    openWorld: true
    readOnly: true
  name: list-leaderboards
- description: Get the top scores from a leaderboard
  hints:
    openWorld: true
    readOnly: true
  name: get-top-scores
- description: Submit a player's score to a leaderboard
  hints:
    idempotent: true
    readOnly: false
  name: submit-leaderboard-score
- description: Get a player's current rank and score on a leaderboard
  hints:
    openWorld: false
    readOnly: true
  name: get-player-rank
---
