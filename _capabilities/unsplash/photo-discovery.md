---
api_specs:
- filename: unsplash-openapi.yml
  format: yaml
  label: unsplash
  slug: unsplash
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/unsplash/refs/heads/main/openapi/unsplash-openapi.yml
categories: []
consumed_apis:
- unsplash
description: Workflow capability for discovering and browsing high-quality photos using the Unsplash API. Enables developers, designers, and content creators to search for photos by keyword, browse editorial feeds, get random photos with filters, and explore photos by topic or collection. Used for building photo-powered applications, design tools, and content management systems.
layout: capability
name: Unsplash Photo Discovery
operations:
- description: Browse the Unsplash editorial photo feed
  method: GET
  name: list-photos
  path: /v1/photos
- description: Get a photo by ID
  method: GET
  name: get-photo
  path: /v1/photos/{id}
- description: Get a random photo with optional filters
  method: GET
  name: get-random-photo
  path: /v1/photos/random
- description: Search photos by keyword
  method: GET
  name: search-photos
  path: /v1/search/photos
- description: List editorial topics
  method: GET
  name: list-topics
  path: /v1/topics
- description: Get photos for a topic
  method: GET
  name: get-topic-photos
  path: /v1/topics/{id}/photos
- description: Get photos in a collection
  method: GET
  name: get-collection-photos
  path: /v1/collections/{id}/photos
- description: List photos by a specific user
  method: GET
  name: list-user-photos
  path: /v1/users/{username}/photos
