---
api_specs:
- filename: the-news-api-openapi.yml
  format: yaml
  label: the-news-api
  slug: the-news-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-news-api/refs/heads/main/openapi/the-news-api-openapi.yml
categories: []
consumed_apis:
- the-news-api
description: Comprehensive workflow for monitoring worldwide news, discovering trending stories, and researching topics. Combines headline aggregation, top story search, full archive access, and source discovery. Used by media analysts, journalists, researchers, and developers building news applications.
layout: capability
name: News Monitoring and Discovery
operations:
- description: Get latest headlines organized by category.
  method: GET
  name: get-headlines
  path: /v1/headlines
- description: Get top news stories filtered by keyword, category, and date.
  method: GET
  name: get-top-stories
  path: /v1/top-stories
- description: Search the complete historical and live news archive.
  method: GET
  name: search-all-news
  path: /v1/articles
- description: Get news articles similar to the given article.
  method: GET
  name: get-similar-news
  path: /v1/articles/similar/{uuid}
- description: Get a specific news article by UUID.
  method: GET
  name: get-article-by-uuid
  path: /v1/articles/{uuid}
- description: Discover available news sources by language and category.
  method: GET
  name: get-news-sources
  path: /v1/sources
personas: []
provider_name: The News API
provider_slug: the-news-api
search_terms:
- get latest headlines organized by category.
- full news archive search.
- news
- search the complete historical and live news archive.
- find news articles similar to a given article uuid. useful for discovering related coverage and building content clusters.
- research
- international
- get similar news
- get headlines
- search all news
- retrieve a specific news article by its uuid to get full metadata.
- discover available news sources by language and category.
- top stories with search and filtering.
- media
- get news sources
- search the complete worldwide news archive including historical articles. use for in-depth topic research across all time periods.
- specific article by uuid.
- articles
- headlines
- get top stories
- articles similar to a reference article.
- search
- get news articles similar to the given article.
- monitoring
- available news sources.
- latest news headlines by category and country.
- get article by uuid
- get top news stories globally or filtered by keyword, category, country, language, and date range. use boolean operators (+, |, -, ") for advanced search.
- list available news sources filtered by language and category to discover publishing domains covered by the api.
- get top news stories filtered by keyword, category, and date.
- get the latest news headlines organized by category (general, business, tech, sports, health, etc.) for specified countries and languages.
- get a specific news article by uuid.
slug: news-monitoring
source_filename: news-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"News Monitoring and Discovery\"\n  description: \"Comprehensive workflow for monitoring worldwide news, discovering trending stories, and researching topics. Combines headline aggregation, top story search, full archive access, and source discovery. Used by media analysts, journalists, researchers, and developers building news applications.\"\n  tags:\n    - News\n    - Monitoring\n    - Research\n    - Headlines\n    - Search\n    - International\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEWS_API_TOKEN: NEWS_API_TOKEN\n\ncapability:\n  consumes:\n    - import: the-news-api\n      location: ./shared/the-news-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: news-monitoring-api\n      description: \"Unified REST API for worldwide news monitoring and discovery.\"\n      resources:\n        - path: /v1/headlines\n          name: headlines\n   \
  \       description: \"Latest news headlines by category and country.\"\n          operations:\n            - method: GET\n              name: get-headlines\n              description: \"Get latest headlines organized by category.\"\n              call: \"the-news-api.get-headlines\"\n              with:\n                locale: \"rest.locale\"\n                language: \"rest.language\"\n                categories: \"rest.categories\"\n                headlines_per_category: \"rest.headlines_per_category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/top-stories\n          name: top-stories\n          description: \"Top stories with search and filtering.\"\n          operations:\n            - method: GET\n              name: get-top-stories\n              description: \"Get top news stories filtered by keyword, category, and date.\"\n              call: \"the-news-api.get-top-stories\"\n              with:\n\
  \                search: \"rest.search\"\n                categories: \"rest.categories\"\n                locale: \"rest.locale\"\n                language: \"rest.language\"\n                published_after: \"rest.published_after\"\n                published_before: \"rest.published_before\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/articles\n          name: articles\n          description: \"Full news archive search.\"\n          operations:\n            - method: GET\n              name: search-all-news\n              description: \"Search the complete historical and live news archive.\"\n              call: \"the-news-api.search-all-news\"\n              with:\n                search: \"rest.search\"\n                categories: \"rest.categories\"\n                locale: \"rest.locale\"\n\
  \                language: \"rest.language\"\n                domains: \"rest.domains\"\n                published_after: \"rest.published_after\"\n                published_before: \"rest.published_before\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/articles/similar/{uuid}\n          name: similar-articles\n          description: \"Articles similar to a reference article.\"\n          operations:\n            - method: GET\n              name: get-similar-news\n              description: \"Get news articles similar to the given article.\"\n              call: \"the-news-api.get-similar-news\"\n              with:\n                uuid: \"rest.uuid\"\n                language: \"rest.language\"\n                categories: \"rest.categories\"\n                limit: \"rest.limit\"\n             \
  \ outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/articles/{uuid}\n          name: article\n          description: \"Specific article by UUID.\"\n          operations:\n            - method: GET\n              name: get-article-by-uuid\n              description: \"Get a specific news article by UUID.\"\n              call: \"the-news-api.get-article-by-uuid\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sources\n          name: sources\n          description: \"Available news sources.\"\n          operations:\n            - method: GET\n              name: get-news-sources\n              description: \"Discover available news sources by language and category.\"\n              call: \"the-news-api.get-news-sources\"\n              with:\n                language: \"rest.language\"\n          \
  \      categories: \"rest.categories\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: news-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted news monitoring, topic research, and content discovery.\"\n      tools:\n        - name: get-headlines\n          description: \"Get the latest news headlines organized by category (general, business, tech, sports, health, etc.) for specified countries and languages.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.get-headlines\"\n          with:\n            locale: \"tools.locale\"\n            language: \"tools.language\"\n            categories: \"tools.categories\"\n            headlines_per_category: \"tools.headlines_per_category\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n\n        - name: get-top-stories\n          description: \"Get top news stories globally or filtered by keyword, category, country, language, and date range. Use boolean operators (+, |, -, \\\") for advanced search.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.get-top-stories\"\n          with:\n            search: \"tools.search\"\n            categories: \"tools.categories\"\n            locale: \"tools.locale\"\n            language: \"tools.language\"\n            published_after: \"tools.published_after\"\n            published_before: \"tools.published_before\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-all-news\n          description: \"Search the complete worldwide news archive including historical articles. Use for in-depth\
  \ topic research across all time periods.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.search-all-news\"\n          with:\n            search: \"tools.search\"\n            categories: \"tools.categories\"\n            locale: \"tools.locale\"\n            language: \"tools.language\"\n            domains: \"tools.domains\"\n            published_after: \"tools.published_after\"\n            published_before: \"tools.published_before\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-similar-news\n          description: \"Find news articles similar to a given article UUID. Useful for discovering related coverage and building content clusters.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.get-similar-news\"\
  \n          with:\n            uuid: \"tools.uuid\"\n            language: \"tools.language\"\n            categories: \"tools.categories\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-article-by-uuid\n          description: \"Retrieve a specific news article by its UUID to get full metadata.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.get-article-by-uuid\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-news-sources\n          description: \"List available news sources filtered by language and category to discover publishing domains covered by the API.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"the-news-api.get-news-sources\"\n          with:\n          \
  \  language: \"tools.language\"\n            categories: \"tools.categories\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-news-api/refs/heads/main/capabilities/news-monitoring.yaml
tags:
- News
- Monitoring
- Research
- Headlines
- Search
- International
tools:
- description: Get the latest news headlines organized by category (general, business, tech, sports, health, etc.) for specified countries and languages.
  hints:
    idempotent: true
    readOnly: true
  name: get-headlines
- description: Get top news stories globally or filtered by keyword, category, country, language, and date range. Use boolean operators (+, |, -, ") for advanced search.
  hints:
    idempotent: true
    readOnly: true
  name: get-top-stories
- description: Search the complete worldwide news archive including historical articles. Use for in-depth topic research across all time periods.
  hints:
    idempotent: true
    readOnly: true
  name: search-all-news
- description: Find news articles similar to a given article UUID. Useful for discovering related coverage and building content clusters.
  hints:
    idempotent: true
    readOnly: true
  name: get-similar-news
- description: Retrieve a specific news article by its UUID to get full metadata.
  hints:
    idempotent: true
    readOnly: true
  name: get-article-by-uuid
- description: List available news sources filtered by language and category to discover publishing domains covered by the API.
  hints:
    idempotent: true
    readOnly: true
  name: get-news-sources
---
