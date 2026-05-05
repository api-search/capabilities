---
api_specs:
- filename: the-odds-api-openapi.yml
  format: yaml
  label: the-odds-api
  slug: the-odds-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-odds-api/refs/heads/main/openapi/the-odds-api-openapi.yml
categories: []
consumed_apis:
- the-odds-api
description: Comprehensive workflow for sports betting research, odds comparison, and line movement analysis. Combines live odds from multiple bookmakers, real-time scores, event discovery, and historical odds data. Used by bettors, analysts, trading desks, and developers building sports betting applications.
layout: capability
name: Sports Betting Intelligence
operations:
- description: List all available sports with their keys and descriptions.
  method: GET
  name: get-sports
  path: /v1/sports
- description: Get current odds from bookmakers for comparison.
  method: GET
  name: get-sport-odds
  path: /v1/sports/{sport}/odds
- description: Get live scores updated every 30 seconds.
  method: GET
  name: get-sport-scores
  path: /v1/sports/{sport}/scores
- description: Get upcoming event IDs for a sport.
  method: GET
  name: get-sport-events
  path: /v1/sports/{sport}/events
- description: Get comprehensive odds for a single event.
  method: GET
  name: get-event-odds
  path: /v1/sports/{sport}/events/{eventId}/odds
- description: Get teams or players in a sport.
  method: GET
  name: get-sport-participants
  path: /v1/sports/{sport}/participants
- description: Get historical odds at a specific timestamp.
  method: GET
  name: get-historical-odds
  path: /v1/historical/sports/{sport}/odds
