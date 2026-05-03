---
categories: []
consumed_apis:
- twitch-helix
- twitch-igdb
description: Unified workflow for discovering Twitch content including live streams, channels, games, clips, and videos. Used by app developers and content aggregators to surface the most relevant Twitch content.
layout: capability
name: Twitch Content Discovery
operations:
- description: Get active live streams filtered by game, language, or user
  method: GET
  name: get-streams
  path: /v1/streams
- description: Search for Twitch channels
  method: GET
  name: search-channels
  path: /v1/channels
- description: Get clips from a broadcaster or game
  method: GET
  name: get-clips
  path: /v1/clips
- description: Get videos from a broadcaster or game
  method: GET
  name: get-videos
  path: /v1/videos
- description: Get the most popular games on Twitch
  method: GET
  name: get-top-games
  path: /v1/games
- description: Query detailed game information from IGDB
  method: POST
  name: query-games
  path: /v1/game-database
personas: []
provider_name: Twitch
provider_slug: twitch
search_terms:
- get streams
- video
- query detailed game information from igdb
- entertainment
- query game platforms
- live stream discovery
- get top games
- search for twitch channels
- query games
- get clips from a broadcaster or game
- content clips
- get clips
- get games
- search for twitch channels by name
- get videos from a broadcaster or game
- get the most popular games on twitch
- get the most popular game categories on twitch right now
- twitch
- content discovery
- get active live streams filtered by game, language, or user
- get game information by id or name
- get videos
- channel information and search
- find active live streams on twitch by game, language, or user
- game and category discovery
- search channels
- get vods and highlight videos from a broadcaster
- gaming
- query gaming platform information from igdb
- detailed game metadata from igdb
- get video clips from a broadcaster or game category
- vod and highlight videos
- streaming
- query game database
- query the igdb game database for detailed game metadata
- live video
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Twitch Content Discovery\"\n  description: >-\n    Unified workflow for discovering Twitch content including live streams,\n    channels, games, clips, and videos. Used by app developers and content\n    aggregators to surface the most relevant Twitch content.\n  tags:\n    - Twitch\n    - Content Discovery\n    - Streaming\n    - Gaming\n    - Video\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TWITCH_ACCESS_TOKEN: TWITCH_ACCESS_TOKEN\n      TWITCH_CLIENT_ID: TWITCH_CLIENT_ID\n\ncapability:\n  consumes:\n    - import: twitch-helix\n      location: ./shared/helix.yaml\n    - import: twitch-igdb\n      location: ./shared/igdb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: twitch-content-discovery-api\n      description: \"Unified REST API for Twitch content discovery.\"\n      resources:\n        - path: /v1/streams\n          name: streams\n    \
  \      description: \"Live stream discovery\"\n          operations:\n            - method: GET\n              name: get-streams\n              description: \"Get active live streams filtered by game, language, or user\"\n              call: \"twitch-helix.get-streams\"\n              with:\n                game_id: \"rest.game_id\"\n                language: \"rest.language\"\n                first: \"rest.first\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: channels\n          description: \"Channel information and search\"\n          operations:\n            - method: GET\n              name: search-channels\n              description: \"Search for Twitch channels\"\n              call: \"twitch-helix.search-channels\"\n              with:\n                query: \"rest.query\"\n                live_only: \"rest.live_only\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/clips\n          name: clips\n          description: \"Content clips\"\n          operations:\n            - method: GET\n              name: get-clips\n              description: \"Get clips from a broadcaster or game\"\n              call: \"twitch-helix.get-clips\"\n              with:\n                broadcaster_id: \"rest.broadcaster_id\"\n                game_id: \"rest.game_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/videos\n          name: videos\n          description: \"VOD and highlight videos\"\n          operations:\n            - method: GET\n              name: get-videos\n              description: \"Get videos from a broadcaster or game\"\n              call: \"twitch-helix.get-videos\"\n              with:\n                user_id: \"rest.user_id\"\n                game_id: \"rest.game_id\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n        - path: /v1/games\n          name: games\n          description: \"Game and category discovery\"\n          operations:\n            - method: GET\n              name: get-top-games\n              description: \"Get the most popular games on Twitch\"\n              call: \"twitch-helix.get-top-games\"\n              with:\n                first: \"rest.first\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/game-database\n          name: game-database\n          description: \"Detailed game metadata from IGDB\"\n          operations:\n            - method: POST\n              name: query-games\n              description: \"Query detailed game information from IGDB\"\n              call: \"twitch-igdb.query-games\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n\
  \      namespace: twitch-content-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Twitch content discovery.\"\n      tools:\n        - name: get-streams\n          description: \"Find active live streams on Twitch by game, language, or user\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-streams\"\n          with:\n            game_id: \"tools.game_id\"\n            language: \"tools.language\"\n            first: \"tools.first\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-channels\n          description: \"Search for Twitch channels by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.search-channels\"\n          with:\n            query: \"tools.query\"\n            live_only: \"tools.live_only\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-clips\n          description: \"Get video clips from a broadcaster or game category\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-clips\"\n          with:\n            broadcaster_id: \"tools.broadcaster_id\"\n            game_id: \"tools.game_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-videos\n          description: \"Get VODs and highlight videos from a broadcaster\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-videos\"\n          with:\n            user_id: \"tools.user_id\"\n            game_id: \"tools.game_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-top-games\n          description: \"Get the most popular game categories on Twitch right now\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-top-games\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-games\n          description: \"Get game information by ID or name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-helix.get-games\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-game-database\n          description: \"Query the IGDB game database for detailed game metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-igdb.query-games\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-game-platforms\n          description: \"Query gaming platform information from\
  \ IGDB\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"twitch-igdb.query-platforms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/twitch/refs/heads/main/capabilities/content-discovery.yaml
tags:
- Twitch
- Content Discovery
- Streaming
- Gaming
- Video
tools:
- description: Find active live streams on Twitch by game, language, or user
  hints:
    openWorld: true
    readOnly: true
  name: get-streams
- description: Search for Twitch channels by name
  hints:
    openWorld: true
    readOnly: true
  name: search-channels
- description: Get video clips from a broadcaster or game category
  hints:
    openWorld: true
    readOnly: true
  name: get-clips
- description: Get VODs and highlight videos from a broadcaster
  hints:
    openWorld: true
    readOnly: true
  name: get-videos
- description: Get the most popular game categories on Twitch right now
  hints:
    openWorld: true
    readOnly: true
  name: get-top-games
- description: Get game information by ID or name
  hints:
    openWorld: true
    readOnly: true
  name: get-games
- description: Query the IGDB game database for detailed game metadata
  hints:
    openWorld: true
    readOnly: true
  name: query-game-database
- description: Query gaming platform information from IGDB
  hints:
    openWorld: true
    readOnly: true
  name: query-game-platforms
---
