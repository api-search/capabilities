---
categories: []
consumed_apis: []
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
- player game data
- update player game data
- permanently delete a player account
- list players
- game development
- get player details
- get player
- friends
- authentication
- query player data
- get player account
- get player game data
- player management
- save player data
- get a player's saved game data from the cloud
- individual player operations
- list all player accounts in the project
- get player data
- save player game data
- unity
- identity
- game services
- multiplayer
- cloud gaming
- delete player
- player account management
- list all players
- get details for a specific player account
- query player data with field-based filters
- social
- delete player account
- real-time 3d
- update a player's saved game data in the cloud
slug: player-identity
source_filename: player-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unity Player Identity\n  description: Unified capability combining Unity Player Authentication, Friends, and Cloud Save APIs for complete player\n    identity and social management. Enables player authentication, account management, social connections, and game state\n    persistence.\n  tags:\n  - Unity\n  - Authentication\n  - Identity\n  - Friends\n  - Social\n  - Player Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNITY_AUTH_TOKEN: UNITY_AUTH_TOKEN\n    UNITY_CLOUD_SAVE_TOKEN: UNITY_CLOUD_SAVE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: unity-auth\n    baseUri: https://player-auth.services.api.unity.com\n    description: Unity Player Authentication API\n    authentication:\n      type: bearer\n      token: '{{UNITY_AUTH_TOKEN}}'\n    resources:\n    - name: anonymous-auth\n      path: /v1/authentication/anonymous\n      description: Anonymous player authentication\n\
  \      operations:\n      - name: sign-in-anonymously\n        method: POST\n        description: Sign in a player anonymously\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sessionTokens: '{{tools.session_tokens}}'\n    - name: username-password-auth\n      path: /v1/authentication/usernamepassword/sign-in\n      description: Username and password sign-in\n      operations:\n      - name: sign-in-with-password\n        method: POST\n        description: Sign in with username and password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n    - name: external-token-auth\n      path: /v1/authentication/external-token\n      description:\
  \ External identity provider authentication\n      operations:\n      - name: sign-in-with-external-token\n        method: POST\n        description: Sign in with external identity provider token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            idProvider: '{{tools.id_provider}}'\n            token: '{{tools.token}}'\n    - name: token-refresh\n      path: /v1/token/refresh\n      description: Token refresh\n      operations:\n      - name: refresh-token\n        method: POST\n        description: Refresh an authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            refreshToken: '{{tools.refresh_token}}'\n    - name: players-admin\n      path: /v1/players\n      description: Player account\
  \ administration\n      operations:\n      - name: list-players\n        method: GET\n        description: List all players in the project\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of players to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-admin\n      path: /v1/players/{playerId}\n      description: Individual player management\n      operations:\n      - name: get-player\n        method: GET\n        description: Get player details\n        inputParameters:\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-player\n      \
  \  method: DELETE\n        description: Delete a player account\n        inputParameters:\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: unity-cloud-save\n    baseUri: https://cloud-save.services.api.unity.com\n    description: Unity Cloud Save API for player game state persistence\n    authentication:\n      type: bearer\n      token: '{{UNITY_CLOUD_SAVE_TOKEN}}'\n    resources:\n    - name: player-data\n      path: /v1/data/projects/{projectId}/players/{playerId}\n      description: Player data operations\n      operations:\n      - name: get-player-data\n        method: GET\n        description: Get all data items for a player\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n       \
  \   required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-data-items\n      path: /v1/data/projects/{projectId}/players/{playerId}/items\n      description: Set player data items\n      operations:\n      - name: set-player-data\n        method: POST\n        description: Create or update player data items\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n    - name: player-query\n      path: /v1/data/projects/{projectId}/players/{playerId}/query\n      description: Query player data with filters\n      operations:\n      - name: query-player-data\n        method: POST\n        description: Query player data using field-based filters\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unity player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            returnKeys: '{{tools.return_keys}}'\n            fields: '{{tools.fields}}'\n\
  \  exposes:\n  - type: rest\n    port: 8082\n    namespace: unity-player-identity-api\n    description: Unified REST API for Unity player identity, authentication, and data management.\n    resources:\n    - path: /v1/players\n      name: players\n      description: Player account management\n      operations:\n      - method: GET\n        name: list-players\n        description: List All Players\n        call: unity-auth.list-players\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}\n      name: player\n      description: Individual player operations\n      operations:\n      - method: GET\n        name: get-player\n        description: Get Player Details\n        call: unity-auth.get-player\n        with:\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-player\n        description: Delete Player Account\n\
  \        call: unity-auth.delete-player\n        with:\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/data\n      name: player-data\n      description: Player game data\n      operations:\n      - method: GET\n        name: get-player-data\n        description: Get Player Game Data\n        call: unity-cloud-save.get-player-data\n        with:\n          projectId: rest.projectId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: save-player-data\n        description: Save Player Game Data\n        call: unity-cloud-save.set-player-data\n        with:\n          projectId: rest.projectId\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: unity-player-identity-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted Unity player identity management.\n    tools:\n    - name: list-players\n      description: List all player accounts in the project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unity-auth.list-players\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-account\n      description: Get details for a specific player account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-auth.get-player\n      with:\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-player-account\n      description: Permanently delete a player account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: unity-auth.delete-player\n      with:\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-player-game-data\n      description: Get a player's saved game data from the cloud\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-cloud-save.get-player-data\n      with:\n        projectId: tools.projectId\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-player-game-data\n      description: Update a player's saved game data in the cloud\n      hints:\n        readOnly: false\n        idempotent: true\n      call: unity-cloud-save.set-player-data\n      with:\n        projectId: tools.projectId\n        playerId: tools.playerId\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-player-data\n      description: Query player data with field-based filters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-cloud-save.query-player-data\n      with:\n        projectId: tools.projectId\n \
  \       playerId: tools.playerId\n        return_keys: tools.return_keys\n        fields: tools.fields\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
