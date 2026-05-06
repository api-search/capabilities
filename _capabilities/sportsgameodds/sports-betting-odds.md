---
categories: []
consumed_apis: []
description: Unified sports betting odds capability composing SportsGameOdds data to support odds comparison, event monitoring, player prop research, and market discovery across 80+ sportsbooks and 50+ leagues. Used by sports bettors, traders, and fantasy sports analysts.
layout: capability
name: SportsGameOdds Sports Betting Odds
operations:
- description: List sporting events with sport, league, and status filters
  method: GET
  name: list-events
  path: /v1/events
- description: Get event with full multi-sportsbook odds
  method: GET
  name: get-event
  path: /v1/events/{eventId}
- description: List teams by sport or league
  method: GET
  name: list-teams
  path: /v1/teams
- description: Get team by ID
  method: GET
  name: get-team
  path: /v1/teams/{teamId}
- description: List players by team, sport, or league
  method: GET
  name: list-players
  path: /v1/players
- description: Get player by ID
  method: GET
  name: get-player
  path: /v1/players/{playerId}
- description: List all 50+ covered sports
  method: GET
  name: list-sports
  path: /v1/sports
- description: List all leagues with optional sport filter
  method: GET
  name: list-leagues
  path: /v1/leagues
- description: List available betting markets (moneylines, spreads, totals, props)
  method: GET
  name: list-markets
  path: /v1/markets
- description: Retrieve statistical data for events
  method: GET
  name: list-stats
  path: /v1/stats
- description: Get API usage metrics
  method: GET
  name: get-usage
  path: /v1/account/usage
