---
categories: []
consumed_apis:
- nyt-article-search
- nyt-archive
- nyt-top-stories
- nyt-newswire
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
- new york times
- get top stories from the specified nyt section.
- news
- get articles currently featured on a specific nyt section front page.
- research
- get top stories by section
- movies
- search nyt articles using keywords, filters, and facets.
- get all nyt articles for a specific year and month.
- get recently published nyt articles in real-time.
- monitor the nyt newswire for recently published articles by section in real-time.
- nyt article archive by year and month.
- publishing
- news discovery
- search articles
- books
- media
- real-time nyt article stream.
- get articles by month
- articles
- top stories from a specific nyt section.
- retrieve all nyt articles published in a specific year and month, going back to 1851.
- search nyt articles by keyword, date range, and facets.
- search nyt articles from 1851 to today using keywords, date ranges, and section filters.
- get newswire content
- journalism
slug: article-research
source_filename: article-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NYT Article Research\"\n  description: \"Unified workflow for researching and discovering NYT content. Combines article search, archive access, top stories, and the newswire to support journalists, researchers, and developers building news applications. Enables keyword-based article discovery, historical archive access, and real-time content monitoring.\"\n  tags:\n    - New York Times\n    - Research\n    - Articles\n    - Journalism\n    - News Discovery\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      NYT_API_KEY: NYT_API_KEY\n\ncapability:\n  consumes:\n    - import: nyt-article-search\n      location: ./shared/article-search.yaml\n    - import: nyt-archive\n      location: ./shared/archive.yaml\n    - import: nyt-top-stories\n      location: ./shared/top-stories.yaml\n    - import: nyt-newswire\n      location: ./shared/times-newswire.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8080\n      namespace: nyt-article-research-api\n      description: \"Unified REST API for researching and discovering NYT articles.\"\n      resources:\n        - path: /v1/articles\n          name: article-search\n          description: \"Search NYT articles by keyword, date range, and facets.\"\n          operations:\n            - method: GET\n              name: search-articles\n              description: \"Search NYT articles using keywords, filters, and facets.\"\n              call: \"nyt-article-search.search-articles\"\n              with:\n                q: \"rest.q\"\n                fq: \"rest.fq\"\n                begin_date: \"rest.begin_date\"\n                end_date: \"rest.end_date\"\n                sort: \"rest.sort\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/archive/{year}/{month}\n          name: archive\n          description: \"NYT\
  \ article archive by year and month.\"\n          operations:\n            - method: GET\n              name: get-articles-by-month\n              description: \"Get all NYT articles for a specific year and month.\"\n              call: \"nyt-archive.get-articles-by-month\"\n              with:\n                year: \"rest.year\"\n                month: \"rest.month\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/top-stories/{section}\n          name: top-stories\n          description: \"Top stories from a specific NYT section.\"\n          operations:\n            - method: GET\n              name: get-top-stories-by-section\n              description: \"Get top stories from the specified NYT section.\"\n              call: \"nyt-top-stories.get-top-stories-by-section\"\n              with:\n                section: \"rest.section\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n\n        - path: /v1/newswire/{source}/{section}\n          name: newswire\n          description: \"Real-time NYT article stream.\"\n          operations:\n            - method: GET\n              name: get-newswire-content\n              description: \"Get recently published NYT articles in real-time.\"\n              call: \"nyt-newswire.get-newswire-content\"\n              with:\n                source: \"rest.source\"\n                section: \"rest.section\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: nyt-article-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NYT article research and content discovery.\"\n      tools:\n        - name: search-articles\n          description: \"Search NYT articles from 1851 to today using keywords, date ranges, and section filters.\"\
  \n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-article-search.search-articles\"\n          with:\n            q: \"tools.q\"\n            fq: \"tools.fq\"\n            begin_date: \"tools.begin_date\"\n            end_date: \"tools.end_date\"\n            sort: \"tools.sort\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-articles-by-month\n          description: \"Retrieve all NYT articles published in a specific year and month, going back to 1851.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-archive.get-articles-by-month\"\n          with:\n            year: \"tools.year\"\n            month: \"tools.month\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-stories-by-section\n          description: \"Get articles currently\
  \ featured on a specific NYT section front page.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-top-stories.get-top-stories-by-section\"\n          with:\n            section: \"tools.section\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-newswire-content\n          description: \"Monitor the NYT newswire for recently published articles by section in real-time.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-newswire.get-newswire-content\"\n          with:\n            source: \"tools.source\"\n            section: \"tools.section\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
