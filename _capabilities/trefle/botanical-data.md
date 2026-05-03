---
categories: []
consumed_apis:
- trefle
description: Workflow capability for Trefle botanical data covering plant search, species detail retrieval, taxonomy navigation, and geographic distribution analysis. Designed for gardening applications, agricultural tools, ecological research platforms, and farming automation systems that need plant species data.
layout: capability
name: Trefle Botanical Data
operations:
- description: List plant species with pagination
  method: GET
  name: list-plants
  path: /v1/plants
- description: Search plants by common or scientific name
  method: GET
  name: search-plants
  path: /v1/plants/search
- description: Get a specific plant by ID or slug
  method: GET
  name: get-plant
  path: /v1/plants/{id}
- description: List species with taxonomy and growth data
  method: GET
  name: list-species
  path: /v1/species
- description: Search species by name
  method: GET
  name: search-species
  path: /v1/species/search
- description: Get full species data including morphology and distribution
  method: GET
  name: get-species
  path: /v1/species/{id}
- description: List all plant families
  method: GET
  name: list-families
  path: /v1/families
- description: List all plant genera
  method: GET
  name: list-genus
  path: /v1/genus
- description: List all distribution zones
  method: GET
  name: list-distributions
  path: /v1/distributions
- description: Get plants native or established in a geographic zone
  method: GET
  name: get-plants-by-distribution
  path: /v1/distributions/{id}/plants
