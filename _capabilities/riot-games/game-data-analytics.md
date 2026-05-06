---
categories: []
consumed_apis: []
description: Unified capability for Riot Games game data analytics across League of Legends. Enables player profile lookup, match history analysis, ranked standing tracking, champion mastery insights, and live game monitoring for developers building community tools and analytics platforms.
layout: capability
name: Riot Games Game Data Analytics
operations:
- description: Get League of Legends summoner profile
  method: GET
  name: get-summoner-by-puuid
  path: /v1/summoners/{encryptedPUUID}
- description: Get champion mastery data for a player
  method: GET
  name: get-champion-mastery
  path: /v1/champion-mastery/{encryptedPUUID}
- description: Get ranked standings for a summoner
  method: GET
  name: get-league-entries
  path: /v1/ranked/{encryptedSummonerId}
- description: Get recent match IDs for a player
  method: GET
  name: get-match-ids
  path: /v1/matches/{puuid}/ids
- description: Get full match details and participant stats
  method: GET
  name: get-match
  path: /v1/matches/{matchId}
- description: Get current live game for a summoner
  method: GET
  name: get-live-game
  path: /v1/live-games/{encryptedSummonerId}
- description: Get currently featured live games
  method: GET
  name: get-featured-games
  path: /v1/featured-games
- description: Get free champion rotation
  method: GET
  name: get-champion-rotations
  path: /v1/champions/rotation
