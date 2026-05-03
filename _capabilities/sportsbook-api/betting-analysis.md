---
api_specs:
- filename: sportsbook-api-openapi.yml
  format: yaml
  label: sportsbook-api
  slug: sportsbook-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sportsbook-api/refs/heads/main/openapi/sportsbook-api-openapi.yml
categories: []
consumed_apis:
- sportsbook-api
description: Unified sports betting analysis capability composing Sportsbook API data for odds comparison, arbitrage detection, positive EV identification, and middling strategy research across NFL, NBA, MLB, NHL, NCAA, and soccer.
layout: capability
name: Sportsbook API Betting Analysis
operations:
- description: Get real-time betting odds for a sport and league
  method: GET
  name: get-odds
  path: /v1/odds
- description: Find guaranteed profit arbitrage opportunities
  method: GET
  name: get-arbitrage
  path: /v1/arbitrage
- description: Find bets with positive expected value
  method: GET
  name: get-positive-ev
  path: /v1/positive-ev
- description: Find middling betting opportunities
  method: GET
  name: get-middles
  path: /v1/middles
- description: List supported sports
  method: GET
  name: list-sports
  path: /v1/sports
- description: List all sportsbooks
  method: GET
  name: list-bookmakers
  path: /v1/bookmakers
personas: []
provider_name: Sportsbook API
provider_slug: sportsbook-api
search_terms:
- positive expected value bets
- gambling
- list all sportsbooks
- expected value
- get arbitrage
- get real-time betting odds from fanduel, draftkings, betmgm, and 7+ more sportsbooks. filter by sport (football/basketball/baseball/hockey/soccer) and league (nfl/nba/mlb/nhl/epl).
- 'list all sportsbooks aggregated: fanduel, draftkings, betmgm, kalshi, thescore, fanatics, betrivers, polymarket, bovada, betonline.'
- list supported sports
- find middling opportunities where betting both sides of a game at different lines creates a scenario where both bets can win.
- nfl
- real-time odds from 10+ sportsbooks
- sports data
- supported sports and leagues
- odds
- get odds
- list sports
- aggregated sportsbooks
- find guaranteed profit arbitrage opportunities across sportsbooks. returns events where betting both sides locks in a risk-free profit.
- arbitrage
- middling opportunities
- mlb
- find middling betting opportunities
- list bookmakers
- find positive expected value bets by comparing sportsbook odds to no-vig fair odds consensus. returns bets with above-average long-term profitability.
- nhl
- get real-time betting odds for a sport and league
- nba
- odds comparison
- 'list all sports covered: football (nfl, ncaaf, ufl, cfl), basketball (nba, wnba), baseball (mlb), hockey (nhl), and soccer (epl, mls, la liga).'
- arbitrage opportunities across sportsbooks
- get positive ev
- find bets with positive expected value
- find guaranteed profit arbitrage opportunities
- sports betting
- get middles
slug: betting-analysis
source_filename: betting-analysis.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sportsbook API Betting Analysis\"\n  description: >-\n    Unified sports betting analysis capability composing Sportsbook API data for\n    odds comparison, arbitrage detection, positive EV identification, and middling\n    strategy research across NFL, NBA, MLB, NHL, NCAA, and soccer.\n  tags:\n    - Sports Betting\n    - Arbitrage\n    - Expected Value\n    - Odds Comparison\n    - NFL\n    - NBA\n    - MLB\n    - NHL\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAPIDAPI_KEY: RAPIDAPI_KEY\n\ncapability:\n  consumes:\n    - import: sportsbook-api\n      location: ./shared/sportsbook-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: betting-analysis-api\n      description: \"Unified REST API for sports betting odds, arbitrage, and +EV analysis.\"\n      resources:\n        - path: /v1/odds\n          name: odds\n          description: \"Real-time\
  \ odds from 10+ sportsbooks\"\n          operations:\n            - method: GET\n              name: get-odds\n              description: \"Get real-time betting odds for a sport and league\"\n              call: \"sportsbook-api.get-odds\"\n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n                market: \"rest.market\"\n                bookmaker: \"rest.bookmaker\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/arbitrage\n          name: arbitrage\n          description: \"Arbitrage opportunities across sportsbooks\"\n          operations:\n            - method: GET\n              name: get-arbitrage\n              description: \"Find guaranteed profit arbitrage opportunities\"\n              call: \"sportsbook-api.get-arbitrage\"\n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n                minProfit:\
  \ \"rest.minProfit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/positive-ev\n          name: positive-ev\n          description: \"Positive expected value bets\"\n          operations:\n            - method: GET\n              name: get-positive-ev\n              description: \"Find bets with positive expected value\"\n              call: \"sportsbook-api.get-positive-ev\"\n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n                minEv: \"rest.minEv\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/middles\n          name: middles\n          description: \"Middling opportunities\"\n          operations:\n            - method: GET\n              name: get-middles\n              description: \"Find middling betting opportunities\"\n              call: \"sportsbook-api.get-middles\"\
  \n              with:\n                sport: \"rest.sport\"\n                league: \"rest.league\"\n                minWindow: \"rest.minWindow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sports\n          name: sports\n          description: \"Supported sports and leagues\"\n          operations:\n            - method: GET\n              name: list-sports\n              description: \"List supported sports\"\n              call: \"sportsbook-api.list-sports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bookmakers\n          name: bookmakers\n          description: \"Aggregated sportsbooks\"\n          operations:\n            - method: GET\n              name: list-bookmakers\n              description: \"List all sportsbooks\"\n              call: \"sportsbook-api.list-bookmakers\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: betting-analysis-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports betting analysis and strategy research.\"\n      tools:\n        - name: get-odds\n          description: \"Get real-time betting odds from FanDuel, DraftKings, BetMGM, and 7+ more sportsbooks. Filter by sport (football/basketball/baseball/hockey/soccer) and league (NFL/NBA/MLB/NHL/EPL).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.get-odds\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n            market: \"tools.market\"\n            bookmaker: \"tools.bookmaker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-arbitrage\n          description: \"Find guaranteed profit arbitrage opportunities across sportsbooks.\
  \ Returns events where betting both sides locks in a risk-free profit.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.get-arbitrage\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n            minProfit: \"tools.minProfit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-positive-ev\n          description: \"Find positive expected value bets by comparing sportsbook odds to no-vig fair odds consensus. Returns bets with above-average long-term profitability.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.get-positive-ev\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n            minEv: \"tools.minEv\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-middles\n\
  \          description: \"Find middling opportunities where betting both sides of a game at different lines creates a scenario where both bets can win.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.get-middles\"\n          with:\n            sport: \"tools.sport\"\n            league: \"tools.league\"\n            minWindow: \"tools.minWindow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sports\n          description: \"List all sports covered: football (NFL, NCAAF, UFL, CFL), basketball (NBA, WNBA), baseball (MLB), hockey (NHL), and soccer (EPL, MLS, La Liga).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.list-sports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bookmakers\n          description: \"List all sportsbooks aggregated:\
  \ FanDuel, DraftKings, BetMGM, Kalshi, theScore, Fanatics, BetRivers, Polymarket, Bovada, BetOnline.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsbook-api.list-bookmakers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sportsbook-api/refs/heads/main/capabilities/betting-analysis.yaml
