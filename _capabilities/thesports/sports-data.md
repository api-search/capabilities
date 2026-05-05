---
categories: []
consumed_apis:
- thesports-football
description: Unified sports data capability for accessing real-time football data including live match tracking, standings, team and player analytics. Used by media platforms, OTT services, and sports analytics applications.
layout: capability
name: TheSports Sports Data
operations:
- description: List all available football competitions
  method: GET
  name: list-competitions
  path: /v1/competitions
- description: Get detailed information about a competition
  method: GET
  name: get-competition-details
  path: /v1/competitions/{competition_id}
- description: List football teams
  method: GET
  name: list-teams
  path: /v1/teams
- description: Get detailed team information
  method: GET
  name: get-team-details
  path: /v1/teams/{team_id}
- description: List players filtered by team
  method: GET
  name: list-players
  path: /v1/players
- description: Get detailed player information and statistics
  method: GET
  name: get-player-details
  path: /v1/players/{player_id}
- description: List matches for a competition or date
  method: GET
  name: list-matches
  path: /v1/matches
- description: Get detailed match information
  method: GET
  name: get-match-details
  path: /v1/matches/{match_id}
- description: Get match starting lineup and substitutes
  method: GET
  name: get-match-lineup
  path: /v1/matches/{match_id}/lineup
- description: Get detailed match statistics
  method: GET
  name: get-match-statistics
  path: /v1/matches/{match_id}/statistics
- description: Get competition standings and league table
  method: GET
  name: get-standings
  path: /v1/standings
