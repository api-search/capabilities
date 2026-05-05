---
categories: []
consumed_apis:
- nyt-most-popular
- nyt-books
- nyt-movie-reviews
description: Workflow for discovering NYT content trends, popular articles, books, movies, and entertainment coverage. Combines the Most Popular API, Books API, and Movie Reviews API to support media analysts, editorial teams, and content recommendation systems.
layout: capability
name: NYT Content Discovery
operations:
- description: Get most emailed articles by section and time period.
  method: GET
  name: get-most-emailed
  path: /v1/most-emailed/{section}/{time-period}
- description: Get most shared articles by section and time period.
  method: GET
  name: get-most-shared
  path: /v1/most-shared/{section}/{time-period}
- description: Get most viewed articles by section and time period.
  method: GET
  name: get-most-viewed
  path: /v1/most-viewed/{section}/{time-period}
- description: Get current NYT Best Sellers list.
  method: GET
  name: get-best-seller-list
  path: /v1/best-sellers
- description: Get NYT book reviews by title, author, or ISBN.
  method: GET
  name: get-book-reviews
  path: /v1/book-reviews
- description: Get NYT movie reviews, optionally filtered to Critics' Picks.
  method: GET
  name: get-movie-reviews
  path: /v1/movie-reviews
- description: Search NYT movie reviews by keyword or reviewer.
  method: GET
  name: search-movie-reviews
  path: /v1/movie-reviews/search
personas: []
provider_name: The New York Times
provider_slug: the-new-york-times
search_terms:
- new york times
- get current nyt best sellers list for a specific category (e.g., hardcover-fiction).
- news
- search movie reviews
- search nyt movie reviews by keyword, reviewer name, or date range.
- get nyt movie reviews with optional filter for critics' picks.
- get nyt movie critic profiles and biographies.
- search nyt movie reviews by keyword or reviewer.
- movies
- get movie critics
- get most shared
- most viewed nyt articles.
- get most emailed
- get best seller history
- publishing
- most shared nyt articles.
- get nyt book reviews by title, author, or isbn.
- entertainment
- nyt best sellers lists.
- books
- get most viewed
- media
- get the most socially shared nyt articles by section and time period.
- trending
- content
- get nyt movie reviews, optionally filtered to critics' picks.
- get movie reviews
- articles
- most emailed nyt articles.
- search the full history of nyt best sellers by author, title, or isbn.
- get the most emailed nyt articles by section and time period (1 day, 7 days, 30 days).
- journalism
- get most shared articles by section and time period.
- nyt book reviews.
- nyt movie reviews.
- get best seller list
- get most emailed articles by section and time period.
- get book reviews
- get the most viewed nyt articles by section and time period.
- get most viewed articles by section and time period.
- get current nyt best sellers list.
- search nyt movie reviews.
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"NYT Content Discovery\"\n  description: \"Workflow for discovering NYT content trends, popular articles, books, movies, and entertainment coverage. Combines the Most Popular API, Books API, and Movie Reviews API to support media analysts, editorial teams, and content recommendation systems.\"\n  tags:\n    - New York Times\n    - Content\n    - Trending\n    - Books\n    - Movies\n    - Entertainment\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      NYT_API_KEY: NYT_API_KEY\n\ncapability:\n  consumes:\n    - import: nyt-most-popular\n      location: ./shared/most-popular.yaml\n    - import: nyt-books\n      location: ./shared/books.yaml\n    - import: nyt-movie-reviews\n      location: ./shared/movie-reviews.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: nyt-content-discovery-api\n      description: \"Unified REST API for discovering trending NYT content,\
  \ book rankings, and movie reviews.\"\n      resources:\n        - path: /v1/most-emailed/{section}/{time-period}\n          name: most-emailed\n          description: \"Most emailed NYT articles.\"\n          operations:\n            - method: GET\n              name: get-most-emailed\n              description: \"Get most emailed articles by section and time period.\"\n              call: \"nyt-most-popular.get-most-emailed\"\n              with:\n                section: \"rest.section\"\n                time-period: \"rest.time-period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/most-shared/{section}/{time-period}\n          name: most-shared\n          description: \"Most shared NYT articles.\"\n          operations:\n            - method: GET\n              name: get-most-shared\n              description: \"Get most shared articles by section and time period.\"\n              call: \"nyt-most-popular.get-most-shared\"\
  \n              with:\n                section: \"rest.section\"\n                time-period: \"rest.time-period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/most-viewed/{section}/{time-period}\n          name: most-viewed\n          description: \"Most viewed NYT articles.\"\n          operations:\n            - method: GET\n              name: get-most-viewed\n              description: \"Get most viewed articles by section and time period.\"\n              call: \"nyt-most-popular.get-most-viewed\"\n              with:\n                section: \"rest.section\"\n                time-period: \"rest.time-period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/best-sellers\n          name: best-sellers\n          description: \"NYT Best Sellers lists.\"\n          operations:\n            - method: GET\n              name: get-best-seller-list\n\
  \              description: \"Get current NYT Best Sellers list.\"\n              call: \"nyt-books.get-best-seller-list\"\n              with:\n                list: \"rest.list\"\n                bestsellers-date: \"rest.bestsellers-date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/book-reviews\n          name: book-reviews\n          description: \"NYT book reviews.\"\n          operations:\n            - method: GET\n              name: get-book-reviews\n              description: \"Get NYT book reviews by title, author, or ISBN.\"\n              call: \"nyt-books.get-book-reviews\"\n              with:\n                isbn: \"rest.isbn\"\n                title: \"rest.title\"\n                author: \"rest.author\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/movie-reviews\n          name: movie-reviews\n          description:\
  \ \"NYT movie reviews.\"\n          operations:\n            - method: GET\n              name: get-movie-reviews\n              description: \"Get NYT movie reviews, optionally filtered to Critics' Picks.\"\n              call: \"nyt-movie-reviews.get-movie-reviews\"\n              with:\n                type: \"rest.type\"\n                offset: \"rest.offset\"\n                order: \"rest.order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/movie-reviews/search\n          name: movie-reviews-search\n          description: \"Search NYT movie reviews.\"\n          operations:\n            - method: GET\n              name: search-movie-reviews\n              description: \"Search NYT movie reviews by keyword or reviewer.\"\n              call: \"nyt-movie-reviews.search-movie-reviews\"\n              with:\n                query: \"rest.query\"\n                reviewer: \"rest.reviewer\"\n             \
  \   critics-pick: \"rest.critics-pick\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: nyt-content-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted content trend analysis and entertainment discovery.\"\n      tools:\n        - name: get-most-emailed\n          description: \"Get the most emailed NYT articles by section and time period (1 day, 7 days, 30 days).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-most-popular.get-most-emailed\"\n          with:\n            section: \"tools.section\"\n            time-period: \"tools.time-period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-most-shared\n          description: \"Get the most socially shared NYT articles by section and time period.\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"nyt-most-popular.get-most-shared\"\n          with:\n            section: \"tools.section\"\n            time-period: \"tools.time-period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-most-viewed\n          description: \"Get the most viewed NYT articles by section and time period.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-most-popular.get-most-viewed\"\n          with:\n            section: \"tools.section\"\n            time-period: \"tools.time-period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-best-seller-list\n          description: \"Get current NYT Best Sellers list for a specific category (e.g., hardcover-fiction).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-books.get-best-seller-list\"\
  \n          with:\n            list: \"tools.list\"\n            bestsellers-date: \"tools.bestsellers-date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-best-seller-history\n          description: \"Search the full history of NYT Best Sellers by author, title, or ISBN.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-books.get-best-seller-history\"\n          with:\n            author: \"tools.author\"\n            title: \"tools.title\"\n            isbn: \"tools.isbn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-book-reviews\n          description: \"Get NYT book reviews by title, author, or ISBN.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-books.get-book-reviews\"\n          with:\n            isbn: \"tools.isbn\"\n            title: \"tools.title\"\
  \n            author: \"tools.author\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-movie-reviews\n          description: \"Get NYT movie reviews with optional filter for Critics' Picks.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-movie-reviews.get-movie-reviews\"\n          with:\n            type: \"tools.type\"\n            order: \"tools.order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-movie-reviews\n          description: \"Search NYT movie reviews by keyword, reviewer name, or date range.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-movie-reviews.search-movie-reviews\"\n          with:\n            query: \"tools.query\"\n            reviewer: \"tools.reviewer\"\n            critics-pick: \"tools.critics-pick\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-movie-critics\n          description: \"Get NYT movie critic profiles and biographies.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nyt-movie-reviews.get-movie-critics\"\n          with:\n            reviewer: \"tools.reviewer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-new-york-times/refs/heads/main/capabilities/content-discovery.yaml
