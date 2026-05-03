---
api_specs:
- filename: the-cat-api-openapi.yml
  format: yaml
  label: catapi
  slug: catapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/the-cat-api/refs/heads/main/openapi/the-cat-api-openapi.yml
categories: []
consumed_apis:
- catapi
description: Workflow capability for discovering, browsing, and curating cat content. Combines image search with breed lookup, category filtering, voting, and favouriting to support cat app builders, media platforms, and educational tools.
layout: capability
name: Cat Content Discovery
operations:
- description: Search cat images with optional breed and category filters.
  method: GET
  name: search-images
  path: /v1/images
- description: Get details for a specific cat image.
  method: GET
  name: get-image
  path: /v1/images/{image_id}
- description: List all cat breeds with characteristics.
  method: GET
  name: list-breeds
  path: /v1/breeds
- description: Search cat breeds by name.
  method: GET
  name: search-breeds
  path: /v1/breeds/search
- description: List all image categories.
  method: GET
  name: list-categories
  path: /v1/categories
- description: List the user's favourite cat images.
  method: GET
  name: list-favourites
  path: /v1/favourites
- description: Save a cat image as a favourite.
  method: POST
  name: save-favourite
  path: /v1/favourites
- description: List all user votes.
  method: GET
  name: list-votes
  path: /v1/votes
- description: Cast an upvote or downvote on an image.
  method: POST
  name: create-vote
  path: /v1/votes
