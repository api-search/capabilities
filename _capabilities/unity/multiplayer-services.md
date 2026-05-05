---
categories: []
consumed_apis:
- unity-lobby
- unity-matchmaker
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
- get lobby
- individual matchmaking ticket
- join an existing game lobby by id
- list matchmaking queues
- create a new game lobby
- get matchmaking status
- create lobby
- cancel ticket
- get ticket status
- multiplayer
- real-time 3d
- cloud gaming
- create ticket
- individual lobby operations
- join game lobby
- unity
- game services
- enter matchmaking queue
- online gaming
- search lobbies
- create a new multiplayer game lobby
- check matchmaking status
- check if a match has been found for a matchmaking ticket
- create game lobby
- enter the matchmaking queue for a game session
- matchmaking
- delete and close a game lobby
- game lobby management
- cancel matchmaking
- search available lobbies
- get the current state of a game lobby
- close game lobby
- lobby discovery
- cancel an active matchmaking ticket
- get lobby details
- search for available public game lobbies
- game development
- lobby
- matchmaking queue management
- game server hosting
- start matchmaking
- list all configured matchmaking queues
slug: multiplayer-services
source_filename: multiplayer-services.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unity Multiplayer Services\"\n  description: \"Unified capability combining Unity Lobby, Matchmaker, and Multiplay Game Server Hosting APIs for complete multiplayer session management. Enables player discovery, skill-based matching, server allocation, and session lifecycle management.\"\n  tags:\n    - Unity\n    - Multiplayer\n    - Lobby\n    - Matchmaking\n    - Game Server Hosting\n    - Online Gaming\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNITY_LOBBY_TOKEN: UNITY_LOBBY_TOKEN\n      UNITY_MATCHMAKER_TOKEN: UNITY_MATCHMAKER_TOKEN\n      UNITY_MULTIPLAY_TOKEN: UNITY_MULTIPLAY_TOKEN\n\ncapability:\n  consumes:\n    - import: unity-lobby\n      location: ./shared/lobby.yaml\n    - import: unity-matchmaker\n      location: ./shared/matchmaker.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: unity-multiplayer-api\n      description: \"Unified\
  \ REST API for Unity multiplayer services including lobby creation, matchmaking, and server allocation.\"\n      resources:\n        - path: /v1/lobbies\n          name: lobbies\n          description: \"Game lobby management\"\n          operations:\n            - method: POST\n              name: create-lobby\n              description: \"Create a New Game Lobby\"\n              call: \"unity-lobby.create-lobby\"\n              with: {}\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/lobbies/{lobbyId}\n          name: lobby\n          description: \"Individual lobby operations\"\n          operations:\n            - method: GET\n              name: get-lobby\n              description: \"Get Lobby Details\"\n              call: \"unity-lobby.get-lobby\"\n              with:\n                lobbyId: \"rest.lobbyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/lobbies/search\n          name: lobby-search\n          description: \"Lobby discovery\"\n          operations:\n            - method: POST\n              name: search-lobbies\n              description: \"Search Available Lobbies\"\n              call: \"unity-lobby.query-lobbies\"\n              with: {}\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/matchmaking/tickets\n          name: matchmaking-tickets\n          description: \"Matchmaking queue management\"\n          operations:\n            - method: POST\n              name: create-ticket\n              description: \"Enter Matchmaking Queue\"\n              call: \"unity-matchmaker.create-ticket\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/matchmaking/tickets/{ticketId}\n          name: matchmaking-ticket\n          description: \"Individual matchmaking ticket\"\n          operations:\n            - method: GET\n              name: get-ticket-status\n              description: \"Get Matchmaking Status\"\n              call: \"unity-matchmaker.get-ticket\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                ticketId: \"rest.ticketId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-ticket\n              description: \"Cancel Matchmaking\"\n              call: \"unity-matchmaker.delete-ticket\"\n              with:\n                projectId: \"rest.projectId\"\n                environmentId: \"rest.environmentId\"\n                ticketId: \"rest.ticketId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: unity-multiplayer-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Unity multiplayer session management.\"\n      tools:\n        # Lobby tools\n        - name: create-game-lobby\n          description: \"Create a new multiplayer game lobby\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-lobby.create-lobby\"\n          with:\n            name: \"tools.name\"\n            max_players: \"tools.max_players\"\n            is_private: \"tools.is_private\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lobby-details\n          description: \"Get the current state of a game lobby\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unity-lobby.get-lobby\"\n          with:\n            lobbyId: \"tools.lobbyId\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: join-game-lobby\n          description: \"Join an existing game lobby by ID\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-lobby.join-lobby-by-id\"\n          with:\n            lobbyId: \"tools.lobbyId\"\n            player_id: \"tools.player_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-available-lobbies\n          description: \"Search for available public game lobbies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unity-lobby.query-lobbies\"\n          with:\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-game-lobby\n          description: \"Delete and close a game lobby\"\n          hints:\n            readOnly:\
  \ false\n            destructive: true\n            idempotent: true\n          call: \"unity-lobby.delete-lobby\"\n          with:\n            lobbyId: \"tools.lobbyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Matchmaker tools\n        - name: start-matchmaking\n          description: \"Enter the matchmaking queue for a game session\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"unity-matchmaker.create-ticket\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            players: \"tools.players\"\n            queue_name: \"tools.queue_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-matchmaking-status\n          description: \"Check if a match has been found for a matchmaking ticket\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: false\n          call: \"unity-matchmaker.get-ticket\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            ticketId: \"tools.ticketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-matchmaking\n          description: \"Cancel an active matchmaking ticket\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"unity-matchmaker.delete-ticket\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n            ticketId: \"tools.ticketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-matchmaking-queues\n          description: \"List all configured matchmaking queues\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"unity-matchmaker.list-queues\"\n          with:\n            projectId: \"tools.projectId\"\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