personas: []
provider_name: Unsplash
provider_slug: unsplash
search_terms:
- editorial topics
- get collection photos
- photography
- photo search
- list photos
- photos
- open source
- get photos from a specific unsplash editorial topic (nature, architecture, travel, etc.)
- get full details of an unsplash photo by its id
- search collections
- list photos by a specific user
- unsplash
- list topics
- search photos by keyword
- get topic photos
- list editorial topics
- get a photo by id
- images
- get photos by topic
- get photos uploaded by a specific unsplash photographer
- browse editorial photos
- search photos
- search
- media
- stock photography
- get photo
- browse the unsplash editorial feed for curated high-quality photos
- photos by collection
- get photos for a topic
- photos by topic
- get photos in a collection
- browse the unsplash editorial photo feed
- stock photos
- get random photo
- single photo operations
- get all photos in a specific unsplash collection
- get user photos
- editorial photo feed
- photos by user
- random photo
- get a random photo with optional filters
- get a random unsplash photo, optionally filtered by query, orientation, or topic
- search unsplash for high-quality photos matching a keyword or description
- get photo by id
- list user photos
- creative
- search unsplash for curated photo collections
slug: photo-discovery
source_filename: photo-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unsplash Photo Discovery\n  description: >-\n    Workflow capability for discovering and browsing high-quality photos using the\n    Unsplash API. Enables developers, designers, and content creators to search for\n    photos by keyword, browse editorial feeds, get random photos with filters, and\n    explore photos by topic or collection. Used for building photo-powered applications,\n    design tools, and content management systems.\n  tags:\n    - Unsplash\n    - Photos\n    - Search\n    - Images\n    - Creative\n    - Stock Photography\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNSPLASH_ACCESS_KEY: UNSPLASH_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: unsplash\n      location: ./shared/unsplash.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unsplash-discovery-api\n      description: Unified REST API for Unsplash photo discovery.\n \
  \     resources:\n        - path: /v1/photos\n          name: photos\n          description: Editorial photo feed\n          operations:\n            - method: GET\n              name: list-photos\n              description: Browse the Unsplash editorial photo feed\n              call: \"unsplash.list-photos\"\n              with:\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                order_by: \"rest.order_by\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/photos/{id}\n          name: photo\n          description: Single photo operations\n          operations:\n            - method: GET\n              name: get-photo\n              description: Get a photo by ID\n              call: \"unsplash.get-photo\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n     \
  \   - path: /v1/photos/random\n          name: random-photo\n          description: Random photo\n          operations:\n            - method: GET\n              name: get-random-photo\n              description: Get a random photo with optional filters\n              call: \"unsplash.get-random-photo\"\n              with:\n                query: \"rest.query\"\n                orientation: \"rest.orientation\"\n                content_filter: \"rest.content_filter\"\n                count: \"rest.count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search/photos\n          name: photo-search\n          description: Photo search\n          operations:\n            - method: GET\n              name: search-photos\n              description: Search photos by keyword\n              call: \"unsplash.search-photos\"\n              with:\n                query: \"rest.query\"\n                page: \"rest.page\"\n\
  \                per_page: \"rest.per_page\"\n                orientation: \"rest.orientation\"\n                color: \"rest.color\"\n                content_filter: \"rest.content_filter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/topics\n          name: topics\n          description: Editorial topics\n          operations:\n            - method: GET\n              name: list-topics\n              description: List editorial topics\n              call: \"unsplash.list-topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/topics/{id}/photos\n          name: topic-photos\n          description: Photos by topic\n          operations:\n            - method: GET\n              name: get-topic-photos\n              description: Get photos for a topic\n              call: \"unsplash.get-topic-photos\"\n              with:\n         \
  \       id_or_slug: \"rest.id\"\n                page: \"rest.page\"\n                per_page: \"rest.per_page\"\n                orientation: \"rest.orientation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collections/{id}/photos\n          name: collection-photos\n          description: Photos by collection\n          operations:\n            - method: GET\n              name: get-collection-photos\n              description: Get photos in a collection\n              call: \"unsplash.get-collection-photos\"\n              with:\n                id: \"rest.id\"\n                page: \"rest.page\"\n                orientation: \"rest.orientation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/{username}/photos\n          name: user-photos\n          description: Photos by user\n          operations:\n            - method: GET\n\
  \              name: list-user-photos\n              description: List photos by a specific user\n              call: \"unsplash.list-user-photos\"\n              with:\n                username: \"rest.username\"\n                page: \"rest.page\"\n                order_by: \"rest.order_by\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: unsplash-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted photo discovery and selection using Unsplash.\n      tools:\n        - name: search-photos\n          description: Search Unsplash for high-quality photos matching a keyword or description\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unsplash.search-photos\"\n          with:\n            query: \"tools.query\"\n            per_page: \"tools.per_page\"\n            orientation: \"tools.orientation\"\n   \
  \         color: \"tools.color\"\n            content_filter: \"tools.content_filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-random-photo\n          description: Get a random Unsplash photo, optionally filtered by query, orientation, or topic\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unsplash.get-random-photo\"\n          with:\n            query: \"tools.query\"\n            orientation: \"tools.orientation\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-photo-by-id\n          description: Get full details of an Unsplash photo by its ID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unsplash.get-photo\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n        - name: browse-editorial-photos\n          description: Browse the Unsplash editorial feed for curated high-quality photos\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unsplash.list-photos\"\n          with:\n            page: \"tools.page\"\n            per_page: \"tools.per_page\"\n            order_by: \"tools.order_by\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-photos-by-topic\n          description: Get photos from a specific Unsplash editorial topic (nature, architecture, travel, etc.)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unsplash.get-topic-photos\"\n          with:\n            id_or_slug: \"tools.topic\"\n            per_page: \"tools.per_page\"\n            orientation: \"tools.orientation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: search-collections\n          description: Search Unsplash for curated photo collections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"unsplash.search-collections\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-collection-photos\n          description: Get all photos in a specific Unsplash collection\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unsplash.get-collection-photos\"\n          with:\n            id: \"tools.id\"\n            orientation: \"tools.orientation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user-photos\n          description: Get photos uploaded by a specific Unsplash photographer\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"unsplash.list-user-photos\"\n          with:\n            username: \"tools.username\"\n            per_page: \"tools.per_page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unsplash/refs/heads/main/capabilities/photo-discovery.yaml
tags:
- Unsplash
- Photos
- Search
- Images
- Creative
- Stock Photography
tools:
- description: Search Unsplash for high-quality photos matching a keyword or description
  hints:
    openWorld: true
    readOnly: true
  name: search-photos
- description: Get a random Unsplash photo, optionally filtered by query, orientation, or topic
  hints:
    openWorld: true
    readOnly: true
  name: get-random-photo
- description: Get full details of an Unsplash photo by its ID
  hints:
    openWorld: false
    readOnly: true
  name: get-photo-by-id
- description: Browse the Unsplash editorial feed for curated high-quality photos
  hints:
    openWorld: true
    readOnly: true
  name: browse-editorial-photos
- description: Get photos from a specific Unsplash editorial topic (nature, architecture, travel, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: get-photos-by-topic
- description: Search Unsplash for curated photo collections
  hints:
    openWorld: true
    readOnly: true
  name: search-collections
- description: Get all photos in a specific Unsplash collection
  hints:
    openWorld: false
    readOnly: true
  name: get-collection-photos
- description: Get photos uploaded by a specific Unsplash photographer
  hints:
    openWorld: false
    readOnly: true
  name: get-user-photos
---
