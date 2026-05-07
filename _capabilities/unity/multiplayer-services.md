---
categories: []
consumed_apis: []
description: Unified capability combining Unity Lobby, Matchmaker, and Multiplay Game Server Hosting APIs for complete multiplayer session management. Enables player discovery, skill-based matching, server allocation, and session lifecycle management.
layout: capability
name: Unity Multiplayer Services
operations:
- description: Create a New Game Lobby
  method: POST
  name: create-lobby
  path: /v1/lobbies
- description: Get Lobby Details
  method: GET
  name: get-lobby
  path: /v1/lobbies/{lobbyId}
- description: Search Available Lobbies
  method: POST
  name: search-lobbies
  path: /v1/lobbies/search
- description: Enter Matchmaking Queue
  method: POST
  name: create-ticket
  path: /v1/matchmaking/tickets
- description: Get Matchmaking Status
  method: GET
  name: get-ticket-status
  path: /v1/matchmaking/tickets/{ticketId}
- description: Cancel Matchmaking
  method: DELETE
  name: cancel-ticket
  path: /v1/matchmaking/tickets/{ticketId}
personas: []
provider_name: Unity
provider_slug: unity
search_terms:
- get the current state of a game lobby
- join an existing game lobby by id
- delete and close a game lobby
- lobby
- online gaming
- individual matchmaking ticket
- cancel matchmaking
- game development
- lobby discovery
- enter the matchmaking queue for a game session
- game lobby management
- game server hosting
- matchmaking
- check matchmaking status
- enter matchmaking queue
- close game lobby
- create game lobby
- unity
- game services
- get lobby
- search available lobbies
- join game lobby
- multiplayer
- list all configured matchmaking queues
- cancel ticket
- search for available public game lobbies
- individual lobby operations
- cloud gaming
- get ticket status
- create a new game lobby
- get lobby details
- create lobby
- search lobbies
- matchmaking queue management
- create ticket
- get matchmaking status
- create a new multiplayer game lobby
- cancel an active matchmaking ticket
- real-time 3d
- list matchmaking queues
- check if a match has been found for a matchmaking ticket
- start matchmaking
slug: multiplayer-services
source_filename: multiplayer-services.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unity Multiplayer Services\n  description: Unified capability combining Unity Lobby, Matchmaker, and Multiplay Game Server Hosting APIs for complete multiplayer\n    session management. Enables player discovery, skill-based matching, server allocation, and session lifecycle management.\n  tags:\n  - Unity\n  - Multiplayer\n  - Lobby\n  - Matchmaking\n  - Game Server Hosting\n  - Online Gaming\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNITY_LOBBY_TOKEN: UNITY_LOBBY_TOKEN\n    UNITY_MATCHMAKER_TOKEN: UNITY_MATCHMAKER_TOKEN\n    UNITY_MULTIPLAY_TOKEN: UNITY_MULTIPLAY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: unity-lobby\n    baseUri: https://lobby.services.api.unity.com\n    description: Unity Lobby API for multiplayer lobby management\n    authentication:\n      type: bearer\n      token: '{{UNITY_LOBBY_TOKEN}}'\n    resources:\n    - name: lobbies\n      path: /v1/lobbies\n\
  \      description: Lobby creation and listing\n      operations:\n      - name: create-lobby\n        method: POST\n        description: Create a new multiplayer lobby\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            maxPlayers: '{{tools.max_players}}'\n            isPrivate: '{{tools.is_private}}'\n    - name: lobby-by-id\n      path: /v1/lobbies/{lobbyId}\n      description: Lobby management by ID\n      operations:\n      - name: get-lobby\n        method: GET\n        description: Get lobby details\n        inputParameters:\n        - name: lobbyId\n          in: path\n          type: string\n          required: true\n          description: Lobby identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-lobby\n\
  \        method: PATCH\n        description: Update lobby configuration\n        inputParameters:\n        - name: lobbyId\n          in: path\n          type: string\n          required: true\n          description: Lobby identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            isLocked: '{{tools.is_locked}}'\n      - name: delete-lobby\n        method: DELETE\n        description: Delete a lobby\n        inputParameters:\n        - name: lobbyId\n          in: path\n          type: string\n          required: true\n          description: Lobby identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lobby-join\n      path: /v1/lobbies/{lobbyId}/join\n      description: Join a lobby by ID\n      operations:\n  \
  \    - name: join-lobby-by-id\n        method: POST\n        description: Join a lobby using its ID\n        inputParameters:\n        - name: lobbyId\n          in: path\n          type: string\n          required: true\n          description: Lobby identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            playerId: '{{tools.player_id}}'\n    - name: lobby-by-code\n      path: /v1/lobbies/code/{lobbyCode}\n      description: Join a lobby by code\n      operations:\n      - name: join-lobby-by-code\n        method: POST\n        description: Join a lobby using its join code\n        inputParameters:\n        - name: lobbyCode\n          in: path\n          type: string\n          required: true\n          description: Lobby join code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n        body:\n          type: json\n          data:\n            playerId: '{{tools.player_id}}'\n    - name: lobby-query\n      path: /v1/lobbies/query\n      description: Search for available lobbies\n      operations:\n      - name: query-lobbies\n        method: POST\n        description: Search for public lobbies with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            count: '{{tools.count}}'\n    - name: lobby-heartbeat\n      path: /v1/lobbies/{lobbyId}/heartbeat\n      description: Lobby heartbeat\n      operations:\n      - name: heartbeat-lobby\n        method: POST\n        description: Send heartbeat to keep lobby active\n        inputParameters:\n        - name: lobbyId\n          in: path\n          type: string\n          required: true\n          description: Lobby identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: unity-matchmaker\n    baseUri: https://matchmaker.services.api.unity.com\n    description: Unity Matchmaker API for player matching\n    authentication:\n      type: bearer\n      token: '{{UNITY_MATCHMAKER_TOKEN}}'\n    resources:\n    - name: tickets\n      path: /v3/projects/{projectId}/environments/{environmentId}/tickets\n      description: Matchmaking ticket management\n      operations:\n      - name: create-ticket\n        method: POST\n        description: Create a matchmaking ticket\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            players: '{{tools.players}}'\n            queueName: '{{tools.queue_name}}'\n    - name: ticket-by-id\n      path: /v3/projects/{projectId}/environments/{environmentId}/tickets/{ticketId}\n      description: Ticket status and deletion\n      operations:\n      - name: get-ticket\n        method: GET\n        description: Get matchmaking ticket status\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: ticketId\n          in: path\n          type: string\n          required: true\n          description: Ticket identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-ticket\n        method: DELETE\n        description: Cancel a matchmaking ticket\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        - name: ticketId\n          in: path\n          type: string\n          required: true\n          description: Ticket identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /v3/projects/{projectId}/environments/{environmentId}/queues\n      description: Matchmaking queue configuration\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all\
  \ matchmaking queues\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Unity project identifier\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: unity-multiplayer-api\n    description: Unified REST API for Unity multiplayer services including lobby creation, matchmaking, and server allocation.\n    resources:\n    - path: /v1/lobbies\n      name: lobbies\n      description: Game lobby management\n      operations:\n      - method: POST\n        name: create-lobby\n        description: Create a New Game Lobby\n        call: unity-lobby.create-lobby\n        with: {}\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/lobbies/{lobbyId}\n      name: lobby\n      description: Individual lobby operations\n      operations:\n      - method: GET\n        name: get-lobby\n        description: Get Lobby Details\n        call: unity-lobby.get-lobby\n        with:\n          lobbyId: rest.lobbyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lobbies/search\n      name: lobby-search\n      description: Lobby discovery\n      operations:\n      - method: POST\n        name: search-lobbies\n        description: Search Available Lobbies\n        call: unity-lobby.query-lobbies\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matchmaking/tickets\n      name: matchmaking-tickets\n      description: Matchmaking queue management\n      operations:\n      - method: POST\n        name: create-ticket\n        description: Enter Matchmaking Queue\n        call: unity-matchmaker.create-ticket\n\
  \        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matchmaking/tickets/{ticketId}\n      name: matchmaking-ticket\n      description: Individual matchmaking ticket\n      operations:\n      - method: GET\n        name: get-ticket-status\n        description: Get Matchmaking Status\n        call: unity-matchmaker.get-ticket\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          ticketId: rest.ticketId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-ticket\n        description: Cancel Matchmaking\n        call: unity-matchmaker.delete-ticket\n        with:\n          projectId: rest.projectId\n          environmentId: rest.environmentId\n          ticketId: rest.ticketId\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: unity-multiplayer-mcp\n    transport: http\n    description: MCP server for AI-assisted Unity multiplayer session management.\n    tools:\n    - name: create-game-lobby\n      description: Create a new multiplayer game lobby\n      hints:\n        readOnly: false\n        idempotent: false\n      call: unity-lobby.create-lobby\n      with:\n        name: tools.name\n        max_players: tools.max_players\n        is_private: tools.is_private\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lobby-details\n      description: Get the current state of a game lobby\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-lobby.get-lobby\n      with:\n        lobbyId: tools.lobbyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: join-game-lobby\n      description: Join an existing game lobby by ID\n      hints:\n        readOnly: false\n\
  \        idempotent: false\n      call: unity-lobby.join-lobby-by-id\n      with:\n        lobbyId: tools.lobbyId\n        player_id: tools.player_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-available-lobbies\n      description: Search for available public game lobbies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unity-lobby.query-lobbies\n      with:\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-game-lobby\n      description: Delete and close a game lobby\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: unity-lobby.delete-lobby\n      with:\n        lobbyId: tools.lobbyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-matchmaking\n      description: Enter the matchmaking queue for a game session\n      hints:\n        readOnly: false\n        idempotent:\
  \ false\n      call: unity-matchmaker.create-ticket\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        players: tools.players\n        queue_name: tools.queue_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-matchmaking-status\n      description: Check if a match has been found for a matchmaking ticket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unity-matchmaker.get-ticket\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-matchmaking\n      description: Cancel an active matchmaking ticket\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: unity-matchmaker.delete-ticket\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n\
  \        ticketId: tools.ticketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-matchmaking-queues\n      description: List all configured matchmaking queues\n      hints:\n        readOnly: true\n        openWorld: true\n      call: unity-matchmaker.list-queues\n      with:\n        projectId: tools.projectId\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unity/refs/heads/main/capabilities/multiplayer-services.yaml
tags:
- Unity
- Multiplayer
- Lobby
- Matchmaking
- Game Server Hosting
- Online Gaming
tools:
- description: Create a new multiplayer game lobby
  hints:
    idempotent: false
    readOnly: false
  name: create-game-lobby
- description: Get the current state of a game lobby
  hints:
    openWorld: false
    readOnly: true
  name: get-lobby-details
- description: Join an existing game lobby by ID
  hints:
    idempotent: false
    readOnly: false
  name: join-game-lobby
- description: Search for available public game lobbies
  hints:
    openWorld: true
    readOnly: true
  name: search-available-lobbies
- description: Delete and close a game lobby
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: close-game-lobby
- description: Enter the matchmaking queue for a game session
  hints:
    idempotent: false
    readOnly: false
  name: start-matchmaking
- description: Check if a match has been found for a matchmaking ticket
  hints:
    openWorld: false
    readOnly: true
  name: check-matchmaking-status
- description: Cancel an active matchmaking ticket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-matchmaking
- description: List all configured matchmaking queues
  hints:
    openWorld: true
    readOnly: true
  name: list-matchmaking-queues
---
