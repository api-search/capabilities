---
categories: []
consumed_apis: []
description: Content discovery capability for TechRepublic's technology news and analysis. Enables searching, browsing, and retrieving enterprise IT articles, category taxonomies, author profiles, and media assets via the WordPress REST API. Used by content aggregators, research tools, AI assistants, and enterprise news monitoring applications.
layout: capability
name: TechRepublic Content Discovery
operations:
- description: List and search TechRepublic technology articles.
  method: GET
  name: list-articles
  path: /v1/articles
- description: Get a specific TechRepublic article by ID.
  method: GET
  name: get-article
  path: /v1/articles/{id}
- description: List TechRepublic topic categories.
  method: GET
  name: list-topics
  path: /v1/topics
- description: Get a specific TechRepublic topic category by ID.
  method: GET
  name: get-topic
  path: /v1/topics/{id}
- description: List TechRepublic content tags.
  method: GET
  name: list-tags
  path: /v1/tags
- description: List TechRepublic authors.
  method: GET
  name: list-authors
  path: /v1/authors
- description: Get a specific TechRepublic author by ID.
  method: GET
  name: get-author
  path: /v1/authors/{id}
- description: List TechRepublic media assets.
  method: GET
  name: list-media
  path: /v1/media
personas: []
provider_name: TechRepublic
provider_slug: techrepublic
search_terms:
- get a specific techrepublic topic category by id.
- techrepublic technology articles and news posts.
- list techrepublic topic categories.
- search tags
- get details about a specific techrepublic topic category.
- list tags
- techrepublic media assets and images.
- enterprise it
- list and search techrepublic technology articles.
- get article
- get profile information for a specific techrepublic author.
- publishing
- list all techrepublic topic categories for content navigation.
- techrepublic authors and contributors.
- list techrepublic authors and contributors.
- list media
- techrepublic
- a specific techrepublic author profile.
- retrieve the full content of a specific techrepublic article by id.
- get a specific techrepublic article by id.
- list techrepublic content tags.
- search techrepublic content tags for topic discovery.
- technology news
- list authors
- content
- list techrepublic authors.
- techrepublic content tags.
- search articles
- list articles
- list topics
- search techrepublic articles by keyword, topic, date range, or author.
- wordpress
- content discovery
- media
- get author
- a specific techrepublic topic category.
- a specific techrepublic article.
- get topic
- techrepublic topic categories.
- get a specific techrepublic author by id.
- list techrepublic media assets.
- list techrepublic media assets including images and attachments.
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TechRepublic Content Discovery\n  description: Content discovery capability for TechRepublic's technology news and analysis. Enables searching, browsing,\n    and retrieving enterprise IT articles, category taxonomies, author profiles, and media assets via the WordPress REST API.\n    Used by content aggregators, research tools, AI assistants, and enterprise news monitoring applications.\n  tags:\n  - TechRepublic\n  - Content Discovery\n  - Technology News\n  - Enterprise IT\n  - WordPress\n  - Media\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: techrepublic-wp\n    baseUri: https://www.techrepublic.com/wp-json/wp/v2\n    description: TechRepublic WordPress REST API v2 - content access endpoints.\n    resources:\n    - name: posts\n      path: /posts\n      description: TechRepublic articles and news posts.\n      operations:\n      - name: list-posts\n        method: GET\n\
  \        description: Retrieve a collection of published posts.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return (max 100).\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Limit to posts published after a given ISO 8601 date.\n        - name: before\n          in: query\n          type: string\n          required: false\n          description: Limit to posts published before a given ISO 8601 date.\n        - name: categories\n          in: query\n          type: array\n       \
  \   required: false\n          description: Limit to posts in specified category IDs.\n        - name: tags\n          in: query\n          type: array\n          required: false\n          description: Limit to posts with specified tag IDs.\n        - name: orderby\n          in: query\n          type: string\n          required: false\n          description: Sort collection by attribute.\n        - name: order\n          in: query\n          type: string\n          required: false\n          description: Order sort ascending or descending.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-post\n        method: GET\n        description: Retrieve a specific post by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the post.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      description: TechRepublic content categories and topic areas.\n      operations:\n      - name: list-categories\n        method: GET\n        description: Retrieve a collection of categories.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        - name: hide_empty\n          in: query\n          type: boolean\n          required: false\n          description: Whether to hide terms not assigned to any posts.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-category\n        method: GET\n        description: Retrieve a specific category by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the category.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: TechRepublic content tags.\n      operations:\n      - name: list-tags\n        method: GET\n        description: Retrieve a collection of tags.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n       \
  \   description: Maximum number of items to return.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-tag\n        method: GET\n        description: Retrieve a specific tag by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authors\n      path: /users\n      description: TechRepublic authors and contributors.\n      operations:\n      - name: list-authors\n        method: GET\n        description: Retrieve a collection of authors.\n        inputParameters:\n        - name:\
  \ page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-author\n        method: GET\n        description: Retrieve a specific author by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the author.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ media\n      path: /media\n      description: TechRepublic media attachments and images.\n      operations:\n      - name: list-media\n        method: GET\n        description: Retrieve a collection of media items.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        - name: media_type\n          in: query\n          type: string\n          required: false\n          description: Limit to attachments of a particular media type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n      \
  \    value: $.\n      - name: get-media\n        method: GET\n        description: Retrieve a specific media item by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the media item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages\n      path: /pages\n      description: TechRepublic static pages.\n      operations:\n      - name: list-pages\n        method: GET\n        description: Retrieve a collection of pages.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Current page of the collection.\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: search\n      \
  \    in: query\n          type: string\n          required: false\n          description: Limit results to those matching a string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-page\n        method: GET\n        description: Retrieve a specific page by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Unique identifier for the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: techrepublic-content-api\n    description: Unified REST API for discovering and retrieving TechRepublic content.\n    resources:\n    - path: /v1/articles\n      name: articles\n      description: TechRepublic technology articles and news posts.\n      operations:\n      - method: GET\n\
  \        name: list-articles\n        description: List and search TechRepublic technology articles.\n        call: techrepublic-wp.list-posts\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          search: rest.search\n          categories: rest.categories\n          tags: rest.tags\n          after: rest.after\n          before: rest.before\n          orderby: rest.orderby\n          order: rest.order\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/articles/{id}\n      name: article\n      description: A specific TechRepublic article.\n      operations:\n      - method: GET\n        name: get-article\n        description: Get a specific TechRepublic article by ID.\n        call: techrepublic-wp.get-post\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topics\n      name: topics\n      description: TechRepublic topic categories.\n  \
  \    operations:\n      - method: GET\n        name: list-topics\n        description: List TechRepublic topic categories.\n        call: techrepublic-wp.list-categories\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          search: rest.search\n          hide_empty: rest.hide_empty\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/topics/{id}\n      name: topic\n      description: A specific TechRepublic topic category.\n      operations:\n      - method: GET\n        name: get-topic\n        description: Get a specific TechRepublic topic category by ID.\n        call: techrepublic-wp.get-category\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: TechRepublic content tags.\n      operations:\n      - method: GET\n        name: list-tags\n        description: List TechRepublic content tags.\n \
  \       call: techrepublic-wp.list-tags\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          search: rest.search\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/authors\n      name: authors\n      description: TechRepublic authors and contributors.\n      operations:\n      - method: GET\n        name: list-authors\n        description: List TechRepublic authors.\n        call: techrepublic-wp.list-authors\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          search: rest.search\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/authors/{id}\n      name: author\n      description: A specific TechRepublic author profile.\n      operations:\n      - method: GET\n        name: get-author\n        description: Get a specific TechRepublic author by ID.\n        call: techrepublic-wp.get-author\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/media\n      name: media\n      description: TechRepublic media assets and images.\n      operations:\n      - method: GET\n        name: list-media\n        description: List TechRepublic media assets.\n        call: techrepublic-wp.list-media\n        with:\n          page: rest.page\n          per_page: rest.per_page\n          search: rest.search\n          media_type: rest.media_type\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: techrepublic-content-mcp\n    transport: http\n    description: MCP server for AI-assisted TechRepublic content discovery and research.\n    tools:\n    - name: search-articles\n      description: Search TechRepublic articles by keyword, topic, date range, or author.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: techrepublic-wp.list-posts\n      with:\n        search: tools.search\n        categories:\
  \ tools.categories\n        tags: tools.tags\n        after: tools.after\n        before: tools.before\n        per_page: tools.per_page\n        orderby: tools.orderby\n        order: tools.order\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-article\n      description: Retrieve the full content of a specific TechRepublic article by ID.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.get-post\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-topics\n      description: List all TechRepublic topic categories for content navigation.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.list-categories\n      with:\n        per_page: tools.per_page\n        hide_empty: tools.hide_empty\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-topic\n      description: Get details about a specific TechRepublic topic category.\n\
  \      hints:\n        readOnly: true\n      call: techrepublic-wp.get-category\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-tags\n      description: Search TechRepublic content tags for topic discovery.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.list-tags\n      with:\n        search: tools.search\n        per_page: tools.per_page\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-authors\n      description: List TechRepublic authors and contributors.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.list-authors\n      with:\n        search: tools.search\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-author\n      description: Get profile information for a specific TechRepublic author.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.get-author\n      with:\n        id: tools.id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-media\n      description: List TechRepublic media assets including images and attachments.\n      hints:\n        readOnly: true\n      call: techrepublic-wp.list-media\n      with:\n        search: tools.search\n        media_type: tools.media_type\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/techrepublic/refs/heads/main/capabilities/content-discovery.yaml
tags:
- TechRepublic
- Content Discovery
- Technology News
- Enterprise IT
- WordPress
- Media
tools:
- description: Search TechRepublic articles by keyword, topic, date range, or author.
  hints:
    openWorld: true
    readOnly: true
  name: search-articles
- description: Retrieve the full content of a specific TechRepublic article by ID.
  hints:
    readOnly: true
  name: get-article
- description: List all TechRepublic topic categories for content navigation.
  hints:
    readOnly: true
  name: list-topics
- description: Get details about a specific TechRepublic topic category.
  hints:
    readOnly: true
  name: get-topic
- description: Search TechRepublic content tags for topic discovery.
  hints:
    readOnly: true
  name: search-tags
- description: List TechRepublic authors and contributors.
  hints:
    readOnly: true
  name: list-authors
- description: Get profile information for a specific TechRepublic author.
  hints:
    readOnly: true
  name: get-author
- description: List TechRepublic media assets including images and attachments.
  hints:
    readOnly: true
  name: list-media
---
