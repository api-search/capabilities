---
categories: []
consumed_apis: []
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
- remote config
- get player game save data
- get all virtual currency balances for a player
- get player item inventory
- get a player's current rank and score on a leaderboard
- cloud save
- submit a player's score to a leaderboard
- game development
- purchase virtual item
- get player inventory
- live ops
- player virtual currency balance management
- list all game leaderboards
- get all currency balances for a player
- player game save data
- save player game progress
- get the top scores from a leaderboard
- retrieve a player's saved game progress and state
- get player progress
- game leaderboard management
- unity
- purchase item
- deduct virtual currency from a player's balance
- game services
- leaderboard score data
- get currency balances
- list all leaderboards
- add currency to player balance
- add virtual currency to a player's balance
- get player currencies
- get player score and rank
- save player game progress and state to the cloud
- get inventory
- get top leaderboard scores
- purchase an in-game item using virtual currency
- submit leaderboard score
- get save data
- multiplayer
- cloud gaming
- get top scores
- player-specific leaderboard score
- leaderboards
- purchase a virtual item
- save data
- player item inventory
- deduct player currency
- add currency
- economy
- get player rank
- real-time 3d
- submit player score to leaderboard
- save player progress
- game operations
- submit score
- add player currency
- get all items in a player's inventory
- virtual item purchases
- list leaderboards
slug: live-game-operations
source_filename: live-game-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unity Live Game Operations\n  description: Unified capability for Unity live game operations combining Economy, Cloud Save, Leaderboards, and Remote Config\n    APIs. Enables game economy management, player progression, competitive ranking, and real-time configuration for live service\n    games.\n  tags:\n  - Unity\n  - Live Ops\n  - Economy\n  - Leaderboards\n  - Cloud Save\n  - Remote Config\n  - Game Operations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNITY_ECONOMY_TOKEN: UNITY_ECONOMY_TOKEN\n    UNITY_CLOUD_SAVE_TOKEN: UNITY_CLOUD_SAVE_TOKEN\n    UNITY_LEADERBOARDS_TOKEN: UNITY_LEADERBOARDS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: unity-economy\n    baseUri: https://economy.services.api.unity.com\n    description: Unity Economy API for in-game currency and inventory management\n    authentication:\n      type: bearer\n      token: '{{UNITY_ECONOMY_TOKEN}}'\n\
  \    resources:\n    - name: currency-balances\n      path: /v2/projects/{projectId}/environments/{environmentId}/players/{playerId}/currencies\n      description: Player currency balance management\n      operations:\n      - name: get-player-currency-balances\n        method: GET\n        description: Get all currency balances for a player\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: currency-increment\n      path: /v2/projects/{projectId}/environments/{environmentId}/players/{playerId}/currencies/{currencyId}/increment\n\
  \      description: Increment player currency balance\n      operations:\n      - name: increment-currency-balance\n        method: POST\n        description: Increase a player's currency balance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        - name: currencyId\n          in: path\n          type: string\n          required: true\n          description: Currency identifier (e.g., GOLD, GEMS)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            amount: '{{tools.amount}}'\n    - name: currency-decrement\n      path: /v2/projects/{projectId}/environments/{environmentId}/players/{playerId}/currencies/{currencyId}/decrement\n      description: Decrement player currency balance\n      operations:\n      - name: decrement-currency-balance\n        method: POST\n        description: Decrease a player's currency balance\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        - name: currencyId\n          in: path\n          type: string\n          required: true\n          description: Currency identifier\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n    - name: inventory\n      path: /v2/projects/{projectId}/environments/{environmentId}/players/{playerId}/inventory\n      description: Player inventory management\n      operations:\n      - name: get-player-inventory\n        method: GET\n        description: Get all inventory items for a player\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-purchases\n      path: /v2/projects/{projectId}/environments/{environmentId}/players/{playerId}/purchases/virtual\n      description: Virtual purchase processing\n      operations:\n      - name: make-virtual-purchase\n        method: POST\n        description: Process a virtual purchase for a player\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.purchase_id}}'\n  - type: http\n    namespace: unity-cloud-save\n    baseUri: https://cloud-save.services.api.unity.com\n    description: Unity Cloud Save API for player game state persistence\n    authentication:\n      type: bearer\n      token: '{{UNITY_CLOUD_SAVE_TOKEN}}'\n    resources:\n    - name: player-data\n      path: /v1/data/projects/{projectId}/players/{playerId}\n      description: Player data operations\n      operations:\n      - name: get-player-data\n        method: GET\n        description: Get all data items for a player\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-data-items\n      path: /v1/data/projects/{projectId}/players/{playerId}/items\n      description: Set player data items\n      operations:\n      - name: set-player-data\n        method: POST\n        description: Create or update player data items\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: player-query\n      path: /v1/data/projects/{projectId}/players/{playerId}/query\n      description:\
  \ Query player data with filters\n      operations:\n      - name: query-player-data\n        method: POST\n        description: Query player data using field-based filters\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            returnKeys: '{{tools.return_keys}}'\n            fields: '{{tools.fields}}'\n  - type: http\n    namespace: unity-leaderboards\n    baseUri: https://leaderboards.services.api.unity.com\n    description: Unity Leaderboards API for player score management and ranking\n    authentication:\n      type: bearer\n      token:\
  \ '{{UNITY_LEADERBOARDS_TOKEN}}'\n    resources:\n    - name: leaderboards\n      path: /v1/projects/{projectId}/environments/{environmentId}/leaderboards\n      description: Leaderboard configuration management\n      operations:\n      - name: list-leaderboards\n        method: GET\n        description: List all leaderboard definitions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of leaderboards to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-leaderboard\n        method: POST\n\
  \        description: Create a new leaderboard definition\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            id: '{{tools.leaderboard_id}}'\n            sortOrder: '{{tools.sort_order}}'\n    - name: scores\n      path: /v1/projects/{projectId}/environments/{environmentId}/leaderboards/{leaderboardId}/scores/players/{playerId}\n      description: Player score operations\n      operations:\n      - name: add-player-score\n        method: POST\n        description: Submit a player score to a leaderboard\n        inputParameters:\n  \
  \      - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: leaderboardId\n          in: path\n          type: string\n          required: true\n          description: Leaderboard identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            score: '{{tools.score}}'\n            metadata: '{{tools.metadata}}'\n      - name: get-player-score\n        method: GET\n        description: Retrieve a player's score and rank\n        inputParameters:\n        - name:\
  \ projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: leaderboardId\n          in: path\n          type: string\n          required: true\n          description: Leaderboard identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leaderboard-scores\n      path: /v1/projects/{projectId}/environments/{environmentId}/leaderboards/{leaderboardId}/scores\n      description: Top scores for a leaderboard\n      operations:\n      - name: get-leaderboard-scores\n        method: GET\n        description: Retrieve top scores\
  \ for a leaderboard\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: leaderboardId\n          in: path\n          type: string\n          required: true\n          description: Leaderboard identifier\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of scores to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: unity-live-ops-api\n    description: Unified\
  \ REST API for Unity live game operations including economy, player data, and rankings.\n    resources:\n    - path: /v1/players/{playerId}/currencies\n      name: player-currencies\n      description: Player virtual currency balance management\n      operations:\n      - method: GET\n        name: get-currency-balances\n        description: Get All Currency Balances for a Player\n        call: unity-economy.get-player-currency-balances\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/currencies/{currencyId}/add\n      name: add-currency\n      description: Add currency to player balance\n      operations:\n      - method: POST\n        name: add-currency\n        description: Add Currency to Player Balance\n        call: unity-economy.increment-currency-balance\n        with:\n          projectId:\
  \ rest.projectId\n          environmentId: rest.environmentId\n          playerId: rest.playerId\n          currencyId: rest.currencyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/inventory\n      name: player-inventory\n      description: Player item inventory\n      operations:\n      - method: GET\n        name: get-inventory\n        description: Get Player Item Inventory\n        call: unity-economy.get-player-inventory\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/purchases/virtual\n      name: virtual-purchases\n      description: Virtual item purchases\n      operations:\n      - method: POST\n        name: purchase-item\n        description: Purchase a Virtual Item\n        call: unity-economy.make-virtual-purchase\n  \
  \      with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/save-data\n      name: player-save-data\n      description: Player game save data\n      operations:\n      - method: GET\n        name: get-save-data\n        description: Get Player Game Save Data\n        call: unity-cloud-save.get-player-data\n        with:\n          projectId: rest.projectId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: save-data\n        description: Save Player Game Progress\n        call: unity-cloud-save.set-player-data\n        with:\n          projectId: rest.projectId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leaderboards\n      name: leaderboards\n\
  \      description: Game leaderboard management\n      operations:\n      - method: GET\n        name: list-leaderboards\n        description: List All Leaderboards\n        call: unity-leaderboards.list-leaderboards\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leaderboards/{leaderboardId}/scores\n      name: leaderboard-scores\n      description: Leaderboard score data\n      operations:\n      - method: GET\n        name: get-top-scores\n        description: Get Top Leaderboard Scores\n        call: unity-leaderboards.get-leaderboard-scores\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          leaderboardId: rest.leaderboardId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leaderboards/{leaderboardId}/scores/players/{playerId}\n      name: player-leaderboard-score\n\
  \      description: Player-specific leaderboard score\n      operations:\n      - method: POST\n        name: submit-score\n        description: Submit Player Score to Leaderboard\n        call: unity-leaderboards.add-player-score\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          leaderboardId: rest.leaderboardId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-player-rank\n        description: Get Player Score and Rank\n        call: unity-leaderboards.get-player-score\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          leaderboardId: rest.leaderboardId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: unity-live-ops-mcp\n    transport: http\n    description: MCP server\
  \ for AI-assisted Unity live game operations management.\n    tools:\n    - name: get-player-currencies\n      description: Get all virtual currency balances for a player\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-economy.get-player-currency-balances\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-player-currency\n      description: Add virtual currency to a player's balance\n      hints:\n        readOnly: false\n        idempotent: false\n      call: unity-economy.increment-currency-balance\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        playerId: tools.playerId\n        currencyId: tools.currencyId\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deduct-player-currency\n\
  \      description: Deduct virtual currency from a player's balance\n      hints:\n        readOnly: false\n        idempotent: false\n      call: unity-economy.decrement-currency-balance\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        playerId: tools.playerId\n        currencyId: tools.currencyId\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-inventory\n      description: Get all items in a player's inventory\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-economy.get-player-inventory\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: purchase-virtual-item\n      description: Purchase an in-game item using virtual currency\n      hints:\n        readOnly: false\n      \
  \  idempotent: false\n      call: unity-economy.make-virtual-purchase\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        playerId: tools.playerId\n        purchase_id: tools.purchase_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-progress\n      description: Retrieve a player's saved game progress and state\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-cloud-save.get-player-data\n      with:\n        projectId: tools.projectId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: save-player-progress\n      description: Save player game progress and state to the cloud\n      hints:\n        readOnly: false\n        idempotent: true\n      call: unity-cloud-save.set-player-data\n      with:\n        projectId: tools.projectId\n        playerId: tools.playerId\n        data: tools.data\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-leaderboards\n      description: List all game leaderboards\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unity-leaderboards.list-leaderboards\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-scores\n      description: Get the top scores from a leaderboard\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unity-leaderboards.get-leaderboard-scores\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        leaderboardId: tools.leaderboardId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-leaderboard-score\n      description: Submit a player's score to a leaderboard\n      hints:\n        readOnly: false\n        idempotent: true\n      call: unity-leaderboards.add-player-score\n\
  \      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        leaderboardId: tools.leaderboardId\n        playerId: tools.playerId\n        score: tools.score\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-rank\n      description: Get a player's current rank and score on a leaderboard\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-leaderboards.get-player-score\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        leaderboardId: tools.leaderboardId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
