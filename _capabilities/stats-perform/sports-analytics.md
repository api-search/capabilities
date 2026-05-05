---
categories: []
consumed_apis:
- stats-perform
description: Unified sports analytics capability using the Stats Perform STATS API for accessing live and historical sports data across all major American sports leagues. Enables sports analysts, media platforms, and fantasy sports applications to access scores, box scores, play-by-play, standings, team and player statistics, and editorial content from a single integration point.
layout: capability
name: Stats Perform Sports Analytics
operations:
- description: List event scores for a sport and league on a given date.
  method: GET
  name: list-scores
  path: /v1/scores/{sport}/{league}
- description: Get score for a specific event.
  method: GET
  name: get-event-score
  path: /v1/scores/{sport}/{league}/{eventId}
- description: Get full box score with player statistics.
  method: GET
  name: get-box-score
  path: /v1/box-scores/{sport}/{league}/{eventId}
- description: Get play-by-play data for an event.
  method: GET
  name: get-play-by-play
  path: /v1/play-by-play/{sport}/{league}/{eventId}
- description: Get standings for a sports league.
  method: GET
  name: get-standings
  path: /v1/standings/{sport}/{league}
- description: List teams in a sports league.
  method: GET
  name: list-teams
  path: /v1/teams/{sport}/{league}
- description: List sports editorial news.
  method: GET
  name: list-news
  path: /v1/news/{sport}/{league}
