---
api_specs:
- filename: thecocktaildb-openapi.yml
  format: yaml
  label: cocktaildb
  slug: cocktaildb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/thecocktaildb/refs/heads/main/openapi/thecocktaildb-openapi.yml
categories: []
consumed_apis:
- cocktaildb
description: Unified workflow for cocktail recipe discovery, search, and drink recommendations. Combines search, lookup, filter, and listing capabilities for bartenders, mixologists, and cocktail enthusiasts.
layout: capability
name: TheCocktailDB Cocktail Discovery
operations:
- description: Search for cocktails by name
  method: GET
  name: search-cocktails
  path: /v1/cocktails
- description: Retrieve a random cocktail recipe
  method: GET
  name: get-random-cocktail
  path: /v1/cocktails/random
- description: Look up a cocktail by ID
  method: GET
  name: lookup-cocktail
  path: /v1/cocktails/{id}
- description: Filter cocktails by ingredient, category, glass, or alcoholic status
  method: GET
  name: filter-cocktails
  path: /v1/cocktails/filter
- description: List all drink categories
  method: GET
  name: list-categories
  path: /v1/categories
personas: []
provider_name: TheCocktailDB
provider_slug: thecocktaildb
search_terms:
- search for a cocktail ingredient by name
- get random cocktail
- browse all cocktails starting with a specific letter
- find cocktails that use a specific ingredient
- list all available ingredients in the database
- filter by category
- get details for a specific ingredient by its id
- list ingredients
- filter by glass type
- filter by alcoholic status
- get a random cocktail
- filter by ingredient
- search cocktails
- filter cocktails by attributes
- search ingredients
- lookup cocktail by id
- lookup ingredient by id
- filter cocktails by ingredient, category, glass, or alcoholic status
- list glass types
- look up a cocktail by id
- browse cocktails by letter
- get a completely random cocktail recipe for inspiration
- search and browse cocktails
- food and beverage
- recipes
- retrieve a random cocktail recipe
- filter cocktails by glass type (e.g. cocktail glass, highball glass)
- cocktails
- lookup cocktail
- drinks
- list categories
- filter cocktails by category (e.g. cocktail, shot, punch)
- list all available glass types
- search for cocktails by name
- list drink categories
- search for cocktails by name (e.g. margarita, mojito)
- list all available drink categories
- list all drink categories
- full cocktail recipe details
- get full recipe details for a cocktail by its id
- filter cocktails
- filter cocktails by alcoholic or non-alcoholic status
slug: cocktail-discovery
source_filename: cocktail-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheCocktailDB Cocktail Discovery\"\n  description: \"Unified workflow for cocktail recipe discovery, search, and drink recommendations. Combines search, lookup, filter, and listing capabilities for bartenders, mixologists, and cocktail enthusiasts.\"\n  tags:\n    - Cocktails\n    - Drinks\n    - Recipes\n    - Food And Beverage\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds: []\n\ncapability:\n  consumes:\n    - import: cocktaildb\n      location: ./shared/thecocktaildb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cocktail-discovery-api\n      description: \"Unified REST API for cocktail discovery and recipe lookup.\"\n      resources:\n        - path: /v1/cocktails\n          name: cocktails\n          description: \"Search and browse cocktails\"\n          operations:\n            - method: GET\n              name: search-cocktails\n              description: \"Search for cocktails\
  \ by name\"\n              call: \"cocktaildb.search-cocktails\"\n              with:\n                s: \"rest.s\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cocktails/random\n          name: random-cocktail\n          description: \"Get a random cocktail\"\n          operations:\n            - method: GET\n              name: get-random-cocktail\n              description: \"Retrieve a random cocktail recipe\"\n              call: \"cocktaildb.get-random-cocktail\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cocktails/{id}\n          name: cocktail-detail\n          description: \"Full cocktail recipe details\"\n          operations:\n            - method: GET\n              name: lookup-cocktail\n              description: \"Look up a cocktail by ID\"\n              call: \"cocktaildb.lookup-by-id\"\n              with:\n       \
  \         i: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cocktails/filter\n          name: cocktail-filter\n          description: \"Filter cocktails by attributes\"\n          operations:\n            - method: GET\n              name: filter-cocktails\n              description: \"Filter cocktails by ingredient, category, glass, or alcoholic status\"\n              call: \"cocktaildb.filter-cocktails\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description: \"List drink categories\"\n          operations:\n            - method: GET\n              name: list-categories\n              description: \"List all drink categories\"\n              call: \"cocktaildb.list-filter-values\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cocktail-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cocktail discovery and recipe recommendations.\"\n      tools:\n        - name: search-cocktails\n          description: \"Search for cocktails by name (e.g. margarita, mojito)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.search-cocktails\"\n          with:\n            s: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-cocktails-by-letter\n          description: \"Browse all cocktails starting with a specific letter\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.search-cocktails\"\n          with:\n            f: \"tools.letter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ search-ingredients\n          description: \"Search for a cocktail ingredient by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.search-cocktails\"\n          with:\n            i: \"tools.ingredient\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-cocktail-by-id\n          description: \"Get full recipe details for a cocktail by its ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.lookup-by-id\"\n          with:\n            i: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-ingredient-by-id\n          description: \"Get details for a specific ingredient by its ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.lookup-by-id\"\n          with:\n            iid: \"\
  tools.ingredient_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-random-cocktail\n          description: \"Get a completely random cocktail recipe for inspiration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.get-random-cocktail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-ingredient\n          description: \"Find cocktails that use a specific ingredient\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.filter-cocktails\"\n          with:\n            i: \"tools.ingredient\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-alcoholic-status\n          description: \"Filter cocktails by alcoholic or non-alcoholic status\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: true\n          call: \"cocktaildb.filter-cocktails\"\n          with:\n            a: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-category\n          description: \"Filter cocktails by category (e.g. Cocktail, Shot, Punch)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.filter-cocktails\"\n          with:\n            c: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-glass-type\n          description: \"Filter cocktails by glass type (e.g. Cocktail glass, Highball glass)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.filter-cocktails\"\n          with:\n            g: \"tools.glass\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n  \
  \      - name: list-categories\n          description: \"List all available drink categories\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.list-filter-values\"\n          with:\n            c: list\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-glass-types\n          description: \"List all available glass types\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.list-filter-values\"\n          with:\n            g: list\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ingredients\n          description: \"List all available ingredients in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cocktaildb.list-filter-values\"\n          with:\n            i: list\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thecocktaildb/refs/heads/main/capabilities/cocktail-discovery.yaml
