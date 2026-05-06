---
categories: []
consumed_apis: []
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
- get match details
- list football matches for a competition or date
- football competitions and leagues
- real-time
- single match details
- sports
- get detailed match statistics
- list football teams, optionally filtered by competition
- football
- basketball
- list matches for a competition or date
- list competitions
- analytics
- get detailed team information
- get competition details
- get match starting lineup and substitutes
- single player details
- get detailed match information
- get match lineup
- single team details
- get standings
- get detailed information about a competition
- list teams
- get detailed information about a specific football competition
- get detailed match statistics including possession, shots, and passes
- get team details
- get detailed match information including score and events
- list players
- list matches
- list all available football competitions
- single competition details
- get player details
- football match fixtures and results
- match statistics
- get detailed player profile and statistics
- get match statistics
- list players filtered by team
- get detailed information about a specific football team
- media
- football players
- league standings
- get match starting lineup and substitutes for both teams
- get detailed player information and statistics
- tennis
- data
- football teams
- list football players, optionally filtered by team
- list all football competitions and leagues available in the api
- esports
- get competition standings and league table
- list football teams
- match lineups
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TheSports Sports Data\n  description: Unified sports data capability for accessing real-time football data including live match tracking, standings,\n    team and player analytics. Used by media platforms, OTT services, and sports analytics applications.\n  tags:\n  - Sports\n  - Football\n  - Real-Time\n  - Analytics\n  - Media\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    THESPORTS_API_KEY: THESPORTS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: thesports-football\n    baseUri: https://api.thesports.com/v1\n    description: TheSports Football API providing real-time sports data.\n    authentication:\n      type: apikey\n      key: user_key\n      value: '{{THESPORTS_API_KEY}}'\n      placement: query\n    resources:\n    - name: competitions\n      path: /football/competition\n      description: Football competitions and league data\n      operations:\n      - name: list-competitions\n\
  \        method: GET\n        description: List all football competitions\n        inputParameters:\n        - name: country_id\n          in: query\n          type: string\n          required: false\n          description: Filter by country ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-competition-details\n        method: GET\n        description: Get detailed information about a competition\n        inputParameters:\n        - name: competition_id\n          in: query\n          type: string\n          required: true\n          description: The competition ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /football/team\n      description: Football team data\n      operations:\n      - name: list-teams\n        method: GET\n        description: List football teams\n      \
  \  inputParameters:\n        - name: competition_id\n          in: query\n          type: string\n          required: false\n          description: Filter by competition ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team-details\n        method: GET\n        description: Get detailed information about a team\n        inputParameters:\n        - name: team_id\n          in: query\n          type: string\n          required: true\n          description: The team ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: players\n      path: /football/player\n      description: Football player data\n      operations:\n      - name: list-players\n        method: GET\n        description: List players optionally filtered by team\n        inputParameters:\n        - name: team_id\n          in: query\n     \
  \     type: string\n          required: false\n          description: Filter by team ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-player-details\n        method: GET\n        description: Get detailed player information and statistics\n        inputParameters:\n        - name: player_id\n          in: query\n          type: string\n          required: true\n          description: The player ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matches\n      path: /football/match\n      description: Football match fixtures and results\n      operations:\n      - name: list-matches\n        method: GET\n        description: List matches for a competition or date\n        inputParameters:\n        - name: competition_id\n          in: query\n          type: string\n          required: false\n     \
  \     description: Filter by competition ID\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Filter by date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-match-details\n        method: GET\n        description: Get detailed match information\n        inputParameters:\n        - name: match_id\n          in: query\n          type: string\n          required: true\n          description: The match ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-match-lineup\n        method: GET\n        description: Get match lineup and substitutes\n        inputParameters:\n        - name: match_id\n          in: query\n          type: string\n          required: true\n          description: The match ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-match-statistics\n        method: GET\n        description: Get detailed match statistics\n        inputParameters:\n        - name: match_id\n          in: query\n          type: string\n          required: true\n          description: The match ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: standings\n      path: /football/standings\n      description: League tables and competition standings\n      operations:\n      - name: get-standings\n        method: GET\n        description: Get league standings for a competition\n        inputParameters:\n        - name: competition_id\n          in: query\n          type: string\n          required: true\n          description: The competition ID\n        - name: season_id\n          in: query\n          type: string\n         \
  \ required: false\n          description: The season ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sports-data-api\n    description: Unified REST API for real-time sports data.\n    resources:\n    - path: /v1/competitions\n      name: competitions\n      description: Football competitions and leagues\n      operations:\n      - method: GET\n        name: list-competitions\n        description: List all available football competitions\n        call: thesports-football.list-competitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/competitions/{competition_id}\n      name: competition-details\n      description: Single competition details\n      operations:\n      - method: GET\n        name: get-competition-details\n        description: Get detailed information about a competition\n        call: thesports-football.get-competition-details\n\
  \        with:\n          competition_id: rest.competition_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams\n      name: teams\n      description: Football teams\n      operations:\n      - method: GET\n        name: list-teams\n        description: List football teams\n        call: thesports-football.list-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{team_id}\n      name: team-details\n      description: Single team details\n      operations:\n      - method: GET\n        name: get-team-details\n        description: Get detailed team information\n        call: thesports-football.get-team-details\n        with:\n          team_id: rest.team_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players\n      name: players\n      description: Football players\n      operations:\n      - method: GET\n        name: list-players\n        description:\
  \ List players filtered by team\n        call: thesports-football.list-players\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{player_id}\n      name: player-details\n      description: Single player details\n      operations:\n      - method: GET\n        name: get-player-details\n        description: Get detailed player information and statistics\n        call: thesports-football.get-player-details\n        with:\n          player_id: rest.player_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches\n      name: matches\n      description: Football match fixtures and results\n      operations:\n      - method: GET\n        name: list-matches\n        description: List matches for a competition or date\n        call: thesports-football.list-matches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches/{match_id}\n      name: match-details\n \
  \     description: Single match details\n      operations:\n      - method: GET\n        name: get-match-details\n        description: Get detailed match information\n        call: thesports-football.get-match-details\n        with:\n          match_id: rest.match_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches/{match_id}/lineup\n      name: match-lineup\n      description: Match lineups\n      operations:\n      - method: GET\n        name: get-match-lineup\n        description: Get match starting lineup and substitutes\n        call: thesports-football.get-match-lineup\n        with:\n          match_id: rest.match_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches/{match_id}/statistics\n      name: match-statistics\n      description: Match statistics\n      operations:\n      - method: GET\n        name: get-match-statistics\n        description: Get detailed match statistics\n\
  \        call: thesports-football.get-match-statistics\n        with:\n          match_id: rest.match_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/standings\n      name: standings\n      description: League standings\n      operations:\n      - method: GET\n        name: get-standings\n        description: Get competition standings and league table\n        call: thesports-football.get-standings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sports-data-mcp\n    transport: http\n    description: MCP server for AI-assisted sports data retrieval and analysis.\n    tools:\n    - name: list-competitions\n      description: List all football competitions and leagues available in the API\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.list-competitions\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: get-competition-details\n      description: Get detailed information about a specific football competition\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.get-competition-details\n      with:\n        competition_id: tools.competition_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List football teams, optionally filtered by competition\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.list-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-details\n      description: Get detailed information about a specific football team\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.get-team-details\n      with:\n        team_id: tools.team_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-players\n    \
  \  description: List football players, optionally filtered by team\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.list-players\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player-details\n      description: Get detailed player profile and statistics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.get-player-details\n      with:\n        player_id: tools.player_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-matches\n      description: List football matches for a competition or date\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.list-matches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-match-details\n      description: Get detailed match information including score and events\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: thesports-football.get-match-details\n      with:\n        match_id: tools.match_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-match-lineup\n      description: Get match starting lineup and substitutes for both teams\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.get-match-lineup\n      with:\n        match_id: tools.match_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-match-statistics\n      description: Get detailed match statistics including possession, shots, and passes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: thesports-football.get-match-statistics\n      with:\n        match_id: tools.match_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-standings\n      description: Get competition standings and league table\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: thesports-football.get-standings\n      with:\n        competition_id: tools.competition_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
