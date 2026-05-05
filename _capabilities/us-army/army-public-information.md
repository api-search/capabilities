---
categories: []
consumed_apis:
- army-public
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
- open data
- army press releases and official news
- search and list army news articles
- news
- army public events
- federal government
- search us army news articles by keyword, subject tag, or date range
- list upcoming us army public events and activities
- list army press releases
- list events
- retrieve a specific us army news article by its unique identifier
- military
- get army article
- get article
- media
- public affairs
- retrieve a specific army article by id
- defense
- list official us army press releases and news announcements
- list articles
- list news
- list army public events
- get a single army news article
- list army events
- search army news
- list and search army news articles
- army
- list army news and press releases
slug: army-public-information
source_filename: army-public-information.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"US Army Public Information\"\n  description: >-\n    Unified public information capability for the US Army, providing access to Army news articles,\n    press releases, and public events. Used by journalists, researchers, and public information\n    officers to access official Army content programmatically.\n  tags:\n    - Army\n    - Federal Government\n    - Military\n    - News\n    - Public Affairs\n    - Media\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: army-public\n      location: ./shared/army-public.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: army-information-api\n      description: \"Unified REST API for US Army public information and news.\"\n      resources:\n        - path: /v1/articles/{id}\n          name: article\n          description: \"Retrieve a specific Army article by ID\"\n          operations:\n            - method: GET\n \
  \             name: get-article\n              description: \"Get a single Army news article\"\n              call: \"army-public.get-article-by-id\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/articles\n          name: articles\n          description: \"Search and list Army news articles\"\n          operations:\n            - method: GET\n              name: list-articles\n              description: \"List and search Army news articles\"\n              call: \"army-public.get-articles\"\n              with:\n                q: \"rest.q\"\n                tag: \"rest.tag\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/news\n          name: news\n          description: \"Army press releases and official\
  \ news\"\n          operations:\n            - method: GET\n              name: list-news\n              description: \"List Army news and press releases\"\n              call: \"army-public.get-news\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Army public events\"\n          operations:\n            - method: GET\n              name: list-events\n              description: \"List Army public events\"\n              call: \"army-public.get-events\"\n              with:\n                limit: \"rest.limit\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: army-information-mcp\n \
  \     transport: http\n      description: \"MCP server for AI-assisted access to US Army public news and information.\"\n      tools:\n        - name: get-army-article\n          description: \"Retrieve a specific US Army news article by its unique identifier\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"army-public.get-article-by-id\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-army-news\n          description: \"Search US Army news articles by keyword, subject tag, or date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"army-public.get-articles\"\n          with:\n            q: \"tools.q\"\n            tag: \"tools.tag\"\n            limit: \"tools.limit\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: list-army-press-releases\n          description: \"List official US Army press releases and news announcements\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"army-public.get-news\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-army-events\n          description: \"List upcoming US Army public events and activities\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"army-public.get-events\"\n          with:\n            limit: \"tools.limit\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
