---
api_specs:
- filename: zestful-openapi.yml
  format: yaml
  label: zestful
  slug: zestful
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/zestful/refs/heads/main/openapi/zestful-openapi.yml
categories: []
consumed_apis:
- zestful
description: Workflow capability for enriching recipe data by parsing raw ingredient strings into structured, USDA-matched nutritional data. Used by recipe app developers to build searchable recipes, generate shopping lists, and create ingredient databases.
layout: capability
name: Zestful Recipe Data Enrichment
operations:
- description: Parse a list of raw recipe ingredient strings (up to 100 per request) into structured data with quantity, unit, product name, preparation notes, and USDA FoodData Central database matches.
  method: POST
  name: parse-ingredients
  path: /v1/ingredients/parse
personas: []
provider_name: Zestful
provider_slug: zestful
search_terms:
- parse ingredients
- parse a list of raw recipe ingredient strings into structured json data. extracts quantity, measurement unit, product name, preparation notes, and matches each ingredient against the usda fooddata central database. supports up to 100 ingredients per request. use for building searchable recipes, shopping list generation, and nutritional analysis.
- recipes
- food
- parse raw recipe ingredient strings into structured data
- parse a list of raw recipe ingredient strings (up to 100 per request) into structured data with quantity, unit, product name, preparation notes, and usda fooddata central database matches.
- ingredients
- parse recipe ingredients
- parsers
- usda
slug: recipe-data-enrichment
source_filename: recipe-data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Zestful Recipe Data Enrichment\"\n  description: >-\n    Workflow capability for enriching recipe data by parsing raw ingredient\n    strings into structured, USDA-matched nutritional data. Used by recipe\n    app developers to build searchable recipes, generate shopping lists,\n    and create ingredient databases.\n  tags:\n    - Food\n    - Ingredients\n    - Parsers\n    - Recipes\n    - USDA\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      ZESTFUL_API_KEY: ZESTFUL_API_KEY\n\ncapability:\n  consumes:\n    - import: zestful\n      location: ./shared/zestful.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: recipe-enrichment-api\n      description: \"Unified REST API for recipe data enrichment and ingredient parsing.\"\n      resources:\n        - path: /v1/ingredients/parse\n          name: ingredient-parser\n          description: Parse raw recipe ingredient\
  \ strings into structured data\n          operations:\n            - method: POST\n              name: parse-ingredients\n              description: >-\n                Parse a list of raw recipe ingredient strings (up to 100 per\n                request) into structured data with quantity, unit, product name,\n                preparation notes, and USDA FoodData Central database matches.\n              call: \"zestful.parse-ingredients\"\n              with:\n                ingredients: \"rest.ingredients\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: recipe-enrichment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted recipe data enrichment and ingredient analysis.\"\n      tools:\n        - name: parse-recipe-ingredients\n          description: >-\n            Parse a list of raw recipe ingredient strings into structured JSON\n            data. Extracts\
  \ quantity, measurement unit, product name, preparation\n            notes, and matches each ingredient against the USDA FoodData Central\n            database. Supports up to 100 ingredients per request. Use for\n            building searchable recipes, shopping list generation, and\n            nutritional analysis.\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"zestful.parse-ingredients\"\n          with:\n            ingredients: \"tools.ingredients\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zestful/refs/heads/main/capabilities/recipe-data-enrichment.yaml
tags:
- Food
- Ingredients
- Parsers
- Recipes
- USDA
tools:
- description: Parse a list of raw recipe ingredient strings into structured JSON data. Extracts quantity, measurement unit, product name, preparation notes, and matches each ingredient against the USDA FoodData Central database. Supports up to 100 ingredients per request. Use for building searchable recipes, shopping list generation, and nutritional analysis.
  hints:
    openWorld: true
    readOnly: false
  name: parse-recipe-ingredients
---
