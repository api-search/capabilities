---
api_specs:
- filename: sportradar-sports-data-openapi.yml
  format: yaml
  label: sportradar-data
  slug: sportradar-data
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sportradar/refs/heads/main/openapi/sportradar-sports-data-openapi.yml
categories: []
consumed_apis:
- sportradar-data
description: Unified capability for accessing Sportradar's comprehensive sports data across major leagues and sports. Combines NBA, NFL, and soccer data feeds into a single workflow for sports media platforms, fantasy sports applications, betting platforms, and sports analytics tools. Provides game schedules, live scores, standings, player profiles, and match summaries.
layout: capability
name: Sportradar Sports Data Intelligence
operations:
- description: Get the NBA schedule for a specific date.
  method: GET
  name: get-nba-daily-schedule
  path: /v1/nba/schedules/{date}
- description: Get complete NBA game summary.
  method: GET
  name: get-nba-game-summary
  path: /v1/nba/games/{game_id}
- description: Get NBA standings for a season.
  method: GET
  name: get-nba-standings
  path: /v1/nba/standings/{season_year}
- description: Get an NBA player's profile and statistics.
  method: GET
  name: get-nba-player-profile
  path: /v1/nba/players/{player_id}
- description: Get complete NFL game summary.
  method: GET
  name: get-nfl-game-summary
  path: /v1/nfl/games/{game_id}
- description: Get soccer competition details.
  method: GET
  name: get-soccer-competition-info
  path: /v1/soccer/competitions/{competition_id}
- description: Get soccer match summary with timeline and lineups.
  method: GET
  name: get-soccer-match-summary
  path: /v1/soccer/matches/{sport_event_id}
