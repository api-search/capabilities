---
categories: []
consumed_apis: []
description: Workflow capability for accessing sports data including team information, upcoming events, match results, player profiles, league standings, and sports metadata from TheSportsDB free API.
layout: capability
name: TheSportsDB Sports Data
operations:
- description: List all sports in the database.
  method: GET
  name: list-sports
  path: /v1/sports
- description: List all sports leagues.
  method: GET
  name: list-leagues
  path: /v1/leagues
- description: Search sports teams by name.
  method: GET
  name: search-teams
  path: /v1/teams/search
- description: Get team details by ID.
  method: GET
  name: get-team
  path: /v1/teams/{id}
- description: Get next 5 events for a team.
  method: GET
  name: get-upcoming-events
  path: /v1/teams/{id}/events/upcoming
- description: Get last 5 events for a team.
  method: GET
  name: get-recent-events
  path: /v1/teams/{id}/events/recent
- description: Get standings for a league.
  method: GET
  name: get-standings
  path: /v1/leagues/{leagueId}/standings
- description: Get all events for a league season.
  method: GET
  name: get-league-events
  path: /v1/leagues/{leagueId}/events
- description: Search players by name or team.
  method: GET
  name: search-players
  path: /v1/players/search
- description: Get player details by ID.
  method: GET
  name: get-player
  path: /v1/players/{id}
