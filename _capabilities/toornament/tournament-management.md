---
categories: []
consumed_apis:
- toornament-organizer
description: Workflow capability for full esports tournament lifecycle management using the Toornament Organizer API — covering tournament creation, participant management, bracket progression, match reporting, and final standings.
layout: capability
name: Toornament Tournament Management
operations:
- description: List all tournaments for the authenticated organizer.
  method: GET
  name: list-tournaments
  path: /v1/tournaments
- description: Create a new esports tournament.
  method: POST
  name: create-tournament
  path: /v1/tournaments
- description: Get full tournament details.
  method: GET
  name: get-tournament
  path: /v1/tournaments/{id}
- description: Update tournament configuration.
  method: PATCH
  name: update-tournament
  path: /v1/tournaments/{id}
- description: List all tournament participants.
  method: GET
  name: list-participants
  path: /v1/tournaments/{tournament_id}/participants
- description: Add a participant to the tournament.
  method: POST
  name: add-participant
  path: /v1/tournaments/{tournament_id}/participants
- description: List all stages in a tournament.
  method: GET
  name: list-stages
  path: /v1/tournaments/{tournament_id}/stages
- description: List matches in a tournament stage.
  method: GET
  name: list-matches
  path: /v1/tournaments/{tournament_id}/stages/{stage_id}/matches
- description: Submit match result.
  method: PATCH
  name: report-match
  path: /v1/tournaments/{tournament_id}/matches/{match_id}
- description: Get rankings for a tournament stage.
  method: GET
  name: list-rankings
  path: /v1/tournaments/{tournament_id}/stages/{stage_id}/rankings
- description: List all supported esports games and disciplines.
  method: GET
  name: list-disciplines
  path: /v1/disciplines
