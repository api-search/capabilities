---
categories: []
consumed_apis: []
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
- soccer
- sports data
- get all 32 nfl teams
- get current nfl season
- current nfl season info
- get nfl season
- mlb
- nhl
- get nfl teams
- get the current nfl season year and week, useful for constructing other api queries.
- fantasy sports
- nfl
- live scores
- get nfl current season
- odds
- get all 32 nfl teams with full details including conference, division, city, and stadium.
- nfl teams
- nba
- statistics
slug: sports-data
source_filename: sports-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SportsDataIO Sports Data\n  description: Unified sports data capability composing SportsDataIO APIs for multi-sport data access including live scores,\n    statistics, fantasy projections, odds, player news, injuries, and standings across NFL, MLB, NBA, NHL, and Soccer.\n  tags:\n  - Sports Data\n  - Statistics\n  - Fantasy Sports\n  - Live Scores\n  - Odds\n  - NFL\n  - MLB\n  - NBA\n  - NHL\n  - Soccer\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPORTSDATAIO_NFL_KEY: SPORTSDATAIO_NFL_KEY\n    SPORTSDATAIO_MLB_KEY: SPORTSDATAIO_MLB_KEY\n    SPORTSDATAIO_NBA_KEY: SPORTSDATAIO_NBA_KEY\n    SPORTSDATAIO_NHL_KEY: SPORTSDATAIO_NHL_KEY\n    SPORTSDATAIO_SOCCER_KEY: SPORTSDATAIO_SOCCER_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sportsdataio\n    baseUri: https://api.sportsdata.io\n    description: SportsDataIO REST API for comprehensive sports data\n    authentication:\n     \
  \ type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{SPORTSDATAIO_NFL_KEY}}'\n      placement: header\n    resources:\n    - name: nfl-scores\n      path: /v3/nfl/scores/{format}\n      description: NFL scores and game data\n      operations:\n      - name: get-nfl-current-season\n        method: GET\n        description: Get current NFL season information\n        inputParameters:\n        - name: format\n          in: path\n          type: string\n          required: true\n          description: 'Response format: JSON or XML'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-nfl-teams\n        method: GET\n        description: Get all NFL teams\n        inputParameters:\n        - name: format\n          in: path\n          type: string\n          required: true\n          description: Response format\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: get-nfl-schedule\n        method: GET\n        description: Get NFL schedule for a season\n        inputParameters:\n        - name: format\n          in: path\n          type: string\n          required: true\n          description: Response format\n        - name: season\n          in: path\n          type: string\n          required: true\n          description: Season year (e.g., 2025)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: sports-data-api\n    description: Unified REST API for multi-sport data from SportsDataIO.\n    resources:\n    - path: /v1/nfl/teams\n      name: nfl-teams\n      description: NFL teams\n      operations:\n      - method: GET\n        name: get-nfl-teams\n        description: Get all 32 NFL teams\n        call: sportsdataio.get-nfl-teams\n        with:\n\
  \          format: JSON\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nfl/season\n      name: nfl-season\n      description: Current NFL season info\n      operations:\n      - method: GET\n        name: get-nfl-season\n        description: Get current NFL season\n        call: sportsdataio.get-nfl-current-season\n        with:\n          format: JSON\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: sports-data-mcp\n    transport: http\n    description: MCP server for AI-assisted sports data research and fantasy sports analysis.\n    tools:\n    - name: get-nfl-teams\n      description: Get all 32 NFL teams with full details including conference, division, city, and stadium.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsdataio.get-nfl-teams\n      with:\n        format: JSON\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-nfl-current-season\n      description: Get the current NFL season year and week, useful for constructing other API queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sportsdataio.get-nfl-current-season\n      with:\n        format: JSON\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
