---
categories: []
consumed_apis: []
description: Google News provides RSS feeds that deliver news headlines organized by topic, location, and search query. While not an officially documented REST API, Google News exposes structured RSS/XML feeds that can be consumed programmatically to retrieve top stories, topic-based headlines, location-specific news, and search results across multiple languages and regions.
layout: capability
name: Google News RSS API
operations:
- description: Google News RSS Get Top Headlines
  method: GET
  name: gettopheadlines
  path: /rss
- description: Google News RSS Get Headlines by Topic
  method: GET
  name: gettopicheadlines
  path: /rss/headlines/section/topic/{topic}
- description: Google News RSS Get Headlines by Location
  method: GET
  name: getlocationheadlines
  path: /rss/headlines/section/geo/{location}
- description: Google News RSS Search News
  method: GET
  name: searchnews
  path: /rss/search
personas: []
provider_name: Google News RSS
provider_slug: google-news
search_terms:
- searchnews
- getlocationheadlines
- google news rss search news
- headlines
- google news rss get headlines by location
- google
- google news
- google news rss get top headlines
- gettopicheadlines
- aggregation
- gettopheadlines
- rss
- api
- news
- google news rss get headlines by topic
- media
slug: google-news-capability
source_filename: google-news-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google News RSS API\n  description: Google News provides RSS feeds that deliver news headlines organized by topic, location, and search query.\n    While not an officially documented REST API, Google News exposes structured RSS/XML feeds that can be consumed programmatically\n    to retrieve top stories, topic-based headlines, location-specific news, and search results across multiple languages and\n    regions.\n  tags:\n  - Google\n  - News\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-news\n    baseUri: https://news.google.com\n    description: Google News RSS API HTTP API.\n    resources:\n    - name: rss\n      path: /rss\n      operations:\n      - name: gettopheadlines\n        method: GET\n        description: Google News RSS Get Top Headlines\n        inputParameters:\n        - name: hl\n          in: query\n          type: string\n          description:\
  \ Host language (e.g., en-US).\n        - name: gl\n          in: query\n          type: string\n          description: Geographic location (e.g., US).\n        - name: ceid\n          in: query\n          type: string\n          description: Country and language edition identifier (e.g., US:en).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rss-headlines-section-topic-topic\n      path: /rss/headlines/section/topic/{topic}\n      operations:\n      - name: gettopicheadlines\n        method: GET\n        description: Google News RSS Get Headlines by Topic\n        inputParameters:\n        - name: topic\n          in: path\n          type: string\n          required: true\n          description: The topic identifier.\n        - name: hl\n          in: query\n          type: string\n          description: Host language.\n        - name: gl\n          in: query\n          type: string\n        \
  \  description: Geographic location.\n        - name: ceid\n          in: query\n          type: string\n          description: Country and language edition identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rss-headlines-section-geo-location\n      path: /rss/headlines/section/geo/{location}\n      operations:\n      - name: getlocationheadlines\n        method: GET\n        description: Google News RSS Get Headlines by Location\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: The location name or code.\n        - name: hl\n          in: query\n          type: string\n          description: Host language.\n        - name: gl\n          in: query\n          type: string\n          description: Geographic location.\n        - name: ceid\n          in: query\n          type: string\n         \
  \ description: Country and language edition identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rss-search\n      path: /rss/search\n      operations:\n      - name: searchnews\n        method: GET\n        description: Google News RSS Search News\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The search query string.\n        - name: hl\n          in: query\n          type: string\n          description: Host language.\n        - name: gl\n          in: query\n          type: string\n          description: Geographic location.\n        - name: ceid\n          in: query\n          type: string\n          description: Country and language edition identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: google-news-rest\n    description: REST adapter for Google News RSS API.\n    resources:\n    - path: /rss\n      name: gettopheadlines\n      operations:\n      - method: GET\n        name: gettopheadlines\n        description: Google News RSS Get Top Headlines\n        call: google-news.gettopheadlines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /rss/headlines/section/topic/{topic}\n      name: gettopicheadlines\n      operations:\n      - method: GET\n        name: gettopicheadlines\n        description: Google News RSS Get Headlines by Topic\n        call: google-news.gettopicheadlines\n        with:\n          topic: rest.topic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /rss/headlines/section/geo/{location}\n      name: getlocationheadlines\n      operations:\n      - method: GET\n        name: getlocationheadlines\n        description: Google News\
  \ RSS Get Headlines by Location\n        call: google-news.getlocationheadlines\n        with:\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /rss/search\n      name: searchnews\n      operations:\n      - method: GET\n        name: searchnews\n        description: Google News RSS Search News\n        call: google-news.searchnews\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-news-mcp\n    transport: http\n    description: MCP adapter for Google News RSS API for AI agent use.\n    tools:\n    - name: gettopheadlines\n      description: Google News RSS Get Top Headlines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-news.gettopheadlines\n      with:\n        hl: tools.hl\n        gl: tools.gl\n        ceid: tools.ceid\n      inputParameters:\n      - name: hl\n        type:\
  \ string\n        description: Host language (e.g., en-US).\n      - name: gl\n        type: string\n        description: Geographic location (e.g., US).\n      - name: ceid\n        type: string\n        description: Country and language edition identifier (e.g., US:en).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopicheadlines\n      description: Google News RSS Get Headlines by Topic\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-news.gettopicheadlines\n      with:\n        topic: tools.topic\n        hl: tools.hl\n        gl: tools.gl\n        ceid: tools.ceid\n      inputParameters:\n      - name: topic\n        type: string\n        description: The topic identifier.\n        required: true\n      - name: hl\n        type: string\n        description: Host language.\n      - name: gl\n        type: string\n        description: Geographic location.\n      - name: ceid\n      \
  \  type: string\n        description: Country and language edition identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlocationheadlines\n      description: Google News RSS Get Headlines by Location\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-news.getlocationheadlines\n      with:\n        location: tools.location\n        hl: tools.hl\n        gl: tools.gl\n        ceid: tools.ceid\n      inputParameters:\n      - name: location\n        type: string\n        description: The location name or code.\n        required: true\n      - name: hl\n        type: string\n        description: Host language.\n      - name: gl\n        type: string\n        description: Geographic location.\n      - name: ceid\n        type: string\n        description: Country and language edition identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchnews\n\
  \      description: Google News RSS Search News\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-news.searchnews\n      with:\n        q: tools.q\n        hl: tools.hl\n        gl: tools.gl\n        ceid: tools.ceid\n      inputParameters:\n      - name: q\n        type: string\n        description: The search query string.\n        required: true\n      - name: hl\n        type: string\n        description: Host language.\n      - name: gl\n        type: string\n        description: Geographic location.\n      - name: ceid\n        type: string\n        description: Country and language edition identifier.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-news/refs/heads/main/capabilities/google-news-capability.yaml
tags:
- Google
- News
- API
tools:
- description: Google News RSS Get Top Headlines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopheadlines
- description: Google News RSS Get Headlines by Topic
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopicheadlines
- description: Google News RSS Get Headlines by Location
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocationheadlines
- description: Google News RSS Search News
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchnews
---
