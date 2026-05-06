---
categories: []
consumed_apis: []
description: Workflow capability for discovering, searching, and analyzing podcast content via the Taddy API. Enables content teams, app developers, and media researchers to find podcasts, retrieve episode transcripts, explore top charts, and monitor brand mentions via webhooks.
layout: capability
name: Taddy Podcast Discovery
operations:
- description: Search for podcasts by keyword
  method: GET
  name: search-podcasts
  path: /v1/podcasts
- description: Get full podcast series metadata
  method: GET
  name: get-podcast-series
  path: /v1/podcasts/{name}
- description: Retrieve episode metadata and full transcript
  method: GET
  name: get-podcast-episode
  path: /v1/episodes/{uuid}
- description: Get top podcasts for a country
  method: GET
  name: get-top-charts
  path: /v1/top-charts
- description: Check remaining API request quota for the month
  method: GET
  name: get-api-requests-remaining
  path: /v1/quota
personas: []
provider_name: Taddy API
provider_slug: taddy-api
search_terms:
- webhooks
- get podcast episode
- top charting podcasts by country
- get full metadata for a podcast series including genre, language, host information, and episode count
- api usage quota status
- get top charts
- content discovery
- discover the most popular podcasts in a specific country
- check remaining api request quota for the month
- podcasts
- retrieve a podcast episode with full transcript, chapters, and contributor information
- graphql
- audio
- get episode details with transcript
- retrieve episode metadata and full transcript
- search podcasts
- get detailed podcast series information
- check how many api requests remain in the current billing period
- check api quota
- get top podcasts for a country
- search for podcast series by topic, name, or keyword
- media
- transcripts
- get api requests remaining
- comics
- get full podcast series metadata
- get podcast series
- search for podcasts by keyword
- search and discover podcast series
slug: podcast-discovery
source_filename: podcast-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Taddy Podcast Discovery\n  description: Workflow capability for discovering, searching, and analyzing podcast content via the Taddy API. Enables content\n    teams, app developers, and media researchers to find podcasts, retrieve episode transcripts, explore top charts, and monitor\n    brand mentions via webhooks.\n  tags:\n  - Audio\n  - Content Discovery\n  - Media\n  - Podcasts\n  - Transcripts\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TADDY_API_KEY: TADDY_API_KEY\n    TADDY_USER_ID: TADDY_USER_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: taddy-podcast\n    baseUri: https://api.taddy.org\n    description: GraphQL API for podcast series and episode data\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{TADDY_API_KEY}}'\n      placement: header\n    resources:\n    - name: graphql\n      path: /\n      description: GraphQL endpoint for all\
  \ Taddy API queries\n      operations:\n      - name: get-podcast-series\n        method: POST\n        description: Retrieve podcast series details by name or UUID\n        body:\n          type: json\n          data:\n            query: '{ getPodcastSeries(name: \"{{tools.podcast_name}}\") { uuid name description imageUrl totalEpisodesCount\n              language { name } genres { name } popularityRank { rank } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.getPodcastSeries\n      - name: search-podcasts\n        method: POST\n        description: Search podcasts and episodes by term\n        body:\n          type: json\n          data:\n            query: '{ searchForTerm(term: \"{{tools.search_term}}\", searchContentType: PODCASTSERIES) { searchId podcastSeries\n              { uuid name description imageUrl } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.data.searchForTerm\n      - name: get-podcast-episode\n        method: POST\n        description: Retrieve episode details including transcript\n        body:\n          type: json\n          data:\n            query: '{ getPodcastEpisode(uuid: \"{{tools.episode_uuid}}\") { uuid name description audioUrl duration datePublished\n              transcript episodeNumber seasonNumber } }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.data.getPodcastEpisode\n      - name: get-top-charts\n        method: POST\n        description: Retrieve top chart podcasts by country\n        body:\n          type: json\n          data:\n            query: '{ getTopChartsByCountry(taddyType: PODCASTSERIES, country: {{tools.country}}) { podcastSeries { uuid name\n              imageUrl popularityRank { rank } } } }'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.data.getTopChartsByCountry\n      - name: get-api-requests-remaining\n        method: POST\n        description: Check remaining monthly API request quota\n        body:\n          type: json\n          data:\n            query: '{ getApiRequestsRemaining }'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: integer\n          value: $.data.getApiRequestsRemaining\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: podcast-discovery-api\n    description: Unified REST API for podcast discovery and content analysis.\n    resources:\n    - path: /v1/podcasts\n      name: podcasts\n      description: Search and discover podcast series\n      operations:\n      - method: GET\n        name: search-podcasts\n        description: Search for podcasts by keyword\n        call: taddy-podcast.search-podcasts\n        with:\n          search_term: rest.term\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /v1/podcasts/{name}\n      name: podcast-detail\n      description: Get detailed podcast series information\n      operations:\n      - method: GET\n        name: get-podcast-series\n        description: Get full podcast series metadata\n        call: taddy-podcast.get-podcast-series\n        with:\n          podcast_name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/episodes/{uuid}\n      name: episode-detail\n      description: Get episode details with transcript\n      operations:\n      - method: GET\n        name: get-podcast-episode\n        description: Retrieve episode metadata and full transcript\n        call: taddy-podcast.get-podcast-episode\n        with:\n          episode_uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/top-charts\n      name: top-charts\n      description: Top charting podcasts by country\n\
  \      operations:\n      - method: GET\n        name: get-top-charts\n        description: Get top podcasts for a country\n        call: taddy-podcast.get-top-charts\n        with:\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/quota\n      name: api-quota\n      description: API usage quota status\n      operations:\n      - method: GET\n        name: get-api-requests-remaining\n        description: Check remaining API request quota for the month\n        call: taddy-podcast.get-api-requests-remaining\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: podcast-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted podcast discovery and content research.\n    tools:\n    - name: search-podcasts\n      description: Search for podcast series by topic, name, or keyword\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: taddy-podcast.search-podcasts\n      with:\n        search_term: tools.search_term\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-podcast-series\n      description: Get full metadata for a podcast series including genre, language, host information, and episode count\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taddy-podcast.get-podcast-series\n      with:\n        podcast_name: tools.podcast_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-podcast-episode\n      description: Retrieve a podcast episode with full transcript, chapters, and contributor information\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taddy-podcast.get-podcast-episode\n      with:\n        episode_uuid: tools.episode_uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-charts\n      description: Discover the most popular\
  \ podcasts in a specific country\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taddy-podcast.get-top-charts\n      with:\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-api-quota\n      description: Check how many API requests remain in the current billing period\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taddy-podcast.get-api-requests-remaining\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/taddy-api/refs/heads/main/capabilities/podcast-discovery.yaml
tags:
- Audio
- Content Discovery
- Media
- Podcasts
- Transcripts
tools:
- description: Search for podcast series by topic, name, or keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-podcasts
- description: Get full metadata for a podcast series including genre, language, host information, and episode count
  hints:
    openWorld: false
    readOnly: true
  name: get-podcast-series
- description: Retrieve a podcast episode with full transcript, chapters, and contributor information
  hints:
    openWorld: false
    readOnly: true
  name: get-podcast-episode
- description: Discover the most popular podcasts in a specific country
  hints:
    openWorld: true
    readOnly: true
  name: get-top-charts
- description: Check how many API requests remain in the current billing period
  hints:
    openWorld: false
    readOnly: true
  name: check-api-quota
---
