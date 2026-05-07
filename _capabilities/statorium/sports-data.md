---
categories: []
consumed_apis: []
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
- get nfl standings by division.
- sports data
- get nfl game details including quarter scores and team statistics.
- list nfl games filtered by week, season, or team.
- nfl news feed.
- list latest nfl news.
- get football league standings table.
- get match
- football league standings.
- get full football match details including lineups, events, stats, and head-to-head history.
- get football match
- get standings
- list nfl news
- get basketball standings
- get football team
- football match listings and live scores.
- list football/soccer matches filtered by league, date, team, or live status.
- get nfl standings
- get basketball game box score and quarter-by-quarter breakdown.
- get football standings
- individual football match details.
- nfl game listings.
- list nfl games filtered by week, season, team, or status.
- football league listings.
- list matches
- get nfl game
- get basketball league standings.
- american football
- list football matches
- list football leagues
- list all accessible football leagues.
- get football player
- list football matches filtered by league, date, or status.
- football
- list basketball games.
- sports
- soccer
- get the current standings table for a football league.
- list basketball games
- live scores
- statistics
- get football match details with lineups and head-to-head.
- list all accessible football and soccer leagues.
- get football team details including squad and statistics.
- nfl standings.
- get basketball game
- basketball
- nfl
- get nfl standings by conference and division.
- get the latest nfl news linked to specific players or teams.
- get football player profile and statistics.
- list basketball games filtered by league, date, or status.
- list nfl games
- nba
- basketball game listings.
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Statorium Sports Data\n  description: Unified sports data capability combining Statorium's Football, Basketball, and American Football APIs into\n    a single workflow. Enables sports platforms, fantasy sports apps, and media publishers to access live scores, standings,\n    match details, and news across all sports from a single integration.\n  tags:\n  - Sports\n  - Sports Data\n  - Football\n  - Soccer\n  - Basketball\n  - American Football\n  - NFL\n  - NBA\n  - Live Scores\n  - Statistics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STATORIUM_API_KEY: STATORIUM_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: statorium-football\n    baseUri: https://api.statorium.com/api/v1\n    description: Statorium Football API providing comprehensive football data including live scores, standings, and player\n      statistics.\n    authentication:\n      type: apikey\n      key: apikey\n\
  \      value: '{{STATORIUM_API_KEY}}'\n      placement: query\n    resources:\n    - name: leagues\n      path: /leagues/\n      description: Football leagues and competitions.\n      operations:\n      - name: list-leagues\n        method: GET\n        description: Returns all football leagues the account has permission to access.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-league\n        method: GET\n        description: Returns a specific football league by ID.\n        inputParameters:\n        - name: leagueId\n          in: path\n          type: integer\n          required: true\n          description: League identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: seasons\n      path: /seasons/\n      description: Football seasons.\n      operations:\n      - name: list-seasons\n    \
  \    method: GET\n        description: Returns all seasons, optionally filtered by league.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: false\n          description: Filter by league ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: matches\n      path: /matches/\n      description: Football matches and live scores.\n      operations:\n      - name: list-matches\n        method: GET\n        description: Returns matches filtered by league, season, team, or date.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: false\n          description: Filter by league ID.\n        - name: seasonId\n          in: query\n          type: integer\n          required: false\n          description: Filter by season ID.\n        - name: teamId\n          in: query\n    \
  \      type: integer\n          required: false\n          description: Filter by team ID.\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Filter by date (YYYY-MM-DD).\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: live, scheduled, finished.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-match\n        method: GET\n        description: Returns full match details including lineups, events, and head-to-head.\n        inputParameters:\n        - name: matchId\n          in: path\n          type: integer\n          required: true\n          description: Match identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams/\n\
  \      description: Football teams.\n      operations:\n      - name: list-teams\n        method: GET\n        description: Returns teams filtered by league or season.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: false\n          description: Filter by league ID.\n        - name: seasonId\n          in: query\n          type: integer\n          required: false\n          description: Filter by season ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team\n        method: GET\n        description: Returns detailed team information and squad.\n        inputParameters:\n        - name: teamId\n          in: path\n          type: integer\n          required: true\n          description: Team identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: players\n      path: /players/\n      description: Football players.\n      operations:\n      - name: get-player\n        method: GET\n        description: Returns player profile and statistics.\n        inputParameters:\n        - name: playerId\n          in: path\n          type: integer\n          required: true\n          description: Player identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: standings\n      path: /standings/\n      description: Football league standings.\n      operations:\n      - name: get-standings\n        method: GET\n        description: Returns league standings table.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: true\n          description: League identifier.\n        - name: seasonId\n          in: query\n          type: integer\n          required: false\n\
  \          description: Season identifier (defaults to current).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: statorium-basketball\n    baseUri: https://api.statorium.com/api/v1\n    description: Statorium Basketball API for NBA and international basketball data.\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{STATORIUM_API_KEY}}'\n      placement: query\n    resources:\n    - name: basketball-leagues\n      path: /basketball/leagues/\n      description: Basketball leagues.\n      operations:\n      - name: list-basketball-leagues\n        method: GET\n        description: Returns all accessible basketball leagues.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: basketball-games\n      path: /basketball/games/\n      description: Basketball games.\n     \
  \ operations:\n      - name: list-basketball-games\n        method: GET\n        description: Returns basketball games with filtering.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: false\n          description: Filter by league ID.\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Filter by date.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-basketball-game\n        method: GET\n        description: Returns full game details including quarter scores and player stats.\n        inputParameters:\n        - name: gameId\n          in: path\n          type: integer\n          required: true\n          description: Game\
  \ identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: basketball-standings\n      path: /basketball/standings/\n      description: Basketball standings.\n      operations:\n      - name: get-basketball-standings\n        method: GET\n        description: Returns basketball league standings.\n        inputParameters:\n        - name: leagueId\n          in: query\n          type: integer\n          required: true\n          description: League identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: statorium-nfl\n    baseUri: https://api.statorium.com/api/v1\n    description: Statorium American Football (NFL) API.\n    authentication:\n      type: apikey\n      key: apikey\n      value: '{{STATORIUM_API_KEY}}'\n      placement: query\n    resources:\n    - name: nfl-games\n \
  \     path: /nfl/games/\n      description: NFL games.\n      operations:\n      - name: list-nfl-games\n        method: GET\n        description: Returns NFL games filtered by week, season, team, or status.\n        inputParameters:\n        - name: week\n          in: query\n          type: integer\n          required: false\n          description: NFL week number.\n        - name: season\n          in: query\n          type: integer\n          required: false\n          description: Season year.\n        - name: teamId\n          in: query\n          type: integer\n          required: false\n          description: Filter by team.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-nfl-game\n        method: GET\n        description: Returns full NFL game details.\n\
  \        inputParameters:\n        - name: gameId\n          in: path\n          type: integer\n          required: true\n          description: Game identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfl-teams\n      path: /nfl/teams/\n      description: NFL teams.\n      operations:\n      - name: list-nfl-teams\n        method: GET\n        description: Returns all NFL teams.\n        inputParameters:\n        - name: conference\n          in: query\n          type: string\n          required: false\n          description: Filter by conference (AFC, NFC).\n        - name: division\n          in: query\n          type: string\n          required: false\n          description: Filter by division.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfl-standings\n      path: /nfl/standings/\n      description:\
  \ NFL standings.\n      operations:\n      - name: get-nfl-standings\n        method: GET\n        description: Returns NFL standings by division.\n        inputParameters:\n        - name: season\n          in: query\n          type: integer\n          required: false\n          description: Season year.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nfl-news\n      path: /nfl/news/\n      description: NFL news.\n      operations:\n      - name: list-nfl-news\n        method: GET\n        description: Returns NFL news articles linked to players and teams.\n        inputParameters:\n        - name: teamId\n          in: query\n          type: integer\n          required: false\n          description: Filter by team.\n        - name: playerId\n          in: query\n          type: integer\n          required: false\n          description: Filter by player.\n        - name: count\n          in: query\n\
  \          type: integer\n          required: false\n          description: Number of items to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: statorium-sports-api\n    description: Unified REST API for accessing live sports data across football, basketball, and NFL.\n    resources:\n    - path: /v1/leagues\n      name: leagues\n      description: Football league listings.\n      operations:\n      - method: GET\n        name: list-football-leagues\n        description: List all accessible football leagues.\n        call: statorium-football.list-leagues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches\n      name: matches\n      description: Football match listings and live scores.\n      operations:\n      - method: GET\n        name: list-matches\n        description: List football matches\
  \ filtered by league, date, or status.\n        call: statorium-football.list-matches\n        with:\n          leagueId: rest.leagueId\n          date: rest.date\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matches/{matchId}\n      name: match\n      description: Individual football match details.\n      operations:\n      - method: GET\n        name: get-match\n        description: Get football match details with lineups and head-to-head.\n        call: statorium-football.get-match\n        with:\n          matchId: rest.matchId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/standings\n      name: standings\n      description: Football league standings.\n      operations:\n      - method: GET\n        name: get-standings\n        description: Get football league standings table.\n        call: statorium-football.get-standings\n        with:\n          leagueId: rest.leagueId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/basketball/games\n      name: basketball-games\n      description: Basketball game listings.\n      operations:\n      - method: GET\n        name: list-basketball-games\n        description: List basketball games.\n        call: statorium-basketball.list-basketball-games\n        with:\n          leagueId: rest.leagueId\n          date: rest.date\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nfl/games\n      name: nfl-games\n      description: NFL game listings.\n      operations:\n      - method: GET\n        name: list-nfl-games\n        description: List NFL games filtered by week, season, or team.\n        call: statorium-nfl.list-nfl-games\n        with:\n          week: rest.week\n          season: rest.season\n          teamId: rest.teamId\n          status: rest.status\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/nfl/news\n      name: nfl-news\n      description: NFL news feed.\n      operations:\n      - method: GET\n        name: list-nfl-news\n        description: List latest NFL news.\n        call: statorium-nfl.list-nfl-news\n        with:\n          teamId: rest.teamId\n          count: rest.count\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nfl/standings\n      name: nfl-standings\n      description: NFL standings.\n      operations:\n      - method: GET\n        name: get-nfl-standings\n        description: Get NFL standings by division.\n        call: statorium-nfl.get-nfl-standings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: statorium-sports-mcp\n    transport: http\n    description: MCP server for AI-assisted access to live sports data across football, basketball, and NFL.\n    tools:\n    - name: list-football-leagues\n\
  \      description: List all accessible football and soccer leagues.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: statorium-football.list-leagues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-football-matches\n      description: List football/soccer matches filtered by league, date, team, or live status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: statorium-football.list-matches\n      with:\n        leagueId: tools.leagueId\n        date: tools.date\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-football-match\n      description: Get full football match details including lineups, events, stats, and head-to-head history.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-football.get-match\n      with:\n        matchId: tools.matchId\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-football-standings\n      description: Get the current standings table for a football league.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-football.get-standings\n      with:\n        leagueId: tools.leagueId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-football-team\n      description: Get football team details including squad and statistics.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-football.get-team\n      with:\n        teamId: tools.teamId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-football-player\n      description: Get football player profile and statistics.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-football.get-player\n      with:\n        playerId: tools.playerId\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-basketball-games\n      description: List basketball games filtered by league, date, or status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: statorium-basketball.list-basketball-games\n      with:\n        leagueId: tools.leagueId\n        date: tools.date\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-basketball-game\n      description: Get basketball game box score and quarter-by-quarter breakdown.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-basketball.get-basketball-game\n      with:\n        gameId: tools.gameId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-basketball-standings\n      description: Get basketball league standings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-basketball.get-basketball-standings\n      with:\n        leagueId: tools.leagueId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nfl-games\n      description: List NFL games filtered by week, season, team, or status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: statorium-nfl.list-nfl-games\n      with:\n        week: tools.week\n        season: tools.season\n        teamId: tools.teamId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nfl-game\n      description: Get NFL game details including quarter scores and team statistics.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-nfl.get-nfl-game\n      with:\n        gameId: tools.gameId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nfl-standings\n      description: Get NFL standings by conference and division.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: statorium-nfl.get-nfl-standings\n\
  \      with:\n        season: tools.season\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nfl-news\n      description: Get the latest NFL news linked to specific players or teams.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: statorium-nfl.list-nfl-news\n      with:\n        teamId: tools.teamId\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
