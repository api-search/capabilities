---
categories: []
consumed_apis: []
description: A REST News API to search current and historical articles and retrieve trending news in over 22 languages across 30 countries from 60,000+ sources.
layout: capability
name: GNews API
operations:
- description: Search articles
  method: GET
  name: searcharticles
  path: /search
- description: Get top headlines
  method: GET
  name: topheadlines
  path: /top-headlines
personas: []
provider_name: GNews
provider_slug: gnews
search_terms:
- articles
- get top headlines
- headlines
- topheadlines
- search articles
- search
- api
- searcharticles
- news
- gnews
slug: gnews-capability
source_filename: gnews-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GNews API\n  description: A REST News API to search current and historical articles and retrieve trending news in over 22 languages across\n    30 countries from 60,000+ sources.\n  tags:\n  - Gnews\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: gnews\n    baseUri: https://gnews.io/api/v4\n    description: GNews API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apikey\n      value: '{{GNEWS_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      operations:\n      - name: searcharticles\n        method: GET\n        description: Search articles\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Keywords or phrase to search for. Supports logical operators (AND, OR, NOT) and exact phrase matching\n            with quotes.\n     \
  \   - name: lang\n          in: query\n          type: string\n          description: ISO 639-1 two-letter language code.\n        - name: country\n          in: query\n          type: string\n          description: ISO 3166-1 alpha-2 two-letter country code.\n        - name: max\n          in: query\n          type: integer\n          description: Maximum number of articles to return (1-100).\n        - name: in\n          in: query\n          type: string\n          description: Comma-separated list of attributes to search in (title, description, content).\n        - name: nullable\n          in: query\n          type: string\n          description: Comma-separated list of attributes allowed to be null.\n        - name: from\n          in: query\n          type: string\n          description: Lower bound publish date (YYYY-MM-DDThh:mm:ssZ).\n        - name: to\n          in: query\n          type: string\n          description: Upper bound publish date (YYYY-MM-DDThh:mm:ssZ).\n     \
  \   - name: sortby\n          in: query\n          type: string\n          description: Sort order (publishedAt or relevance).\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination (paid plans).\n        - name: expand\n          in: query\n          type: string\n          description: Set to \"content\" to retrieve the full article content (paid plans).\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: top-headlines\n      path: /top-headlines\n      operations:\n      - name: topheadlines\n        method: GET\n        description: Get top headlines\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: News category.\n  \
  \      - name: lang\n          in: query\n          type: string\n          description: ISO 639-1 two-letter language code.\n        - name: country\n          in: query\n          type: string\n          description: ISO 3166-1 alpha-2 two-letter country code.\n        - name: max\n          in: query\n          type: integer\n          description: Maximum number of articles to return (1-100).\n        - name: nullable\n          in: query\n          type: string\n          description: Comma-separated list of attributes allowed to be null.\n        - name: from\n          in: query\n          type: string\n          description: Lower bound publish date.\n        - name: to\n          in: query\n          type: string\n          description: Upper bound publish date.\n        - name: q\n          in: query\n          type: string\n          description: Optional keyword filter applied to headlines.\n        - name: page\n          in: query\n          type: integer\n          description:\
  \ Page number for pagination (paid plans).\n        - name: expand\n          in: query\n          type: string\n          description: Set to \"content\" for full article content (paid plans).\n        - name: apikey\n          in: query\n          type: string\n          required: true\n          description: API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gnews-rest\n    description: REST adapter for GNews API.\n    resources:\n    - path: /search\n      name: searcharticles\n      operations:\n      - method: GET\n        name: searcharticles\n        description: Search articles\n        call: gnews.searcharticles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /top-headlines\n      name: topheadlines\n      operations:\n      - method: GET\n        name: topheadlines\n        description:\
  \ Get top headlines\n        call: gnews.topheadlines\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: gnews-mcp\n    transport: http\n    description: MCP adapter for GNews API for AI agent use.\n    tools:\n    - name: searcharticles\n      description: Search articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gnews.searcharticles\n      with:\n        q: tools.q\n        lang: tools.lang\n        country: tools.country\n        max: tools.max\n        in: tools.in\n        nullable: tools.nullable\n        from: tools.from\n        to: tools.to\n        sortby: tools.sortby\n        page: tools.page\n        expand: tools.expand\n        apikey: tools.apikey\n      inputParameters:\n      - name: q\n        type: string\n        description: Keywords or phrase to search for. Supports logical operators (AND, OR, NOT) and exact phrase matching\n      \
  \    with quotes.\n        required: true\n      - name: lang\n        type: string\n        description: ISO 639-1 two-letter language code.\n      - name: country\n        type: string\n        description: ISO 3166-1 alpha-2 two-letter country code.\n      - name: max\n        type: integer\n        description: Maximum number of articles to return (1-100).\n      - name: in\n        type: string\n        description: Comma-separated list of attributes to search in (title, description, content).\n      - name: nullable\n        type: string\n        description: Comma-separated list of attributes allowed to be null.\n      - name: from\n        type: string\n        description: Lower bound publish date (YYYY-MM-DDThh:mm:ssZ).\n      - name: to\n        type: string\n        description: Upper bound publish date (YYYY-MM-DDThh:mm:ssZ).\n      - name: sortby\n        type: string\n        description: Sort order (publishedAt or relevance).\n      - name: page\n        type: integer\n\
  \        description: Page number for pagination (paid plans).\n      - name: expand\n        type: string\n        description: Set to \"content\" to retrieve the full article content (paid plans).\n      - name: apikey\n        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: topheadlines\n      description: Get top headlines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: gnews.topheadlines\n      with:\n        category: tools.category\n        lang: tools.lang\n        country: tools.country\n        max: tools.max\n        nullable: tools.nullable\n        from: tools.from\n        to: tools.to\n        q: tools.q\n        page: tools.page\n        expand: tools.expand\n        apikey: tools.apikey\n      inputParameters:\n      - name: category\n        type: string\n        description: News category.\n \
  \     - name: lang\n        type: string\n        description: ISO 639-1 two-letter language code.\n      - name: country\n        type: string\n        description: ISO 3166-1 alpha-2 two-letter country code.\n      - name: max\n        type: integer\n        description: Maximum number of articles to return (1-100).\n      - name: nullable\n        type: string\n        description: Comma-separated list of attributes allowed to be null.\n      - name: from\n        type: string\n        description: Lower bound publish date.\n      - name: to\n        type: string\n        description: Upper bound publish date.\n      - name: q\n        type: string\n        description: Optional keyword filter applied to headlines.\n      - name: page\n        type: integer\n        description: Page number for pagination (paid plans).\n      - name: expand\n        type: string\n        description: Set to \"content\" for full article content (paid plans).\n      - name: apikey\n        type: string\n\
  \        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GNEWS_TOKEN: GNEWS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gnews/refs/heads/main/capabilities/gnews-capability.yaml
tags:
- Gnews
- API
tools:
- description: Search articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searcharticles
- description: Get top headlines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: topheadlines
---
