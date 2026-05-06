---
categories: []
consumed_apis: []
description: The FreeToGame API provides programmatic access to a comprehensive database of free-to-play online games and free MMO games. It exposes endpoints for listing games, retrieving game details, and filtering or sorting games by category, platform, and tag. The API is read-only, requires no authentication, returns JSON responses, and is rate limited to a maximum of 10 requests per second.
layout: capability
name: FreeToGame API
operations:
- description: List Games
  method: GET
  name: listgames
  path: /games
- description: Get Game
  method: GET
  name: getgame
  path: /game
- description: Filter Games
  method: GET
  name: filtergames
  path: /filter
personas: []
provider_name: FreeToGame
provider_slug: freetogame
search_terms:
- get game
- filter games
- freetogame
- api
- gaming
- listgames
- getgame
- list games
- filtergames
- games
slug: freetogame-capability
source_filename: freetogame-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FreeToGame API\n  description: The FreeToGame API provides programmatic access to a comprehensive database of free-to-play online games and\n    free MMO games. It exposes endpoints for listing games, retrieving game details, and filtering or sorting games by category,\n    platform, and tag. The API is read-only, requires no authentication, returns JSON responses, and is rate limited to a\n    maximum of 10 requests per second.\n  tags:\n  - Freetogame\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: freetogame\n    baseUri: https://www.freetogame.com/api\n    description: FreeToGame API HTTP API.\n    resources:\n    - name: games\n      path: /games\n      operations:\n      - name: listgames\n        method: GET\n        description: List Games\n        inputParameters:\n        - name: platform\n          in: query\n          type: string\n          description:\
  \ Filter games by platform.\n        - name: category\n          in: query\n          type: string\n          description: Filter games by genre or category (for example mmorpg, shooter, strategy, moba, racing, sports, social,\n            sandbox, open-world, survival, pvp, pve, pixel, voxel, z\n        - name: sort-by\n          in: query\n          type: string\n          description: Sort order for results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: game\n      path: /game\n      operations:\n      - name: getgame\n        method: GET\n        description: Get Game\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: The unique identifier of the game.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filter\n \
  \     path: /filter\n      operations:\n      - name: filtergames\n        method: GET\n        description: Filter Games\n        inputParameters:\n        - name: tag\n          in: query\n          type: string\n          required: true\n          description: One or more tags joined by periods.\n        - name: platform\n          in: query\n          type: string\n          description: Filter games by platform.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: freetogame-rest\n    description: REST adapter for FreeToGame API.\n    resources:\n    - path: /games\n      name: listgames\n      operations:\n      - method: GET\n        name: listgames\n        description: List Games\n        call: freetogame.listgames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /game\n      name: getgame\n      operations:\n\
  \      - method: GET\n        name: getgame\n        description: Get Game\n        call: freetogame.getgame\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filter\n      name: filtergames\n      operations:\n      - method: GET\n        name: filtergames\n        description: Filter Games\n        call: freetogame.filtergames\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: freetogame-mcp\n    transport: http\n    description: MCP adapter for FreeToGame API for AI agent use.\n    tools:\n    - name: listgames\n      description: List Games\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freetogame.listgames\n      with:\n        platform: tools.platform\n        category: tools.category\n        sort-by: tools.sort-by\n      inputParameters:\n      - name: platform\n        type: string\n        description: Filter games\
  \ by platform.\n      - name: category\n        type: string\n        description: Filter games by genre or category (for example mmorpg, shooter, strategy, moba, racing, sports, social,\n          sandbox, open-world, survival, pvp, pve, pixel, voxel, z\n      - name: sort-by\n        type: string\n        description: Sort order for results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgame\n      description: Get Game\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: freetogame.getgame\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: The unique identifier of the game.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filtergames\n      description: Filter Games\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ freetogame.filtergames\n      with:\n        tag: tools.tag\n        platform: tools.platform\n      inputParameters:\n      - name: tag\n        type: string\n        description: One or more tags joined by periods.\n        required: true\n      - name: platform\n        type: string\n        description: Filter games by platform.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/freetogame/refs/heads/main/capabilities/freetogame-capability.yaml
tags:
- Freetogame
- API
tools:
- description: List Games
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgames
- description: Get Game
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgame
- description: Filter Games
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: filtergames
---
