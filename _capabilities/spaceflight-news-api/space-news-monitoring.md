---
api_specs:
- filename: spaceflight-news-api-openapi.yml
  format: yaml
  label: snapi
  slug: snapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spaceflight-news-api/refs/heads/main/openapi/spaceflight-news-api-openapi.yml
categories: []
consumed_apis:
- snapi
description: Workflow capability for monitoring and aggregating spaceflight news, blogs, and mission reports. Useful for applications that want to track space industry developments, follow specific launches, or build space news feeds and dashboards.
layout: capability
name: Spaceflight News Monitoring
operations:
- description: List the latest spaceflight news articles with optional filtering
  method: GET
  name: list-articles
  path: /v1/articles
- description: Get a spaceflight news article by ID
  method: GET
  name: get-article
  path: /v1/articles/{id}
- description: List spaceflight blog posts
  method: GET
  name: list-blogs
  path: /v1/blogs
- description: List spaceflight mission reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Get API version and list of all supported news sources
  method: GET
  name: get-info
  path: /v1/info
personas: []
provider_name: Spaceflight News API
provider_slug: spaceflight-news-api
search_terms:
- news
- space
- list formal spaceflight mission reports published by space agencies and organizations
- list blogs
- spaceflight news articles aggregated from 43+ sources
- list spaceflight blog posts
- spaceflight blog posts with in-depth coverage
- get article
- spaceflight
- get a spaceflight news article by id
- list the latest spaceflight news articles from 43+ sources; supports filtering by news site or keyword search
- media
- single spaceflight news article
- get a specific spaceflight news article by its id
- list spaceflight blog posts providing in-depth coverage of launches and missions
- list the latest spaceflight news articles with optional filtering
- formal spaceflight mission reports from agencies
- get api version and list of all supported news sources
- monitoring
- list articles
- list spaceflight mission reports
- get api info
- api metadata and news source list
- list reports
- get spaceflight news api version and the complete list of aggregated news sources
- get info
slug: space-news-monitoring
source_filename: space-news-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Spaceflight News Monitoring\n  description: >-\n    Workflow capability for monitoring and aggregating spaceflight news, blogs, and\n    mission reports. Useful for applications that want to track space industry developments,\n    follow specific launches, or build space news feeds and dashboards.\n  tags:\n    - News\n    - Space\n    - Spaceflight\n    - Media\n    - Monitoring\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: snapi\n      location: ./shared/spaceflight-news-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: space-news-api\n      description: Unified REST API for spaceflight news monitoring and aggregation.\n      resources:\n        - path: /v1/articles\n          name: articles\n          description: Spaceflight news articles aggregated from 43+ sources\n          operations:\n            - method: GET\n              name: list-articles\n\
  \              description: List the latest spaceflight news articles with optional filtering\n              call: \"snapi.list-articles\"\n              with:\n                search: \"rest.search\"\n                news_site: \"rest.news_site\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/articles/{id}\n          name: article\n          description: Single spaceflight news article\n          operations:\n            - method: GET\n              name: get-article\n              description: Get a spaceflight news article by ID\n              call: \"snapi.get-article\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/blogs\n          name: blogs\n          description: Spaceflight blog posts with in-depth\
  \ coverage\n          operations:\n            - method: GET\n              name: list-blogs\n              description: List spaceflight blog posts\n              call: \"snapi.list-blogs\"\n              with:\n                search: \"rest.search\"\n                news_site: \"rest.news_site\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: Formal spaceflight mission reports from agencies\n          operations:\n            - method: GET\n              name: list-reports\n              description: List spaceflight mission reports\n              call: \"snapi.list-reports\"\n              with:\n                search: \"rest.search\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/info\n          name: info\n\
  \          description: API metadata and news source list\n          operations:\n            - method: GET\n              name: get-info\n              description: Get API version and list of all supported news sources\n              call: \"snapi.get-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: space-news-mcp\n      transport: http\n      description: MCP server for AI-assisted spaceflight news monitoring and research.\n      tools:\n        - name: list-articles\n          description: List the latest spaceflight news articles from 43+ sources; supports filtering by news site or keyword search\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"snapi.list-articles\"\n          with:\n            search: \"tools.search\"\n            news_site: \"tools.news_site\"\n            limit: \"tools.limit\"\n            launch: \"tools.launch\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-article\n          description: Get a specific spaceflight news article by its ID\n          hints:\n            readOnly: true\n          call: \"snapi.get-article\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-blogs\n          description: List spaceflight blog posts providing in-depth coverage of launches and missions\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"snapi.list-blogs\"\n          with:\n            search: \"tools.search\"\n            news_site: \"tools.news_site\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: List formal spaceflight mission reports published by space agencies and organizations\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"snapi.list-reports\"\n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-info\n          description: Get Spaceflight News API version and the complete list of aggregated news sources\n          hints:\n            readOnly: true\n          call: \"snapi.get-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spaceflight-news-api/refs/heads/main/capabilities/space-news-monitoring.yaml
tags:
- News
- Space
- Spaceflight
- Media
- Monitoring
tools:
- description: List the latest spaceflight news articles from 43+ sources; supports filtering by news site or keyword search
  hints:
    openWorld: true
    readOnly: true
  name: list-articles
- description: Get a specific spaceflight news article by its ID
  hints:
    readOnly: true
  name: get-article
- description: List spaceflight blog posts providing in-depth coverage of launches and missions
  hints:
    openWorld: true
    readOnly: true
  name: list-blogs
- description: List formal spaceflight mission reports published by space agencies and organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get Spaceflight News API version and the complete list of aggregated news sources
  hints:
    readOnly: true
  name: get-api-info
---
