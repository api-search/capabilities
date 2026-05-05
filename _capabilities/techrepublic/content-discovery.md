---
categories: []
consumed_apis:
- techrepublic-wp
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
- techrepublic topic categories.
- get author
- wordpress
- a specific techrepublic article.
- search tags
- list techrepublic topic categories.
- list techrepublic content tags.
- content discovery
- list techrepublic authors and contributors.
- enterprise it
- techrepublic authors and contributors.
- list authors
- get a specific techrepublic article by id.
- list and search techrepublic technology articles.
- techrepublic media assets and images.
- list techrepublic authors.
- search techrepublic content tags for topic discovery.
- list techrepublic media assets.
- get a specific techrepublic topic category by id.
- techrepublic technology articles and news posts.
- get details about a specific techrepublic topic category.
- publishing
- search articles
- get article
- retrieve the full content of a specific techrepublic article by id.
- list topics
- a specific techrepublic topic category.
- techrepublic content tags.
- list media
- list all techrepublic topic categories for content navigation.
- media
- search techrepublic articles by keyword, topic, date range, or author.
- get a specific techrepublic author by id.
- content
- list techrepublic media assets including images and attachments.
- list articles
- get profile information for a specific techrepublic author.
- get topic
- a specific techrepublic author profile.
- technology news
- list tags
- techrepublic
slug: content-discovery
source_filename: content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TechRepublic Content Discovery\"\n  description: >-\n    Content discovery capability for TechRepublic's technology news and analysis.\n    Enables searching, browsing, and retrieving enterprise IT articles, category\n    taxonomies, author profiles, and media assets via the WordPress REST API.\n    Used by content aggregators, research tools, AI assistants, and enterprise\n    news monitoring applications.\n  tags:\n    - TechRepublic\n    - Content Discovery\n    - Technology News\n    - Enterprise IT\n    - WordPress\n    - Media\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: techrepublic-wp\n      location: ./shared/wordpress-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: techrepublic-content-api\n      description: \"Unified REST API for discovering and retrieving TechRepublic content.\"\n      resources:\n        - path: /v1/articles\n \
  \         name: articles\n          description: \"TechRepublic technology articles and news posts.\"\n          operations:\n            - method: GET\n              name: list-articles\n              description: \"List and search TechRepublic technology articles.\"\n              call: \"techrepublic-wp.list-posts\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                search: \"rest.search\"\n                categories: \"rest.categories\"\n                tags: \"rest.tags\"\n                after: \"rest.after\"\n                before: \"rest.before\"\n                orderby: \"rest.orderby\"\n                order: \"rest.order\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/articles/{id}\n          name: article\n          description: \"A specific TechRepublic article.\"\n          operations:\n            - method: GET\n             \
  \ name: get-article\n              description: \"Get a specific TechRepublic article by ID.\"\n              call: \"techrepublic-wp.get-post\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/topics\n          name: topics\n          description: \"TechRepublic topic categories.\"\n          operations:\n            - method: GET\n              name: list-topics\n              description: \"List TechRepublic topic categories.\"\n              call: \"techrepublic-wp.list-categories\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                search: \"rest.search\"\n                hide_empty: \"rest.hide_empty\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/topics/{id}\n          name: topic\n          description: \"A specific\
  \ TechRepublic topic category.\"\n          operations:\n            - method: GET\n              name: get-topic\n              description: \"Get a specific TechRepublic topic category by ID.\"\n              call: \"techrepublic-wp.get-category\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags\n          name: tags\n          description: \"TechRepublic content tags.\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List TechRepublic content tags.\"\n              call: \"techrepublic-wp.list-tags\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/authors\n          name: authors\n\
  \          description: \"TechRepublic authors and contributors.\"\n          operations:\n            - method: GET\n              name: list-authors\n              description: \"List TechRepublic authors.\"\n              call: \"techrepublic-wp.list-authors\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/authors/{id}\n          name: author\n          description: \"A specific TechRepublic author profile.\"\n          operations:\n            - method: GET\n              name: get-author\n              description: \"Get a specific TechRepublic author by ID.\"\n              call: \"techrepublic-wp.get-author\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/media\n          name: media\n          description: \"TechRepublic media assets and images.\"\n          operations:\n            - method: GET\n              name: list-media\n              description: \"List TechRepublic media assets.\"\n              call: \"techrepublic-wp.list-media\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                search: \"rest.search\"\n                media_type: \"rest.media_type\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: techrepublic-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TechRepublic content discovery and research.\"\n      tools:\n        - name: search-articles\n          description: \"Search TechRepublic articles by keyword, topic, date range, or author.\"\n          hints:\n            readOnly: true\n \
  \           openWorld: true\n          call: \"techrepublic-wp.list-posts\"\n          with:\n            search: \"tools.search\"\n            categories: \"tools.categories\"\n            tags: \"tools.tags\"\n            after: \"tools.after\"\n            before: \"tools.before\"\n            per_page: \"tools.per_page\"\n            orderby: \"tools.orderby\"\n            order: \"tools.order\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-article\n          description: \"Retrieve the full content of a specific TechRepublic article by ID.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.get-post\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-topics\n          description: \"List all TechRepublic topic categories for content navigation.\"\n          hints:\n            readOnly:\
  \ true\n          call: \"techrepublic-wp.list-categories\"\n          with:\n            per_page: \"tools.per_page\"\n            hide_empty: \"tools.hide_empty\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-topic\n          description: \"Get details about a specific TechRepublic topic category.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.get-category\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-tags\n          description: \"Search TechRepublic content tags for topic discovery.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.list-tags\"\n          with:\n            search: \"tools.search\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        -\
  \ name: list-authors\n          description: \"List TechRepublic authors and contributors.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.list-authors\"\n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-author\n          description: \"Get profile information for a specific TechRepublic author.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.get-author\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-media\n          description: \"List TechRepublic media assets including images and attachments.\"\n          hints:\n            readOnly: true\n          call: \"techrepublic-wp.list-media\"\n          with:\n            search: \"tools.search\"\n            media_type: \"tools.media_type\"\n  \
  \        outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
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
