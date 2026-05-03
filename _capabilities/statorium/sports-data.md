---
categories: []
consumed_apis:
- statorium-football
- statorium-basketball
- statorium-nfl
description: Unified sports data capability combining Statorium's Football, Basketball, and American Football APIs into a single workflow. Enables sports platforms, fantasy sports apps, and media publishers to access live scores, standings, match details, and news across all sports from a single integration.
layout: capability
name: Statorium Sports Data
operations:
- description: List all accessible football leagues.
  method: GET
  name: list-football-leagues
  path: /v1/leagues
- description: List football matches filtered by league, date, or status.
  method: GET
  name: list-matches
  path: /v1/matches
- description: Get football match details with lineups and head-to-head.
  method: GET
  name: get-match
  path: /v1/matches/{matchId}
- description: Get football league standings table.
  method: GET
  name: get-standings
  path: /v1/standings
- description: List basketball games.
  method: GET
  name: list-basketball-games
  path: /v1/basketball/games
- description: List NFL games filtered by week, season, or team.
  method: GET
  name: list-nfl-games
  path: /v1/nfl/games
- description: List latest NFL news.
  method: GET
  name: list-nfl-news
  path: /v1/nfl/news
- description: Get NFL standings by division.
  method: GET
  name: get-nfl-standings
  path: /v1/nfl/standings
personas: []
provider_name: Statorium
provider_slug: statorium
search_terms:
- get football team
- get football player
- basketball
- nfl game listings.
- list football matches
- football league standings.
- list football/soccer matches filtered by league, date, team, or live status.
- get nfl game
- list all accessible football leagues.
- get nfl standings by conference and division.
- soccer
- football league listings.
- get basketball game
- list matches
- get full football match details including lineups, events, stats, and head-to-head history.
- nfl
- get football league standings table.
- live scores
- get nfl standings
- get football match
- list nfl news
- sports data
- get football player profile and statistics.
- get football standings
- get basketball game box score and quarter-by-quarter breakdown.
- list basketball games
- nfl news feed.
- statistics
- get nfl game details including quarter scores and team statistics.
- list football leagues
- get football team details including squad and statistics.
- list basketball games.
- list all accessible football and soccer leagues.
- list football matches filtered by league, date, or status.
- get match
- basketball game listings.
- get basketball league standings.
- nfl standings.
- get football match details with lineups and head-to-head.
- list latest nfl news.
- list nfl games filtered by week, season, team, or status.
- football match listings and live scores.
- list basketball games filtered by league, date, or status.
- nba
- list nfl games
- list nfl games filtered by week, season, or team.
- get nfl standings by division.
- get the current standings table for a football league.
- individual football match details.
- sports
- football
- get standings
- get basketball standings
- get the latest nfl news linked to specific players or teams.
- american football
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Statorium Sports Data\"\n  description: >-\n    Unified sports data capability combining Statorium's Football, Basketball,\n    and American Football APIs into a single workflow. Enables sports platforms,\n    fantasy sports apps, and media publishers to access live scores, standings,\n    match details, and news across all sports from a single integration.\n  tags:\n    - Sports\n    - Sports Data\n    - Football\n    - Soccer\n    - Basketball\n    - American Football\n    - NFL\n    - NBA\n    - Live Scores\n    - Statistics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STATORIUM_API_KEY: STATORIUM_API_KEY\n\ncapability:\n  consumes:\n    - import: statorium-football\n      location: ./shared/football-api.yaml\n    - import: statorium-basketball\n      location: ./shared/basketball-api.yaml\n    - import: statorium-nfl\n      location: ./shared/american-football-api.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: statorium-sports-api\n      description: \"Unified REST API for accessing live sports data across football, basketball, and NFL.\"\n      resources:\n        - path: /v1/leagues\n          name: leagues\n          description: \"Football league listings.\"\n          operations:\n            - method: GET\n              name: list-football-leagues\n              description: \"List all accessible football leagues.\"\n              call: \"statorium-football.list-leagues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/matches\n          name: matches\n          description: \"Football match listings and live scores.\"\n          operations:\n            - method: GET\n              name: list-matches\n              description: \"List football matches filtered by league, date, or status.\"\n              call: \"statorium-football.list-matches\"\
  \n              with:\n                leagueId: \"rest.leagueId\"\n                date: \"rest.date\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/matches/{matchId}\n          name: match\n          description: \"Individual football match details.\"\n          operations:\n            - method: GET\n              name: get-match\n              description: \"Get football match details with lineups and head-to-head.\"\n              call: \"statorium-football.get-match\"\n              with:\n                matchId: \"rest.matchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/standings\n          name: standings\n          description: \"Football league standings.\"\n          operations:\n            - method: GET\n              name: get-standings\n              description: \"Get football\
  \ league standings table.\"\n              call: \"statorium-football.get-standings\"\n              with:\n                leagueId: \"rest.leagueId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/basketball/games\n          name: basketball-games\n          description: \"Basketball game listings.\"\n          operations:\n            - method: GET\n              name: list-basketball-games\n              description: \"List basketball games.\"\n              call: \"statorium-basketball.list-basketball-games\"\n              with:\n                leagueId: \"rest.leagueId\"\n                date: \"rest.date\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nfl/games\n          name: nfl-games\n          description: \"NFL game listings.\"\n          operations:\n            - method: GET\n \
  \             name: list-nfl-games\n              description: \"List NFL games filtered by week, season, or team.\"\n              call: \"statorium-nfl.list-nfl-games\"\n              with:\n                week: \"rest.week\"\n                season: \"rest.season\"\n                teamId: \"rest.teamId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nfl/news\n          name: nfl-news\n          description: \"NFL news feed.\"\n          operations:\n            - method: GET\n              name: list-nfl-news\n              description: \"List latest NFL news.\"\n              call: \"statorium-nfl.list-nfl-news\"\n              with:\n                teamId: \"rest.teamId\"\n                count: \"rest.count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nfl/standings\n          name:\
  \ nfl-standings\n          description: \"NFL standings.\"\n          operations:\n            - method: GET\n              name: get-nfl-standings\n              description: \"Get NFL standings by division.\"\n              call: \"statorium-nfl.get-nfl-standings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: statorium-sports-mcp\n      transport: http\n      description: \"MCP server for AI-assisted access to live sports data across football, basketball, and NFL.\"\n      tools:\n        - name: list-football-leagues\n          description: \"List all accessible football and soccer leagues.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statorium-football.list-leagues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-football-matches\n          description: \"List\
  \ football/soccer matches filtered by league, date, team, or live status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statorium-football.list-matches\"\n          with:\n            leagueId: \"tools.leagueId\"\n            date: \"tools.date\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-football-match\n          description: \"Get full football match details including lineups, events, stats, and head-to-head history.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-football.get-match\"\n          with:\n            matchId: \"tools.matchId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-football-standings\n          description: \"Get the current standings table for a football league.\"\n          hints:\n   \
  \         readOnly: true\n            openWorld: false\n          call: \"statorium-football.get-standings\"\n          with:\n            leagueId: \"tools.leagueId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-football-team\n          description: \"Get football team details including squad and statistics.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-football.get-team\"\n          with:\n            teamId: \"tools.teamId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-football-player\n          description: \"Get football player profile and statistics.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-football.get-player\"\n          with:\n            playerId: \"tools.playerId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-basketball-games\n          description: \"List basketball games filtered by league, date, or status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statorium-basketball.list-basketball-games\"\n          with:\n            leagueId: \"tools.leagueId\"\n            date: \"tools.date\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-basketball-game\n          description: \"Get basketball game box score and quarter-by-quarter breakdown.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-basketball.get-basketball-game\"\n          with:\n            gameId: \"tools.gameId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-basketball-standings\n          description: \"\
  Get basketball league standings.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-basketball.get-basketball-standings\"\n          with:\n            leagueId: \"tools.leagueId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nfl-games\n          description: \"List NFL games filtered by week, season, team, or status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statorium-nfl.list-nfl-games\"\n          with:\n            week: \"tools.week\"\n            season: \"tools.season\"\n            teamId: \"tools.teamId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nfl-game\n          description: \"Get NFL game details including quarter scores and team statistics.\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: false\n          call: \"statorium-nfl.get-nfl-game\"\n          with:\n            gameId: \"tools.gameId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nfl-standings\n          description: \"Get NFL standings by conference and division.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"statorium-nfl.get-nfl-standings\"\n          with:\n            season: \"tools.season\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nfl-news\n          description: \"Get the latest NFL news linked to specific players or teams.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"statorium-nfl.list-nfl-news\"\n          with:\n            teamId: \"tools.teamId\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/statorium/refs/heads/main/capabilities/sports-data.yaml