tags:
- Cocktails
- Drinks
- Recipes
- Food And Beverage
tools:
- description: Search for cocktails by name (e.g. margarita, mojito)
  hints:
    openWorld: true
    readOnly: true
  name: search-cocktails
- description: Browse all cocktails starting with a specific letter
  hints:
    openWorld: true
    readOnly: true
  name: browse-cocktails-by-letter
- description: Search for a cocktail ingredient by name
  hints:
    openWorld: true
    readOnly: true
  name: search-ingredients
- description: Get full recipe details for a cocktail by its ID
  hints:
    openWorld: true
    readOnly: true
  name: lookup-cocktail-by-id
- description: Get details for a specific ingredient by its ID
  hints:
    openWorld: true
    readOnly: true
  name: lookup-ingredient-by-id
- description: Get a completely random cocktail recipe for inspiration
  hints:
    openWorld: true
    readOnly: true
  name: get-random-cocktail
- description: Find cocktails that use a specific ingredient
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-ingredient
- description: Filter cocktails by alcoholic or non-alcoholic status
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-alcoholic-status
- description: Filter cocktails by category (e.g. Cocktail, Shot, Punch)
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-category
- description: Filter cocktails by glass type (e.g. Cocktail glass, Highball glass)
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-glass-type
- description: List all available drink categories
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: List all available glass types
  hints:
    openWorld: true
    readOnly: true
  name: list-glass-types
- description: List all available ingredients in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-ingredients
---
