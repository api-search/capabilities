---
api_specs:
- filename: sportsgameodds-openapi.yml
  format: yaml
  label: sportsgameodds
  slug: sportsgameodds
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sportsgameodds/refs/heads/main/openapi/sportsgameodds-openapi.yml
categories: []
consumed_apis:
- sportsgameodds
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
- supported sports catalog
- list available betting markets (moneylines, spreads, totals, props)
- gambling
- get player details and props odds by player id.
- get team by id
- list sports teams for a given sport or league.
- get player
- player props
- soccer
- list all 50+ sports covered by sportsgameodds.
- betting market types
- ufc
- individual sports team
- get player by id
- nfl
- list all 50+ covered sports
- sports teams
- supported leagues catalog
- list events
- get details for a specific sports team by id.
- list teams
- get event
- sports data
- list players by team, sport, or league
- odds
- list markets
- list sports
- athletes for player prop research
- list all leagues with optional sport filter
- single sporting event with complete odds across all sportsbooks
- list available betting market types — moneylines, spreads, totals, team props, and player props.
- get event with full multi-sportsbook odds
- sporting events with live odds from multiple sportsbooks
- get usage
- mlb
- get current api usage metrics and remaining rate limit quota.
- list sporting events with sport, league, and status filters
- list stats
- get team
- list leagues
- nhl
- retrieve statistical data for events
- nba
- list all covered leagues (nfl, nba, mlb, nhl, epl, ucl, ufc, pga, atp, etc.).
- list teams by sport or league
- list players
- fantasy sports
- get api usage metrics
- get full odds for a specific event from all 80+ sportsbooks across all markets.
- list athletes for player prop research by team, sport, or league.
- individual athlete with props data
- api usage and rate limit status
- game and player statistics
- list sporting events with live odds. filter by sport (nfl, nba, etc.), league, and status (scheduled/live/completed).
- sports betting
- retrieve statistical data for events by sport or league.
- get account usage
slug: sports-betting-odds
source_filename: sports-betting-odds.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SportsGameOdds Sports Betting Odds\"\n  description: >-\n    Unified sports betting odds capability composing SportsGameOdds data to support\n    odds comparison, event monitoring, player prop research, and market discovery\n    across 80+ sportsbooks and 50+ leagues. Used by sports bettors, traders, and\n    fantasy sports analysts.\n  tags:\n    - Sports Betting\n    - Odds\n    - NFL\n    - NBA\n    - MLB\n    - NHL\n    - Soccer\n    - UFC\n    - Player Props\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPORTSGAMEODDS_API_KEY: SPORTSGAMEODDS_API_KEY\n\ncapability:\n  consumes:\n    - import: sportsgameodds\n      location: ./shared/sportsgameodds.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sports-betting-odds-api\n      description: \"Unified REST API for sports betting odds comparison and research.\"\n      resources:\n        - path: /v1/events\n\
  \          name: events\n          description: \"Sporting events with live odds from multiple sportsbooks\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List sporting events with sport, league, and status filters\"\n              call: \"sportsgameodds.list-events\"\n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n                status: \"rest.status\"\n                dateFrom: \"rest.dateFrom\"\n                dateTo: \"rest.dateTo\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/{eventId}\n          name: event\n          description: \"Single sporting event with complete odds across all sportsbooks\"\n          operations:\n            - method: GET\n              name: get-event\n              description: \"Get event with full multi-sportsbook\
  \ odds\"\n              call: \"sportsgameodds.get-event\"\n              with:\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams\n          name: teams\n          description: \"Sports teams\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List teams by sport or league\"\n              call: \"sportsgameodds.list-teams\"\n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams/{teamId}\n          name: team\n          description: \"Individual sports team\"\n          operations:\n            - method: GET\n              name: get-team\n              description: \"Get team by ID\"\n              call: \"sportsgameodds.get-team\"\n   \
  \           with:\n                teamId: \"rest.teamId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players\n          name: players\n          description: \"Athletes for player prop research\"\n          operations:\n            - method: GET\n              name: list-players\n              description: \"List players by team, sport, or league\"\n              call: \"sportsgameodds.list-players\"\n              with:\n                teamId: \"rest.teamId\"\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{playerId}\n          name: player\n          description: \"Individual athlete with props data\"\n          operations:\n            - method: GET\n              name: get-player\n              description: \"Get player by ID\"\n              call:\
  \ \"sportsgameodds.get-player\"\n              with:\n                playerId: \"rest.playerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sports\n          name: sports\n          description: \"Supported sports catalog\"\n          operations:\n            - method: GET\n              name: list-sports\n              description: \"List all 50+ covered sports\"\n              call: \"sportsgameodds.list-sports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/leagues\n          name: leagues\n          description: \"Supported leagues catalog\"\n          operations:\n            - method: GET\n              name: list-leagues\n              description: \"List all leagues with optional sport filter\"\n              call: \"sportsgameodds.list-leagues\"\n              with:\n                sport: \"rest.sport\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/markets\n          name: markets\n          description: \"Betting market types\"\n          operations:\n            - method: GET\n              name: list-markets\n              description: \"List available betting markets (moneylines, spreads, totals, props)\"\n              call: \"sportsgameodds.list-markets\"\n              with:\n                sport: \"rest.sport\"\n                betType: \"rest.betType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stats\n          name: stats\n          description: \"Game and player statistics\"\n          operations:\n            - method: GET\n              name: list-stats\n              description: \"Retrieve statistical data for events\"\n              call: \"sportsgameodds.list-stats\"\n              with:\n                eventId: \"rest.eventId\"\n                sport:\
  \ \"rest.sport\"\n                league: \"rest.league\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account/usage\n          name: usage\n          description: \"API usage and rate limit status\"\n          operations:\n            - method: GET\n              name: get-usage\n              description: \"Get API usage metrics\"\n              call: \"sportsgameodds.get-usage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sports-betting-odds-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports betting odds research and comparison.\"\n      tools:\n        - name: list-events\n          description: \"List sporting events with live odds. Filter by sport (NFL, NBA, etc.), league, and status (scheduled/live/completed).\"\n          hints:\n            readOnly: true\n    \
  \        openWorld: true\n          call: \"sportsgameodds.list-events\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n            status: \"tools.status\"\n            dateFrom: \"tools.dateFrom\"\n            dateTo: \"tools.dateTo\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-event\n          description: \"Get full odds for a specific event from all 80+ sportsbooks across all markets.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.get-event\"\n          with:\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-teams\n          description: \"List sports teams for a given sport or league.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"sportsgameodds.list-teams\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team\n          description: \"Get details for a specific sports team by ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.get-team\"\n          with:\n            teamId: \"tools.teamId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-players\n          description: \"List athletes for player prop research by team, sport, or league.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.list-players\"\n          with:\n            teamId: \"tools.teamId\"\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-player\n          description: \"Get player details and props odds by player ID.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.get-player\"\n          with:\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sports\n          description: \"List all 50+ sports covered by SportsGameOdds.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.list-sports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leagues\n          description: \"List all covered leagues (NFL, NBA, MLB, NHL, EPL, UCL, UFC, PGA, ATP, etc.).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.list-leagues\"\n          with:\n\
  \            sport: \"tools.sport\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-markets\n          description: \"List available betting market types — moneylines, spreads, totals, team props, and player props.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.list-markets\"\n          with:\n            sport: \"tools.sport\"\n            betType: \"tools.betType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stats\n          description: \"Retrieve statistical data for events by sport or league.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsgameodds.list-stats\"\n          with:\n            eventId: \"tools.eventId\"\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-account-usage\n          description: \"Get current API usage metrics and remaining rate limit quota.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sportsgameodds.get-usage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
