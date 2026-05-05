---
categories: []
consumed_apis:
- rawg
description: Unified game discovery and research capability powered by the RAWG Video Games Database. Enables developers, content creators, and gaming applications to search, filter, and retrieve comprehensive game metadata including detailed game information, platform availability, developer and publisher data, genre classification, community ratings, screenshots, trailers, achievements, store links, and social content. Supports AI-assisted game recommendation workflows through MCP tooling.
layout: capability
name: RAWG Game Discovery
operations:
- description: Search and filter games across the RAWG database
  method: GET
  name: list-games
  path: /v1/games
- description: Get full game details
  method: GET
  name: get-game
  path: /v1/games/{id}
- description: List DLCs and game editions
  method: GET
  name: list-game-additions
  path: /v1/games/{id}/additions
- description: List games in the series
  method: GET
  name: list-game-series
  path: /v1/games/{id}/series
- description: List game screenshots
  method: GET
  name: list-game-screenshots
  path: /v1/games/{id}/screenshots
- description: List store purchase links
  method: GET
  name: list-game-stores
  path: /v1/games/{id}/stores
- description: List game achievements
  method: GET
  name: list-game-achievements
  path: /v1/games/{id}/achievements
- description: List game trailers
  method: GET
  name: list-game-trailers
  path: /v1/games/{id}/trailers
- description: List recent Reddit posts for the game
  method: GET
  name: list-game-reddit-posts
  path: /v1/games/{id}/reddit
- description: List all game genres
  method: GET
  name: list-genres
  path: /v1/genres
- description: List all gaming platforms
  method: GET
  name: list-platforms
  path: /v1/platforms
- description: List game development studios
  method: GET
  name: list-developers
  path: /v1/developers
- description: List game publishers
  method: GET
  name: list-publishers
  path: /v1/publishers
- description: List game storefronts
  method: GET
  name: list-stores
  path: /v1/stores
- description: List all game tags
  method: GET
  name: list-tags
  path: /v1/tags
- description: List individual game creators
  method: GET
  name: list-creators
  path: /v1/creators
