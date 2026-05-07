---
categories: []
consumed_apis: []
description: Locate articles and breaking news headlines from news sources and blogs across the web with a JSON API.
layout: capability
name: News API
operations:
- description: Search all articles
  method: GET
  name: geteverything
  path: /everything
- description: Get top breaking news headlines
  method: GET
  name: gettopheadlines
  path: /top-headlines
- description: Get available news sources
  method: GET
  name: getsources
  path: /top-headlines/sources
personas: []
provider_name: News API
provider_slug: news-api
search_terms:
- articles
- headlines
- search
- get available news sources
- geteverything
- search all articles
- getsources
- gettopheadlines
- api
- news
- get top breaking news headlines
slug: news-api-capability
source_filename: news-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: News API\n  description: Locate articles and breaking news headlines from news sources and blogs across the web with a JSON API.\n  tags:\n  - News\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: news-api\n    baseUri: https://newsapi.org/v2\n    description: News API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apiKey\n      value: '{{NEWS_API_TOKEN}}'\n    resources:\n    - name: everything\n      path: /everything\n      operations:\n      - name: geteverything\n        method: GET\n        description: Search all articles\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Keywords or phrases to search for in article title and body.\n        - name: searchIn\n          in: query\n          type: string\n          description: Fields to restrict the q search\
  \ to. Comma-separated list of title, description, content.\n        - name: sources\n          in: query\n          type: string\n          description: Comma-separated string of identifiers for the news sources or blogs (max 20).\n        - name: domains\n          in: query\n          type: string\n          description: Comma-separated string of domains to restrict the search to.\n        - name: excludeDomains\n          in: query\n          type: string\n          description: Comma-separated string of domains to remove from results.\n        - name: from\n          in: query\n          type: string\n          description: A date and optional time for the oldest article allowed (ISO 8601).\n        - name: to\n          in: query\n          type: string\n          description: A date and optional time for the newest article allowed (ISO 8601).\n        - name: language\n          in: query\n          type: string\n          description: The 2-letter ISO-639-1 code of the language.\n\
  \        - name: sortBy\n          in: query\n          type: string\n          description: The order to sort articles in.\n        - name: pageSize\n          in: query\n          type: integer\n          description: The number of results to return per page.\n        - name: page\n          in: query\n          type: integer\n          description: Use this to page through the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-headlines\n      path: /top-headlines\n      operations:\n      - name: gettopheadlines\n        method: GET\n        description: Get top breaking news headlines\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          description: The 2-letter ISO 3166-1 code of the country to get headlines for.\n        - name: category\n          in: query\n          type: string\n          description: The category to get\
  \ headlines for.\n        - name: sources\n          in: query\n          type: string\n          description: Comma-separated string of identifiers for news sources or blogs.\n        - name: q\n          in: query\n          type: string\n          description: Keywords or phrases to search for in article title and body.\n        - name: pageSize\n          in: query\n          type: integer\n          description: The number of results to return per page (max 100).\n        - name: page\n          in: query\n          type: integer\n          description: Use this to page through the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-headlines-sources\n      path: /top-headlines/sources\n      operations:\n      - name: getsources\n        method: GET\n        description: Get available news sources\n        inputParameters:\n        - name: category\n          in: query\n         \
  \ type: string\n          description: Filter sources by category.\n        - name: language\n          in: query\n          type: string\n          description: Filter sources by language (2-letter ISO-639-1 code).\n        - name: country\n          in: query\n          type: string\n          description: Filter sources by country (2-letter ISO 3166-1 code).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: news-api-rest\n    description: REST adapter for News API.\n    resources:\n    - path: /everything\n      name: geteverything\n      operations:\n      - method: GET\n        name: geteverything\n        description: Search all articles\n        call: news-api.geteverything\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /top-headlines\n      name: gettopheadlines\n      operations:\n      - method: GET\n\
  \        name: gettopheadlines\n        description: Get top breaking news headlines\n        call: news-api.gettopheadlines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /top-headlines/sources\n      name: getsources\n      operations:\n      - method: GET\n        name: getsources\n        description: Get available news sources\n        call: news-api.getsources\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: news-api-mcp\n    transport: http\n    description: MCP adapter for News API for AI agent use.\n    tools:\n    - name: geteverything\n      description: Search all articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: news-api.geteverything\n      with:\n        q: tools.q\n        searchIn: tools.searchIn\n        sources: tools.sources\n        domains: tools.domains\n        excludeDomains: tools.excludeDomains\n\
  \        from: tools.from\n        to: tools.to\n        language: tools.language\n        sortBy: tools.sortBy\n        pageSize: tools.pageSize\n        page: tools.page\n      inputParameters:\n      - name: q\n        type: string\n        description: Keywords or phrases to search for in article title and body.\n      - name: searchIn\n        type: string\n        description: Fields to restrict the q search to. Comma-separated list of title, description, content.\n      - name: sources\n        type: string\n        description: Comma-separated string of identifiers for the news sources or blogs (max 20).\n      - name: domains\n        type: string\n        description: Comma-separated string of domains to restrict the search to.\n      - name: excludeDomains\n        type: string\n        description: Comma-separated string of domains to remove from results.\n      - name: from\n        type: string\n        description: A date and optional time for the oldest article allowed\
  \ (ISO 8601).\n      - name: to\n        type: string\n        description: A date and optional time for the newest article allowed (ISO 8601).\n      - name: language\n        type: string\n        description: The 2-letter ISO-639-1 code of the language.\n      - name: sortBy\n        type: string\n        description: The order to sort articles in.\n      - name: pageSize\n        type: integer\n        description: The number of results to return per page.\n      - name: page\n        type: integer\n        description: Use this to page through the results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettopheadlines\n      description: Get top breaking news headlines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: news-api.gettopheadlines\n      with:\n        country: tools.country\n        category: tools.category\n        sources: tools.sources\n        q: tools.q\n        pageSize: tools.pageSize\n\
  \        page: tools.page\n      inputParameters:\n      - name: country\n        type: string\n        description: The 2-letter ISO 3166-1 code of the country to get headlines for.\n      - name: category\n        type: string\n        description: The category to get headlines for.\n      - name: sources\n        type: string\n        description: Comma-separated string of identifiers for news sources or blogs.\n      - name: q\n        type: string\n        description: Keywords or phrases to search for in article title and body.\n      - name: pageSize\n        type: integer\n        description: The number of results to return per page (max 100).\n      - name: page\n        type: integer\n        description: Use this to page through the results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsources\n      description: Get available news sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n   \
  \   call: news-api.getsources\n      with:\n        category: tools.category\n        language: tools.language\n        country: tools.country\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter sources by category.\n      - name: language\n        type: string\n        description: Filter sources by language (2-letter ISO-639-1 code).\n      - name: country\n        type: string\n        description: Filter sources by country (2-letter ISO 3166-1 code).\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NEWS_API_TOKEN: NEWS_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/news-api/refs/heads/main/capabilities/news-api-capability.yaml
tags:
- News
- Api
- API
tools:
- description: Search all articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteverything
- description: Get top breaking news headlines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettopheadlines
- description: Get available news sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsources
---