personas: []
provider_name: SportsGameOdds
provider_slug: sportsgameodds
search_terms:
- soccer
- list events
- sports data
- list stats
- get event with full multi-sportsbook odds
- get player by id
- supported leagues catalog
- list sports teams for a given sport or league.
- get details for a specific sports team by id.
- gambling
- get current api usage metrics and remaining rate limit quota.
- sports betting
- get event
- list sports
- mlb
- get usage
- nhl
- list teams
- list all covered leagues (nfl, nba, mlb, nhl, epl, ucl, ufc, pga, atp, etc.).
- supported sports catalog
- list players
- single sporting event with complete odds across all sportsbooks
- ufc
- get player details and props odds by player id.
- sporting events with live odds from multiple sportsbooks
- list all leagues with optional sport filter
- fantasy sports
- sports teams
- list players by team, sport, or league
- list all 50+ covered sports
- list sporting events with live odds. filter by sport (nfl, nba, etc.), league, and status (scheduled/live/completed).
- get account usage
- list markets
- api usage and rate limit status
- list leagues
- nfl
- get player
- retrieve statistical data for events
- list sporting events with sport, league, and status filters
- get team
- list teams by sport or league
- individual athlete with props data
- list all 50+ sports covered by sportsgameodds.
- odds
- betting market types
- get full odds for a specific event from all 80+ sportsbooks across all markets.
- player props
- list available betting markets (moneylines, spreads, totals, props)
- game and player statistics
- athletes for player prop research
- list athletes for player prop research by team, sport, or league.
- retrieve statistical data for events by sport or league.
- get team by id
- individual sports team
- get api usage metrics
- nba
- list available betting market types — moneylines, spreads, totals, team props, and player props.
slug: sports-betting-odds
source_filename: sports-betting-odds.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SportsGameOdds Sports Betting Odds\n  description: Unified sports betting odds capability composing SportsGameOdds data to support odds comparison, event monitoring,\n    player prop research, and market discovery across 80+ sportsbooks and 50+ leagues. Used by sports bettors, traders, and\n    fantasy sports analysts.\n  tags:\n  - Sports Betting\n  - Odds\n  - NFL\n  - NBA\n  - MLB\n  - NHL\n  - Soccer\n  - UFC\n  - Player Props\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPORTSGAMEODDS_API_KEY: SPORTSGAMEODDS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sportsgameodds\n    baseUri: https://api.sportsgameodds.com/v1\n    description: SportsGameOdds REST API for real-time sports betting odds data\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{SPORTSGAMEODDS_API_KEY}}'\n      placement: header\n    resources:\n    - name: events\n     \
  \ path: /events/\n      description: Sporting events with live odds from multiple sportsbooks\n      operations:\n      - name: list-events\n        method: GET\n        description: List sporting events with optional sport, league, status, and date filters\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Sport filter (football, basketball, baseball, hockey, soccer)\n        - name: league\n          in: query\n          type: string\n          required: false\n          description: League filter (NFL, NBA, MLB, NHL, EPL, etc.)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Event status filter (scheduled, live, completed)\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n          description: Start date filter (ISO 8601 date)\n        - name: dateTo\n          in: query\n\
  \          type: string\n          required: false\n          description: End date filter (ISO 8601 date)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return (max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-event\n        method: GET\n        description: Get a specific sporting event by ID with odds and scores\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Unique event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams/\n      description: Sports teams data\n      operations:\n      - name: list-teams\n        method: GET\n        description: List teams with optional\
  \ sport and league filters\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Filter by sport\n        - name: league\n          in: query\n          type: string\n          required: false\n          description: Filter by league\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team\n        method: GET\n        description: Get a specific team by ID\n        inputParameters:\n        - name: teamId\n          in: path\n          type: string\n          required: true\n          description: Unique team identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: players\n      path: /players/\n      description: Sports players data including props odds\n      operations:\n      - name: list-players\n       \
  \ method: GET\n        description: List players with optional team, sport, and league filters\n        inputParameters:\n        - name: teamId\n          in: query\n          type: string\n          required: false\n          description: Filter by team ID\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Filter by sport\n        - name: league\n          in: query\n          type: string\n          required: false\n          description: Filter by league\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-player\n        method: GET\n        description: Get a specific player by ID\n        inputParameters:\n        - name: playerId\n          in: path\n          type: string\n          required: true\n          description: Unique player identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: sports\n      path: /sports/\n      description: Supported sports catalog\n      operations:\n      - name: list-sports\n        method: GET\n        description: List all supported sports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leagues\n      path: /leagues/\n      description: Supported leagues catalog\n      operations:\n      - name: list-leagues\n        method: GET\n        description: List all supported leagues with optional sport filter\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Filter leagues by sport\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: markets\n      path: /markets/\n      description: Supported betting market\
  \ types\n      operations:\n      - name: list-markets\n        method: GET\n        description: List all supported betting markets including moneylines, spreads, totals, and props\n        inputParameters:\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Filter markets by sport\n        - name: betType\n          in: query\n          type: string\n          required: false\n          description: Filter by bet type (moneyline, spread, total, prop)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats\n      path: /stats/\n      description: Game and player statistical data\n      operations:\n      - name: list-stats\n        method: GET\n        description: Retrieve statistical data for events\n        inputParameters:\n        - name: eventId\n          in: query\n          type: string\n          required: false\n      \
  \    description: Filter by event ID\n        - name: sport\n          in: query\n          type: string\n          required: false\n          description: Filter by sport\n        - name: league\n          in: query\n          type: string\n          required: false\n          description: Filter by league\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account\n      path: /account/usage/\n      description: API account usage and rate limit information\n      operations:\n      - name: get-usage\n        method: GET\n        description: Get current API usage metrics and rate limit status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sports-betting-odds-api\n    description: Unified REST API for sports betting odds comparison and research.\n    resources:\n\
  \    - path: /v1/events\n      name: events\n      description: Sporting events with live odds from multiple sportsbooks\n      operations:\n      - method: GET\n        name: list-events\n        description: List sporting events with sport, league, and status filters\n        call: sportsgameodds.list-events\n        with:\n          sport: rest.sport\n          league: rest.league\n          status: rest.status\n          dateFrom: rest.dateFrom\n          dateTo: rest.dateTo\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{eventId}\n      name: event\n      description: Single sporting event with complete odds across all sportsbooks\n      operations:\n      - method: GET\n        name: get-event\n        description: Get event with full multi-sportsbook odds\n        call: sportsgameodds.get-event\n        with:\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Sports teams\n      operations:\n      - method: GET\n        name: list-teams\n        description: List teams by sport or league\n        call: sportsgameodds.list-teams\n        with:\n          sport: rest.sport\n          league: rest.league\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{teamId}\n      name: team\n      description: Individual sports team\n      operations:\n      - method: GET\n        name: get-team\n        description: Get team by ID\n        call: sportsgameodds.get-team\n        with:\n          teamId: rest.teamId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players\n      name: players\n      description: Athletes for player prop research\n      operations:\n      - method: GET\n        name: list-players\n        description: List players by team, sport, or league\n        call: sportsgameodds.list-players\n\
  \        with:\n          teamId: rest.teamId\n          sport: rest.sport\n          league: rest.league\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{playerId}\n      name: player\n      description: Individual athlete with props data\n      operations:\n      - method: GET\n        name: get-player\n        description: Get player by ID\n        call: sportsgameodds.get-player\n        with:\n          playerId: rest.playerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sports\n      name: sports\n      description: Supported sports catalog\n      operations:\n      - method: GET\n        name: list-sports\n        description: List all 50+ covered sports\n        call: sportsgameodds.list-sports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leagues\n      name: leagues\n      description: Supported leagues catalog\n      operations:\n    \
  \  - method: GET\n        name: list-leagues\n        description: List all leagues with optional sport filter\n        call: sportsgameodds.list-leagues\n        with:\n          sport: rest.sport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/markets\n      name: markets\n      description: Betting market types\n      operations:\n      - method: GET\n        name: list-markets\n        description: List available betting markets (moneylines, spreads, totals, props)\n        call: sportsgameodds.list-markets\n        with:\n          sport: rest.sport\n          betType: rest.betType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats\n      name: stats\n      description: Game and player statistics\n      operations:\n      - method: GET\n        name: list-stats\n        description: Retrieve statistical data for events\n        call: sportsgameodds.list-stats\n        with:\n          eventId:\
  \ rest.eventId\n          sport: rest.sport\n          league: rest.league\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/account/usage\n      name: usage\n      description: API usage and rate limit status\n      operations:\n      - method: GET\n        name: get-usage\n        description: Get API usage metrics\n        call: sportsgameodds.get-usage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sports-betting-odds-mcp\n    transport: http\n    description: MCP server for AI-assisted sports betting odds research and comparison.\n    tools:\n    - name: list-events\n      description: List sporting events with live odds. Filter by sport (NFL, NBA, etc.), league, and status (scheduled/live/completed).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.list-events\n      with:\n        sport: tools.sport\n        league: tools.league\n\
  \        status: tools.status\n        dateFrom: tools.dateFrom\n        dateTo: tools.dateTo\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event\n      description: Get full odds for a specific event from all 80+ sportsbooks across all markets.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.get-event\n      with:\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List sports teams for a given sport or league.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.list-teams\n      with:\n        sport: tools.sport\n        league: tools.league\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team\n      description: Get details for a specific sports team by ID.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: sportsgameodds.get-team\n      with:\n        teamId: tools.teamId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-players\n      description: List athletes for player prop research by team, sport, or league.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.list-players\n      with:\n        teamId: tools.teamId\n        sport: tools.sport\n        league: tools.league\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player\n      description: Get player details and props odds by player ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.get-player\n      with:\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sports\n      description: List all 50+ sports covered by SportsGameOdds.\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: sportsgameodds.list-sports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-leagues\n      description: List all covered leagues (NFL, NBA, MLB, NHL, EPL, UCL, UFC, PGA, ATP, etc.).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.list-leagues\n      with:\n        sport: tools.sport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-markets\n      description: List available betting market types — moneylines, spreads, totals, team props, and player props.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsgameodds.list-markets\n      with:\n        sport: tools.sport\n        betType: tools.betType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stats\n      description: Retrieve statistical data for events by sport or league.\n      hints:\n        readOnly: true\n        openWorld: true\n \
  \     call: sportsgameodds.list-stats\n      with:\n        eventId: tools.eventId\n        sport: tools.sport\n        league: tools.league\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-usage\n      description: Get current API usage metrics and remaining rate limit quota.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sportsgameodds.get-usage\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sportsgameodds/refs/heads/main/capabilities/sports-betting-odds.yaml
tags:
- Sports Betting
- Odds
- NFL
- NBA
- MLB
- NHL
- Soccer
- UFC
- Player Props
tools:
- description: List sporting events with live odds. Filter by sport (NFL, NBA, etc.), league, and status (scheduled/live/completed).
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: Get full odds for a specific event from all 80+ sportsbooks across all markets.
  hints:
    openWorld: true
    readOnly: true
  name: get-event
- description: List sports teams for a given sport or league.
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Get details for a specific sports team by ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-team
- description: List athletes for player prop research by team, sport, or league.
  hints:
    openWorld: true
    readOnly: true
  name: list-players
- description: Get player details and props odds by player ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-player
- description: List all 50+ sports covered by SportsGameOdds.
  hints:
    openWorld: true
    readOnly: true
  name: list-sports
- description: List all covered leagues (NFL, NBA, MLB, NHL, EPL, UCL, UFC, PGA, ATP, etc.).
  hints:
    openWorld: true
    readOnly: true
  name: list-leagues
- description: List available betting market types — moneylines, spreads, totals, team props, and player props.
  hints:
    openWorld: true
    readOnly: true
  name: list-markets
- description: Retrieve statistical data for events by sport or league.
  hints:
    openWorld: true
    readOnly: true
  name: list-stats
- description: Get current API usage metrics and remaining rate limit quota.
  hints:
    openWorld: false
    readOnly: true
  name: get-account-usage
---
