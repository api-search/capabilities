---
categories: []
consumed_apis: []
description: Unified workflow for video game discovery, metadata lookup, and platform research. Combines game search, platform browsing, artwork retrieval, and reference data (genres, developers, publishers) for game developers, collectors, and gaming applications.
layout: capability
name: TheGamesDB Video Game Discovery
operations:
- description: Search for games by name
  method: GET
  name: search-games
  path: /v1/games
- description: Get game details by ID
  method: GET
  name: get-game
  path: /v1/games/{id}
- description: Get artwork for a game
  method: GET
  name: get-game-images
  path: /v1/games/{id}/images
- description: List all gaming platforms
  method: GET
  name: list-platforms
  path: /v1/platforms
- description: List all game genres
  method: GET
  name: list-genres
  path: /v1/genres
personas: []
provider_name: TheGamesDB
provider_slug: thegamesdb
search_terms:
- list all platforms
- get artwork and images for a game (boxart, screenshots, fanart)
- search games by name
- metadata
- get game artwork
- game artwork and images
- get games by platform
- list all game genres in the database
- list platforms
- search platforms by name
- list all gaming platforms in the database with their ids
- gaming platforms
- game genres
- get game by id
- list all game publishers in the database
- find all games for a specific gaming platform
- artwork
- search games
- list all gaming platforms
- gaming
- search and browse video games
- search for video games by name (e.g. halo, mario, zelda)
- video games
- search for a gaming platform by name
- database
- get complete game details by game id
- list publishers
- list all game developers in the database
- game metadata and details
- get game details by id
- search for games by name
- get artwork for a game
- get game
- get game images
- list all game genres
- list developers
- list genres
slug: video-game-discovery
source_filename: video-game-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TheGamesDB Video Game Discovery\n  description: Unified workflow for video game discovery, metadata lookup, and platform research. Combines game search, platform\n    browsing, artwork retrieval, and reference data (genres, developers, publishers) for game developers, collectors, and\n    gaming applications.\n  tags:\n  - Gaming\n  - Video Games\n  - Database\n  - Metadata\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THEGAMESDB_API_KEY: THEGAMESDB_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: gamesdb\n    baseUri: https://api.thegamesdb.net\n    description: Open video game metadata database API\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{THEGAMESDB_API_KEY}}'\n      placement: query\n    resources:\n    - name: games-by-id\n      path: /v1/Games/ByGameID\n      description: Fetch games by ID\n      operations:\n      - name: get-games-by-id\n\
  \        method: GET\n        description: Fetch game details by ID with optional fields and includes\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Game ID or comma-delimited list\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Optional fields to include\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Optional includes (boxart, platform)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: games-by-name\n      path: /v1.1/Games/ByGameName\n      description: Search games by name\n      operations:\n      - name: search-games-by-name\n        method: GET\n        description: Search for games by name\n        inputParameters:\n        - name: name\n          in: query\n\
  \          type: string\n          required: true\n          description: Game name search term\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Optional fields\n        - name: filter[platform]\n          in: query\n          type: string\n          required: false\n          description: Filter by platform ID\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Optional includes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: games-by-platform\n      path: /v1/Games/ByPlatformID\n      description: Fetch games by platform ID\n      operations:\n      - name: get-games-by-platform\n        method: GET\n        description: Fetch games for one or more platforms\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n      \
  \    required: true\n          description: Platform ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: game-images\n      path: /v1/Games/Images\n      description: Retrieve game artwork and images\n      operations:\n      - name: get-game-images\n        method: GET\n        description: Get artwork and images for games\n        inputParameters:\n        - name: games_id\n          in: query\n          type: string\n          required: true\n          description: Game ID\n        - name: filter[type]\n          in: query\n          type: string\n          required: false\n          description: Image type filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: platforms\n      path: /v1/Platforms\n      description: List all gaming platforms\n      operations:\n      - name: list-platforms\n        method:\
  \ GET\n        description: Retrieve all gaming platforms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-platforms-by-id\n        method: GET\n        description: Retrieve platforms by ID\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Platform ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: genres\n      path: /v1/Genres\n      description: List all game genres\n      operations:\n      - name: list-genres\n        method: GET\n        description: Retrieve all game genres\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: developers\n      path: /v1/Developers\n      description: List all game developers\n      operations:\n\
  \      - name: list-developers\n        method: GET\n        description: Retrieve all game developers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: publishers\n      path: /v1/Publishers\n      description: List all game publishers\n      operations:\n      - name: list-publishers\n        method: GET\n        description: Retrieve all game publishers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: game-discovery-api\n    description: Unified REST API for video game discovery and metadata lookup.\n    resources:\n    - path: /v1/games\n      name: games\n      description: Search and browse video games\n      operations:\n      - method: GET\n        name: search-games\n        description: Search for games by name\n        call: gamesdb.search-games-by-name\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/games/{id}\n      name: game-detail\n      description: Game metadata and details\n      operations:\n      - method: GET\n        name: get-game\n        description: Get game details by ID\n        call: gamesdb.get-games-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/games/{id}/images\n      name: game-images\n      description: Game artwork and images\n      operations:\n      - method: GET\n        name: get-game-images\n        description: Get artwork for a game\n        call: gamesdb.get-game-images\n        with:\n          games_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/platforms\n      name: platforms\n      description: Gaming platforms\n      operations:\n      - method: GET\n        name: list-platforms\n\
  \        description: List all gaming platforms\n        call: gamesdb.list-platforms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/genres\n      name: genres\n      description: Game genres\n      operations:\n      - method: GET\n        name: list-genres\n        description: List all game genres\n        call: gamesdb.list-genres\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: game-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted video game discovery and research.\n    tools:\n    - name: search-games-by-name\n      description: Search for video games by name (e.g. Halo, Mario, Zelda)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.search-games-by-name\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-game-by-id\n      description:\
  \ Get complete game details by game ID\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.get-games-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-games-by-platform\n      description: Find all games for a specific gaming platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.get-games-by-platform\n      with:\n        id: tools.platform_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-game-artwork\n      description: Get artwork and images for a game (boxart, screenshots, fanart)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.get-game-images\n      with:\n        games_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-platforms\n      description: List all gaming platforms in the database with their IDs\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.list-platforms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-platforms-by-name\n      description: Search for a gaming platform by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.get-platforms-by-id\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-genres\n      description: List all game genres in the database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.list-genres\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-developers\n      description: List all game developers in the database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.list-developers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-publishers\n\
  \      description: List all game publishers in the database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gamesdb.list-publishers\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thegamesdb/refs/heads/main/capabilities/video-game-discovery.yaml
tags:
- Gaming
- Video Games
- Database
- Metadata
tools:
- description: Search for video games by name (e.g. Halo, Mario, Zelda)
  hints:
    openWorld: true
    readOnly: true
  name: search-games-by-name
- description: Get complete game details by game ID
  hints:
    openWorld: true
    readOnly: true
  name: get-game-by-id
- description: Find all games for a specific gaming platform
  hints:
    openWorld: true
    readOnly: true
  name: get-games-by-platform
- description: Get artwork and images for a game (boxart, screenshots, fanart)
  hints:
    openWorld: true
    readOnly: true
  name: get-game-artwork
- description: List all gaming platforms in the database with their IDs
  hints:
    openWorld: true
    readOnly: true
  name: list-all-platforms
- description: Search for a gaming platform by name
  hints:
    openWorld: true
    readOnly: true
  name: search-platforms-by-name
- description: List all game genres in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-genres
- description: List all game developers in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-developers
- description: List all game publishers in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-publishers
---
