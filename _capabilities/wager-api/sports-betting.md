---
categories: []
consumed_apis: []
description: Workflow capability for sports betting applications using the Wager API. Combines real-time game odds, player props, futures markets, injury reports, and game schedules in a unified workflow. Designed for sports betting apps, bots, and predictive models needing comprehensive pre-game and in-game data across NFL, NCAA, NBA, MLB, NHL, soccer, tennis, and golf.
layout: capability
name: Wager API Sports Betting
operations:
- description: Get real-time game odds for spreads, moneylines, and totals
  method: GET
  name: get-game-odds
  path: /v1/odds
- description: Get player prop odds
  method: GET
  name: get-player-props
  path: /v1/props
- description: Get futures and championship odds
  method: GET
  name: get-futures-odds
  path: /v1/futures
- description: Get player roster information
  method: GET
  name: get-players
  path: /v1/players
- description: Get player stats and game log
  method: GET
  name: get-player-stats
  path: /v1/players/{playerId}/stats
- description: Get player projections for upcoming games
  method: GET
  name: get-player-projections
  path: /v1/players/{playerId}/projections
- description: Get current injury reports
  method: GET
  name: get-injury-reports
  path: /v1/injuries
- description: Get game schedules and results
  method: GET
  name: get-games
  path: /v1/games
- description: Get team depth charts
  method: GET
  name: get-depth-charts
  path: /v1/depth-charts