tags:
- New York Times
- Content
- Trending
- Books
- Movies
- Entertainment
tools:
- description: Get the most emailed NYT articles by section and time period (1 day, 7 days, 30 days).
  hints:
    idempotent: true
    readOnly: true
  name: get-most-emailed
- description: Get the most socially shared NYT articles by section and time period.
  hints:
    idempotent: true
    readOnly: true
  name: get-most-shared
- description: Get the most viewed NYT articles by section and time period.
  hints:
    idempotent: true
    readOnly: true
  name: get-most-viewed
- description: Get current NYT Best Sellers list for a specific category (e.g., hardcover-fiction).
  hints:
    idempotent: true
    readOnly: true
  name: get-best-seller-list
- description: Search the full history of NYT Best Sellers by author, title, or ISBN.
  hints:
    idempotent: true
    readOnly: true
  name: get-best-seller-history
- description: Get NYT book reviews by title, author, or ISBN.
  hints:
    idempotent: true
    readOnly: true
  name: get-book-reviews
- description: Get NYT movie reviews with optional filter for Critics' Picks.
  hints:
    idempotent: true
    readOnly: true
  name: get-movie-reviews
- description: Search NYT movie reviews by keyword, reviewer name, or date range.
  hints:
    idempotent: true
    readOnly: true
  name: search-movie-reviews
- description: Get NYT movie critic profiles and biographies.
  hints:
    idempotent: true
    readOnly: true
  name: get-movie-critics
---
