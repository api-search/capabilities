---
categories: []
consumed_apis: []
description: Unified content discovery workflow for TechCrunch. Combines article retrieval, category and tag browsing, author profiles, media access, and full-text search through the WordPress REST API. Designed for developers building news aggregators, content analytics tools, media monitoring applications, and AI-powered research assistants that need to access TechCrunch's technology news content.
layout: capability
name: TechCrunch Content Discovery
operations:
- description: List TechCrunch articles with filtering and pagination
  method: GET
  name: list-posts
  path: /v1/posts
- description: Get a specific TechCrunch article
  method: GET
  name: get-post
  path: /v1/posts/{id}
- description: List all content categories
  method: GET
  name: list-categories
  path: /v1/categories
- description: Get a specific category
  method: GET
  name: get-category
  path: /v1/categories/{id}
- description: List all content tags
  method: GET
  name: list-tags
  path: /v1/tags
- description: List all TechCrunch authors
  method: GET
  name: list-authors
  path: /v1/authors
- description: Get an author profile
  method: GET
  name: get-author
  path: /v1/authors/{id}
- description: List media attachments
  method: GET
  name: list-media
  path: /v1/media
- description: Search across all TechCrunch content
  method: GET
  name: search-content
  path: /v1/search
personas: []
provider_name: TechCrunch
provider_slug: techcrunch
search_terms:
- search techcrunch articles by keyword, topic, or company name
- list all techcrunch content tags
- list tags
- techcrunch content tags
- get article
- list all techcrunch authors
- startups
- list all content categories
- list media
- list techcrunch authors and journalists
- single article retrieval
- list recent techcrunch articles with optional filters by category, tag, author, or date
- get details for a specific content category
- list categories
- techcrunch authors and contributors
- venture capital
- search content
- technology news
- get a specific techcrunch article
- content
- list authors
- full-text content search
- search articles
- search across all techcrunch content
- get profile for a specific techcrunch author
- get category
- list articles
- list all content tags
- rss
- list posts
- single category
- list techcrunch articles with filtering and pagination
- wordpress
- get an author profile
- media
- get author
- techcrunch technology news articles
- list all techcrunch content categories (startups, ai, security, etc.)
- single author profile
- techcrunch content categories
- get a specific category
- media attachments
- list media attachments
- get the full content of a specific techcrunch article by id
- news
- get post
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TechCrunch Content Discovery\n  description: Unified content discovery workflow for TechCrunch. Combines article retrieval, category and tag browsing, author\n    profiles, media access, and full-text search through the WordPress REST API. Designed for developers building news aggregators,\n    content analytics tools, media monitoring applications, and AI-powered research assistants that need to access TechCrunch's\n    technology news content.\n  tags:\n  - Content\n  - Media\n  - News\n  - RSS\n  - Startups\n  - Technology News\n  - Venture Capital\n  - WordPress\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: techcrunch-wp\n    baseUri: https://techcrunch.com/wp-json/wp/v2\n    description: TechCrunch WordPress REST API - public read access\n    resources:\n    - name: posts\n      path: /posts\n      description: TechCrunch article and post content\n      operations:\n \
  \     - name: list-posts\n        method: GET\n        description: Retrieve paginated list of published TechCrunch posts\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page (max 100)\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Filter posts after ISO8601 date\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: Filter posts before ISO8601 date\n        - name: author\n          in: query\n          type: array\n          required: false\n          description: Filter\
  \ by author IDs\n        - name: categories\n          in: query\n          type: array\n          required: false\n          description: Filter by category IDs\n        - name: tags\n          in: query\n          type: array\n          required: false\n          description: Filter by tag IDs\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Sort direction (asc/desc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-post\n        method: GET\n        description: Retrieve a specific post by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Post ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      description: Post categories\n      operations:\n      - name: list-categories\n        method: GET\n        description: List all TechCrunch categories\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search categories\n        - name: hide_empty\n          in: query\n          type: boolean\n          required: false\n          description: Hide empty categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ get-category\n        method: GET\n        description: Get a specific category\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Category ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Post tags\n      operations:\n      - name: list-tags\n        method: GET\n        description: List all TechCrunch tags\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search tags\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tag\n        method: GET\n        description: Get a specific tag\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Tag ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authors\n      path: /users\n      description: Authors and contributors\n      operations:\n      - name: list-authors\n        method: GET\n        description: List TechCrunch authors and contributors\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: search\n      \
  \    in: query\n          type: string\n          required: false\n          description: Search authors\n        - name: who\n          in: query\n          type: string\n          required: false\n          description: Filter to authors only\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-author\n        method: GET\n        description: Get a specific author\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Author ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: media\n      path: /media\n      description: Media attachments and images\n      operations:\n      - name: list-media\n        method: GET\n        description: List media attachments\n        inputParameters:\n        - name: page\n          in:\
  \ query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: media_type\n          in: query\n          type: string\n          required: false\n          description: Filter by media type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-media\n        method: GET\n        description: Get a specific media item\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Media ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Full-text content search\n      operations:\n      - name: search-content\n\
  \        method: GET\n        description: Search across all TechCrunch content\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Content type filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: content-discovery-api\n    description: Unified REST API for TechCrunch content discovery and retrieval.\n    resources:\n    - path: /v1/posts\n      name: posts\n   \
  \   description: TechCrunch technology news articles\n      operations:\n      - method: GET\n        name: list-posts\n        description: List TechCrunch articles with filtering and pagination\n        call: techcrunch-wp.list-posts\n        with:\n          search: rest.search\n          categories: rest.categories\n          tags: rest.tags\n          author: rest.author\n          after: rest.after\n          before: rest.before\n          page: rest.page\n          per_page: rest.per_page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/posts/{id}\n      name: post\n      description: Single article retrieval\n      operations:\n      - method: GET\n        name: get-post\n        description: Get a specific TechCrunch article\n        call: techcrunch-wp.get-post\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description:\
  \ TechCrunch content categories\n      operations:\n      - method: GET\n        name: list-categories\n        description: List all content categories\n        call: techcrunch-wp.list-categories\n        with:\n          search: rest.search\n          hide_empty: rest.hide_empty\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories/{id}\n      name: category\n      description: Single category\n      operations:\n      - method: GET\n        name: get-category\n        description: Get a specific category\n        call: techcrunch-wp.get-category\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: TechCrunch content tags\n      operations:\n      - method: GET\n        name: list-tags\n        description: List all content tags\n        call: techcrunch-wp.list-tags\n        with:\n          search: rest.search\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authors\n      name: authors\n      description: TechCrunch authors and contributors\n      operations:\n      - method: GET\n        name: list-authors\n        description: List all TechCrunch authors\n        call: techcrunch-wp.list-authors\n        with:\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authors/{id}\n      name: author\n      description: Single author profile\n      operations:\n      - method: GET\n        name: get-author\n        description: Get an author profile\n        call: techcrunch-wp.get-author\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media\n      name: media\n      description: Media attachments\n      operations:\n      - method: GET\n        name: list-media\n        description: List media attachments\n \
  \       call: techcrunch-wp.list-media\n        with:\n          media_type: rest.media_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Full-text content search\n      operations:\n      - method: GET\n        name: search-content\n        description: Search across all TechCrunch content\n        call: techcrunch-wp.search-content\n        with:\n          search: rest.search\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: content-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted TechCrunch content discovery and research.\n    tools:\n    - name: search-articles\n      description: Search TechCrunch articles by keyword, topic, or company name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techcrunch-wp.search-content\n      with:\n   \
  \     search: tools.search\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-articles\n      description: List recent TechCrunch articles with optional filters by category, tag, author, or date\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techcrunch-wp.list-posts\n      with:\n        search: tools.search\n        categories: tools.categories\n        tags: tools.tags\n        author: tools.author\n        after: tools.after\n        before: tools.before\n        per_page: tools.per_page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-article\n      description: Get the full content of a specific TechCrunch article by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: techcrunch-wp.get-post\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-categories\n      description:\
  \ List all TechCrunch content categories (startups, AI, security, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techcrunch-wp.list-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-category\n      description: Get details for a specific content category\n      hints:\n        readOnly: true\n        openWorld: false\n      call: techcrunch-wp.get-category\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tags\n      description: List all TechCrunch content tags\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techcrunch-wp.list-tags\n      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-authors\n      description: List TechCrunch authors and journalists\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techcrunch-wp.list-authors\n\
  \      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-author\n      description: Get profile for a specific TechCrunch author\n      hints:\n        readOnly: true\n        openWorld: false\n      call: techcrunch-wp.get-author\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/techcrunch/refs/heads/main/capabilities/content-discovery.yaml
tags:
- Content
- Media
- News
- RSS
- Startups
- Technology News
- Venture Capital
- WordPress
tools:
- description: Search TechCrunch articles by keyword, topic, or company name
  hints:
    openWorld: true
    readOnly: true
  name: search-articles
- description: List recent TechCrunch articles with optional filters by category, tag, author, or date
  hints:
    openWorld: true
    readOnly: true
  name: list-articles
- description: Get the full content of a specific TechCrunch article by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-article
- description: List all TechCrunch content categories (startups, AI, security, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: Get details for a specific content category
  hints:
    openWorld: false
    readOnly: true
  name: get-category
- description: List all TechCrunch content tags
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: List TechCrunch authors and journalists
  hints:
    openWorld: true
    readOnly: true
  name: list-authors
- description: Get profile for a specific TechCrunch author
  hints:
    openWorld: false
    readOnly: true
  name: get-author
---
