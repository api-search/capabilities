---
categories: []
consumed_apis: []
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
- nyt best sellers lists.
- get most viewed
- movies
- get most viewed articles by section and time period.
- most shared nyt articles.
- new york times
- most emailed nyt articles.
- get current nyt best sellers list for a specific category (e.g., hardcover-fiction).
- get best seller history
- get most emailed
- most viewed nyt articles.
- articles
- publishing
- get nyt movie critic profiles and biographies.
- get the most viewed nyt articles by section and time period.
- search nyt movie reviews by keyword, reviewer name, or date range.
- journalism
- get nyt book reviews by title, author, or isbn.
- get most emailed articles by section and time period.
- trending
- content
- search nyt movie reviews.
- get the most socially shared nyt articles by section and time period.
- search movie reviews
- get current nyt best sellers list.
- get nyt movie reviews, optionally filtered to critics' picks.
- get movie critics
- entertainment
- nyt book reviews.
- get book reviews
- search the full history of nyt best sellers by author, title, or isbn.
- nyt movie reviews.
- get movie reviews
- media
- get the most emailed nyt articles by section and time period (1 day, 7 days, 30 days).
- get most shared articles by section and time period.
- get nyt movie reviews with optional filter for critics' picks.
- search nyt movie reviews by keyword or reviewer.
- get best seller list
- get most shared
- news
- books
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NYT Content Discovery\n  description: Workflow for discovering NYT content trends, popular articles, books, movies, and entertainment coverage. Combines\n    the Most Popular API, Books API, and Movie Reviews API to support media analysts, editorial teams, and content recommendation\n    systems.\n  tags:\n  - New York Times\n  - Content\n  - Trending\n  - Books\n  - Movies\n  - Entertainment\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NYT_API_KEY: NYT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: nyt-most-popular\n    baseUri: https://api.nytimes.com/svc/mostpopular/v2\n    description: NYT Most Popular API returning the most emailed, shared, and viewed articles.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: most-emailed\n      path: /mostemailed/{section}/{time-period}.json\n\
  \      description: Get the most emailed NYT articles by section and time period.\n      operations:\n      - name: get-most-emailed\n        method: GET\n        description: Get most emailed articles for a section over a time period.\n        inputParameters:\n        - name: section\n          in: path\n          type: string\n          required: true\n          description: Section name (e.g., Technology, Arts) or all-sections.\n        - name: time-period\n          in: path\n          type: string\n          required: true\n          description: 'Time period: 1 (day), 7 (week), or 30 (month).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: most-shared\n      path: /mostshared/{section}/{time-period}.json\n      description: Get the most shared NYT articles by section and time period.\n      operations:\n      - name: get-most-shared\n        method: GET\n        description: Get most shared\
  \ articles for a section over a time period.\n        inputParameters:\n        - name: section\n          in: path\n          type: string\n          required: true\n          description: Section name (e.g., Technology, Arts) or all-sections.\n        - name: time-period\n          in: path\n          type: string\n          required: true\n          description: 'Time period: 1 (day), 7 (week), or 30 (month).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: most-viewed\n      path: /mostviewed/{section}/{time-period}.json\n      description: Get the most viewed NYT articles by section and time period.\n      operations:\n      - name: get-most-viewed\n        method: GET\n        description: Get most viewed articles for a section over a time period.\n        inputParameters:\n        - name: section\n          in: path\n          type: string\n          required: true\n          description:\
  \ Section name (e.g., Technology, Arts) or all-sections.\n        - name: time-period\n          in: path\n          type: string\n          required: true\n          description: 'Time period: 1 (day), 7 (week), or 30 (month).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: nyt-books\n    baseUri: https://api.nytimes.com/svc/books/v3\n    description: NYT Books API providing best seller lists and book review information.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: best-seller-lists\n      path: /lists.json\n      description: Get current NYT Best Sellers lists by list name.\n      operations:\n      - name: get-best-seller-list\n        method: GET\n        description: Get best sellers for a specific list with optional filters.\n        inputParameters:\n        - name: list\n\
  \          in: query\n          type: string\n          required: false\n          description: Name of the best-seller list (e.g., hardcover-fiction).\n        - name: bestsellers-date\n          in: query\n          type: string\n          required: false\n          description: YYYY-MM-DD week-ending date for the best seller sales data.\n        - name: published-date\n          in: query\n          type: string\n          required: false\n          description: YYYY-MM-DD date the best-seller list was published.\n        - name: isbn\n          in: query\n          type: string\n          required: false\n          description: ISBN (10 or 13 digits).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: best-seller-history\n      path: /lists/best-sellers/history.json\n      description: Get historical best seller data searchable by title, author, ISBN.\n      operations:\n      - name: get-best-seller-history\n\
  \        method: GET\n        description: Search the full history of NYT Best Sellers lists.\n        inputParameters:\n        - name: author\n          in: query\n          type: string\n          required: false\n          description: The author of the best seller.\n        - name: title\n          in: query\n          type: string\n          required: false\n          description: The title of the best seller.\n        - name: isbn\n          in: query\n          type: string\n          required: false\n          description: ISBN (10 or 13 digits).\n        - name: publisher\n          in: query\n          type: string\n          required: false\n          description: The standardized name of the publisher.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-names\n      path: /lists/names.json\n      description: Get all available NYT Best Sellers list names.\n      operations:\n     \
  \ - name: get-best-seller-list-names\n        method: GET\n        description: Get a list of all Best Sellers list names with encoded names for API requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-overview\n      path: /lists/overview.json\n      description: Get an overview of all best seller lists for a given week.\n      operations:\n      - name: get-best-seller-list-overview\n        method: GET\n        description: Get a weekly overview of all NYT Best Sellers lists.\n        inputParameters:\n        - name: published_date\n          in: query\n          type: string\n          required: false\n          description: YYYY-MM-DD date for the best-seller list publication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviews\n      path: /reviews.json\n      description: Get NYT book\
  \ reviews.\n      operations:\n      - name: get-book-reviews\n        method: GET\n        description: Get NYT book reviews by title, author, or ISBN.\n        inputParameters:\n        - name: isbn\n          in: query\n          type: integer\n          required: false\n          description: ISBN of the book.\n        - name: title\n          in: query\n          type: string\n          required: false\n          description: Title of the book.\n        - name: author\n          in: query\n          type: string\n          required: false\n          description: Author of the book.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: nyt-movie-reviews\n    baseUri: https://api.nytimes.com/svc/movies/v2\n    description: NYT Movie Reviews API providing access to reviews, critics, and critics' picks.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n\
  \      placement: query\n    resources:\n    - name: critics\n      path: /critics/{reviewer}.json\n      description: Get movie critic profiles by reviewer name or category.\n      operations:\n      - name: get-movie-critics\n        method: GET\n        description: Get movie critic profiles including name, bio, and image.\n        inputParameters:\n        - name: reviewer\n          in: path\n          type: string\n          required: true\n          description: Reviewer name, or 'all', 'full-time', or 'part-time'.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviews\n      path: /reviews/{type}.json\n      description: Get movie reviews filtered by critics' pick status.\n      operations:\n      - name: get-movie-reviews\n        method: GET\n        description: Get movie reviews, optionally filtered to Critics' Picks.\n        inputParameters:\n        - name: type\n          in: path\n\
  \          type: string\n          required: true\n          description: 'Filter type: ''all'' for all reviews, ''picks'' for Critics'' Picks.'\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Starting point of results (multiple of 20).\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: 'Sort order: by-opening-date or by-publication-date.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviews-search\n      path: /reviews/search.json\n      description: Search for movie reviews by keyword, date ranges, or reviewer.\n      operations:\n      - name: search-movie-reviews\n        method: GET\n        description: Search movie reviews by keyword, opening date, publication date, or reviewer.\n        inputParameters:\n        - name: query\n          in: query\n\
  \          type: string\n          required: false\n          description: Search keyword (e.g. lebowski).\n        - name: critics-pick\n          in: query\n          type: string\n          required: false\n          description: Set to Y to only show critics' picks.\n        - name: reviewer\n          in: query\n          type: string\n          required: false\n          description: Filter by reviewer byline.\n        - name: opening-date\n          in: query\n          type: string\n          required: false\n          description: US opening date range (e.g. 1930-01-01:1940-01-01).\n        - name: publication-date\n          in: query\n          type: string\n          required: false\n          description: Review publication date range.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort by by-opening-date or by-publication-date.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: nyt-content-discovery-api\n    description: Unified REST API for discovering trending NYT content, book rankings, and movie reviews.\n    resources:\n    - path: /v1/most-emailed/{section}/{time-period}\n      name: most-emailed\n      description: Most emailed NYT articles.\n      operations:\n      - method: GET\n        name: get-most-emailed\n        description: Get most emailed articles by section and time period.\n        call: nyt-most-popular.get-most-emailed\n        with:\n          section: rest.section\n          time-period: rest.time-period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/most-shared/{section}/{time-period}\n      name: most-shared\n      description: Most shared NYT articles.\n      operations:\n      - method: GET\n        name: get-most-shared\n        description: Get most shared articles by section\
  \ and time period.\n        call: nyt-most-popular.get-most-shared\n        with:\n          section: rest.section\n          time-period: rest.time-period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/most-viewed/{section}/{time-period}\n      name: most-viewed\n      description: Most viewed NYT articles.\n      operations:\n      - method: GET\n        name: get-most-viewed\n        description: Get most viewed articles by section and time period.\n        call: nyt-most-popular.get-most-viewed\n        with:\n          section: rest.section\n          time-period: rest.time-period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/best-sellers\n      name: best-sellers\n      description: NYT Best Sellers lists.\n      operations:\n      - method: GET\n        name: get-best-seller-list\n        description: Get current NYT Best Sellers list.\n        call: nyt-books.get-best-seller-list\n        with:\n\
  \          list: rest.list\n          bestsellers-date: rest.bestsellers-date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/book-reviews\n      name: book-reviews\n      description: NYT book reviews.\n      operations:\n      - method: GET\n        name: get-book-reviews\n        description: Get NYT book reviews by title, author, or ISBN.\n        call: nyt-books.get-book-reviews\n        with:\n          isbn: rest.isbn\n          title: rest.title\n          author: rest.author\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movie-reviews\n      name: movie-reviews\n      description: NYT movie reviews.\n      operations:\n      - method: GET\n        name: get-movie-reviews\n        description: Get NYT movie reviews, optionally filtered to Critics' Picks.\n        call: nyt-movie-reviews.get-movie-reviews\n        with:\n          type: rest.type\n          offset: rest.offset\n          order:\
  \ rest.order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/movie-reviews/search\n      name: movie-reviews-search\n      description: Search NYT movie reviews.\n      operations:\n      - method: GET\n        name: search-movie-reviews\n        description: Search NYT movie reviews by keyword or reviewer.\n        call: nyt-movie-reviews.search-movie-reviews\n        with:\n          query: rest.query\n          reviewer: rest.reviewer\n          critics-pick: rest.critics-pick\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: nyt-content-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted content trend analysis and entertainment discovery.\n    tools:\n    - name: get-most-emailed\n      description: Get the most emailed NYT articles by section and time period (1 day, 7 days, 30 days).\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: nyt-most-popular.get-most-emailed\n      with:\n        section: tools.section\n        time-period: tools.time-period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-most-shared\n      description: Get the most socially shared NYT articles by section and time period.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-most-popular.get-most-shared\n      with:\n        section: tools.section\n        time-period: tools.time-period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-most-viewed\n      description: Get the most viewed NYT articles by section and time period.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-most-popular.get-most-viewed\n      with:\n        section: tools.section\n        time-period: tools.time-period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-best-seller-list\n  \
  \    description: Get current NYT Best Sellers list for a specific category (e.g., hardcover-fiction).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-books.get-best-seller-list\n      with:\n        list: tools.list\n        bestsellers-date: tools.bestsellers-date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-best-seller-history\n      description: Search the full history of NYT Best Sellers by author, title, or ISBN.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-books.get-best-seller-history\n      with:\n        author: tools.author\n        title: tools.title\n        isbn: tools.isbn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-book-reviews\n      description: Get NYT book reviews by title, author, or ISBN.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-books.get-book-reviews\n      with:\n        isbn:\
  \ tools.isbn\n        title: tools.title\n        author: tools.author\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie-reviews\n      description: Get NYT movie reviews with optional filter for Critics' Picks.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-movie-reviews.get-movie-reviews\n      with:\n        type: tools.type\n        order: tools.order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-movie-reviews\n      description: Search NYT movie reviews by keyword, reviewer name, or date range.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-movie-reviews.search-movie-reviews\n      with:\n        query: tools.query\n        reviewer: tools.reviewer\n        critics-pick: tools.critics-pick\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-movie-critics\n      description: Get NYT movie critic profiles\
  \ and biographies.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-movie-reviews.get-movie-critics\n      with:\n        reviewer: tools.reviewer\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