personas: []
provider_name: Toornament
provider_slug: toornament
search_terms:
- tournaments
- list all registered participants in a toornament tournament.
- create and list tournaments.
- competition
- get full tournament details.
- toornament
- supported esports disciplines.
- update tournament configuration.
- list matches
- list all supported esports game disciplines available on toornament.
- brackets
- list participants
- list all stages defined in a tournament (group stage, elimination rounds, etc.).
- list all tournament participants.
- add a participant to the tournament.
- report and view a specific match.
- list tournaments
- list all matches in a tournament stage, including bracket display data.
- retrieve the current standings and rankings for a tournament stage.
- tournament stage rankings and standings.
- list all stages in a tournament.
- submit match result.
- list all supported esports games and disciplines.
- submit the final score and result for a completed tournament match.
- esports
- delete tournament
- matches
- tournament stages and brackets.
- retrieve full details of a specific toornament tournament.
- participants
- report match
- list all tournaments for the authenticated organizer.
- create tournament
- list rankings
- report match result
- get stage rankings
- create a new esports tournament.
- create a new esports tournament on toornament with full configuration.
- add a new participant (player or team) to a tournament.
- get or update a specific tournament.
- gaming
- manage tournament participants.
- get tournament
- list all esports tournaments organized by the authenticated user.
- get rankings for a tournament stage.
- list disciplines
- update tournament settings such as name, dates, registration, and rules.
- permanently delete a tournament.
- tournament match schedule and results.
- add participant
- list matches in a tournament stage.
- list stages
- update tournament
slug: tournament-management
source_filename: tournament-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toornament Tournament Management\"\n  description: \"Workflow capability for full esports tournament lifecycle management using the Toornament Organizer API — covering tournament creation, participant management, bracket progression, match reporting, and final standings.\"\n  tags:\n    - Brackets\n    - Competition\n    - Esports\n    - Gaming\n    - Matches\n    - Participants\n    - Tournaments\n    - Toornament\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOORNAMENT_API_KEY: TOORNAMENT_API_KEY\n      TOORNAMENT_ACCESS_TOKEN: TOORNAMENT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: toornament-organizer\n      location: ./shared/toornament-organizer.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: toornament-tournament-management-api\n      description: \"Unified REST API for esports tournament lifecycle management.\"\n      resources:\n\
  \        - path: /v1/tournaments\n          name: tournaments\n          description: \"Create and list tournaments.\"\n          operations:\n            - method: GET\n              name: list-tournaments\n              description: \"List all tournaments for the authenticated organizer.\"\n              call: \"toornament-organizer.list-tournaments\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tournament\n              description: \"Create a new esports tournament.\"\n              call: \"toornament-organizer.create-tournament\"\n              with:\n                discipline: \"rest.discipline\"\n                name: \"rest.name\"\n                participant_type: \"rest.participant_type\"\n                size: \"rest.size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{id}\n  \
  \        name: tournament\n          description: \"Get or update a specific tournament.\"\n          operations:\n            - method: GET\n              name: get-tournament\n              description: \"Get full tournament details.\"\n              call: \"toornament-organizer.get-tournament\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-tournament\n              description: \"Update tournament configuration.\"\n              call: \"toornament-organizer.update-tournament\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{tournament_id}/participants\n          name: participants\n          description: \"Manage tournament participants.\"\n          operations:\n            - method:\
  \ GET\n              name: list-participants\n              description: \"List all tournament participants.\"\n              call: \"toornament-organizer.list-participants\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: add-participant\n              description: \"Add a participant to the tournament.\"\n              call: \"toornament-organizer.create-participant\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{tournament_id}/stages\n          name: stages\n          description: \"Tournament stages and brackets.\"\n          operations:\n            - method: GET\n              name: list-stages\n           \
  \   description: \"List all stages in a tournament.\"\n              call: \"toornament-organizer.list-stages\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{tournament_id}/stages/{stage_id}/matches\n          name: matches\n          description: \"Tournament match schedule and results.\"\n          operations:\n            - method: GET\n              name: list-matches\n              description: \"List matches in a tournament stage.\"\n              call: \"toornament-organizer.list-matches\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n                stage_id: \"rest.stage_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{tournament_id}/matches/{match_id}\n          name: match\n          description:\
  \ \"Report and view a specific match.\"\n          operations:\n            - method: PATCH\n              name: report-match\n              description: \"Submit match result.\"\n              call: \"toornament-organizer.report-match\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n                match_id: \"rest.match_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tournaments/{tournament_id}/stages/{stage_id}/rankings\n          name: rankings\n          description: \"Tournament stage rankings and standings.\"\n          operations:\n            - method: GET\n              name: list-rankings\n              description: \"Get rankings for a tournament stage.\"\n              call: \"toornament-organizer.list-rankings\"\n              with:\n                tournament_id: \"rest.tournament_id\"\n                stage_id: \"rest.stage_id\"\n              outputParameters:\n\
  \                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/disciplines\n          name: disciplines\n          description: \"Supported esports disciplines.\"\n          operations:\n            - method: GET\n              name: list-disciplines\n              description: \"List all supported esports games and disciplines.\"\n              call: \"toornament-organizer.list-disciplines\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: toornament-tournament-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted esports tournament management on Toornament.\"\n      tools:\n        - name: list-tournaments\n          description: \"List all esports tournaments organized by the authenticated user.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.list-tournaments\"\
  \n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-tournament\n          description: \"Create a new esports tournament on Toornament with full configuration.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"toornament-organizer.create-tournament\"\n          with:\n            discipline: \"tools.discipline\"\n            name: \"tools.name\"\n            participant_type: \"tools.participant_type\"\n            size: \"tools.size\"\n            timezone: \"tools.timezone\"\n            platforms: \"tools.platforms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-tournament\n          description: \"Retrieve full details of a specific Toornament tournament.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.get-tournament\"\n          with:\n      \
  \      id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-tournament\n          description: \"Update tournament settings such as name, dates, registration, and rules.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"toornament-organizer.update-tournament\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-tournament\n          description: \"Permanently delete a tournament.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"toornament-organizer.delete-tournament\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-participants\n          description: \"List all registered\
  \ participants in a Toornament tournament.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.list-participants\"\n          with:\n            tournament_id: \"tools.tournament_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: add-participant\n          description: \"Add a new participant (player or team) to a tournament.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"toornament-organizer.create-participant\"\n          with:\n            tournament_id: \"tools.tournament_id\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stages\n          description: \"List all stages defined in a tournament (group stage, elimination rounds, etc.).\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"toornament-organizer.list-stages\"\n          with:\n            tournament_id: \"tools.tournament_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-matches\n          description: \"List all matches in a tournament stage, including bracket display data.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.list-matches\"\n          with:\n            tournament_id: \"tools.tournament_id\"\n            stage_id: \"tools.stage_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: report-match-result\n          description: \"Submit the final score and result for a completed tournament match.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"toornament-organizer.report-match\"\n          with:\n            tournament_id: \"tools.tournament_id\"\
  \n            match_id: \"tools.match_id\"\n            opponents: \"tools.opponents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-stage-rankings\n          description: \"Retrieve the current standings and rankings for a tournament stage.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.list-rankings\"\n          with:\n            tournament_id: \"tools.tournament_id\"\n            stage_id: \"tools.stage_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-disciplines\n          description: \"List all supported esports game disciplines available on Toornament.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toornament-organizer.list-disciplines\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toornament/refs/heads/main/capabilities/tournament-management.yaml
tags:
- Brackets
- Competition
- Esports
- Gaming
- Matches
- Participants
- Tournaments
- Toornament
tools:
- description: List all esports tournaments organized by the authenticated user.
  hints:
    idempotent: true
    readOnly: true
  name: list-tournaments
- description: Create a new esports tournament on Toornament with full configuration.
  hints:
    idempotent: false
    readOnly: false
  name: create-tournament
- description: Retrieve full details of a specific Toornament tournament.
  hints:
    idempotent: true
    readOnly: true
  name: get-tournament
- description: Update tournament settings such as name, dates, registration, and rules.
  hints:
    idempotent: true
    readOnly: false
  name: update-tournament
- description: Permanently delete a tournament.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-tournament
- description: List all registered participants in a Toornament tournament.
  hints:
    idempotent: true
    readOnly: true
  name: list-participants
- description: Add a new participant (player or team) to a tournament.
  hints:
    idempotent: false
    readOnly: false
  name: add-participant
- description: List all stages defined in a tournament (group stage, elimination rounds, etc.).
  hints:
    idempotent: true
    readOnly: true
  name: list-stages
- description: List all matches in a tournament stage, including bracket display data.
  hints:
    idempotent: true
    readOnly: true
  name: list-matches
- description: Submit the final score and result for a completed tournament match.
  hints:
    idempotent: true
    readOnly: false
  name: report-match-result
- description: Retrieve the current standings and rankings for a tournament stage.
  hints:
    idempotent: true
    readOnly: true
  name: get-stage-rankings
- description: List all supported esports game disciplines available on Toornament.
  hints:
    idempotent: true
    readOnly: true
  name: list-disciplines
---
