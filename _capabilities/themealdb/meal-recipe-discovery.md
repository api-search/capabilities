---
api_specs:
- filename: themealdb-openapi.yml
  format: yaml
  label: mealdb
  slug: mealdb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/themealdb/refs/heads/main/openapi/themealdb-openapi.yml
categories: []
consumed_apis:
- mealdb
description: Unified workflow for meal recipe discovery, search, and cooking inspiration. Combines search, lookup, filter, and category listing for home cooks, meal planners, and food enthusiasts.
layout: capability
name: TheMealDB Meal Recipe Discovery
operations:
- description: Search for meals by name
  method: GET
  name: search-meals
  path: /v1/meals
- description: Retrieve a random meal recipe
  method: GET
  name: get-random-meal
  path: /v1/meals/random
- description: Look up a meal by ID
  method: GET
  name: lookup-meal
  path: /v1/meals/{id}
- description: List all meal categories
  method: GET
  name: list-categories
  path: /v1/categories
- description: Filter meals by ingredient, category, or area
  method: GET
  name: filter-meals
  path: /v1/meals/filter
personas: []
provider_name: TheMealDB
provider_slug: themealdb
search_terms:
- meals
- filter meals by regional cuisine (e.g. italian, japanese, mexican)
- cooking
- nutrition
- food
- list all available ingredients in the database
- list all regional cuisines available in the database
- filter by category
- list ingredients
- filter meals
- filter meals by attributes
- get full recipe details for a meal by its id
- search for meal recipes by name (e.g. chicken, pasta, sushi)
- filter by ingredient
- retrieve a random meal recipe
- meal categories
- list all categories
- browse meals by letter
- full meal recipe details
- filter meals by category (e.g. chicken, seafood, dessert)
- browse all meals starting with a specific letter
- get a completely random meal recipe for cooking inspiration
- search meals
- filter by area
- find meals that use a specific ingredient
- search for meals by name
- recipes
- list areas
- filter meals by ingredient, category, or area
- lookup meal by id
- lookup meal
- list categories
- get random meal
- search and browse meal recipes
- look up a meal by id
- get a random meal recipe
- list all meal categories
- list all meal categories with thumbnails and descriptions
slug: meal-recipe-discovery
source_filename: meal-recipe-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheMealDB Meal Recipe Discovery\"\n  description: \"Unified workflow for meal recipe discovery, search, and cooking inspiration. Combines search, lookup, filter, and category listing for home cooks, meal planners, and food enthusiasts.\"\n  tags:\n    - Recipes\n    - Meals\n    - Food\n    - Cooking\n    - Nutrition\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds: []\n\ncapability:\n  consumes:\n    - import: mealdb\n      location: ./shared/themealdb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: meal-discovery-api\n      description: \"Unified REST API for meal recipe discovery and cooking inspiration.\"\n      resources:\n        - path: /v1/meals\n          name: meals\n          description: \"Search and browse meal recipes\"\n          operations:\n            - method: GET\n              name: search-meals\n              description: \"Search for meals by name\"\n              call:\
  \ \"mealdb.search-meals\"\n              with:\n                s: \"rest.s\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meals/random\n          name: random-meal\n          description: \"Get a random meal recipe\"\n          operations:\n            - method: GET\n              name: get-random-meal\n              description: \"Retrieve a random meal recipe\"\n              call: \"mealdb.get-random-meal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meals/{id}\n          name: meal-detail\n          description: \"Full meal recipe details\"\n          operations:\n            - method: GET\n              name: lookup-meal\n              description: \"Look up a meal by ID\"\n              call: \"mealdb.lookup-meal-by-id\"\n              with:\n                i: \"rest.id\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description: \"Meal categories\"\n          operations:\n            - method: GET\n              name: list-categories\n              description: \"List all meal categories\"\n              call: \"mealdb.list-all-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/meals/filter\n          name: meal-filter\n          description: \"Filter meals by attributes\"\n          operations:\n            - method: GET\n              name: filter-meals\n              description: \"Filter meals by ingredient, category, or area\"\n              call: \"mealdb.filter-meals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: meal-discovery-mcp\n      transport: http\n      description: \"MCP server for\
  \ AI-assisted meal recipe discovery and cooking planning.\"\n      tools:\n        - name: search-meals\n          description: \"Search for meal recipes by name (e.g. chicken, pasta, sushi)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.search-meals\"\n          with:\n            s: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-meals-by-letter\n          description: \"Browse all meals starting with a specific letter\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.search-meals\"\n          with:\n            f: \"tools.letter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lookup-meal-by-id\n          description: \"Get full recipe details for a meal by its ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"mealdb.lookup-meal-by-id\"\n          with:\n            i: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-random-meal\n          description: \"Get a completely random meal recipe for cooking inspiration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.get-random-meal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-all-categories\n          description: \"List all meal categories with thumbnails and descriptions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.list-all-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-ingredient\n          description: \"Find meals that use a specific ingredient\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: true\n          call: \"mealdb.filter-meals\"\n          with:\n            i: \"tools.ingredient\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-category\n          description: \"Filter meals by category (e.g. Chicken, Seafood, Dessert)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.filter-meals\"\n          with:\n            c: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-by-area\n          description: \"Filter meals by regional cuisine (e.g. Italian, Japanese, Mexican)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.filter-meals\"\n          with:\n            a: \"tools.area\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-areas\n   \
  \       description: \"List all regional cuisines available in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.list-filter-values\"\n          with:\n            a: list\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ingredients\n          description: \"List all available ingredients in the database\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"mealdb.list-filter-values\"\n          with:\n            i: list\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/themealdb/refs/heads/main/capabilities/meal-recipe-discovery.yaml
tags:
- Recipes
- Meals
- Food
- Cooking
- Nutrition
tools:
- description: Search for meal recipes by name (e.g. chicken, pasta, sushi)
  hints:
    openWorld: true
    readOnly: true
  name: search-meals
- description: Browse all meals starting with a specific letter
  hints:
    openWorld: true
    readOnly: true
  name: browse-meals-by-letter
- description: Get full recipe details for a meal by its ID
  hints:
    openWorld: true
    readOnly: true
  name: lookup-meal-by-id
- description: Get a completely random meal recipe for cooking inspiration
  hints:
    openWorld: true
    readOnly: true
  name: get-random-meal
- description: List all meal categories with thumbnails and descriptions
  hints:
    openWorld: true
    readOnly: true
  name: list-all-categories
- description: Find meals that use a specific ingredient
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-ingredient
- description: Filter meals by category (e.g. Chicken, Seafood, Dessert)
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-category
- description: Filter meals by regional cuisine (e.g. Italian, Japanese, Mexican)
  hints:
    openWorld: true
    readOnly: true
  name: filter-by-area
- description: List all regional cuisines available in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-areas
- description: List all available ingredients in the database
  hints:
    openWorld: true
    readOnly: true
  name: list-ingredients
---