personas: []
provider_name: The Odds API
provider_slug: the-odds-api
search_terms:
- sports betting
- get historical odds
- list all available sports with their api keys. use this to discover which sports are available before requesting odds.
- odds comparison
- available sports with active event coverage.
- get current betting odds for a sport from multiple bookmakers. specify regions (us, uk, au, eu) and markets (h2h=moneyline, spreads=handicap, totals=over-under, outrights=futures).
- get historical betting odds at a specific timestamp for line movement analysis. available from june 2020 at 5-10 minute intervals.
- get upcoming event ids for a sport.
- get comprehensive odds for a single event.
- get sport participants
- upcoming events for a sport.
- get sports
- get the complete list of teams or players in a sport for reference.
- teams and players in a sport.
- get sport scores
- live odds from multiple bookmakers.
- historical odds snapshots.
- scores
- get live and recent game scores for a sport. scores update approximately every 30 seconds. use daysfrom (1-3) to include recently completed games.
- get sport events
- list all available sports with their keys and descriptions.
- sports
- line movement
- betting
- get live scores updated every 30 seconds.
- get upcoming event ids and metadata for a sport without consuming odds quota.
- all markets for a specific event.
- get event odds
- get current odds from bookmakers for comparison.
- get sport odds
- odds
- get teams or players in a sport.
- get all available betting markets for a specific event including player props, alternate lines, and period markets.
- historical analysis
- live scores
- historical data
- live and recent game scores.
- get historical odds at a specific timestamp.
slug: sports-betting-intelligence
source_filename: sports-betting-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sports Betting Intelligence\"\n  description: \"Comprehensive workflow for sports betting research, odds comparison, and line movement analysis. Combines live odds from multiple bookmakers, real-time scores, event discovery, and historical odds data. Used by bettors, analysts, trading desks, and developers building sports betting applications.\"\n  tags:\n    - Sports Betting\n    - Odds Comparison\n    - Line Movement\n    - Live Scores\n    - Historical Analysis\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      ODDS_API_KEY: ODDS_API_KEY\n\ncapability:\n  consumes:\n    - import: the-odds-api\n      location: ./shared/the-odds-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sports-betting-intelligence-api\n      description: \"Unified REST API for sports betting intelligence and odds analysis.\"\n      resources:\n        - path: /v1/sports\n  \
  \        name: sports\n          description: \"Available sports with active event coverage.\"\n          operations:\n            - method: GET\n              name: get-sports\n              description: \"List all available sports with their keys and descriptions.\"\n              call: \"the-odds-api.get-sports\"\n              with:\n                all: \"rest.all\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/sports/{sport}/odds\n          name: odds\n          description: \"Live odds from multiple bookmakers.\"\n          operations:\n            - method: GET\n              name: get-sport-odds\n              description: \"Get current odds from bookmakers for comparison.\"\n              call: \"the-odds-api.get-sport-odds\"\n              with:\n                sport: \"rest.sport\"\n                regions: \"rest.regions\"\n                markets: \"rest.markets\"\n                oddsFormat: \"\
  rest.oddsFormat\"\n                commenceTimeFrom: \"rest.commenceTimeFrom\"\n                commenceTimeTo: \"rest.commenceTimeTo\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/sports/{sport}/scores\n          name: scores\n          description: \"Live and recent game scores.\"\n          operations:\n            - method: GET\n              name: get-sport-scores\n              description: \"Get live scores updated every 30 seconds.\"\n              call: \"the-odds-api.get-sport-scores\"\n              with:\n                sport: \"rest.sport\"\n                daysFrom: \"rest.daysFrom\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/sports/{sport}/events\n          name: events\n          description: \"Upcoming events for a sport.\"\n          operations:\n            - method: GET\n              name: get-sport-events\n  \
  \            description: \"Get upcoming event IDs for a sport.\"\n              call: \"the-odds-api.get-sport-events\"\n              with:\n                sport: \"rest.sport\"\n                commenceTimeFrom: \"rest.commenceTimeFrom\"\n                commenceTimeTo: \"rest.commenceTimeTo\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/sports/{sport}/events/{eventId}/odds\n          name: event-odds\n          description: \"All markets for a specific event.\"\n          operations:\n            - method: GET\n              name: get-event-odds\n              description: \"Get comprehensive odds for a single event.\"\n              call: \"the-odds-api.get-event-odds\"\n              with:\n                sport: \"rest.sport\"\n                eventId: \"rest.eventId\"\n                regions: \"rest.regions\"\n                markets: \"rest.markets\"\n                oddsFormat: \"rest.oddsFormat\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sports/{sport}/participants\n          name: participants\n          description: \"Teams and players in a sport.\"\n          operations:\n            - method: GET\n              name: get-sport-participants\n              description: \"Get teams or players in a sport.\"\n              call: \"the-odds-api.get-sport-participants\"\n              with:\n                sport: \"rest.sport\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/historical/sports/{sport}/odds\n          name: historical-odds\n          description: \"Historical odds snapshots.\"\n          operations:\n            - method: GET\n              name: get-historical-odds\n              description: \"Get historical odds at a specific timestamp.\"\n              call: \"the-odds-api.get-historical-odds\"\n            \
  \  with:\n                sport: \"rest.sport\"\n                date: \"rest.date\"\n                regions: \"rest.regions\"\n                markets: \"rest.markets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sports-betting-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports betting research and odds analysis.\"\n      tools:\n        - name: get-sports\n          description: \"List all available sports with their API keys. Use this to discover which sports are available before requesting odds.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-sports\"\n          with:\n            all: \"tools.all\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-sport-odds\n          description: \"Get current betting\
  \ odds for a sport from multiple bookmakers. Specify regions (us, uk, au, eu) and markets (h2h=moneyline, spreads=handicap, totals=over-under, outrights=futures).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-sport-odds\"\n          with:\n            sport: \"tools.sport\"\n            regions: \"tools.regions\"\n            markets: \"tools.markets\"\n            oddsFormat: \"tools.oddsFormat\"\n            commenceTimeFrom: \"tools.commenceTimeFrom\"\n            commenceTimeTo: \"tools.commenceTimeTo\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-sport-scores\n          description: \"Get live and recent game scores for a sport. Scores update approximately every 30 seconds. Use daysFrom (1-3) to include recently completed games.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-sport-scores\"\
  \n          with:\n            sport: \"tools.sport\"\n            daysFrom: \"tools.daysFrom\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-sport-events\n          description: \"Get upcoming event IDs and metadata for a sport without consuming odds quota.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-sport-events\"\n          with:\n            sport: \"tools.sport\"\n            commenceTimeFrom: \"tools.commenceTimeFrom\"\n            commenceTimeTo: \"tools.commenceTimeTo\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-event-odds\n          description: \"Get all available betting markets for a specific event including player props, alternate lines, and period markets.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-event-odds\"\
  \n          with:\n            sport: \"tools.sport\"\n            eventId: \"tools.eventId\"\n            regions: \"tools.regions\"\n            markets: \"tools.markets\"\n            oddsFormat: \"tools.oddsFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sport-participants\n          description: \"Get the complete list of teams or players in a sport for reference.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-odds-api.get-sport-participants\"\n          with:\n            sport: \"tools.sport\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-historical-odds\n          description: \"Get historical betting odds at a specific timestamp for line movement analysis. Available from June 2020 at 5-10 minute intervals.\"\n          hints:\n            readOnly: true\n            idempotent: true\n     \
  \     call: \"the-odds-api.get-historical-odds\"\n          with:\n            sport: \"tools.sport\"\n            date: \"tools.date\"\n            regions: \"tools.regions\"\n            markets: \"tools.markets\"\n            oddsFormat: \"tools.oddsFormat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-odds-api/refs/heads/main/capabilities/sports-betting-intelligence.yaml
tags:
- Sports Betting
- Odds Comparison
- Line Movement
- Live Scores
- Historical Analysis
tools:
- description: List all available sports with their API keys. Use this to discover which sports are available before requesting odds.
  hints:
    idempotent: true
    readOnly: true
  name: get-sports
- description: Get current betting odds for a sport from multiple bookmakers. Specify regions (us, uk, au, eu) and markets (h2h=moneyline, spreads=handicap, totals=over-under, outrights=futures).
  hints:
    idempotent: true
    readOnly: true
  name: get-sport-odds
- description: Get live and recent game scores for a sport. Scores update approximately every 30 seconds. Use daysFrom (1-3) to include recently completed games.
  hints:
    idempotent: true
    readOnly: true
  name: get-sport-scores
- description: Get upcoming event IDs and metadata for a sport without consuming odds quota.
  hints:
    idempotent: true
    readOnly: true
  name: get-sport-events
- description: Get all available betting markets for a specific event including player props, alternate lines, and period markets.
  hints:
    idempotent: true
    readOnly: true
  name: get-event-odds
- description: Get the complete list of teams or players in a sport for reference.
  hints:
    idempotent: true
    readOnly: true
  name: get-sport-participants
- description: Get historical betting odds at a specific timestamp for line movement analysis. Available from June 2020 at 5-10 minute intervals.
  hints:
    idempotent: true
    readOnly: true
  name: get-historical-odds
---
