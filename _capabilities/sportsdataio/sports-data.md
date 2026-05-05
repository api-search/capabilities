---
categories: []
consumed_apis:
- sportsdataio
description: Unified sports data capability composing SportsDataIO APIs for multi-sport data access including live scores, statistics, fantasy projections, odds, player news, injuries, and standings across NFL, MLB, NBA, NHL, and Soccer.
layout: capability
name: SportsDataIO Sports Data
operations:
- description: Get all 32 NFL teams
  method: GET
  name: get-nfl-teams
  path: /v1/nfl/teams
- description: Get current NFL season
  method: GET
  name: get-nfl-season
  path: /v1/nfl/season
personas: []
provider_name: SportsDataIO
provider_slug: sportsdataio
search_terms:
- get all 32 nfl teams with full details including conference, division, city, and stadium.
- get nfl current season
- sports data
- get nfl teams
- nfl teams
- get nfl season
- get all 32 nfl teams
- statistics
- soccer
- fantasy sports
- current nfl season info
- mlb
- get current nfl season
- nfl
- odds
- nhl
- get the current nfl season year and week, useful for constructing other api queries.
- live scores
- nba
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SportsDataIO Sports Data\"\n  description: >-\n    Unified sports data capability composing SportsDataIO APIs for multi-sport\n    data access including live scores, statistics, fantasy projections, odds,\n    player news, injuries, and standings across NFL, MLB, NBA, NHL, and Soccer.\n  tags:\n    - Sports Data\n    - Statistics\n    - Fantasy Sports\n    - Live Scores\n    - Odds\n    - NFL\n    - MLB\n    - NBA\n    - NHL\n    - Soccer\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPORTSDATAIO_NFL_KEY: SPORTSDATAIO_NFL_KEY\n      SPORTSDATAIO_MLB_KEY: SPORTSDATAIO_MLB_KEY\n      SPORTSDATAIO_NBA_KEY: SPORTSDATAIO_NBA_KEY\n      SPORTSDATAIO_NHL_KEY: SPORTSDATAIO_NHL_KEY\n      SPORTSDATAIO_SOCCER_KEY: SPORTSDATAIO_SOCCER_KEY\n\ncapability:\n  consumes:\n    - import: sportsdataio\n      location: ./shared/sportsdataio.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n\
  \      namespace: sports-data-api\n      description: \"Unified REST API for multi-sport data from SportsDataIO.\"\n      resources:\n        - path: /v1/nfl/teams\n          name: nfl-teams\n          description: \"NFL teams\"\n          operations:\n            - method: GET\n              name: get-nfl-teams\n              description: \"Get all 32 NFL teams\"\n              call: \"sportsdataio.get-nfl-teams\"\n              with:\n                format: \"JSON\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/nfl/season\n          name: nfl-season\n          description: \"Current NFL season info\"\n          operations:\n            - method: GET\n              name: get-nfl-season\n              description: \"Get current NFL season\"\n              call: \"sportsdataio.get-nfl-current-season\"\n              with:\n                format: \"JSON\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: sports-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports data research and fantasy sports analysis.\"\n      tools:\n        - name: get-nfl-teams\n          description: \"Get all 32 NFL teams with full details including conference, division, city, and stadium.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsdataio.get-nfl-teams\"\n          with:\n            format: \"JSON\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-nfl-current-season\n          description: \"Get the current NFL season year and week, useful for constructing other API queries.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sportsdataio.get-nfl-current-season\"\n          with:\n            format: \"JSON\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sportsdataio/refs/heads/main/capabilities/sports-data.yaml
tags:
- Sports Data
- Statistics
- Fantasy Sports
- Live Scores
- Odds
- NFL
- MLB
- NBA
- NHL
- Soccer
tools:
- description: Get all 32 NFL teams with full details including conference, division, city, and stadium.
  hints:
    openWorld: true
    readOnly: true
  name: get-nfl-teams
- description: Get the current NFL season year and week, useful for constructing other API queries.
  hints:
    openWorld: true
    readOnly: true
  name: get-nfl-current-season
---
