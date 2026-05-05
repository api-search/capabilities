---
api_specs:
- filename: thegamesdb-openapi.yml
  format: yaml
  label: gamesdb
  slug: gamesdb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/thegamesdb/refs/heads/main/openapi/thegamesdb-openapi.yml
categories: []
consumed_apis:
- gamesdb
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
- list developers
- list all platforms
- get games by platform
- get game artwork
- get game
- list all gaming platforms
- search for video games by name (e.g. halo, mario, zelda)
- search for a gaming platform by name
- get game details by id
- search platforms by name
- game metadata and details
- metadata
- get complete game details by game id
- list all game genres
- list all gaming platforms in the database with their ids
- get game by id
- list publishers
- search for games by name
- database
- list all game genres in the database
- search and browse video games
- get game images
- artwork
- search games
- gaming
- search games by name
- game artwork and images
- list genres
- list platforms
- find all games for a specific gaming platform
- list all game publishers in the database
- get artwork and images for a game (boxart, screenshots, fanart)
- gaming platforms
- video games
- game genres
- list all game developers in the database
- get artwork for a game
slug: video-game-discovery
source_filename: video-game-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheGamesDB Video Game Discovery\"\n  description: \"Unified workflow for video game discovery, metadata lookup, and platform research. Combines game search, platform browsing, artwork retrieval, and reference data (genres, developers, publishers) for game developers, collectors, and gaming applications.\"\n  tags:\n    - Gaming\n    - Video Games\n    - Database\n    - Metadata\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      THEGAMESDB_API_KEY: THEGAMESDB_API_KEY\n\ncapability:\n  consumes:\n    - import: gamesdb\n      location: ./shared/thegamesdb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: game-discovery-api\n      description: \"Unified REST API for video game discovery and metadata lookup.\"\n      resources:\n        - path: /v1/games\n          name: games\n          description: \"Search and browse video games\"\n          operations:\n\
  \            - method: GET\n              name: search-games\n              description: \"Search for games by name\"\n              call: \"gamesdb.search-games-by-name\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}\n          name: game-detail\n          description: \"Game metadata and details\"\n          operations:\n            - method: GET\n              name: get-game\n              description: \"Get game details by ID\"\n              call: \"gamesdb.get-games-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/images\n          name: game-images\n          description: \"Game artwork and images\"\n          operations:\n            - method: GET\n              name: get-game-images\n        \
  \      description: \"Get artwork for a game\"\n              call: \"gamesdb.get-game-images\"\n              with:\n                games_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/platforms\n          name: platforms\n          description: \"Gaming platforms\"\n          operations:\n            - method: GET\n              name: list-platforms\n              description: \"List all gaming platforms\"\n              call: \"gamesdb.list-platforms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/genres\n          name: genres\n          description: \"Game genres\"\n          operations:\n            - method: GET\n              name: list-genres\n              description: \"List all game genres\"\n              call: \"gamesdb.list-genres\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: game-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted video game discovery and research.\"\n      tools:\n        - name: search-games-by-name\n          description: \"Search for video games by name (e.g. Halo, Mario, Zelda)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.search-games-by-name\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-game-by-id\n          description: \"Get complete game details by game ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.get-games-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-games-by-platform\n\
  \          description: \"Find all games for a specific gaming platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.get-games-by-platform\"\n          with:\n            id: \"tools.platform_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-game-artwork\n          description: \"Get artwork and images for a game (boxart, screenshots, fanart)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.get-game-images\"\n          with:\n            games_id: \"tools.game_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-platforms\n          description: \"List all gaming platforms in the database with their IDs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.list-platforms\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: search-platforms-by-name\n          description: \"Search for a gaming platform by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.get-platforms-by-id\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-genres\n          description: \"List all game genres in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.list-genres\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-developers\n          description: \"List all game developers in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.list-developers\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-publishers\n          description: \"List all game publishers in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gamesdb.list-publishers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
