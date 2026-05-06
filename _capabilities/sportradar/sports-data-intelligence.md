---
categories: []
consumed_apis: []
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
- sports data
- real-time
- sports
- soccer competition information.
- nba league standings.
- get complete nfl game summary.
- get nfl game summary
- get the nba schedule for a specific date.
- get soccer match summary
- get nba standings
- get nba game summary
- soccer match summaries.
- get soccer competition details.
- get an nba player's profile and statistics.
- fantasy sports
- get complete nba game box score and statistics by game id.
- get complete nba game summary.
- get soccer competition info
- 'get the nba game schedule for a specific date (format: yyyy/mm/dd).'
- get nba daily schedule
- media
- nba game schedules by date.
- nfl game summaries.
- nba game summaries and box scores.
- get nba schedule
- get nba standings for a season.
- get details about a soccer league or competition by sportradar competition id.
- get soccer match summary with timeline and lineups.
- data
- get current nba league standings by season year.
- get a soccer match summary including scoreline, timeline, lineups, and incidents.
- get nba player profile
- get career statistics and biographical info for an nba player.
- esports
- nba player profiles.
- statistics
- get complete nfl game summary with play-by-play drives and statistics.
slug: sports-data-intelligence
source_filename: sports-data-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sportradar Sports Data Intelligence\n  description: Unified capability for accessing Sportradar's comprehensive sports data across major leagues and sports. Combines\n    NBA, NFL, and soccer data feeds into a single workflow for sports media platforms, fantasy sports applications, betting\n    platforms, and sports analytics tools. Provides game schedules, live scores, standings, player profiles, and match summaries.\n  tags:\n  - Sports\n  - Sports Data\n  - Real-Time\n  - Statistics\n  - Fantasy Sports\n  - Media\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPORTRADAR_API_KEY: SPORTRADAR_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sportradar-data\n    baseUri: https://api.sportradar.com\n    description: Sportradar Sports Data API.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{SPORTRADAR_API_KEY}}'\n      placement: query\n    resources:\n\
  \    - name: nba-schedules\n      path: /nba/trial/v8/en/games/{date}/schedule.json\n      description: NBA daily schedule.\n      operations:\n      - name: get-nba-daily-schedule\n        method: GET\n        description: Retrieve the NBA game schedule for a specific date.\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: Date in YYYY/MM/DD format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nba-games\n      path: /nba/trial/v8/en/games/{game_id}/summary.json\n      description: NBA game summaries.\n      operations:\n      - name: get-nba-game-summary\n        method: GET\n        description: Retrieve a complete NBA game summary including box score and statistics.\n        inputParameters:\n        - name: game_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Unique NBA game identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nba-standings\n      path: /nba/trial/v8/en/seasons/{season_year}/REG/standings.json\n      description: NBA standings.\n      operations:\n      - name: get-nba-standings\n        method: GET\n        description: Retrieve current NBA standings for the specified season.\n        inputParameters:\n        - name: season_year\n          in: path\n          type: string\n          required: true\n          description: Season year (e.g., 2024).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nba-players\n      path: /nba/trial/v8/en/players/{player_id}/profile.json\n      description: NBA player profiles.\n      operations:\n      - name: get-nba-player-profile\n        method: GET\n        description: Retrieve biographical and statistical\
  \ profile for an NBA player.\n        inputParameters:\n        - name: player_id\n          in: path\n          type: string\n          required: true\n          description: Unique Sportradar player identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfl-games\n      path: /nfl/trial/v7/en/games/{game_id}/summary.json\n      description: NFL game summaries.\n      operations:\n      - name: get-nfl-game-summary\n        method: GET\n        description: Retrieve a complete NFL game summary including drives and statistics.\n        inputParameters:\n        - name: game_id\n          in: path\n          type: string\n          required: true\n          description: Unique NFL game identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: soccer-competitions\n      path: /soccer-t3/trial/v4/en/competitions/{competition_id}/info.json\n\
  \      description: Soccer competition information.\n      operations:\n      - name: get-soccer-competition-info\n        method: GET\n        description: Retrieve information about a soccer competition.\n        inputParameters:\n        - name: competition_id\n          in: path\n          type: string\n          required: true\n          description: Competition URN (e.g., sr:competition:17 for Premier League).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: soccer-matches\n      path: /soccer-t3/trial/v4/en/sport_events/{sport_event_id}/summary.json\n      description: Soccer match summaries.\n      operations:\n      - name: get-soccer-match-summary\n        method: GET\n        description: Retrieve a detailed soccer match summary including timeline and lineups.\n        inputParameters:\n        - name: sport_event_id\n          in: path\n          type: string\n          required: true\n\
  \          description: Sport event URN (e.g., sr:match:12345).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sportradar-intelligence-api\n    description: Unified REST API for Sportradar sports data intelligence.\n    resources:\n    - path: /v1/nba/schedules/{date}\n      name: nba-schedules\n      description: NBA game schedules by date.\n      operations:\n      - method: GET\n        name: get-nba-daily-schedule\n        description: Get the NBA schedule for a specific date.\n        call: sportradar-data.get-nba-daily-schedule\n        with:\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nba/games/{game_id}\n      name: nba-games\n      description: NBA game summaries and box scores.\n      operations:\n      - method: GET\n        name: get-nba-game-summary\n        description:\
  \ Get complete NBA game summary.\n        call: sportradar-data.get-nba-game-summary\n        with:\n          game_id: rest.game_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nba/standings/{season_year}\n      name: nba-standings\n      description: NBA league standings.\n      operations:\n      - method: GET\n        name: get-nba-standings\n        description: Get NBA standings for a season.\n        call: sportradar-data.get-nba-standings\n        with:\n          season_year: rest.season_year\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nba/players/{player_id}\n      name: nba-players\n      description: NBA player profiles.\n      operations:\n      - method: GET\n        name: get-nba-player-profile\n        description: Get an NBA player's profile and statistics.\n        call: sportradar-data.get-nba-player-profile\n        with:\n          player_id: rest.player_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/nfl/games/{game_id}\n      name: nfl-games\n      description: NFL game summaries.\n      operations:\n      - method: GET\n        name: get-nfl-game-summary\n        description: Get complete NFL game summary.\n        call: sportradar-data.get-nfl-game-summary\n        with:\n          game_id: rest.game_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/soccer/competitions/{competition_id}\n      name: soccer-competitions\n      description: Soccer competition information.\n      operations:\n      - method: GET\n        name: get-soccer-competition-info\n        description: Get soccer competition details.\n        call: sportradar-data.get-soccer-competition-info\n        with:\n          competition_id: rest.competition_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/soccer/matches/{sport_event_id}\n      name: soccer-matches\n\
  \      description: Soccer match summaries.\n      operations:\n      - method: GET\n        name: get-soccer-match-summary\n        description: Get soccer match summary with timeline and lineups.\n        call: sportradar-data.get-soccer-match-summary\n        with:\n          sport_event_id: rest.sport_event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sportradar-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted sports data analysis and reporting.\n    tools:\n    - name: get-nba-schedule\n      description: 'Get the NBA game schedule for a specific date (format: YYYY/MM/DD).'\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-nba-daily-schedule\n      with:\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nba-game-summary\n      description: Get complete NBA game box\
  \ score and statistics by game ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-nba-game-summary\n      with:\n        game_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nba-standings\n      description: Get current NBA league standings by season year.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-nba-standings\n      with:\n        season_year: tools.season_year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nba-player-profile\n      description: Get career statistics and biographical info for an NBA player.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-nba-player-profile\n      with:\n        player_id: tools.player_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nfl-game-summary\n      description:\
  \ Get complete NFL game summary with play-by-play drives and statistics.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-nfl-game-summary\n      with:\n        game_id: tools.game_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-soccer-competition-info\n      description: Get details about a soccer league or competition by Sportradar competition ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-soccer-competition-info\n      with:\n        competition_id: tools.competition_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-soccer-match-summary\n      description: Get a soccer match summary including scoreline, timeline, lineups, and incidents.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportradar-data.get-soccer-match-summary\n      with:\n        sport_event_id: tools.sport_event_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
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