tags:
- Sports
- Sports Data
- Football
- Soccer
- Basketball
- American Football
- NFL
- NBA
- Live Scores
- Statistics
tools:
- description: List all accessible football and soccer leagues.
  hints:
    openWorld: true
    readOnly: true
  name: list-football-leagues
- description: List football/soccer matches filtered by league, date, team, or live status.
  hints:
    openWorld: true
    readOnly: true
  name: list-football-matches
- description: Get full football match details including lineups, events, stats, and head-to-head history.
  hints:
    openWorld: false
    readOnly: true
  name: get-football-match
- description: Get the current standings table for a football league.
  hints:
    openWorld: false
    readOnly: true
  name: get-football-standings
- description: Get football team details including squad and statistics.
  hints:
    openWorld: false
    readOnly: true
  name: get-football-team
- description: Get football player profile and statistics.
  hints:
    openWorld: false
    readOnly: true
  name: get-football-player
- description: List basketball games filtered by league, date, or status.
  hints:
    openWorld: true
    readOnly: true
  name: list-basketball-games
- description: Get basketball game box score and quarter-by-quarter breakdown.
  hints:
    openWorld: false
    readOnly: true
  name: get-basketball-game
- description: Get basketball league standings.
  hints:
    openWorld: false
    readOnly: true
  name: get-basketball-standings
- description: List NFL games filtered by week, season, team, or status.
  hints:
    openWorld: true
    readOnly: true
  name: list-nfl-games
- description: Get NFL game details including quarter scores and team statistics.
  hints:
    openWorld: false
    readOnly: true
  name: get-nfl-game
- description: Get NFL standings by conference and division.
  hints:
    openWorld: false
    readOnly: true
  name: get-nfl-standings
- description: Get the latest NFL news linked to specific players or teams.
  hints:
    openWorld: true
    readOnly: true
  name: list-nfl-news
---