personas: []
provider_name: Sportradar
provider_slug: sportradar
search_terms:
- get nba standings for a season.
- get soccer match summary with timeline and lineups.
- get complete nfl game summary with play-by-play drives and statistics.
- get nba game summary
- get complete nfl game summary.
- sports data
- data
- nba league standings.
- get soccer competition info
- get nba standings
- get the nba schedule for a specific date.
- soccer competition information.
- esports
- get nba player profile
- get complete nba game summary.
- statistics
- get soccer match summary
- nfl game summaries.
- get nba daily schedule
- media
- get an nba player's profile and statistics.
- soccer match summaries.
- nba player profiles.
- fantasy sports
- get nba schedule
- sports
- get soccer competition details.
- get career statistics and biographical info for an nba player.
- get nfl game summary
- get a soccer match summary including scoreline, timeline, lineups, and incidents.
- real-time
- nba game schedules by date.
- get details about a soccer league or competition by sportradar competition id.
- nba game summaries and box scores.
- 'get the nba game schedule for a specific date (format: yyyy/mm/dd).'
- get current nba league standings by season year.
- get complete nba game box score and statistics by game id.
slug: sports-data-intelligence
source_filename: sports-data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sportradar Sports Data Intelligence\"\n  description: >-\n    Unified capability for accessing Sportradar's comprehensive sports data\n    across major leagues and sports. Combines NBA, NFL, and soccer data feeds\n    into a single workflow for sports media platforms, fantasy sports applications,\n    betting platforms, and sports analytics tools. Provides game schedules, live\n    scores, standings, player profiles, and match summaries.\n  tags:\n    - Sports\n    - Sports Data\n    - Real-Time\n    - Statistics\n    - Fantasy Sports\n    - Media\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPORTRADAR_API_KEY: SPORTRADAR_API_KEY\n\ncapability:\n  consumes:\n    - import: sportradar-data\n      location: ./shared/sportradar-sports-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sportradar-intelligence-api\n      description: \"Unified REST API\
  \ for Sportradar sports data intelligence.\"\n      resources:\n        - path: /v1/nba/schedules/{date}\n          name: nba-schedules\n          description: \"NBA game schedules by date.\"\n          operations:\n            - method: GET\n              name: get-nba-daily-schedule\n              description: \"Get the NBA schedule for a specific date.\"\n              call: \"sportradar-data.get-nba-daily-schedule\"\n              with:\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nba/games/{game_id}\n          name: nba-games\n          description: \"NBA game summaries and box scores.\"\n          operations:\n            - method: GET\n              name: get-nba-game-summary\n              description: \"Get complete NBA game summary.\"\n              call: \"sportradar-data.get-nba-game-summary\"\n              with:\n                game_id: \"rest.game_id\"\n  \
  \            outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nba/standings/{season_year}\n          name: nba-standings\n          description: \"NBA league standings.\"\n          operations:\n            - method: GET\n              name: get-nba-standings\n              description: \"Get NBA standings for a season.\"\n              call: \"sportradar-data.get-nba-standings\"\n              with:\n                season_year: \"rest.season_year\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nba/players/{player_id}\n          name: nba-players\n          description: \"NBA player profiles.\"\n          operations:\n            - method: GET\n              name: get-nba-player-profile\n              description: \"Get an NBA player's profile and statistics.\"\n              call: \"sportradar-data.get-nba-player-profile\"\n              with:\n    \
  \            player_id: \"rest.player_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nfl/games/{game_id}\n          name: nfl-games\n          description: \"NFL game summaries.\"\n          operations:\n            - method: GET\n              name: get-nfl-game-summary\n              description: \"Get complete NFL game summary.\"\n              call: \"sportradar-data.get-nfl-game-summary\"\n              with:\n                game_id: \"rest.game_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/soccer/competitions/{competition_id}\n          name: soccer-competitions\n          description: \"Soccer competition information.\"\n          operations:\n            - method: GET\n              name: get-soccer-competition-info\n              description: \"Get soccer competition details.\"\n              call: \"sportradar-data.get-soccer-competition-info\"\
  \n              with:\n                competition_id: \"rest.competition_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/soccer/matches/{sport_event_id}\n          name: soccer-matches\n          description: \"Soccer match summaries.\"\n          operations:\n            - method: GET\n              name: get-soccer-match-summary\n              description: \"Get soccer match summary with timeline and lineups.\"\n              call: \"sportradar-data.get-soccer-match-summary\"\n              with:\n                sport_event_id: \"rest.sport_event_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sportradar-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports data analysis and reporting.\"\n      tools:\n        - name: get-nba-schedule\n          description:\
  \ \"Get the NBA game schedule for a specific date (format: YYYY/MM/DD).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-nba-daily-schedule\"\n          with:\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nba-game-summary\n          description: \"Get complete NBA game box score and statistics by game ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-nba-game-summary\"\n          with:\n            game_id: \"tools.game_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nba-standings\n          description: \"Get current NBA league standings by season year.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-nba-standings\"\n\
  \          with:\n            season_year: \"tools.season_year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nba-player-profile\n          description: \"Get career statistics and biographical info for an NBA player.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-nba-player-profile\"\n          with:\n            player_id: \"tools.player_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nfl-game-summary\n          description: \"Get complete NFL game summary with play-by-play drives and statistics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-nfl-game-summary\"\n          with:\n            game_id: \"tools.game_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n       \
  \ - name: get-soccer-competition-info\n          description: \"Get details about a soccer league or competition by Sportradar competition ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-soccer-competition-info\"\n          with:\n            competition_id: \"tools.competition_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-soccer-match-summary\n          description: \"Get a soccer match summary including scoreline, timeline, lineups, and incidents.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportradar-data.get-soccer-match-summary\"\n          with:\n            sport_event_id: \"tools.sport_event_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sportradar/refs/heads/main/capabilities/sports-data-intelligence.yaml
tags:
- Sports
- Sports Data
- Real-Time
- Statistics
- Fantasy Sports
- Media
tools:
- description: 'Get the NBA game schedule for a specific date (format: YYYY/MM/DD).'
  hints:
    idempotent: true
    readOnly: true
  name: get-nba-schedule
- description: Get complete NBA game box score and statistics by game ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-nba-game-summary
- description: Get current NBA league standings by season year.
  hints:
    idempotent: true
    readOnly: true
  name: get-nba-standings
- description: Get career statistics and biographical info for an NBA player.
  hints:
    idempotent: true
    readOnly: true
  name: get-nba-player-profile
- description: Get complete NFL game summary with play-by-play drives and statistics.
  hints:
    idempotent: true
    readOnly: true
  name: get-nfl-game-summary
- description: Get details about a soccer league or competition by Sportradar competition ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-soccer-competition-info
- description: Get a soccer match summary including scoreline, timeline, lineups, and incidents.
  hints:
    idempotent: true
    readOnly: true
  name: get-soccer-match-summary
---