personas: []
provider_name: Trefle
provider_slug: trefle
search_terms:
- search species by name
- list species
- open data
- browse geographic distribution zones
- list plant species with pagination
- search the trefle database for plant species by common or scientific name
- list plant genera
- browse and discover plant species
- plants
- list all plant genera in the trefle botanical taxonomy
- search plants
- browse plant genus taxonomy
- list geographic distribution zones used in trefle plant range data
- science
- browse plant family taxonomy
- get plants in region
- get basic information about a plant by trefle id or slug
- get species detail
- get full species data including morphology and distribution
- agriculture
- list plants
- list families
- list all plant families
- list plant families
- list all plant families in the trefle botanical taxonomy
- get plant details
- get comprehensive species data
- get plant
- get plants by distribution
- data api
- browse species with detailed botanical data
- get comprehensive species data including morphology, growth requirements, and distribution
- list all distribution zones
- ecology
- search trefle plant species by name for detailed botanical data
- botany
- list all plant genera
- list species with taxonomy and growth data
- get plants native or established in a geographic zone
- search plants by common or scientific name
- get species
- get plants in a specific region
- get a specific plant by id or slug
- get plant species native or established in a specific geographic region
- list distributions
- list genus
- search for plants by name
- search species
- list distribution zones
- list plant species from trefle with optional pagination
slug: botanical-data
source_filename: botanical-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trefle Botanical Data\"\n  description: >-\n    Workflow capability for Trefle botanical data covering plant search, species\n    detail retrieval, taxonomy navigation, and geographic distribution analysis.\n    Designed for gardening applications, agricultural tools, ecological research\n    platforms, and farming automation systems that need plant species data.\n  tags:\n    - Agriculture\n    - Botany\n    - Data API\n    - Ecology\n    - Open Data\n    - Plants\n    - Science\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TREFLE_TOKEN: TREFLE_TOKEN\n\ncapability:\n  consumes:\n    - import: trefle\n      location: ./shared/trefle-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trefle-botanical-api\n      description: \"Unified REST API for Trefle botanical data workflows.\"\n      resources:\n        - path: /v1/plants\n          name: plants\n\
  \          description: \"Browse and discover plant species\"\n          operations:\n            - method: GET\n              name: list-plants\n              description: \"List plant species with pagination\"\n              call: \"trefle.list-plants\"\n              with:\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plants/search\n          name: plant-search\n          description: \"Search for plants by name\"\n          operations:\n            - method: GET\n              name: search-plants\n              description: \"Search plants by common or scientific name\"\n              call: \"trefle.search-plants\"\n              with:\n                q: \"rest.q\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plants/{id}\n          name: plant-detail\n       \
  \   description: \"Get plant details\"\n          operations:\n            - method: GET\n              name: get-plant\n              description: \"Get a specific plant by ID or slug\"\n              call: \"trefle.get-plant\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/species\n          name: species\n          description: \"Browse species with detailed botanical data\"\n          operations:\n            - method: GET\n              name: list-species\n              description: \"List species with taxonomy and growth data\"\n              call: \"trefle.list-species\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/species/search\n          name: species-search\n          description: \"Search species\"\n          operations:\n            - method: GET\n              name: search-species\n\
  \              description: \"Search species by name\"\n              call: \"trefle.search-species\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/species/{id}\n          name: species-detail\n          description: \"Get comprehensive species data\"\n          operations:\n            - method: GET\n              name: get-species\n              description: \"Get full species data including morphology and distribution\"\n              call: \"trefle.get-species\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/families\n          name: families\n          description: \"Browse plant family taxonomy\"\n          operations:\n            - method: GET\n              name: list-families\n              description: \"List all plant families\"\
  \n              call: \"trefle.list-families\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/genus\n          name: genus\n          description: \"Browse plant genus taxonomy\"\n          operations:\n            - method: GET\n              name: list-genus\n              description: \"List all plant genera\"\n              call: \"trefle.list-genus\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/distributions\n          name: distributions\n          description: \"Browse geographic distribution zones\"\n          operations:\n            - method: GET\n              name: list-distributions\n              description: \"List all distribution zones\"\n              call: \"trefle.list-distributions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/distributions/{id}/plants\n\
  \          name: plants-by-distribution\n          description: \"Get plants in a specific region\"\n          operations:\n            - method: GET\n              name: get-plants-by-distribution\n              description: \"Get plants native or established in a geographic zone\"\n              call: \"trefle.get-plants-by-distribution\"\n              with:\n                id: \"rest.id\"\n                filter[establishment]: \"rest.establishment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trefle-botanical-mcp\n      transport: http\n      description: \"MCP server for AI-assisted botanical data queries with Trefle.\"\n      tools:\n        # Plant search and discovery\n        - name: search-plants\n          description: \"Search the Trefle database for plant species by common or scientific name\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"trefle.search-plants\"\n          with:\n            q: \"tools.q\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plants\n          description: \"List plant species from Trefle with optional pagination\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trefle.list-plants\"\n          with:\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-plant\n          description: \"Get basic information about a plant by Trefle ID or slug\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trefle.get-plant\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Species detail\n        - name: search-species\n\
  \          description: \"Search Trefle plant species by name for detailed botanical data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trefle.search-species\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-species-detail\n          description: \"Get comprehensive species data including morphology, growth requirements, and distribution\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trefle.get-species\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Taxonomy\n        - name: list-plant-families\n          description: \"List all plant families in the Trefle botanical taxonomy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trefle.list-families\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plant-genera\n          description: \"List all plant genera in the Trefle botanical taxonomy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trefle.list-genus\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        # Distribution\n        - name: list-distribution-zones\n          description: \"List geographic distribution zones used in Trefle plant range data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"trefle.list-distributions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-plants-in-region\n          description: \"Get plant species native or established in a specific geographic region\"\n          hints:\n            readOnly: true\n            openWorld: false\n     \
  \     call: \"trefle.get-plants-by-distribution\"\n          with:\n            id: \"tools.id\"\n            filter[establishment]: \"tools.establishment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trefle/refs/heads/main/capabilities/botanical-data.yaml
tags:
- Agriculture
- Botany
- Data API
- Ecology
- Open Data
- Plants
- Science
tools:
- description: Search the Trefle database for plant species by common or scientific name
  hints:
    openWorld: true
    readOnly: true
  name: search-plants
- description: List plant species from Trefle with optional pagination
  hints:
    openWorld: true
    readOnly: true
  name: list-plants
- description: Get basic information about a plant by Trefle ID or slug
  hints:
    openWorld: false
    readOnly: true
  name: get-plant
- description: Search Trefle plant species by name for detailed botanical data
  hints:
    openWorld: true
    readOnly: true
  name: search-species
- description: Get comprehensive species data including morphology, growth requirements, and distribution
  hints:
    openWorld: false
    readOnly: true
  name: get-species-detail
- description: List all plant families in the Trefle botanical taxonomy
  hints:
    openWorld: true
    readOnly: true
  name: list-plant-families
- description: List all plant genera in the Trefle botanical taxonomy
  hints:
    openWorld: true
    readOnly: true
  name: list-plant-genera
- description: List geographic distribution zones used in Trefle plant range data
  hints:
    openWorld: true
    readOnly: true
  name: list-distribution-zones
- description: Get plant species native or established in a specific geographic region
  hints:
    openWorld: false
    readOnly: true
  name: get-plants-in-region
---