personas: []
provider_name: The Cat API
provider_slug: the-cat-api
search_terms:
- browse image categories.
- search cat breeds by name.
- cast an upvote or downvote on an image.
- list all cat images saved as favourites by the current user.
- animals
- cast an upvote (1) or downvote (0) on a cat image.
- search for cat images, optionally filtered by breed or category.
- create vote
- list all cat breeds with characteristics.
- list the user's favourite cat images.
- cast and track votes on cat images.
- list all available cat image categories for filtering searches.
- images
- list breeds
- save a cat image as a favourite.
- save a cat image to the user's favourites collection.
- list user favourites
- list all votes cast by the current user on cat images.
- search cat images
- save cat favourite
- media
- search images
- list all image categories.
- get details for a specific cat image.
- content discovery
- get image
- list favourites
- manage user favourite images.
- search cat breeds
- list categories
- search for cat breeds by name to find breed-specific information.
- retrieve details and metadata for a specific cat image by id.
- vote on image
- list all cat breeds with detailed characteristics, personality ratings, and origin information.
- list user votes
- retrieve a specific cat image.
- browse and search cat breeds.
- get cat image
- list all user votes.
- search breeds
- search and retrieve cat images.
- list votes
- list image categories
- cats
- search breeds by name.
- save favourite
- search cat images with optional breed and category filters.
- list cat breeds
slug: cat-content-discovery
source_filename: cat-content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Cat Content Discovery\"\n  description: >-\n    Workflow capability for discovering, browsing, and curating cat content.\n    Combines image search with breed lookup, category filtering, voting, and\n    favouriting to support cat app builders, media platforms, and educational tools.\n  tags:\n    - Animals\n    - Cats\n    - Content Discovery\n    - Images\n    - Media\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      CAT_API_KEY: CAT_API_KEY\n\ncapability:\n  consumes:\n    - import: catapi\n      location: ./shared/the-cat-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cat-content-api\n      description: \"Unified REST API for cat content discovery, breed research, and user curation.\"\n      resources:\n        - path: /v1/images\n          name: images\n          description: Search and retrieve cat images.\n          operations:\n         \
  \   - method: GET\n              name: search-images\n              description: Search cat images with optional breed and category filters.\n              call: \"catapi.search-images\"\n              with:\n                limit: \"rest.limit\"\n                breed_ids: \"rest.breed_ids\"\n                category_ids: \"rest.category_ids\"\n                has_breeds: \"rest.has_breeds\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/images/{image_id}\n          name: image-detail\n          description: Retrieve a specific cat image.\n          operations:\n            - method: GET\n              name: get-image\n              description: Get details for a specific cat image.\n              call: \"catapi.get-image\"\n              with:\n                image_id: \"rest.image_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/breeds\n\
  \          name: breeds\n          description: Browse and search cat breeds.\n          operations:\n            - method: GET\n              name: list-breeds\n              description: List all cat breeds with characteristics.\n              call: \"catapi.list-breeds\"\n              with:\n                limit: \"rest.limit\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/breeds/search\n          name: breed-search\n          description: Search breeds by name.\n          operations:\n            - method: GET\n              name: search-breeds\n              description: Search cat breeds by name.\n              call: \"catapi.search-breeds\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description:\
  \ Browse image categories.\n          operations:\n            - method: GET\n              name: list-categories\n              description: List all image categories.\n              call: \"catapi.list-categories\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/favourites\n          name: favourites\n          description: Manage user favourite images.\n          operations:\n            - method: GET\n              name: list-favourites\n              description: List the user's favourite cat images.\n              call: \"catapi.list-favourites\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: save-favourite\n              description: Save a cat image as a favourite.\n              call: \"catapi.save-favourite\"\n              with:\n                image_id: \"rest.image_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/votes\n          name: votes\n          description: Cast and track votes on cat images.\n          operations:\n            - method: GET\n              name: list-votes\n              description: List all user votes.\n              call: \"catapi.list-votes\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-vote\n              description: Cast an upvote or downvote on an image.\n              call: \"catapi.create-vote\"\n              with:\n                image_id: \"rest.image_id\"\n                value: \"rest.value\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cat-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cat content discovery, breed\
  \ research, and curation.\"\n      tools:\n        - name: search-cat-images\n          description: Search for cat images, optionally filtered by breed or category.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"catapi.search-images\"\n          with:\n            limit: \"tools.limit\"\n            breed_ids: \"tools.breed_ids\"\n            category_ids: \"tools.category_ids\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-cat-image\n          description: Retrieve details and metadata for a specific cat image by ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"catapi.get-image\"\n          with:\n            image_id: \"tools.image_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cat-breeds\n          description: List all cat breeds with detailed characteristics,\
  \ personality ratings, and origin information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"catapi.list-breeds\"\n          with:\n            limit: \"tools.limit\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: search-cat-breeds\n          description: Search for cat breeds by name to find breed-specific information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"catapi.search-breeds\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-image-categories\n          description: List all available cat image categories for filtering searches.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"catapi.list-categories\"\n          outputParameters:\n            -\
  \ type: array\n              mapping: \"$.\"\n        - name: list-user-favourites\n          description: List all cat images saved as favourites by the current user.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"catapi.list-favourites\"\n          with:\n            sub_id: \"tools.sub_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: save-cat-favourite\n          description: Save a cat image to the user's favourites collection.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"catapi.save-favourite\"\n          with:\n            image_id: \"tools.image_id\"\n            sub_id: \"tools.sub_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-user-votes\n          description: List all votes cast by the current user on cat images.\n    \
  \      hints:\n            readOnly: true\n            openWorld: false\n          call: \"catapi.list-votes\"\n          with:\n            sub_id: \"tools.sub_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: vote-on-image\n          description: Cast an upvote (1) or downvote (0) on a cat image.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"catapi.create-vote\"\n          with:\n            image_id: \"tools.image_id\"\n            value: \"tools.value\"\n            sub_id: \"tools.sub_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-cat-api/refs/heads/main/capabilities/cat-content-discovery.yaml
tags:
- Animals
- Cats
- Content Discovery
- Images
- Media
tools:
- description: Search for cat images, optionally filtered by breed or category.
  hints:
    openWorld: true
    readOnly: true
  name: search-cat-images
- description: Retrieve details and metadata for a specific cat image by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-cat-image
- description: List all cat breeds with detailed characteristics, personality ratings, and origin information.
  hints:
    openWorld: true
    readOnly: true
  name: list-cat-breeds
- description: Search for cat breeds by name to find breed-specific information.
  hints:
    openWorld: true
    readOnly: true
  name: search-cat-breeds
- description: List all available cat image categories for filtering searches.
  hints:
    openWorld: true
    readOnly: true
  name: list-image-categories
- description: List all cat images saved as favourites by the current user.
  hints:
    openWorld: false
    readOnly: true
  name: list-user-favourites
- description: Save a cat image to the user's favourites collection.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: save-cat-favourite
- description: List all votes cast by the current user on cat images.
  hints:
    openWorld: false
    readOnly: true
  name: list-user-votes
- description: Cast an upvote (1) or downvote (0) on a cat image.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: vote-on-image
---