personas: []
provider_name: TheSports
provider_slug: thesports
search_terms:
- single competition details
- single team details
- get player details
- get detailed match statistics
- get detailed match information including score and events
- get competition details
- get detailed information about a competition
- get match details
- get detailed match statistics including possession, shots, and passes
- match lineups
- football players
- list all football competitions and leagues available in the api
- get detailed information about a specific football competition
- list football matches for a competition or date
- get detailed player profile and statistics
- analytics
- list players
- data
- list football teams, optionally filtered by competition
- list matches
- get match lineup
- get team details
- esports
- get match starting lineup and substitutes
- single player details
- get match statistics
- tennis
- football match fixtures and results
- basketball
- media
- get match starting lineup and substitutes for both teams
- get standings
- match statistics
- sports
- football teams
- list football teams
- football competitions and leagues
- get detailed information about a specific football team
- list football players, optionally filtered by team
- list teams
- real-time
- single match details
- league standings
- get competition standings and league table
- list all available football competitions
- get detailed match information
- get detailed player information and statistics
- list players filtered by team
- list matches for a competition or date
- get detailed team information
- list competitions
- football
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheSports Sports Data\"\n  description: >-\n    Unified sports data capability for accessing real-time football data\n    including live match tracking, standings, team and player analytics.\n    Used by media platforms, OTT services, and sports analytics applications.\n  tags:\n    - Sports\n    - Football\n    - Real-Time\n    - Analytics\n    - Media\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      THESPORTS_API_KEY: THESPORTS_API_KEY\n\ncapability:\n  consumes:\n    - import: thesports-football\n      location: ./shared/football-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sports-data-api\n      description: \"Unified REST API for real-time sports data.\"\n      resources:\n        - path: /v1/competitions\n          name: competitions\n          description: Football competitions and leagues\n          operations:\n            - method: GET\n\
  \              name: list-competitions\n              description: List all available football competitions\n              call: \"thesports-football.list-competitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/competitions/{competition_id}\n          name: competition-details\n          description: Single competition details\n          operations:\n            - method: GET\n              name: get-competition-details\n              description: Get detailed information about a competition\n              call: \"thesports-football.get-competition-details\"\n              with:\n                competition_id: \"rest.competition_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams\n          name: teams\n          description: Football teams\n          operations:\n            - method: GET\n              name: list-teams\n    \
  \          description: List football teams\n              call: \"thesports-football.list-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams/{team_id}\n          name: team-details\n          description: Single team details\n          operations:\n            - method: GET\n              name: get-team-details\n              description: Get detailed team information\n              call: \"thesports-football.get-team-details\"\n              with:\n                team_id: \"rest.team_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players\n          name: players\n          description: Football players\n          operations:\n            - method: GET\n              name: list-players\n              description: List players filtered by team\n              call: \"thesports-football.list-players\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/players/{player_id}\n          name: player-details\n          description: Single player details\n          operations:\n            - method: GET\n              name: get-player-details\n              description: Get detailed player information and statistics\n              call: \"thesports-football.get-player-details\"\n              with:\n                player_id: \"rest.player_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/matches\n          name: matches\n          description: Football match fixtures and results\n          operations:\n            - method: GET\n              name: list-matches\n              description: List matches for a competition or date\n              call: \"thesports-football.list-matches\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n        - path: /v1/matches/{match_id}\n          name: match-details\n          description: Single match details\n          operations:\n            - method: GET\n              name: get-match-details\n              description: Get detailed match information\n              call: \"thesports-football.get-match-details\"\n              with:\n                match_id: \"rest.match_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/matches/{match_id}/lineup\n          name: match-lineup\n          description: Match lineups\n          operations:\n            - method: GET\n              name: get-match-lineup\n              description: Get match starting lineup and substitutes\n              call: \"thesports-football.get-match-lineup\"\n              with:\n                match_id: \"rest.match_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n \
  \       - path: /v1/matches/{match_id}/statistics\n          name: match-statistics\n          description: Match statistics\n          operations:\n            - method: GET\n              name: get-match-statistics\n              description: Get detailed match statistics\n              call: \"thesports-football.get-match-statistics\"\n              with:\n                match_id: \"rest.match_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/standings\n          name: standings\n          description: League standings\n          operations:\n            - method: GET\n              name: get-standings\n              description: Get competition standings and league table\n              call: \"thesports-football.get-standings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sports-data-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted sports data retrieval and analysis.\"\n      tools:\n        - name: list-competitions\n          description: List all football competitions and leagues available in the API\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.list-competitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-competition-details\n          description: Get detailed information about a specific football competition\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-competition-details\"\n          with:\n            competition_id: \"tools.competition_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-teams\n          description: List football teams, optionally filtered by competition\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"thesports-football.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-details\n          description: Get detailed information about a specific football team\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-team-details\"\n          with:\n            team_id: \"tools.team_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-players\n          description: List football players, optionally filtered by team\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.list-players\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-player-details\n          description: Get detailed player profile and\
  \ statistics\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-player-details\"\n          with:\n            player_id: \"tools.player_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-matches\n          description: List football matches for a competition or date\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.list-matches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-match-details\n          description: Get detailed match information including score and events\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-match-details\"\n          with:\n            match_id: \"tools.match_id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-match-lineup\n          description: Get match starting lineup and substitutes for both teams\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-match-lineup\"\n          with:\n            match_id: \"tools.match_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-match-statistics\n          description: Get detailed match statistics including possession, shots, and passes\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"thesports-football.get-match-statistics\"\n          with:\n            match_id: \"tools.match_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-standings\n          description: Get competition standings and league table\n          hints:\n            readOnly: true\n            openWorld: true\n       \
  \   call: \"thesports-football.get-standings\"\n          with:\n            competition_id: \"tools.competition_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thesports/refs/heads/main/capabilities/sports-data.yaml
tags:
- Sports
- Football
- Real-Time
- Analytics
- Media
tools:
- description: List all football competitions and leagues available in the API
  hints:
    openWorld: true
    readOnly: true
  name: list-competitions
- description: Get detailed information about a specific football competition
  hints:
    openWorld: true
    readOnly: true
  name: get-competition-details
- description: List football teams, optionally filtered by competition
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Get detailed information about a specific football team
  hints:
    openWorld: true
    readOnly: true
  name: get-team-details
- description: List football players, optionally filtered by team
  hints:
    openWorld: true
    readOnly: true
  name: list-players
- description: Get detailed player profile and statistics
  hints:
    openWorld: true
    readOnly: true
  name: get-player-details
- description: List football matches for a competition or date
  hints:
    openWorld: true
    readOnly: true
  name: list-matches
- description: Get detailed match information including score and events
  hints:
    openWorld: true
    readOnly: true
  name: get-match-details
- description: Get match starting lineup and substitutes for both teams
  hints:
    openWorld: true
    readOnly: true
  name: get-match-lineup
- description: Get detailed match statistics including possession, shots, and passes
  hints:
    openWorld: true
    readOnly: true
  name: get-match-statistics
- description: Get competition standings and league table
  hints:
    openWorld: true
    readOnly: true
  name: get-standings
---