personas: []
provider_name: Riot Games
provider_slug: riot-games
search_terms:
- get match details
- get match
- get league of legends summoner profile
- teamfight tactics
- analytics
- look up a league of legends summoner profile by puuid
- get summoner by puuid
- summoner profile by puuid
- get champion mastery
- ranked league standings
- league of legends
- get full match details including all participant stats, items, and outcomes
- match details
- get current live game for a summoner
- get full match details and participant stats
- get live game
- get league entries
- get ranked league standings and lp for a summoner across all queues
- get currently featured live games
- riot games
- get ranked standings for a summoner
- gaming
- get match history ids
- get match ids
- get recent match ids for a player to fetch individual match details
- valorant
- featured live games
- champion mastery rankings
- get ranked standings
- get champion mastery rankings to understand a player's most played champions
- get the current free champion rotation for new player recommendations
- get currently featured live games on the platform
- get summoner
- get featured games
- check if a summoner is currently in a live game and get game details
- get free champion rotation
- recent match ids
- get champion rotations
- ranked
- get champion mastery data for a player
- esports
- free champion rotation
- legends of runeterra
- match history
- get recent match ids for a player
- live game data
slug: game-data-analytics
source_filename: game-data-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Riot Games Game Data Analytics\n  description: Unified capability for Riot Games game data analytics across League of Legends. Enables player profile lookup,\n    match history analysis, ranked standing tracking, champion mastery insights, and live game monitoring for developers building\n    community tools and analytics platforms.\n  tags:\n  - Analytics\n  - Gaming\n  - League of Legends\n  - Match History\n  - Ranked\n  - Riot Games\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RIOT_API_KEY: RIOT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: lol-api\n    baseUri: https://na1.api.riotgames.com\n    description: League of Legends game data API.\n    authentication:\n      type: apikey\n      key: X-Riot-Token\n      value: '{{RIOT_API_KEY}}'\n      placement: header\n    resources:\n    - name: summoner\n      path: /lol/summoner/v4/summoners\n      description: Summoner\
  \ profile operations\n      operations:\n      - name: get-summoner-by-puuid\n        method: GET\n        description: Get summoner profile by PUUID\n        inputParameters:\n        - name: encryptedPUUID\n          in: path\n          type: string\n          required: true\n          description: Encrypted PUUID\n        outputRawFormat: json\n        outputParameters:\n        - name: summoner\n          type: object\n          value: $.\n      - name: get-summoner-by-id\n        method: GET\n        description: Get summoner profile by encrypted summoner ID\n        inputParameters:\n        - name: encryptedSummonerId\n          in: path\n          type: string\n          required: true\n          description: Encrypted summoner ID\n        outputRawFormat: json\n        outputParameters:\n        - name: summoner\n          type: object\n          value: $.\n    - name: champion-mastery\n      path: /lol/champion-mastery/v4/champion-masteries\n      description: Champion mastery\
  \ data\n      operations:\n      - name: get-champion-mastery\n        method: GET\n        description: Get all champion mastery entries for a player\n        inputParameters:\n        - name: encryptedPUUID\n          in: path\n          type: string\n          required: true\n          description: Encrypted PUUID\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of entries to return\n        outputRawFormat: json\n        outputParameters:\n        - name: masteries\n          type: array\n          value: $.\n    - name: league\n      path: /lol/league/v4/entries\n      description: Ranked league data\n      operations:\n      - name: get-league-entries-by-summoner\n        method: GET\n        description: Get ranked league entries for a summoner\n        inputParameters:\n        - name: encryptedSummonerId\n          in: path\n          type: string\n          required: true\n          description: Encrypted\
  \ summoner ID\n        outputRawFormat: json\n        outputParameters:\n        - name: entries\n          type: array\n          value: $.\n      - name: get-league-entries\n        method: GET\n        description: Get all entries for a queue, tier, and division\n        inputParameters:\n        - name: queue\n          in: path\n          type: string\n          required: true\n          description: Queue type (e.g., RANKED_SOLO_5x5)\n        - name: tier\n          in: path\n          type: string\n          required: true\n          description: Tier (e.g., GOLD)\n        - name: division\n          in: path\n          type: string\n          required: true\n          description: Division (e.g., I)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: entries\n          type: array\n          value: $.\n    - name: match\n    \
  \  path: /lol/match/v5/matches\n      description: Match history and detail\n      operations:\n      - name: get-match-ids-by-puuid\n        method: GET\n        description: Get list of match IDs for a player\n        inputParameters:\n        - name: puuid\n          in: path\n          type: string\n          required: true\n          description: Player PUUID\n        - name: queue\n          in: query\n          type: integer\n          required: false\n          description: Filter by queue ID\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of match IDs to return\n        outputRawFormat: json\n        outputParameters:\n        - name: matchIds\n          type: array\n          value: $.\n      - name: get-match\n        method: GET\n        description: Get match details by match ID\n        inputParameters:\n        - name: matchId\n          in: path\n          type: string\n          required: true\n\
  \          description: Match ID\n        outputRawFormat: json\n        outputParameters:\n        - name: match\n          type: object\n          value: $.\n    - name: spectator\n      path: /lol/spectator/v5\n      description: Live game data\n      operations:\n      - name: get-live-game\n        method: GET\n        description: Get current live game for a summoner\n        inputParameters:\n        - name: encryptedSummonerId\n          in: path\n          type: string\n          required: true\n          description: Encrypted summoner ID\n        outputRawFormat: json\n        outputParameters:\n        - name: game\n          type: object\n          value: $.\n      - name: get-featured-games\n        method: GET\n        description: Get list of featured live games\n        outputRawFormat: json\n        outputParameters:\n        - name: games\n          type: object\n          value: $.\n    - name: champion\n      path: /lol/champion/v3\n      description: Champion rotation\
  \ data\n      operations:\n      - name: get-champion-rotations\n        method: GET\n        description: Get current free champion rotation\n        outputRawFormat: json\n        outputParameters:\n        - name: rotation\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: riot-analytics-api\n    description: Unified REST API for Riot Games player and match analytics.\n    resources:\n    - path: /v1/summoners/{encryptedPUUID}\n      name: summoner\n      description: Summoner profile by PUUID\n      operations:\n      - method: GET\n        name: get-summoner-by-puuid\n        description: Get League of Legends summoner profile\n        call: lol-api.get-summoner-by-puuid\n        with:\n          encryptedPUUID: rest.encryptedPUUID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/champion-mastery/{encryptedPUUID}\n      name: champion-mastery\n      description: Champion mastery rankings\n\
  \      operations:\n      - method: GET\n        name: get-champion-mastery\n        description: Get champion mastery data for a player\n        call: lol-api.get-champion-mastery\n        with:\n          encryptedPUUID: rest.encryptedPUUID\n          count: rest.count\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/ranked/{encryptedSummonerId}\n      name: ranked\n      description: Ranked league standings\n      operations:\n      - method: GET\n        name: get-league-entries\n        description: Get ranked standings for a summoner\n        call: lol-api.get-league-entries-by-summoner\n        with:\n          encryptedSummonerId: rest.encryptedSummonerId\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/matches/{puuid}/ids\n      name: match-ids\n      description: Recent match IDs\n      operations:\n      - method: GET\n        name: get-match-ids\n        description: Get recent match IDs for a\
  \ player\n        call: lol-api.get-match-ids-by-puuid\n        with:\n          puuid: rest.puuid\n          count: rest.count\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/matches/{matchId}\n      name: match\n      description: Match details\n      operations:\n      - method: GET\n        name: get-match\n        description: Get full match details and participant stats\n        call: lol-api.get-match\n        with:\n          matchId: rest.matchId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/live-games/{encryptedSummonerId}\n      name: live-game\n      description: Live game data\n      operations:\n      - method: GET\n        name: get-live-game\n        description: Get current live game for a summoner\n        call: lol-api.get-live-game\n        with:\n          encryptedSummonerId: rest.encryptedSummonerId\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /v1/featured-games\n      name: featured-games\n      description: Featured live games\n      operations:\n      - method: GET\n        name: get-featured-games\n        description: Get currently featured live games\n        call: lol-api.get-featured-games\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/champions/rotation\n      name: champion-rotation\n      description: Free champion rotation\n      operations:\n      - method: GET\n        name: get-champion-rotations\n        description: Get free champion rotation\n        call: lol-api.get-champion-rotations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: riot-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted Riot Games analytics and player insights.\n    tools:\n    - name: get-summoner\n      description: Look up a League of Legends summoner profile by PUUID\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: lol-api.get-summoner-by-puuid\n      with:\n        encryptedPUUID: tools.encryptedPUUID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-champion-mastery\n      description: Get champion mastery rankings to understand a player's most played champions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-champion-mastery\n      with:\n        encryptedPUUID: tools.encryptedPUUID\n        count: tools.count\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-ranked-standings\n      description: Get ranked league standings and LP for a summoner across all queues\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-league-entries-by-summoner\n      with:\n        encryptedSummonerId: tools.encryptedSummonerId\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-match-history-ids\n\
  \      description: Get recent match IDs for a player to fetch individual match details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-match-ids-by-puuid\n      with:\n        puuid: tools.puuid\n        count: tools.count\n        queue: tools.queue\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-match-details\n      description: Get full match details including all participant stats, items, and outcomes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-match\n      with:\n        matchId: tools.matchId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-live-game\n      description: Check if a summoner is currently in a live game and get game details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-live-game\n      with:\n        encryptedSummonerId: tools.encryptedSummonerId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-featured-games\n      description: Get currently featured live games on the platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-featured-games\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-free-champion-rotation\n      description: Get the current free champion rotation for new player recommendations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: lol-api.get-champion-rotations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/riot-games/refs/heads/main/capabilities/game-data-analytics.yaml
tags:
- Analytics
- Gaming
- League of Legends
- Match History
- Ranked
- Riot Games
tools:
- description: Look up a League of Legends summoner profile by PUUID
  hints:
    openWorld: true
    readOnly: true
  name: get-summoner
- description: Get champion mastery rankings to understand a player's most played champions
  hints:
    openWorld: true
    readOnly: true
  name: get-champion-mastery
- description: Get ranked league standings and LP for a summoner across all queues
  hints:
    openWorld: true
    readOnly: true
  name: get-ranked-standings
- description: Get recent match IDs for a player to fetch individual match details
  hints:
    openWorld: true
    readOnly: true
  name: get-match-history-ids
- description: Get full match details including all participant stats, items, and outcomes
  hints:
    openWorld: true
    readOnly: true
  name: get-match-details
- description: Check if a summoner is currently in a live game and get game details
  hints:
    openWorld: true
    readOnly: true
  name: get-live-game
- description: Get currently featured live games on the platform
  hints:
    openWorld: true
    readOnly: true
  name: get-featured-games
- description: Get the current free champion rotation for new player recommendations
  hints:
    openWorld: true
    readOnly: true
  name: get-free-champion-rotation
---