personas: []
provider_name: RAWG
provider_slug: rawg
search_terms:
- list recent reddit posts for the game
- list game development team
- list all gaming platforms (pc, playstation, xbox, nintendo switch, etc.)
- find where to buy a game across digital storefronts (steam, epic, playstation store, etc.)
- list game publishers
- list game community posts
- metadata
- list all game genres
- get screenshot images for a game
- complete game metadata
- game achievements
- list digital and physical game storefronts (steam, gog, epic games store, etc.)
- entertainment
- game screenshots
- game discovery
- list game achievements
- search and filter games across the rawg database
- list all video game genres (action, rpg, strategy, etc.)
- game trailers and videos
- list genres
- list creator roles
- game developers
- game publishers
- list game dlcs
- list dlcs, game editions, and companion apps for a game
- find other games that are part of the same franchise or series
- list the individual creators and developers who built a game
- get game
- list all achievements available in a game
- list game development studios and companies
- game storefronts
- dlcs and editions for a game
- list all job roles and positions in game development
- list creators
- list parent platform families (playstation, xbox, nintendo, etc.)
- list game publishing companies
- get full game details
- list store purchase links
- list game reddit posts
- video games
- list stores
- get similar games
- list individual game creators
- list all gaming platforms
- list game purchase links
- list parent platforms
- list game trailers
- search and filter the rawg game catalog by title, platform, genre, developer, publisher, tag, release date, or metacritic score
- video game genres
- list publishers
- get recent reddit community posts and discussions about a game
- get creator details
- get official trailers and video content for a game
- gaming platforms
- list all game tags
- list storefronts
- get the profile and credits of an individual game creator
- list developers
- get comprehensive metadata for a specific game including ratings, platforms, genres, website, and community data
- game subreddit posts
- list games
- get game details
- list games in the series
- find visually similar games for recommendation (enterprise tier)
- list game additions
- where to buy the game
- game tags
- list individual game creators, designers, and artists
- games
- database
- list game series
- list game screenshots
- list game stores
- list game development studios
- list dlcs and game editions
- list game storefronts
- video game search and filtering
- search games
- gaming
- game creators
- list platforms
- list all community game tags (singleplayer, open-world, co-op, etc.)
- games in the same series
- list tags
- rawg
slug: game-discovery
source_filename: game-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RAWG Game Discovery\"\n  description: >-\n    Unified game discovery and research capability powered by the RAWG Video\n    Games Database. Enables developers, content creators, and gaming\n    applications to search, filter, and retrieve comprehensive game metadata\n    including detailed game information, platform availability, developer and\n    publisher data, genre classification, community ratings, screenshots,\n    trailers, achievements, store links, and social content. Supports\n    AI-assisted game recommendation workflows through MCP tooling.\n  tags:\n    - RAWG\n    - Video Games\n    - Gaming\n    - Game Discovery\n    - Entertainment\n    - Database\n    - Metadata\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAWG_API_KEY: RAWG_API_KEY\n\ncapability:\n  consumes:\n    - import: rawg\n      location: ./shared/rawg-video-games-database.yaml\n\n  exposes:\n \
  \   - type: rest\n      port: 8080\n      namespace: rawg-discovery-api\n      description: \"Unified REST API for game discovery and metadata retrieval.\"\n      resources:\n        - path: /v1/games\n          name: games\n          description: \"Video game search and filtering\"\n          operations:\n            - method: GET\n              name: list-games\n              description: \"Search and filter games across the RAWG database\"\n              call: \"rawg.list-games\"\n              with:\n                search: \"rest.search\"\n                platforms: \"rest.platforms\"\n                genres: \"rest.genres\"\n                developers: \"rest.developers\"\n                publishers: \"rest.publishers\"\n                tags: \"rest.tags\"\n                dates: \"rest.dates\"\n                metacritic: \"rest.metacritic\"\n                ordering: \"rest.ordering\"\n                page: \"rest.page\"\n                page_size: \"rest.page_size\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}\n          name: game-detail\n          description: \"Complete game metadata\"\n          operations:\n            - method: GET\n              name: get-game\n              description: \"Get full game details\"\n              call: \"rawg.get-game\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/additions\n          name: game-additions\n          description: \"DLCs and editions for a game\"\n          operations:\n            - method: GET\n              name: list-game-additions\n              description: \"List DLCs and game editions\"\n              call: \"rawg.list-game-additions\"\n              with:\n                game_pk: \"rest.id\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/games/{id}/series\n          name: game-series\n          description: \"Games in the same series\"\n          operations:\n            - method: GET\n              name: list-game-series\n              description: \"List games in the series\"\n              call: \"rawg.list-game-series\"\n              with:\n                game_pk: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/screenshots\n          name: game-screenshots\n          description: \"Game screenshots\"\n          operations:\n            - method: GET\n              name: list-game-screenshots\n              description: \"List game screenshots\"\n              call: \"rawg.list-game-screenshots\"\n              with:\n                game_pk: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/stores\n\
  \          name: game-stores\n          description: \"Where to buy the game\"\n          operations:\n            - method: GET\n              name: list-game-stores\n              description: \"List store purchase links\"\n              call: \"rawg.list-game-stores\"\n              with:\n                game_pk: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/achievements\n          name: game-achievements\n          description: \"Game achievements\"\n          operations:\n            - method: GET\n              name: list-game-achievements\n              description: \"List game achievements\"\n              call: \"rawg.list-game-achievements\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/trailers\n          name: game-trailers\n          description:\
  \ \"Game trailers and videos\"\n          operations:\n            - method: GET\n              name: list-game-trailers\n              description: \"List game trailers\"\n              call: \"rawg.list-game-trailers\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/games/{id}/reddit\n          name: game-reddit\n          description: \"Game subreddit posts\"\n          operations:\n            - method: GET\n              name: list-game-reddit-posts\n              description: \"List recent Reddit posts for the game\"\n              call: \"rawg.list-game-reddit-posts\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/genres\n          name: genres\n          description: \"Video game genres\"\n          operations:\n            - method:\
  \ GET\n              name: list-genres\n              description: \"List all game genres\"\n              call: \"rawg.list-genres\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/platforms\n          name: platforms\n          description: \"Gaming platforms\"\n          operations:\n            - method: GET\n              name: list-platforms\n              description: \"List all gaming platforms\"\n              call: \"rawg.list-platforms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/developers\n          name: developers\n          description: \"Game developers\"\n          operations:\n            - method: GET\n              name: list-developers\n              description: \"List game development studios\"\n              call: \"rawg.list-developers\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n        - path: /v1/publishers\n          name: publishers\n          description: \"Game publishers\"\n          operations:\n            - method: GET\n              name: list-publishers\n              description: \"List game publishers\"\n              call: \"rawg.list-publishers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores\n          name: stores\n          description: \"Game storefronts\"\n          operations:\n            - method: GET\n              name: list-stores\n              description: \"List game storefronts\"\n              call: \"rawg.list-stores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tags\n          name: tags\n          description: \"Game tags\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List all game\
  \ tags\"\n              call: \"rawg.list-tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/creators\n          name: creators\n          description: \"Game creators\"\n          operations:\n            - method: GET\n              name: list-creators\n              description: \"List individual game creators\"\n              call: \"rawg.list-creators\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: rawg-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted game discovery and research using the RAWG database.\"\n      tools:\n        - name: search-games\n          description: \"Search and filter the RAWG game catalog by title, platform, genre, developer, publisher, tag, release date, or Metacritic score\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n            idempotent: true\n          call: \"rawg.list-games\"\n          with:\n            search: \"tools.search\"\n            platforms: \"tools.platforms\"\n            genres: \"tools.genres\"\n            developers: \"tools.developers\"\n            publishers: \"tools.publishers\"\n            tags: \"tools.tags\"\n            dates: \"tools.dates\"\n            metacritic: \"tools.metacritic\"\n            ordering: \"tools.ordering\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-game-details\n          description: \"Get comprehensive metadata for a specific game including ratings, platforms, genres, website, and community data\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.get-game\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-dlcs\n\
  \          description: \"List DLCs, game editions, and companion apps for a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-additions\"\n          with:\n            game_pk: \"tools.game_pk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-series\n          description: \"Find other games that are part of the same franchise or series\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-series\"\n          with:\n            game_pk: \"tools.game_pk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-development-team\n          description: \"List the individual creators and developers who built a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-development-team\"\
  \n          with:\n            game_pk: \"tools.game_pk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-screenshots\n          description: \"Get screenshot images for a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-screenshots\"\n          with:\n            game_pk: \"tools.game_pk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-purchase-links\n          description: \"Find where to buy a game across digital storefronts (Steam, Epic, PlayStation Store, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-stores\"\n          with:\n            game_pk: \"tools.game_pk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-achievements\n          description:\
  \ \"List all achievements available in a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-achievements\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-trailers\n          description: \"Get official trailers and video content for a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-trailers\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-game-community-posts\n          description: \"Get recent Reddit community posts and discussions about a game\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-game-reddit-posts\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-similar-games\n          description: \"Find visually similar games for recommendation (enterprise tier)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-suggested-games\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-genres\n          description: \"List all video game genres (Action, RPG, Strategy, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-genres\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-platforms\n          description: \"List all gaming platforms (PC, PlayStation, Xbox, Nintendo Switch, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-platforms\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-parent-platforms\n          description: \"List parent platform families (PlayStation, Xbox, Nintendo, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-parent-platforms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-developers\n          description: \"List game development studios and companies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-developers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-publishers\n          description: \"List game publishing companies\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-publishers\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: list-storefronts\n          description: \"List digital and physical game storefronts (Steam, GOG, Epic Games Store, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-stores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tags\n          description: \"List all community game tags (singleplayer, open-world, co-op, etc.)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-creators\n          description: \"List individual game creators, designers, and artists\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-creators\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: get-creator-details\n          description: \"Get the profile and credits of an individual game creator\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.get-creator\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-creator-roles\n          description: \"List all job roles and positions in game development\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rawg.list-creator-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rawg/refs/heads/main/capabilities/game-discovery.yaml
