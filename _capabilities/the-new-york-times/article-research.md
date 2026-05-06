---
categories: []
consumed_apis: []
description: Unified workflow for researching and discovering NYT content. Combines article search, archive access, top stories, and the newswire to support journalists, researchers, and developers building news applications. Enables keyword-based article discovery, historical archive access, and real-time content monitoring.
layout: capability
name: NYT Article Research
operations:
- description: Search NYT articles using keywords, filters, and facets.
  method: GET
  name: search-articles
  path: /v1/articles
- description: Get all NYT articles for a specific year and month.
  method: GET
  name: get-articles-by-month
  path: /v1/archive/{year}/{month}
- description: Get top stories from the specified NYT section.
  method: GET
  name: get-top-stories-by-section
  path: /v1/top-stories/{section}
- description: Get recently published NYT articles in real-time.
  method: GET
  name: get-newswire-content
  path: /v1/newswire/{source}/{section}
personas: []
provider_name: The New York Times
provider_slug: the-new-york-times
search_terms:
- get recently published nyt articles in real-time.
- get top stories by section
- books
- research
- real-time nyt article stream.
- top stories from a specific nyt section.
- movies
- search nyt articles by keyword, date range, and facets.
- get top stories from the specified nyt section.
- get all nyt articles for a specific year and month.
- nyt article archive by year and month.
- publishing
- news discovery
- new york times
- retrieve all nyt articles published in a specific year and month, going back to 1851.
- search nyt articles from 1851 to today using keywords, date ranges, and section filters.
- monitor the nyt newswire for recently published articles by section in real-time.
- search articles
- news
- journalism
- media
- search nyt articles using keywords, filters, and facets.
- get newswire content
- get articles by month
- get articles currently featured on a specific nyt section front page.
- articles
slug: article-research
source_filename: article-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NYT Article Research\n  description: Unified workflow for researching and discovering NYT content. Combines article search, archive access, top\n    stories, and the newswire to support journalists, researchers, and developers building news applications. Enables keyword-based\n    article discovery, historical archive access, and real-time content monitoring.\n  tags:\n  - New York Times\n  - Research\n  - Articles\n  - Journalism\n  - News Discovery\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NYT_API_KEY: NYT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: nyt-article-search\n    baseUri: https://api.nytimes.com/svc/search/v2\n    description: NYT Article Search API for searching articles by keyword, date range, and facets.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: articles\n\
  \      path: /articlesearch.json\n      description: Search NYT articles by keyword with filtering and faceting.\n      operations:\n      - name: search-articles\n        method: GET\n        description: Search NYT articles using keyword, filters, and facets.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query term. Searched against article body, headline, and byline.\n        - name: fq\n          in: query\n          type: string\n          required: false\n          description: Filtered search query using standard Lucene syntax.\n        - name: begin_date\n          in: query\n          type: string\n          required: false\n          description: Restricts results to articles published on or after this date (YYYYMMDD).\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Restricts results to articles published\
  \ on or before this date (YYYYMMDD).\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: 'Sort results by relevance (default) or pub_date. Values: newest, oldest.'\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page of results (0-10, each page = 10 results).\n        - name: facet_field\n          in: query\n          type: string\n          required: false\n          description: Comma-delimited list of facet fields to include in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: nyt-archive\n    baseUri: https://api.nytimes.com/svc/archive/v1\n    description: NYT Archive API returning all articles published in a given month.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement:\
  \ query\n    resources:\n    - name: archive\n      path: /{year}/{month}.json\n      description: Get all NYT articles published in a specific year and month.\n      operations:\n      - name: get-articles-by-month\n        method: GET\n        description: Returns all NYT articles for a given year and month going back to 1851.\n        inputParameters:\n        - name: year\n          in: path\n          type: integer\n          required: true\n          description: The year (e.g. 2016).\n        - name: month\n          in: path\n          type: integer\n          required: true\n          description: The month number (e.g. 1 for January).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: nyt-top-stories\n    baseUri: https://api.nytimes.com/svc/topstories/v2\n    description: NYT Top Stories API returning articles currently on the specified section.\n    authentication:\n\
  \      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: top-stories\n      path: /{section}.json\n      description: Get top stories for a specific NYT section.\n      operations:\n      - name: get-top-stories-by-section\n        method: GET\n        description: Get articles currently featured on the specified NYT section page.\n        inputParameters:\n        - name: section\n          in: path\n          type: string\n          required: true\n          description: 'Section name: arts, business, health, home, science, technology, us, world, etc.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: nyt-newswire\n    baseUri: https://api.nytimes.com/svc/news/v3\n    description: NYT Times Newswire API delivering real-time article metadata as articles are published.\n    authentication:\n      type: apikey\n\
  \      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: content\n      path: /content/{source}/{section}.json\n      description: Get recent content from a specific source and section.\n      operations:\n      - name: get-newswire-content\n        method: GET\n        description: Get recently published NYT articles by source and section.\n        inputParameters:\n        - name: source\n          in: path\n          type: string\n          required: true\n          description: 'Content source: all, nyt, or iht.'\n        - name: section\n          in: path\n          type: string\n          required: true\n          description: Section name or 'all' for all sections.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return (max 20, default 20).\n        - name: offset\n          in: query\n          type: integer\n          required: false\n \
  \         description: Starting record number (default 0).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nyt-article-research-api\n    description: Unified REST API for researching and discovering NYT articles.\n    resources:\n    - path: /v1/articles\n      name: article-search\n      description: Search NYT articles by keyword, date range, and facets.\n      operations:\n      - method: GET\n        name: search-articles\n        description: Search NYT articles using keywords, filters, and facets.\n        call: nyt-article-search.search-articles\n        with:\n          q: rest.q\n          fq: rest.fq\n          begin_date: rest.begin_date\n          end_date: rest.end_date\n          sort: rest.sort\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/archive/{year}/{month}\n\
  \      name: archive\n      description: NYT article archive by year and month.\n      operations:\n      - method: GET\n        name: get-articles-by-month\n        description: Get all NYT articles for a specific year and month.\n        call: nyt-archive.get-articles-by-month\n        with:\n          year: rest.year\n          month: rest.month\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/top-stories/{section}\n      name: top-stories\n      description: Top stories from a specific NYT section.\n      operations:\n      - method: GET\n        name: get-top-stories-by-section\n        description: Get top stories from the specified NYT section.\n        call: nyt-top-stories.get-top-stories-by-section\n        with:\n          section: rest.section\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/newswire/{source}/{section}\n      name: newswire\n      description: Real-time NYT article stream.\n\
  \      operations:\n      - method: GET\n        name: get-newswire-content\n        description: Get recently published NYT articles in real-time.\n        call: nyt-newswire.get-newswire-content\n        with:\n          source: rest.source\n          section: rest.section\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nyt-article-research-mcp\n    transport: http\n    description: MCP server for AI-assisted NYT article research and content discovery.\n    tools:\n    - name: search-articles\n      description: Search NYT articles from 1851 to today using keywords, date ranges, and section filters.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-article-search.search-articles\n      with:\n        q: tools.q\n        fq: tools.fq\n        begin_date: tools.begin_date\n        end_date: tools.end_date\n        sort: tools.sort\n        page: tools.page\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-articles-by-month\n      description: Retrieve all NYT articles published in a specific year and month, going back to 1851.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-archive.get-articles-by-month\n      with:\n        year: tools.year\n        month: tools.month\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-stories-by-section\n      description: Get articles currently featured on a specific NYT section front page.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-top-stories.get-top-stories-by-section\n      with:\n        section: tools.section\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-newswire-content\n      description: Monitor the NYT newswire for recently published articles by section in real-time.\n      hints:\n        readOnly: true\n      \
  \  idempotent: true\n      call: nyt-newswire.get-newswire-content\n      with:\n        source: tools.source\n        section: tools.section\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-new-york-times/refs/heads/main/capabilities/article-research.yaml
tags:
- New York Times
- Research
- Articles
- Journalism
- News Discovery
tools:
- description: Search NYT articles from 1851 to today using keywords, date ranges, and section filters.
  hints:
    idempotent: true
    readOnly: true
  name: search-articles
- description: Retrieve all NYT articles published in a specific year and month, going back to 1851.
  hints:
    idempotent: true
    readOnly: true
  name: get-articles-by-month
- description: Get articles currently featured on a specific NYT section front page.
  hints:
    idempotent: true
    readOnly: true
  name: get-top-stories-by-section
- description: Monitor the NYT newswire for recently published articles by section in real-time.
  hints:
    idempotent: true
    readOnly: true
  name: get-newswire-content
---