personas: []
provider_name: TheSportsDB
provider_slug: thesportsdb
search_terms:
- get team details by id.
- league season events.
- list teams in league
- get all events/matches for a league in a specific season.
- sports
- get detailed biography and career data for a specific athlete.
- leagues
- get detailed information for a specific sports team including badge, stadium, and social links.
- league standings table.
- search players by name or team.
- search for sports players/athletes by name or team.
- search sports teams by name.
- get league season events
- teams
- search for teams.
- standings
- team details.
- list sports
- get player details by id.
- get the current league standings/table for a specific sports league season.
- all sports categories.
- get standings
- list all sports leagues.
- player details.
- search for sports teams by name or short name across all sports and countries.
- get upcoming team events
- get next 5 events for a team.
- get league standings
- get last 5 events for a team.
- free
- list all sports categories available in thesportsdb.
- database
- list leagues
- search players
- get player
- get standings for a league.
- get recent team events
- get team
- sports leagues.
- players
- get league events
- list all sports in the database.
- upcoming team events.
- recent team events.
- search for players.
- get all events for a league season.
- list all sports leagues available in thesportsdb.
- get recent events
- get the next 5 upcoming matches/games for a specific sports team.
- search teams
- list all teams in a specific sports league (by league name, sport, or country).
- get the last 5 completed matches/games for a specific sports team with scores.
- events
- get upcoming events
- open data
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TheSportsDB Sports Data\n  description: Workflow capability for accessing sports data including team information, upcoming events, match results, player\n    profiles, league standings, and sports metadata from TheSportsDB free API.\n  tags:\n  - Sports\n  - Teams\n  - Players\n  - Events\n  - Leagues\n  - Standings\n  - Free\n  - Open Data\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPORTSDB_API_KEY: SPORTSDB_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sportsdb\n    baseUri: https://www.thesportsdb.com/api/v1/json/{{SPORTSDB_API_KEY}}\n    description: TheSportsDB API v1 — use '3' as key for free tier.\n    resources:\n    - name: search-teams\n      path: /searchteams.php\n      description: Search sports teams by name.\n      operations:\n      - name: search-teams\n        method: GET\n        description: Search for sports teams by name or abbreviation.\n       \
  \ inputParameters:\n        - name: t\n          in: query\n          type: string\n          required: false\n          description: Team name.\n        - name: sname\n          in: query\n          type: string\n          required: false\n          description: Short name/abbreviation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-players\n      path: /searchplayers.php\n      description: Search athletes by name or team.\n      operations:\n      - name: search-players\n        method: GET\n        description: Search for sports players by name or team.\n        inputParameters:\n        - name: t\n          in: query\n          type: string\n          required: false\n          description: Team name.\n        - name: p\n          in: query\n          type: string\n          required: false\n          description: Player name.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: search-events\n      path: /searchevents.php\n      description: Search sports events.\n      operations:\n      - name: search-events\n        method: GET\n        description: Search for sports events by name or season.\n        inputParameters:\n        - name: e\n          in: query\n          type: string\n          required: false\n          description: Event name.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Season.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-leagues\n      path: /all_leagues.php\n      description: List all sports leagues.\n      operations:\n      - name: list-all-leagues\n        method: GET\n        description: Get all sports leagues in the database.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: search-all-teams\n      path: /search_all_teams.php\n      description: List teams in a league.\n      operations:\n      - name: list-all-teams\n        method: GET\n        description: Get all teams in a specific league.\n        inputParameters:\n        - name: l\n          in: query\n          type: string\n          required: false\n          description: League name.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Sport name.\n        - name: c\n          in: query\n          type: string\n          required: false\n          description: Country name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup-team\n      path: /lookupteam.php\n      description: Look up team by ID.\n      operations:\n      - name: lookup-team\n        method:\
  \ GET\n        description: Get detailed data for a specific team.\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: Team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup-player\n      path: /lookupplayer.php\n      description: Look up player by ID.\n      operations:\n      - name: lookup-player\n        method: GET\n        description: Get detailed data for a specific player.\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: Player ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-next\n      path: /eventsnext.php\n      description: Next 5 events for a team.\n      operations:\n      - name: get-next-team-events\n\
  \        method: GET\n        description: Get the next 5 upcoming events for a team.\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: Team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-last\n      path: /eventslast.php\n      description: Last 5 events for a team.\n      operations:\n      - name: get-last-team-events\n        method: GET\n        description: Get the last 5 previous events for a team.\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: Team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-season\n      path: /eventsseason.php\n      description: All events in a season for a league.\n\
  \      operations:\n      - name: get-season-events\n        method: GET\n        description: Get all events for a league in a season.\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n          description: League ID.\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Season (e.g., 2026-2027).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup-table\n      path: /lookuptable.php\n      description: League standings table.\n      operations:\n      - name: lookup-table\n        method: GET\n        description: Get the standings table for a league season.\n        inputParameters:\n        - name: l\n          in: query\n          type: integer\n          required: true\n          description: League ID.\n        - name: s\n          in: query\n          type:\
  \ string\n          required: false\n          description: Season.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: all-sports\n      path: /all_sports.php\n      description: List all sports.\n      operations:\n      - name: list-all-sports\n        method: GET\n        description: Get all sports categories in the database.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sportsdb-data-api\n    description: Unified REST API for sports data from TheSportsDB.\n    resources:\n    - path: /v1/sports\n      name: sports\n      description: All sports categories.\n      operations:\n      - method: GET\n        name: list-sports\n        description: List all sports in the database.\n        call: sportsdb.list-all-sports\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/leagues\n      name: leagues\n      description: Sports leagues.\n      operations:\n      - method: GET\n        name: list-leagues\n        description: List all sports leagues.\n        call: sportsdb.list-all-leagues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/search\n      name: team-search\n      description: Search for teams.\n      operations:\n      - method: GET\n        name: search-teams\n        description: Search sports teams by name.\n        call: sportsdb.search-teams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{id}\n      name: team\n      description: Team details.\n      operations:\n      - method: GET\n        name: get-team\n        description: Get team details by ID.\n        call: sportsdb.lookup-team\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/teams/{id}/events/upcoming\n      name: team-upcoming-events\n      description: Upcoming team events.\n      operations:\n      - method: GET\n        name: get-upcoming-events\n        description: Get next 5 events for a team.\n        call: sportsdb.get-next-team-events\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{id}/events/recent\n      name: team-recent-events\n      description: Recent team events.\n      operations:\n      - method: GET\n        name: get-recent-events\n        description: Get last 5 events for a team.\n        call: sportsdb.get-last-team-events\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leagues/{leagueId}/standings\n      name: league-standings\n      description: League standings table.\n      operations:\n      - method: GET\n        name: get-standings\n    \
  \    description: Get standings for a league.\n        call: sportsdb.lookup-table\n        with:\n          l: rest.leagueId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leagues/{leagueId}/events\n      name: league-events\n      description: League season events.\n      operations:\n      - method: GET\n        name: get-league-events\n        description: Get all events for a league season.\n        call: sportsdb.get-season-events\n        with:\n          id: rest.leagueId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/search\n      name: player-search\n      description: Search for players.\n      operations:\n      - method: GET\n        name: search-players\n        description: Search players by name or team.\n        call: sportsdb.search-players\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/players/{id}\n      name: player\n      description:\
  \ Player details.\n      operations:\n      - method: GET\n        name: get-player\n        description: Get player details by ID.\n        call: sportsdb.lookup-player\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sportsdb-data-mcp\n    transport: http\n    description: MCP server for AI-assisted sports data queries using TheSportsDB.\n    tools:\n    - name: list-sports\n      description: List all sports categories available in TheSportsDB.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.list-all-sports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-leagues\n      description: List all sports leagues available in TheSportsDB.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.list-all-leagues\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: search-teams\n      description: Search for sports teams by name or short name across all sports and countries.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.search-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams-in-league\n      description: List all teams in a specific sports league (by league name, sport, or country).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.list-all-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team\n      description: Get detailed information for a specific sports team including badge, stadium, and social links.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.lookup-team\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upcoming-team-events\n      description: Get the\
  \ next 5 upcoming matches/games for a specific sports team.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.get-next-team-events\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recent-team-events\n      description: Get the last 5 completed matches/games for a specific sports team with scores.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.get-last-team-events\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-league-standings\n      description: Get the current league standings/table for a specific sports league season.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.lookup-table\n      with:\n        l: tools.leagueId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-league-season-events\n      description:\
  \ Get all events/matches for a league in a specific season.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.get-season-events\n      with:\n        id: tools.leagueId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-players\n      description: Search for sports players/athletes by name or team.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.search-players\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-player\n      description: Get detailed biography and career data for a specific athlete.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sportsdb.lookup-player\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thesportsdb/refs/heads/main/capabilities/sports-data.yaml
