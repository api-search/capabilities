---
categories: []
consumed_apis:
- unity-auth
- unity-cloud-save
description: Unified capability combining Unity Player Authentication, Friends, and Cloud Save APIs for complete player identity and social management. Enables player authentication, account management, social connections, and game state persistence.
layout: capability
name: Unity Player Identity
operations:
- description: List All Players
  method: GET
  name: list-players
  path: /v1/players
- description: Get Player Details
  method: GET
  name: get-player
  path: /v1/players/{playerId}
- description: Delete Player Account
  method: DELETE
  name: delete-player
  path: /v1/players/{playerId}
- description: Get Player Game Data
  method: GET
  name: get-player-data
  path: /v1/players/{playerId}/data
- description: Save Player Game Data
  method: POST
  name: save-player-data
  path: /v1/players/{playerId}/data
personas: []
provider_name: Unity
provider_slug: unity
search_terms:
- individual player operations
- player game data
- friends
- delete player
- get player
- query player data with field-based filters
- save player game data
- list all player accounts in the project
- get player details
- get player game data
- get a player's saved game data from the cloud
- list all players
- player management
- get details for a specific player account
- game development
- authentication
- get player account
- game services
- cloud gaming
- permanently delete a player account
- unity
- query player data
- player account management
- identity
- save player data
- update player game data
- delete player account
- update a player's saved game data in the cloud
- social
- list players
- get player data
- multiplayer
- real-time 3d
slug: player-identity
source_filename: player-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unity Player Identity\"\n  description: \"Unified capability combining Unity Player Authentication, Friends, and Cloud Save APIs for complete player identity and social management. Enables player authentication, account management, social connections, and game state persistence.\"\n  tags:\n    - Unity\n    - Authentication\n    - Identity\n    - Friends\n    - Social\n    - Player Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNITY_AUTH_TOKEN: UNITY_AUTH_TOKEN\n      UNITY_CLOUD_SAVE_TOKEN: UNITY_CLOUD_SAVE_TOKEN\n\ncapability:\n  consumes:\n    - import: unity-auth\n      location: ./shared/authentication.yaml\n    - import: unity-cloud-save\n      location: ./shared/cloud-save.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: unity-player-identity-api\n      description: \"Unified REST API for Unity player identity, authentication, and\
  \ data management.\"\n      resources:\n        - path: /v1/players\n          name: players\n          description: \"Player account management\"\n          operations:\n            - method: GET\n              name: list-players\n              description: \"List All Players\"\n              call: \"unity-auth.list-players\"\n              with: {}\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}\n          name: player\n          description: \"Individual player operations\"\n          operations:\n            - method: GET\n              name: get-player\n              description: \"Get Player Details\"\n              call: \"unity-auth.get-player\"\n              with:\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-player\n             \
  \ description: \"Delete Player Account\"\n              call: \"unity-auth.delete-player\"\n              with:\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}/data\n          name: player-data\n          description: \"Player game data\"\n          operations:\n            - method: GET\n              name: get-player-data\n              description: \"Get Player Game Data\"\n              call: \"unity-cloud-save.get-player-data\"\n              with:\n                projectId: \"rest.projectId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: save-player-data\n              description: \"Save Player Game Data\"\n              call: \"unity-cloud-save.set-player-data\"\n              with:\n            \
  \    projectId: \"rest.projectId\"\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: unity-player-identity-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Unity player identity management.\"\n      tools:\n        - name: list-players\n          description: \"List all player accounts in the project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unity-auth.list-players\"\n          with: {}\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-account\n          description: \"Get details for a specific player account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-auth.get-player\"\n          with:\n            playerId: \"tools.playerId\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-player-account\n          description: \"Permanently delete a player account\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"unity-auth.delete-player\"\n          with:\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-game-data\n          description: \"Get a player's saved game data from the cloud\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-cloud-save.get-player-data\"\n          with:\n            projectId: \"tools.projectId\"\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-player-game-data\n          description: \"Update a player's\
  \ saved game data in the cloud\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"unity-cloud-save.set-player-data\"\n          with:\n            projectId: \"tools.projectId\"\n            playerId: \"tools.playerId\"\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-player-data\n          description: \"Query player data with field-based filters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-cloud-save.query-player-data\"\n          with:\n            projectId: \"tools.projectId\"\n            playerId: \"tools.playerId\"\n            return_keys: \"tools.return_keys\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unity/refs/heads/main/capabilities/player-identity.yaml
tags:
- Unity
- Authentication
- Identity
- Friends
- Social
- Player Management
tools:
- description: List all player accounts in the project
  hints:
    openWorld: true
    readOnly: true
  name: list-players
- description: Get details for a specific player account
  hints:
    openWorld: false
    readOnly: true
  name: get-player-account
- description: Permanently delete a player account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-player-account
- description: Get a player's saved game data from the cloud
  hints:
    openWorld: false
    readOnly: true
  name: get-player-game-data
- description: Update a player's saved game data in the cloud
  hints:
    idempotent: true
    readOnly: false
  name: update-player-game-data
- description: Query player data with field-based filters
  hints:
    openWorld: false
    readOnly: true
  name: query-player-data
---