tags:
- Sports Betting
- Arbitrage
- Expected Value
- Odds Comparison
- NFL
- NBA
- MLB
- NHL
tools:
- description: Get real-time betting odds from FanDuel, DraftKings, BetMGM, and 7+ more sportsbooks. Filter by sport (football/basketball/baseball/hockey/soccer) and league (NFL/NBA/MLB/NHL/EPL).
  hints:
    openWorld: true
    readOnly: true
  name: get-odds
- description: Find guaranteed profit arbitrage opportunities across sportsbooks. Returns events where betting both sides locks in a risk-free profit.
  hints:
    openWorld: true
    readOnly: true
  name: get-arbitrage
- description: Find positive expected value bets by comparing sportsbook odds to no-vig fair odds consensus. Returns bets with above-average long-term profitability.
  hints:
    openWorld: true
    readOnly: true
  name: get-positive-ev
- description: Find middling opportunities where betting both sides of a game at different lines creates a scenario where both bets can win.
  hints:
    openWorld: true
    readOnly: true
  name: get-middles
- description: 'List all sports covered: football (NFL, NCAAF, UFL, CFL), basketball (NBA, WNBA), baseball (MLB), hockey (NHL), and soccer (EPL, MLS, La Liga).'
  hints:
    openWorld: true
    readOnly: true
  name: list-sports
- description: 'List all sportsbooks aggregated: FanDuel, DraftKings, BetMGM, Kalshi, theScore, Fanatics, BetRivers, Polymarket, Bovada, BetOnline.'
  hints:
    openWorld: true
    readOnly: true
  name: list-bookmakers
---