tags:
- RAWG
- Video Games
- Gaming
- Game Discovery
- Entertainment
- Database
- Metadata
tools:
- description: Search and filter the RAWG game catalog by title, platform, genre, developer, publisher, tag, release date, or Metacritic score
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-games
- description: Get comprehensive metadata for a specific game including ratings, platforms, genres, website, and community data
  hints:
    idempotent: true
    readOnly: true
  name: get-game-details
- description: List DLCs, game editions, and companion apps for a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-dlcs
- description: Find other games that are part of the same franchise or series
  hints:
    idempotent: true
    readOnly: true
  name: list-game-series
- description: List the individual creators and developers who built a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-development-team
- description: Get screenshot images for a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-screenshots
- description: Find where to buy a game across digital storefronts (Steam, Epic, PlayStation Store, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-game-purchase-links
- description: List all achievements available in a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-achievements
- description: Get official trailers and video content for a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-trailers
- description: Get recent Reddit community posts and discussions about a game
  hints:
    idempotent: true
    readOnly: true
  name: list-game-community-posts
- description: Find visually similar games for recommendation (enterprise tier)
  hints:
    idempotent: true
    readOnly: true
  name: get-similar-games
- description: List all video game genres (Action, RPG, Strategy, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-genres
- description: List all gaming platforms (PC, PlayStation, Xbox, Nintendo Switch, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-platforms
- description: List parent platform families (PlayStation, Xbox, Nintendo, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-parent-platforms
- description: List game development studios and companies
  hints:
    idempotent: true
    readOnly: true
  name: list-developers
- description: List game publishing companies
  hints:
    idempotent: true
    readOnly: true
  name: list-publishers
- description: List digital and physical game storefronts (Steam, GOG, Epic Games Store, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-storefronts
- description: List all community game tags (singleplayer, open-world, co-op, etc.)
  hints:
    idempotent: true
    readOnly: true
  name: list-tags
- description: List individual game creators, designers, and artists
  hints:
    idempotent: true
    readOnly: true
  name: list-creators
- description: Get the profile and credits of an individual game creator
  hints:
    idempotent: true
    readOnly: true
  name: get-creator-details
- description: List all job roles and positions in game development
  hints:
    idempotent: true
    readOnly: true
  name: list-creator-roles
---
