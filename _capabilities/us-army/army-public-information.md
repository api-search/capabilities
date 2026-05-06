---
categories: []
consumed_apis: []
description: Unified public information capability for the US Army, providing access to Army news articles, press releases, and public events. Used by journalists, researchers, and public information officers to access official Army content programmatically.
layout: capability
name: US Army Public Information
operations:
- description: Get a single Army news article
  method: GET
  name: get-article
  path: /v1/articles/{id}
- description: List and search Army news articles
  method: GET
  name: list-articles
  path: /v1/articles
- description: List Army news and press releases
  method: GET
  name: list-news
  path: /v1/news
- description: List Army public events
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: US Army
provider_slug: us-army
search_terms:
- list events
- list army press releases
- list official us army press releases and news announcements
- retrieve a specific us army news article by its unique identifier
- army
- defense
- list news
- get army article
- list articles
- army press releases and official news
- list army events
- list and search army news articles
- get article
- list army news and press releases
- search and list army news articles
- list upcoming us army public events and activities
- news
- public affairs
- army public events
- list army public events
- media
- retrieve a specific army article by id
- search army news
- federal government
- search us army news articles by keyword, subject tag, or date range
- military
- get a single army news article
- open data
slug: army-public-information
source_filename: army-public-information.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Army Public Information\n  description: Unified public information capability for the US Army, providing access to Army news articles, press releases,\n    and public events. Used by journalists, researchers, and public information officers to access official Army content programmatically.\n  tags:\n  - Army\n  - Federal Government\n  - Military\n  - News\n  - Public Affairs\n  - Media\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: army-public\n    baseUri: https://api.army.mil/api/v1\n    description: US Army Public API - articles, news, and events\n    resources:\n    - name: article\n      path: /article/{id}\n      description: US Army news articles\n      operations:\n      - name: get-article-by-id\n        method: GET\n        description: Find and retrieve a specific Army article by its unique ID\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n          description: Article unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles\n      path: /articles\n      description: Collection of US Army news articles\n      operations:\n      - name: get-articles\n        method: GET\n        description: Retrieve a list of US Army news articles\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: tag\n          in: query\n          type: string\n          required: false\n          description: Filter by tag\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of articles to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n \
  \         description: Pagination offset\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start date filter (ISO 8601)\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End date filter (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: news\n      path: /news\n      description: US Army press releases and news items\n      operations:\n      - name: get-news\n        method: GET\n        description: Retrieve US Army press releases and official news\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of items to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      description: US Army public events and activities\n      operations:\n      - name: get-events\n        method: GET\n        description: Retrieve US Army public events\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of events to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: army-information-api\n    description: Unified REST API for US Army public information and news.\n    resources:\n    - path: /v1/articles/{id}\n      name: article\n      description: Retrieve a specific Army article by ID\n      operations:\n      - method: GET\n        name: get-article\n        description: Get a single Army news article\n        call: army-public.get-article-by-id\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/articles\n      name: articles\n      description: Search and list Army news articles\n      operations:\n      - method: GET\n        name: list-articles\n        description: List and search Army news articles\n        call: army-public.get-articles\n        with:\n          q: rest.q\n          tag: rest.tag\n          limit: rest.limit\n          offset: rest.offset\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/news\n      name: news\n      description: Army press releases and official news\n      operations:\n      - method: GET\n        name: list-news\n        description: List Army news and press releases\n        call: army-public.get-news\n        with:\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Army public events\n      operations:\n      - method: GET\n        name: list-events\n        description: List Army public events\n        call: army-public.get-events\n        with:\n          limit: rest.limit\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: army-information-mcp\n    transport: http\n    description: MCP server for\
  \ AI-assisted access to US Army public news and information.\n    tools:\n    - name: get-army-article\n      description: Retrieve a specific US Army news article by its unique identifier\n      hints:\n        readOnly: true\n        openWorld: true\n      call: army-public.get-article-by-id\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-army-news\n      description: Search US Army news articles by keyword, subject tag, or date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: army-public.get-articles\n      with:\n        q: tools.q\n        tag: tools.tag\n        limit: tools.limit\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-army-press-releases\n      description: List official US Army press releases and news announcements\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: army-public.get-news\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-army-events\n      description: List upcoming US Army public events and activities\n      hints:\n        readOnly: true\n        openWorld: true\n      call: army-public.get-events\n      with:\n        limit: tools.limit\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-army/refs/heads/main/capabilities/army-public-information.yaml
tags:
- Army
- Federal Government
- Military
- News
- Public Affairs
- Media
tools:
- description: Retrieve a specific US Army news article by its unique identifier
  hints:
    openWorld: true
    readOnly: true
  name: get-army-article
- description: Search US Army news articles by keyword, subject tag, or date range
  hints:
    openWorld: true
    readOnly: true
  name: search-army-news
- description: List official US Army press releases and news announcements
  hints:
    openWorld: true
    readOnly: true
  name: list-army-press-releases
- description: List upcoming US Army public events and activities
  hints:
    openWorld: true
    readOnly: true
  name: list-army-events
---
