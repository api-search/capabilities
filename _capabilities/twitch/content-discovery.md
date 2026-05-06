---
categories: []
consumed_apis: []
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
- get the most popular game categories on twitch right now
- query game database
- get the most popular games on twitch
- get clips
- get videos
- content discovery
- search for twitch channels by name
- get game information by id or name
- twitch
- channel information and search
- search channels
- content clips
- detailed game metadata from igdb
- gaming
- query the igdb game database for detailed game metadata
- get games
- query detailed game information from igdb
- get video clips from a broadcaster or game category
- query gaming platform information from igdb
- video
- get videos from a broadcaster or game
- find active live streams on twitch by game, language, or user
- get streams
- get vods and highlight videos from a broadcaster
- entertainment
- game and category discovery
- query game platforms
- query games
- get clips from a broadcaster or game
- get active live streams filtered by game, language, or user
- streaming
- live stream discovery
- get top games
- search for twitch channels
- live video
- vod and highlight videos
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Twitch Content Discovery\n  description: Unified workflow for discovering Twitch content including live streams, channels, games, clips, and videos.\n    Used by app developers and content aggregators to surface the most relevant Twitch content.\n  tags:\n  - Twitch\n  - Content Discovery\n  - Streaming\n  - Gaming\n  - Video\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TWITCH_ACCESS_TOKEN: TWITCH_ACCESS_TOKEN\n    TWITCH_CLIENT_ID: TWITCH_CLIENT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: twitch-helix\n    baseUri: https://api.twitch.tv/helix\n    description: Twitch Helix REST API\n    authentication:\n      type: bearer\n      token: '{{TWITCH_ACCESS_TOKEN}}'\n    resources:\n    - name: streams\n      path: /streams\n      description: Live stream information\n      operations:\n      - name: get-streams\n        method: GET\n        description: Get information about active\
  \ streams\n        inputParameters:\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter by game/category ID\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Filter by stream language\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: Filter by user ID\n        - name: user_login\n          in: query\n          type: string\n          required: false\n          description: Filter by user login name\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      description: Channel information and management\n\
  \      operations:\n      - name: get-channel-information\n        method: GET\n        description: Get information about one or more channels\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the broadcaster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User information and management\n      operations:\n      - name: get-users\n        method: GET\n        description: Get information about users\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: User ID\n        - name: login\n          in: query\n          type: string\n          required: false\n          description: User login name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: clips\n      path: /clips\n      description: Clip creation and retrieval\n      operations:\n      - name: get-clips\n        method: GET\n        description: Get clips for a broadcaster, game, or by clip ID\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: false\n          description: Filter clips by broadcaster\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter clips by game\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Clip ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-clip\n        method: POST\n        description: Create a clip from a live stream\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: ID of the broadcaster to clip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: videos\n      path: /videos\n      description: Video management\n      operations:\n      - name: get-videos\n        method: GET\n        description: Get video information by ID, user, or game\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Video ID\n        - name: user_id\n          in: query\n          type: string\n          required: false\n          description: Filter by user ID\n        - name: game_id\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by game ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-channels\n      path: /search/channels\n      description: Search for channels\n      operations:\n      - name: search-channels\n        method: GET\n        description: Search for channels by name\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: live_only\n          in: query\n          type: boolean\n          required: false\n          description: Filter to live-only channels\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: games\n      path: /games\n      description: Game/category information\n      operations:\n      - name: get-games\n        method: GET\n        description: Get game information by ID or name\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: false\n          description: Game ID\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Game name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-top-games\n        method: GET\n        description: Get the most popular games/categories on Twitch\n        inputParameters:\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chat\n      path: /chat\n      description: Chat settings and emotes\n      operations:\n      - name: get-chat-settings\n        method: GET\n        description: Get chat settings for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-chat-message\n        method: POST\n        description: Send a chat message on behalf of a user\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: ID of the channel to send to\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            broadcaster_id: '{{tools.broadcaster_id}}'\n            sender_id: '{{tools.sender_id}}'\n            message: '{{tools.message}}'\n    - name: subscriptions\n      path: /subscriptions\n      description: Subscription information\n      operations:\n      - name: get-broadcaster-subscriptions\n        method: GET\n        description: Get subscription information for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        - name: first\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: polls\n      path: /polls\n  \
  \    description: Channel polls\n      operations:\n      - name: get-polls\n        method: GET\n        description: Get active or past polls for a broadcaster\n        inputParameters:\n        - name: broadcaster_id\n          in: query\n          type: string\n          required: true\n          description: The broadcaster's ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-poll\n        method: POST\n        description: Create a poll for a broadcaster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            broadcaster_id: '{{tools.broadcaster_id}}'\n            title: '{{tools.title}}'\n            choices: '{{tools.choices}}'\n            duration: '{{tools.duration}}'\n    - name: analytics\n      path: /analytics/games\n      description:\
  \ Game analytics\n      operations:\n      - name: get-game-analytics\n        method: GET\n        description: Get analytics data for game developers\n        inputParameters:\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Filter by game ID\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Report type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: twitch-igdb\n    baseUri: https://api.igdb.com/v4\n    description: IGDB video game database API\n    authentication:\n      type: bearer\n      token: '{{TWITCH_ACCESS_TOKEN}}'\n    resources:\n    - name: games\n      path: /games\n      description: Video game data including metadata, ratings, and media\n      operations:\n      - name: query-games\n        method: POST\n        description:\
  \ Query games using Apicalypse query language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: text\n          data:\n            query: '{{tools.query}}'\n    - name: platforms\n      path: /platforms\n      description: Gaming platform data\n      operations:\n      - name: query-platforms\n        method: POST\n        description: Query gaming platforms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: text\n          data:\n            query: '{{tools.query}}'\n    - name: genres\n      path: /genres\n      description: Game genre data\n      operations:\n      - name: query-genres\n        method: POST\n        description: Query game genres\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: companies\n      path: /companies\n      description: Game company data\n      operations:\n      - name: query-companies\n        method: POST\n        description: Query game companies (developers and publishers)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Multi-resource search across IGDB\n      operations:\n      - name: multi-search\n        method: POST\n        description: Search across multiple IGDB resource types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: twitch-content-discovery-api\n    description: Unified REST API for Twitch content discovery.\n    resources:\n    - path: /v1/streams\n      name: streams\n      description: Live stream discovery\n      operations:\n      - method:\
  \ GET\n        name: get-streams\n        description: Get active live streams filtered by game, language, or user\n        call: twitch-helix.get-streams\n        with:\n          game_id: rest.game_id\n          language: rest.language\n          first: rest.first\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Channel information and search\n      operations:\n      - method: GET\n        name: search-channels\n        description: Search for Twitch channels\n        call: twitch-helix.search-channels\n        with:\n          query: rest.query\n          live_only: rest.live_only\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clips\n      name: clips\n      description: Content clips\n      operations:\n      - method: GET\n        name: get-clips\n        description: Get clips from a broadcaster or game\n        call: twitch-helix.get-clips\n \
  \       with:\n          broadcaster_id: rest.broadcaster_id\n          game_id: rest.game_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/videos\n      name: videos\n      description: VOD and highlight videos\n      operations:\n      - method: GET\n        name: get-videos\n        description: Get videos from a broadcaster or game\n        call: twitch-helix.get-videos\n        with:\n          user_id: rest.user_id\n          game_id: rest.game_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/games\n      name: games\n      description: Game and category discovery\n      operations:\n      - method: GET\n        name: get-top-games\n        description: Get the most popular games on Twitch\n        call: twitch-helix.get-top-games\n        with:\n          first: rest.first\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/game-database\n      name: game-database\n\
  \      description: Detailed game metadata from IGDB\n      operations:\n      - method: POST\n        name: query-games\n        description: Query detailed game information from IGDB\n        call: twitch-igdb.query-games\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: twitch-content-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Twitch content discovery.\n    tools:\n    - name: get-streams\n      description: Find active live streams on Twitch by game, language, or user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-streams\n      with:\n        game_id: tools.game_id\n        language: tools.language\n        first: tools.first\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-channels\n      description: Search for Twitch channels by name\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: twitch-helix.search-channels\n      with:\n        query: tools.query\n        live_only: tools.live_only\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-clips\n      description: Get video clips from a broadcaster or game category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-clips\n      with:\n        broadcaster_id: tools.broadcaster_id\n        game_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-videos\n      description: Get VODs and highlight videos from a broadcaster\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-videos\n      with:\n        user_id: tools.user_id\n        game_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-games\n      description: Get the most popular game categories on Twitch right now\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-top-games\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-games\n      description: Get game information by ID or name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-helix.get-games\n      with:\n        id: tools.id\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-game-database\n      description: Query the IGDB game database for detailed game metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-igdb.query-games\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-game-platforms\n      description: Query gaming platform information from IGDB\n      hints:\n        readOnly: true\n        openWorld: true\n      call: twitch-igdb.query-platforms\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
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