personas: []
provider_name: Stats Perform
provider_slug: stats-perform
search_terms:
- list event scores
- live and historical event scores by sport and league.
- list event scores for a sport and league on a specific date.
- teams in a league.
- editorial
- editorial news articles.
- get event box score
- league standings.
- hockey
- get team
- sports analytics
- list sports news
- sports data
- get play by play
- get detailed play-by-play sequence for a sports event.
- get score for a specific event.
- list event scores for a sport and league on a given date.
- get the complete box score with all player statistics for a sports event.
- get the current standings for a sports league by conference and division.
- golf
- tennis
- list scores
- statistics
- basketball
- soccer
- score for a specific event.
- get standings
- sports
- list teams in a sports league.
- list all teams in a specified sports league.
- get box score
- list teams
- get editorial news articles, previews, and recaps for a sport and league.
- get standings for a sports league.
- play-by-play data for an event.
- get play-by-play data for an event.
- list news
- list sports editorial news.
- get full box score with player statistics.
- get event score
- full box score for an event.
- live scores
- get the live or final score for a specific sports event.
- get detailed team information including roster and statistics.
- get event play by play
- baseball
- football
slug: sports-analytics
source_filename: sports-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stats Perform Sports Analytics\"\n  description: >-\n    Unified sports analytics capability using the Stats Perform STATS API\n    for accessing live and historical sports data across all major American\n    sports leagues. Enables sports analysts, media platforms, and fantasy\n    sports applications to access scores, box scores, play-by-play,\n    standings, team and player statistics, and editorial content from\n    a single integration point.\n  tags:\n    - Sports Analytics\n    - Sports Data\n    - Football\n    - Baseball\n    - Basketball\n    - Hockey\n    - Soccer\n    - Live Scores\n    - Statistics\n    - Editorial\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STATS_PERFORM_API_KEY: STATS_PERFORM_API_KEY\n\ncapability:\n  consumes:\n    - import: stats-perform\n      location: ./shared/stats-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ stats-perform-analytics-api\n      description: \"Unified REST API for multi-sport data analytics via Stats Perform.\"\n      resources:\n        - path: /v1/scores/{sport}/{league}\n          name: scores\n          description: \"Live and historical event scores by sport and league.\"\n          operations:\n            - method: GET\n              name: list-scores\n              description: \"List event scores for a sport and league on a given date.\"\n              call: \"stats-perform.list-scores\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scores/{sport}/{league}/{eventId}\n          name: event-score\n          description: \"Score for a specific event.\"\n          operations:\n            - method: GET\n              name: get-event-score\n             \
  \ description: \"Get score for a specific event.\"\n              call: \"stats-perform.get-event-score\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/box-scores/{sport}/{league}/{eventId}\n          name: box-score\n          description: \"Full box score for an event.\"\n          operations:\n            - method: GET\n              name: get-box-score\n              description: \"Get full box score with player statistics.\"\n              call: \"stats-perform.get-event-box-score\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/play-by-play/{sport}/{league}/{eventId}\n\
  \          name: play-by-play\n          description: \"Play-by-play data for an event.\"\n          operations:\n            - method: GET\n              name: get-play-by-play\n              description: \"Get play-by-play data for an event.\"\n              call: \"stats-perform.get-event-play-by-play\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n                eventId: \"rest.eventId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/standings/{sport}/{league}\n          name: standings\n          description: \"League standings.\"\n          operations:\n            - method: GET\n              name: get-standings\n              description: \"Get standings for a sports league.\"\n              call: \"stats-perform.get-standings\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n         \
  \       season: \"rest.season\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/{sport}/{league}\n          name: teams\n          description: \"Teams in a league.\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List teams in a sports league.\"\n              call: \"stats-perform.list-teams\"\n              with:\n                sport: \"rest.sport\"\n                leaguePath: \"rest.league\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news/{sport}/{league}\n          name: news\n          description: \"Editorial news articles.\"\n          operations:\n            - method: GET\n              name: list-news\n              description: \"List sports editorial news.\"\n              call: \"stats-perform.list-news\"\n              with:\n                sport:\
  \ \"rest.sport\"\n                leaguePath: \"rest.league\"\n                count: \"rest.count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: stats-perform-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sports analytics using Stats Perform data.\"\n      tools:\n        - name: list-event-scores\n          description: \"List event scores for a sport and league on a specific date.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stats-perform.list-scores\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-score\n          description: \"Get the live or final score for a specific sports event.\"\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"stats-perform.get-event-score\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-box-score\n          description: \"Get the complete box score with all player statistics for a sports event.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"stats-perform.get-event-box-score\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-event-play-by-play\n          description: \"Get detailed play-by-play sequence for a sports event.\"\n          hints:\n          \
  \  readOnly: true\n            openWorld: false\n          call: \"stats-perform.get-event-play-by-play\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            eventId: \"tools.eventId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n          description: \"List all teams in a specified sports league.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stats-perform.list-teams\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team\n          description: \"Get detailed team information including roster and statistics.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"stats-perform.get-team\"\n          with:\n      \
  \      sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            teamId: \"tools.teamId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-standings\n          description: \"Get the current standings for a sports league by conference and division.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"stats-perform.get-standings\"\n          with:\n            sport: \"tools.sport\"\n            leaguePath: \"tools.league\"\n            season: \"tools.season\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-sports-news\n          description: \"Get editorial news articles, previews, and recaps for a sport and league.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stats-perform.list-news\"\n          with:\n            sport: \"tools.sport\"\n        \
  \    leaguePath: \"tools.league\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stats-perform/refs/heads/main/capabilities/sports-analytics.yaml
tags:
- Sports Analytics
- Sports Data
- Football
- Baseball
- Basketball
- Hockey
- Soccer
- Live Scores
- Statistics
- Editorial
tools:
- description: List event scores for a sport and league on a specific date.
  hints:
    openWorld: true
    readOnly: true
  name: list-event-scores
- description: Get the live or final score for a specific sports event.
  hints:
    openWorld: false
    readOnly: true
  name: get-event-score
- description: Get the complete box score with all player statistics for a sports event.
  hints:
    openWorld: false
    readOnly: true
  name: get-event-box-score
- description: Get detailed play-by-play sequence for a sports event.
  hints:
    openWorld: false
    readOnly: true
  name: get-event-play-by-play
- description: List all teams in a specified sports league.
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Get detailed team information including roster and statistics.
  hints:
    openWorld: false
    readOnly: true
  name: get-team
- description: Get the current standings for a sports league by conference and division.
  hints:
    openWorld: false
    readOnly: true
  name: get-standings
- description: Get editorial news articles, previews, and recaps for a sport and league.
  hints:
    openWorld: true
    readOnly: true
  name: list-sports-news
---