personas: []
provider_name: Wager API
provider_slug: wager-api
search_terms:
- championship and season futures
- player injury reports
- sports data
- get real-time game odds for spreads, moneylines, and totals
- get current injury reports
- get championship and season futures odds including super bowl, nba finals, and more
- futures
- get player projections
- get player roster information
- player statistical projections
- get player prop odds
- get real-time game odds for any sport including spreads, moneylines, totals, and alternate lines. supports nfl, ncaa, nba, mlb, nhl, soccer, tennis, and golf.
- team depth charts
- mlb
- real-time game odds
- get game schedules and results
- get depth charts
- get injury reports
- player statistics
- get player proposition odds for passing yards, points, home runs, and other stats
- get player statistics including season totals and game-by-game log
- get games
- fantasy sports
- nhl
- wager api
- get futures odds
- game schedules and results
- get player stats and game log
- get team depth charts
- get team depth charts showing starter and backup designations by position
- get futures and championship odds
- get players
- odds
- player roster information
- get player stats
- get current player injury reports with status, practice participation, and return timeline
- sports betting
- get player projections for upcoming games
- get game schedules and results for a sport with scores and status
- sports odds
- ncaa
- get game odds
- nfl
- player proposition odds
- get player props
- player props
- nba
- get statistical projections for a player's upcoming games for model building
slug: sports-betting
source_filename: sports-betting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wager API Sports Betting\n  description: Workflow capability for sports betting applications using the Wager API. Combines real-time game odds, player\n    props, futures markets, injury reports, and game schedules in a unified workflow. Designed for sports betting apps, bots,\n    and predictive models needing comprehensive pre-game and in-game data across NFL, NCAA, NBA, MLB, NHL, soccer, tennis,\n    and golf.\n  tags:\n  - Wager API\n  - Sports Betting\n  - Odds\n  - Player Props\n  - Futures\n  - NFL\n  - NBA\n  - MLB\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WAGER_API_KEY: WAGER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: wager-api\n    baseUri: https://api.wagerapi.com\n    description: Wager API sports betting data platform\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{WAGER_API_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: odds\n      path: /v1/odds\n      description: Real-time game odds\n      operations:\n      - name: get-game-odds\n        method: GET\n        description: Get real-time game odds for spreads, moneylines, and totals\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: Odds market type filter\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n    - name: props\n      path: /v1/props\n      description: Player proposition odds\n      operations:\n      - name: get-player-props\n        method: GET\n        description: Get player proposition odds\n\
  \        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: game_id\n          in: query\n          type: string\n          required: false\n          description: Game identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n    - name: futures\n      path: /v1/futures\n      description: Futures and championship odds\n      operations:\n      - name: get-futures-odds\n        method: GET\n        description: Get futures and championship market odds\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: market\n          in: query\n          type: string\n          required: false\n          description: Futures market type\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: data\n          type: array\n          value: $.data\n    - name: players\n      path: /v1/players\n      description: Player information\n      operations:\n      - name: get-players\n        method: GET\n        description: Get player roster information\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: team_id\n          in: query\n          type: string\n          required: false\n          description: Team filter\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n    - name: player-stats\n      path: /v1/players/{playerId}/stats\n      description: Player statistics\n      operations:\n      - name: get-player-stats\n        method: GET\n        description: Get player statistics and game log\n        inputParameters:\n        - name: playerId\n          in: path\n\
  \          type: string\n          required: true\n          description: Player identifier\n        - name: season\n          in: query\n          type: string\n          required: false\n          description: Season year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: player-projections\n      path: /v1/players/{playerId}/projections\n      description: Player projections\n      operations:\n      - name: get-player-projections\n        method: GET\n        description: Get statistical projections for a player's upcoming games\n        inputParameters:\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: injuries\n      path: /v1/injuries\n      description: Injury reports\n\
  \      operations:\n      - name: get-injury-reports\n        method: GET\n        description: Get current injury reports for players\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Injury status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n    - name: games\n      path: /v1/games\n      description: Game schedules and results\n      operations:\n      - name: get-games\n        method: GET\n        description: Get game schedules, results, and status\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: date\n          in: query\n          type:\
  \ string\n          required: false\n          description: Date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n    - name: depth-charts\n      path: /v1/depth-charts\n      description: Team depth charts\n      operations:\n      - name: get-depth-charts\n        method: GET\n        description: Get team depth charts for lineup analysis\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: true\n          description: Sport identifier\n        - name: team_id\n          in: query\n          type: string\n          required: false\n          description: Team filter\n        outputRawFormat: json\n        outputParameters:\n        - name: data\n          type: array\n          value: $.data\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sports-betting-api\n    description: Unified REST API for sports betting data workflows.\n\
  \    resources:\n    - path: /v1/odds\n      name: game-odds\n      description: Real-time game odds\n      operations:\n      - method: GET\n        name: get-game-odds\n        description: Get real-time game odds for spreads, moneylines, and totals\n        call: wager-api.get-game-odds\n        with:\n          sport: rest.sport\n          market: rest.market\n          date: rest.date\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/props\n      name: player-props\n      description: Player proposition odds\n      operations:\n      - method: GET\n        name: get-player-props\n        description: Get player prop odds\n        call: wager-api.get-player-props\n        with:\n          sport: rest.sport\n          game_id: rest.game_id\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/futures\n      name: futures\n      description: Championship and season futures\n      operations:\n      -\
  \ method: GET\n        name: get-futures-odds\n        description: Get futures and championship odds\n        call: wager-api.get-futures-odds\n        with:\n          sport: rest.sport\n          market: rest.market\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/players\n      name: players\n      description: Player roster information\n      operations:\n      - method: GET\n        name: get-players\n        description: Get player roster information\n        call: wager-api.get-players\n        with:\n          sport: rest.sport\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/players/{playerId}/stats\n      name: player-stats\n      description: Player statistics\n      operations:\n      - method: GET\n        name: get-player-stats\n        description: Get player stats and game log\n        call: wager-api.get-player-stats\n        with:\n          playerId: rest.playerId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}/projections\n      name: player-projections\n      description: Player statistical projections\n      operations:\n      - method: GET\n        name: get-player-projections\n        description: Get player projections for upcoming games\n        call: wager-api.get-player-projections\n        with:\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/injuries\n      name: injuries\n      description: Player injury reports\n      operations:\n      - method: GET\n        name: get-injury-reports\n        description: Get current injury reports\n        call: wager-api.get-injury-reports\n        with:\n          sport: rest.sport\n          status: rest.status\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/games\n      name: games\n      description: Game schedules and results\n      operations:\n\
  \      - method: GET\n        name: get-games\n        description: Get game schedules and results\n        call: wager-api.get-games\n        with:\n          sport: rest.sport\n          date: rest.date\n        outputParameters:\n        - type: array\n          mapping: $.data\n    - path: /v1/depth-charts\n      name: depth-charts\n      description: Team depth charts\n      operations:\n      - method: GET\n        name: get-depth-charts\n        description: Get team depth charts\n        call: wager-api.get-depth-charts\n        with:\n          sport: rest.sport\n          team_id: rest.team_id\n        outputParameters:\n        - type: array\n          mapping: $.data\n  - type: mcp\n    port: 9080\n    namespace: sports-betting-mcp\n    transport: http\n    description: MCP server for AI-assisted sports betting analysis and model building.\n    tools:\n    - name: get-game-odds\n      description: Get real-time game odds for any sport including spreads, moneylines, totals,\
  \ and alternate lines. Supports\n        NFL, NCAA, NBA, MLB, NHL, soccer, tennis, and golf.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-game-odds\n      with:\n        sport: tools.sport\n        market: tools.market\n        date: tools.date\n        game_id: tools.game_id\n      outputParameters:\n      - type: array\n        mapping: $.data\n    - name: get-player-props\n      description: Get player proposition odds for passing yards, points, home runs, and other stats\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-player-props\n      with:\n        sport: tools.sport\n        game_id: tools.game_id\n        player_id: tools.player_id\n        market: tools.market\n      outputParameters:\n      - type: array\n        mapping: $.data\n    - name: get-futures-odds\n      description: Get championship and season futures odds including Super Bowl, NBA Finals, and more\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: wager-api.get-futures-odds\n      with:\n        sport: tools.sport\n        market: tools.market\n      outputParameters:\n      - type: array\n        mapping: $.data\n    - name: get-injury-reports\n      description: Get current player injury reports with status, practice participation, and return timeline\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-injury-reports\n      with:\n        sport: tools.sport\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.data\n    - name: get-player-stats\n      description: Get player statistics including season totals and game-by-game log\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-player-stats\n      with:\n        playerId: tools.playerId\n        season: tools.season\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-projections\n\
  \      description: Get statistical projections for a player's upcoming games for model building\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-player-projections\n      with:\n        playerId: tools.playerId\n        game_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-games\n      description: Get game schedules and results for a sport with scores and status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-games\n      with:\n        sport: tools.sport\n        date: tools.date\n        status: tools.status\n      outputParameters:\n      - type: array\n        mapping: $.data\n    - name: get-depth-charts\n      description: Get team depth charts showing starter and backup designations by position\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wager-api.get-depth-charts\n      with:\n        sport: tools.sport\n    \
  \    team_id: tools.team_id\n      outputParameters:\n      - type: array\n        mapping: $.data\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wager-api/refs/heads/main/capabilities/sports-betting.yaml