tags:
- Sports
- Teams
- Players
- Events
- Leagues
- Standings
- Free
- Open Data
tools:
- description: List all sports categories available in TheSportsDB.
  hints:
    idempotent: true
    readOnly: true
  name: list-sports
- description: List all sports leagues available in TheSportsDB.
  hints:
    idempotent: true
    readOnly: true
  name: list-leagues
- description: Search for sports teams by name or short name across all sports and countries.
  hints:
    idempotent: true
    readOnly: true
  name: search-teams
- description: List all teams in a specific sports league (by league name, sport, or country).
  hints:
    idempotent: true
    readOnly: true
  name: list-teams-in-league
- description: Get detailed information for a specific sports team including badge, stadium, and social links.
  hints:
    idempotent: true
    readOnly: true
  name: get-team
- description: Get the next 5 upcoming matches/games for a specific sports team.
  hints:
    idempotent: true
    readOnly: true
  name: get-upcoming-team-events
- description: Get the last 5 completed matches/games for a specific sports team with scores.
  hints:
    idempotent: true
    readOnly: true
  name: get-recent-team-events
- description: Get the current league standings/table for a specific sports league season.
  hints:
    idempotent: true
    readOnly: true
  name: get-league-standings
- description: Get all events/matches for a league in a specific season.
  hints:
    idempotent: true
    readOnly: true
  name: get-league-season-events
- description: Search for sports players/athletes by name or team.
  hints:
    idempotent: true
    readOnly: true
  name: search-players
- description: Get detailed biography and career data for a specific athlete.
  hints:
    idempotent: true
    readOnly: true
  name: get-player
---
