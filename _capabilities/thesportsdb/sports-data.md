---
categories: []
consumed_apis:
- sportsdb
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
- list all sports in the database.
- free
- open data
- search for teams.
- search for sports teams by name or short name across all sports and countries.
- get upcoming team events
- all sports categories.
- get detailed information for a specific sports team including badge, stadium, and social links.
- get player
- sports leagues.
- recent team events.
- get next 5 events for a team.
- get recent team events
- get all events/matches for a league in a specific season.
- list all sports leagues available in thesportsdb.
- get standings for a league.
- get player details by id.
- get the current league standings/table for a specific sports league season.
- get recent events
- players
- team details.
- list sports
- get last 5 events for a team.
- league season events.
- get detailed biography and career data for a specific athlete.
- get league standings
- search players
- list all sports categories available in thesportsdb.
- get team details by id.
- get the last 5 completed matches/games for a specific sports team with scores.
- events
- search teams
- search for sports players/athletes by name or team.
- database
- get team
- search players by name or team.
- leagues
- list leagues
- standings
- search for players.
- search sports teams by name.
- league standings table.
- get all events for a league season.
- sports
- get upcoming events
- list teams in league
- upcoming team events.
- teams
- get the next 5 upcoming matches/games for a specific sports team.
- get league season events
- get league events
- get standings
- player details.
- list all teams in a specific sports league (by league name, sport, or country).
- list all sports leagues.
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheSportsDB Sports Data\"\n  description: \"Workflow capability for accessing sports data including team information, upcoming events, match results, player profiles, league standings, and sports metadata from TheSportsDB free API.\"\n  tags:\n    - Sports\n    - Teams\n    - Players\n    - Events\n    - Leagues\n    - Standings\n    - Free\n    - Open Data\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPORTSDB_API_KEY: SPORTSDB_API_KEY\n\ncapability:\n  consumes:\n    - import: sportsdb\n      location: ./shared/thesportsdb-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sportsdb-data-api\n      description: \"Unified REST API for sports data from TheSportsDB.\"\n      resources:\n        - path: /v1/sports\n          name: sports\n          description: \"All sports categories.\"\n          operations:\n            - method: GET\n          \
  \    name: list-sports\n              description: \"List all sports in the database.\"\n              call: \"sportsdb.list-all-sports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leagues\n          name: leagues\n          description: \"Sports leagues.\"\n          operations:\n            - method: GET\n              name: list-leagues\n              description: \"List all sports leagues.\"\n              call: \"sportsdb.list-all-leagues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/search\n          name: team-search\n          description: \"Search for teams.\"\n          operations:\n            - method: GET\n              name: search-teams\n              description: \"Search sports teams by name.\"\n              call: \"sportsdb.search-teams\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/teams/{id}\n          name: team\n          description: \"Team details.\"\n          operations:\n            - method: GET\n              name: get-team\n              description: \"Get team details by ID.\"\n              call: \"sportsdb.lookup-team\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/{id}/events/upcoming\n          name: team-upcoming-events\n          description: \"Upcoming team events.\"\n          operations:\n            - method: GET\n              name: get-upcoming-events\n              description: \"Get next 5 events for a team.\"\n              call: \"sportsdb.get-next-team-events\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/{id}/events/recent\n\
  \          name: team-recent-events\n          description: \"Recent team events.\"\n          operations:\n            - method: GET\n              name: get-recent-events\n              description: \"Get last 5 events for a team.\"\n              call: \"sportsdb.get-last-team-events\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leagues/{leagueId}/standings\n          name: league-standings\n          description: \"League standings table.\"\n          operations:\n            - method: GET\n              name: get-standings\n              description: \"Get standings for a league.\"\n              call: \"sportsdb.lookup-table\"\n              with:\n                l: \"rest.leagueId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leagues/{leagueId}/events\n          name: league-events\n\
  \          description: \"League season events.\"\n          operations:\n            - method: GET\n              name: get-league-events\n              description: \"Get all events for a league season.\"\n              call: \"sportsdb.get-season-events\"\n              with:\n                id: \"rest.leagueId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/players/search\n          name: player-search\n          description: \"Search for players.\"\n          operations:\n            - method: GET\n              name: search-players\n              description: \"Search players by name or team.\"\n              call: \"sportsdb.search-players\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/players/{id}\n          name: player\n          description: \"Player details.\"\n          operations:\n            - method: GET\n         \
  \     name: get-player\n              description: \"Get player details by ID.\"\n              call: \"sportsdb.lookup-player\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sportsdb-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports data queries using TheSportsDB.\"\n      tools:\n        - name: list-sports\n          description: \"List all sports categories available in TheSportsDB.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.list-all-sports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-leagues\n          description: \"List all sports leagues available in TheSportsDB.\"\n          hints:\n            readOnly: true\n            idempotent: true\n         \
  \ call: \"sportsdb.list-all-leagues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-teams\n          description: \"Search for sports teams by name or short name across all sports and countries.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.search-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams-in-league\n          description: \"List all teams in a specific sports league (by league name, sport, or country).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.list-all-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team\n          description: \"Get detailed information for a specific sports team including badge, stadium, and social links.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"sportsdb.lookup-team\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-upcoming-team-events\n          description: \"Get the next 5 upcoming matches/games for a specific sports team.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.get-next-team-events\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recent-team-events\n          description: \"Get the last 5 completed matches/games for a specific sports team with scores.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.get-last-team-events\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n\n        - name: get-league-standings\n          description: \"Get the current league standings/table for a specific sports league season.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.lookup-table\"\n          with:\n            l: \"tools.leagueId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-league-season-events\n          description: \"Get all events/matches for a league in a specific season.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.get-season-events\"\n          with:\n            id: \"tools.leagueId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-players\n          description: \"Search for sports players/athletes by name or team.\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"sportsdb.search-players\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-player\n          description: \"Get detailed biography and career data for a specific athlete.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sportsdb.lookup-player\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