tags:
- Wager API
- Sports Betting
- Odds
- Player Props
- Futures
- NFL
- NBA
- MLB
tools:
- description: Get real-time game odds for any sport including spreads, moneylines, totals, and alternate lines. Supports NFL, NCAA, NBA, MLB, NHL, soccer, tennis, and golf.
  hints:
    openWorld: true
    readOnly: true
  name: get-game-odds
- description: Get player proposition odds for passing yards, points, home runs, and other stats
  hints:
    openWorld: true
    readOnly: true
  name: get-player-props
- description: Get championship and season futures odds including Super Bowl, NBA Finals, and more
  hints:
    openWorld: true
    readOnly: true
  name: get-futures-odds
- description: Get current player injury reports with status, practice participation, and return timeline
  hints:
    openWorld: true
    readOnly: true
  name: get-injury-reports
- description: Get player statistics including season totals and game-by-game log
  hints:
    openWorld: true
    readOnly: true
  name: get-player-stats
- description: Get statistical projections for a player's upcoming games for model building
  hints:
    openWorld: true
    readOnly: true
  name: get-player-projections
- description: Get game schedules and results for a sport with scores and status
  hints:
    openWorld: true
    readOnly: true
  name: get-games
- description: Get team depth charts showing starter and backup designations by position
  hints:
    openWorld: true
    readOnly: true
  name: get-depth-charts
---
