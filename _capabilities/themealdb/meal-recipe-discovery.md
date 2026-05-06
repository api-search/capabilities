---
categories: []
consumed_apis: []
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
- filter by ingredient
- meal categories
- browse meals by letter
- list all categories
- nutrition
- search for meal recipes by name (e.g. chicken, pasta, sushi)
- list all regional cuisines available in the database
- full meal recipe details
- retrieve a random meal recipe
- get random meal
- get a completely random meal recipe for cooking inspiration
- browse all meals starting with a specific letter
- get full recipe details for a meal by its id
- find meals that use a specific ingredient
- lookup meal by id
- search for meals by name
- filter meals by regional cuisine (e.g. italian, japanese, mexican)
- filter meals
- list all meal categories with thumbnails and descriptions
- look up a meal by id
- filter by area
- filter meals by attributes
- recipes
- list all meal categories
- search and browse meal recipes
- lookup meal
- cooking
- list ingredients
- filter meals by ingredient, category, or area
- get a random meal recipe
- list categories
- list all available ingredients in the database
- meals
- list areas
- food
- filter by category
- search meals
- filter meals by category (e.g. chicken, seafood, dessert)
slug: meal-recipe-discovery
source_filename: meal-recipe-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TheMealDB Meal Recipe Discovery\n  description: Unified workflow for meal recipe discovery, search, and cooking inspiration. Combines search, lookup, filter,\n    and category listing for home cooks, meal planners, and food enthusiasts.\n  tags:\n  - Recipes\n  - Meals\n  - Food\n  - Cooking\n  - Nutrition\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds: []\ncapability:\n  consumes:\n  - type: http\n    namespace: mealdb\n    baseUri: https://www.themealdb.com/api/json/v1/1\n    description: Open meal and recipe database API\n    resources:\n    - name: search\n      path: /search.php\n      description: Search meals by name or first letter\n      operations:\n      - name: search-meals\n        method: GET\n        description: Search for meals by name or first letter\n        inputParameters:\n        - name: s\n          in: query\n          type: string\n          required: false\n          description: Meal name to search\n\
  \        - name: f\n          in: query\n          type: string\n          required: false\n          description: First letter to browse alphabetically\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup\n      path: /lookup.php\n      description: Look up a meal by ID\n      operations:\n      - name: lookup-meal-by-id\n        method: GET\n        description: Retrieve full meal details by ID\n        inputParameters:\n        - name: i\n          in: query\n          type: string\n          required: true\n          description: Meal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: random\n      path: /random.php\n      description: Get a random meal\n      operations:\n      - name: get-random-meal\n        method: GET\n        description: Retrieve a single random meal with full recipe\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories.php\n      description: Get all meal categories\n      operations:\n      - name: list-all-categories\n        method: GET\n        description: Get all meal categories with thumbnails and descriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filter\n      path: /filter.php\n      description: Filter meals by ingredient, category, or area\n      operations:\n      - name: filter-meals\n        method: GET\n        description: Filter meals by ingredient, category, or region\n        inputParameters:\n        - name: i\n          in: query\n          type: string\n          required: false\n          description: Filter by ingredient\n        - name: c\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by category\n        - name: a\n          in: query\n          type: string\n          required: false\n          description: Filter by area/region\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list\n      path: /list.php\n      description: List available categories, areas, or ingredients\n      operations:\n      - name: list-filter-values\n        method: GET\n        description: List all available filter values for categories, areas, or ingredients\n        inputParameters:\n        - name: c\n          in: query\n          type: string\n          required: false\n          description: Set to 'list' for categories\n        - name: a\n          in: query\n          type: string\n          required: false\n          description: Set to 'list' for areas\n        - name: i\n          in: query\n          type: string\n          required: false\n          description:\
  \ Set to 'list' for ingredients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: meal-discovery-api\n    description: Unified REST API for meal recipe discovery and cooking inspiration.\n    resources:\n    - path: /v1/meals\n      name: meals\n      description: Search and browse meal recipes\n      operations:\n      - method: GET\n        name: search-meals\n        description: Search for meals by name\n        call: mealdb.search-meals\n        with:\n          s: rest.s\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meals/random\n      name: random-meal\n      description: Get a random meal recipe\n      operations:\n      - method: GET\n        name: get-random-meal\n        description: Retrieve a random meal recipe\n        call: mealdb.get-random-meal\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/meals/{id}\n      name: meal-detail\n      description: Full meal recipe details\n      operations:\n      - method: GET\n        name: lookup-meal\n        description: Look up a meal by ID\n        call: mealdb.lookup-meal-by-id\n        with:\n          i: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description: Meal categories\n      operations:\n      - method: GET\n        name: list-categories\n        description: List all meal categories\n        call: mealdb.list-all-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/meals/filter\n      name: meal-filter\n      description: Filter meals by attributes\n      operations:\n      - method: GET\n        name: filter-meals\n        description: Filter meals by ingredient, category, or area\n        call: mealdb.filter-meals\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: meal-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted meal recipe discovery and cooking planning.\n    tools:\n    - name: search-meals\n      description: Search for meal recipes by name (e.g. chicken, pasta, sushi)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.search-meals\n      with:\n        s: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-meals-by-letter\n      description: Browse all meals starting with a specific letter\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.search-meals\n      with:\n        f: tools.letter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-meal-by-id\n      description: Get full recipe details for a meal by its ID\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: mealdb.lookup-meal-by-id\n      with:\n        i: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-random-meal\n      description: Get a completely random meal recipe for cooking inspiration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.get-random-meal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-all-categories\n      description: List all meal categories with thumbnails and descriptions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.list-all-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filter-by-ingredient\n      description: Find meals that use a specific ingredient\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.filter-meals\n      with:\n        i: tools.ingredient\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: filter-by-category\n      description: Filter meals by category (e.g. Chicken, Seafood, Dessert)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.filter-meals\n      with:\n        c: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filter-by-area\n      description: Filter meals by regional cuisine (e.g. Italian, Japanese, Mexican)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.filter-meals\n      with:\n        a: tools.area\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-areas\n      description: List all regional cuisines available in the database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.list-filter-values\n      with:\n        a: list\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ingredients\n      description: List all available\
  \ ingredients in the database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: mealdb.list-filter-values\n      with:\n        i: list\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
