---
categories: []
consumed_apis: []
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
- soccer
- sports data
- live and historical event scores by sport and league.
- list sports editorial news.
- get play-by-play data for an event.
- league standings.
- sports
- football
- basketball
- get event play by play
- get the complete box score with all player statistics for a sports event.
- hockey
- list news
- get the current standings for a sports league by conference and division.
- get standings
- sports analytics
- list teams
- score for a specific event.
- editorial news articles.
- teams in a league.
- list all teams in a specified sports league.
- golf
- full box score for an event.
- list event scores
- list event scores for a sport and league on a given date.
- get the live or final score for a specific sports event.
- get event score
- get full box score with player statistics.
- get play by play
- list sports news
- get team
- get editorial news articles, previews, and recaps for a sport and league.
- get detailed team information including roster and statistics.
- live scores
- editorial
- play-by-play data for an event.
- list event scores for a sport and league on a specific date.
- get event box score
- list scores
- get score for a specific event.
- list teams in a sports league.
- baseball
- get box score
- statistics
- get detailed play-by-play sequence for a sports event.
- get standings for a sports league.
- tennis
slug: sports-analytics
source_filename: sports-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stats Perform Sports Analytics\n  description: Unified sports analytics capability using the Stats Perform STATS API for accessing live and historical sports\n    data across all major American sports leagues. Enables sports analysts, media platforms, and fantasy sports applications\n    to access scores, box scores, play-by-play, standings, team and player statistics, and editorial content from a single\n    integration point.\n  tags:\n  - Sports Analytics\n  - Sports Data\n  - Football\n  - Baseball\n  - Basketball\n  - Hockey\n  - Soccer\n  - Live Scores\n  - Statistics\n  - Editorial\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STATS_PERFORM_API_KEY: STATS_PERFORM_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stats-perform\n    baseUri: https://api.stats.com/v1\n    description: Stats Perform STATS API for comprehensive multi-sport data.\n    authentication:\n     \
  \ type: apikey\n      key: api_key\n      value: '{{STATS_PERFORM_API_KEY}}'\n      placement: query\n    resources:\n    - name: event-scores\n      path: /stats/{sport}/{leaguePath}/scores/\n      description: Event scores for sports leagues.\n      operations:\n      - name: list-scores\n        method: GET\n        description: Returns scores for events on a given date.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path identifier.\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Date in YYYYMMDD format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-event-score\n        method:\
  \ GET\n        description: Returns score for a specific event.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-box-scores\n      path: /stats/{sport}/{leaguePath}/box/\n      description: Event box scores.\n      operations:\n      - name: get-event-box-score\n        method: GET\n        description: Returns the full box score for a specific event.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n\
  \          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-pbp\n      path: /stats/{sport}/{leaguePath}/playbyplay/\n      description: Play-by-play event data.\n      operations:\n      - name: get-event-play-by-play\n        method: GET\n        description: Returns play-by-play data for a specific event.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n\
  \        - name: eventId\n          in: path\n          type: string\n          required: true\n          description: Event identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /stats/{sport}/{leaguePath}/teams/\n      description: Sports teams.\n      operations:\n      - name: list-teams\n        method: GET\n        description: Returns teams in a league.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-team\n        method: GET\n        description: Returns detailed team information.\n\
  \        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n        - name: teamId\n          in: path\n          type: string\n          required: true\n          description: Team identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: standings\n      path: /stats/{sport}/{leaguePath}/standings/\n      description: League standings.\n      operations:\n      - name: get-standings\n        method: GET\n        description: Returns league standings.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n     \
  \     type: string\n          required: true\n          description: League path.\n        - name: season\n          in: query\n          type: string\n          required: false\n          description: Season year.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news\n      path: /editorial/{sport}/{leaguePath}/news/\n      description: Sports editorial news.\n      operations:\n      - name: list-news\n        method: GET\n        description: Returns editorial news articles for a sport/league.\n        inputParameters:\n        - name: sport\n          in: path\n          type: string\n          required: true\n          description: Sport category.\n        - name: leaguePath\n          in: path\n          type: string\n          required: true\n          description: League path.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Number of articles to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stats-perform-analytics-api\n    description: Unified REST API for multi-sport data analytics via Stats Perform.\n    resources:\n    - path: /v1/scores/{sport}/{league}\n      name: scores\n      description: Live and historical event scores by sport and league.\n      operations:\n      - method: GET\n        name: list-scores\n        description: List event scores for a sport and league on a given date.\n        call: stats-perform.list-scores\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scores/{sport}/{league}/{eventId}\n      name: event-score\n      description: Score for a specific event.\n      operations:\n    \
  \  - method: GET\n        name: get-event-score\n        description: Get score for a specific event.\n        call: stats-perform.get-event-score\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/box-scores/{sport}/{league}/{eventId}\n      name: box-score\n      description: Full box score for an event.\n      operations:\n      - method: GET\n        name: get-box-score\n        description: Get full box score with player statistics.\n        call: stats-perform.get-event-box-score\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/play-by-play/{sport}/{league}/{eventId}\n      name: play-by-play\n      description: Play-by-play data for an event.\n      operations:\n      - method:\
  \ GET\n        name: get-play-by-play\n        description: Get play-by-play data for an event.\n        call: stats-perform.get-event-play-by-play\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          eventId: rest.eventId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/standings/{sport}/{league}\n      name: standings\n      description: League standings.\n      operations:\n      - method: GET\n        name: get-standings\n        description: Get standings for a sports league.\n        call: stats-perform.get-standings\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          season: rest.season\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{sport}/{league}\n      name: teams\n      description: Teams in a league.\n      operations:\n      - method: GET\n        name: list-teams\n        description: List teams in a sports\
  \ league.\n        call: stats-perform.list-teams\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news/{sport}/{league}\n      name: news\n      description: Editorial news articles.\n      operations:\n      - method: GET\n        name: list-news\n        description: List sports editorial news.\n        call: stats-perform.list-news\n        with:\n          sport: rest.sport\n          leaguePath: rest.league\n          count: rest.count\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: stats-perform-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted sports analytics using Stats Perform data.\n    tools:\n    - name: list-event-scores\n      description: List event scores for a sport and league on a specific date.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: stats-perform.list-scores\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-score\n      description: Get the live or final score for a specific sports event.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: stats-perform.get-event-score\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-box-score\n      description: Get the complete box score with all player statistics for a sports event.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: stats-perform.get-event-box-score\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: get-event-play-by-play\n      description: Get detailed play-by-play sequence for a sports event.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: stats-perform.get-event-play-by-play\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        eventId: tools.eventId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List all teams in a specified sports league.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stats-perform.list-teams\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team\n      description: Get detailed team information including roster and statistics.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: stats-perform.get-team\n      with:\n        sport: tools.sport\n \
  \       leaguePath: tools.league\n        teamId: tools.teamId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-standings\n      description: Get the current standings for a sports league by conference and division.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: stats-perform.get-standings\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        season: tools.season\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sports-news\n      description: Get editorial news articles, previews, and recaps for a sport and league.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stats-perform.list-news\n      with:\n        sport: tools.sport\n        leaguePath: tools.league\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
