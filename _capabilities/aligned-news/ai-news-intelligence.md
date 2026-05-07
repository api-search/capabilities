---
api_specs:
- filename: aligned-news-openapi.yml
  format: yaml
  label: aligned-news
  slug: aligned-news
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/aligned-news/refs/heads/main/openapi/aligned-news-openapi.yml
categories: []
consumed_apis:
- aligned-news
description: Workflow capability that exposes the Aligned News REST surface as a unified AI news intelligence service. Used by AI agents, briefing tools, and research dashboards to discover stories, monitor early signals, ingest trend reports, and run full-text search across the Aligned News corpus.
layout: capability
name: AI News Intelligence
operations:
- description: List recent stories
  method: GET
  name: listStories
  path: /v1/stories
- description: Get a single story with full body
  method: GET
  name: getStory
  path: /v1/stories
- description: List recent signals
  method: GET
  name: listSignals
  path: /v1/signals
- description: Get a single signal with analysis
  method: GET
  name: getSignal
  path: /v1/signals
- description: List recent reports
  method: GET
  name: listReports
  path: /v1/reports
- description: Get a single report with full content
  method: GET
  name: getReport
  path: /v1/reports
- description: List bundles
  method: GET
  name: listBundles
  path: /v1/bundles
- description: Get a single bundle
  method: GET
  name: getBundle
  path: /v1/bundles
- description: List active news sections
  method: GET
  name: listSections
  path: /v1/sections
- description: Get the news feed grouped by section
  method: GET
  name: getNewsFeed
  path: /v1/news-feed
- description: Full-text search across stories, signals, and reports
  method: GET
  name: searchContent
  path: /v1/search
personas:
- description: Engineer building AI agents that need real-time AI news context
  id: ai-agent-builder
  name: AI Agent Builder
- description: Analyst tracking AI industry trends, funding, and product launches
  id: research-analyst
  name: Research Analyst
- description: Investor or trader using early signals to inform positions
  id: trader
  name: Trader
- description: Editorial team syndicating AI news into downstream products
  id: news-publisher
  name: News Publisher
provider_name: Aligned News
provider_slug: aligned-news
search_terms:
- listReports
- list recent signals
- ai
- get a single bundle
- mcp
- listStories
- get the news feed grouped by section
- unified ai news intelligence workflow exposing the aligned news rest surface to ai agents, briefing tools, and research dashboards.
- ai agent builder
- getBundle
- ai signals
- full-text search across stories, signals, and reports
- list bundles
- cross-content search
- listBundles
- analyst tracking ai industry trends, funding, and product launches
- signals
- news sections
- editorial team syndicating ai news into downstream products
- searchContent
- agents
- investor or trader using early signals to inform positions
- intelligence
- ai news stories
- getSignal
- unified news feed
- list active news sections
- getReport
- early pattern detections and trend analysis
- engineer building ai agents that need real-time ai news context
- list recent stories
- getNewsFeed
- real-time ai news stories and section-level feeds
- themed story bundles
- listSections
- get a single story with full body
- research analyst
- get a single signal with analysis
- news publisher
- get a single report with full content
- cross-content full-text search
- trader
- getStory
- aligned news
- ai trend reports
- news
- listSignals
- themed bundles and section taxonomy
- list recent reports
slug: ai-news-intelligence
source_filename: ai-news-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AI News Intelligence\n  description: >-\n    Workflow capability that exposes the Aligned News REST surface as a unified\n    AI news intelligence service. Used by AI agents, briefing tools, and\n    research dashboards to discover stories, monitor early signals, ingest\n    trend reports, and run full-text search across the Aligned News corpus.\n  tags:\n    - Aligned News\n    - AI\n    - News\n    - Intelligence\n    - Agents\n  created: '2026-05-06'\n  modified: '2026-05-06'\nbinds:\n  - namespace: env\n    keys:\n      ALIGNED_NEWS_API_KEY: ALIGNED_NEWS_API_KEY\ncapability:\n  consumes:\n    - import: aligned-news\n      location: ./shared/aligned-news.yaml\n  exposes:\n    - type: rest\n      port: 7090\n      namespace: ai-news-intelligence-api\n      description: Unified REST API for browsing and searching Aligned News content.\n      resources:\n        - path: /v1/stories\n          name: stories\n          description: AI news\
  \ stories\n          operations:\n            - method: GET\n              name: listStories\n              description: List recent stories\n              call: aligned-news.listStories\n              with:\n                section: rest.section\n                tag: rest.tag\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: GET\n              path: /{id}\n              name: getStory\n              description: Get a single story with full body\n              call: aligned-news.getStory\n              with:\n                id: rest.id\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/signals\n          name: signals\n          description: AI signals\n          operations:\n            - method: GET\n              name: listSignals\n              description: List recent signals\n              call: aligned-news.listSignals\n\
  \              with:\n                badge: rest.badge\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: GET\n              path: /{id}\n              name: getSignal\n              description: Get a single signal with analysis\n              call: aligned-news.getSignal\n              with:\n                id: rest.id\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/reports\n          name: reports\n          description: AI trend reports\n          operations:\n            - method: GET\n              name: listReports\n              description: List recent reports\n              call: aligned-news.listReports\n              with:\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: GET\n              path:\
  \ /{id}\n              name: getReport\n              description: Get a single report with full content\n              call: aligned-news.getReport\n              with:\n                id: rest.id\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/bundles\n          name: bundles\n          description: Themed story bundles\n          operations:\n            - method: GET\n              name: listBundles\n              description: List bundles\n              call: aligned-news.listBundles\n              with:\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n            - method: GET\n              path: /{id}\n              name: getBundle\n              description: Get a single bundle\n              call: aligned-news.getBundle\n              with:\n                id: rest.id\n              outputParameters:\n                - type:\
  \ object\n                  mapping: '$.'\n        - path: /v1/sections\n          name: sections\n          description: News sections\n          operations:\n            - method: GET\n              name: listSections\n              description: List active news sections\n              call: aligned-news.listSections\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/news-feed\n          name: news-feed\n          description: Unified news feed\n          operations:\n            - method: GET\n              name: getNewsFeed\n              description: Get the news feed grouped by section\n              call: aligned-news.getNewsFeed\n              with:\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n        - path: /v1/search\n          name: search\n          description: Cross-content search\n          operations:\n           \
  \ - method: GET\n              name: searchContent\n              description: Full-text search across stories, signals, and reports\n              call: aligned-news.searchContent\n              with:\n                q: rest.q\n                limit: rest.limit\n              outputParameters:\n                - type: object\n                  mapping: '$.'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aligned-news/refs/heads/main/capabilities/ai-news-intelligence.yaml
tags:
- Aligned News
- AI
- News
- Intelligence
- Agents
tools: []
---
