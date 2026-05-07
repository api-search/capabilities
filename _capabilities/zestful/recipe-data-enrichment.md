---
categories: []
consumed_apis: []
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
- food
- parse raw recipe ingredient strings into structured data
- recipes
- parsers
- ingredients
- parse recipe ingredients
- parse ingredients
- parse a list of raw recipe ingredient strings (up to 100 per request) into structured data with quantity, unit, product name, preparation notes, and usda fooddata central database matches.
- usda
- parse a list of raw recipe ingredient strings into structured json data. extracts quantity, measurement unit, product name, preparation notes, and matches each ingredient against the usda fooddata central database. supports up to 100 ingredients per request. use for building searchable recipes, shopping list generation, and nutritional analysis.
slug: recipe-data-enrichment
source_filename: recipe-data-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Zestful Recipe Data Enrichment\n  description: Workflow capability for enriching recipe data by parsing raw ingredient strings into structured, USDA-matched\n    nutritional data. Used by recipe app developers to build searchable recipes, generate shopping lists, and create ingredient\n    databases.\n  tags:\n  - Food\n  - Ingredients\n  - Parsers\n  - Recipes\n  - USDA\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ZESTFUL_API_KEY: ZESTFUL_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: zestful\n    baseUri: https://zestfuldata.com\n    description: Zestful ingredient parser API that extracts structured data from free-form recipe ingredient text.\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{ZESTFUL_API_KEY}}'\n      placement: header\n    resources:\n    - name: ingredients\n      path: /parseIngredients\n      description: Parse raw ingredient\
  \ strings into structured JSON\n      operations:\n      - name: parse-ingredients\n        method: POST\n        description: Parse a list of raw ingredient strings into structured data including quantity, unit, product name, preparation\n          notes, and USDA nutritional database matches.\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: array\n          value: $.results\n        - name: requestsRemaining\n          type: integer\n          value: $.requestsRemaining\n        body:\n          type: json\n          data:\n            ingredients: '{{tools.ingredients}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: recipe-enrichment-api\n    description: Unified REST API for recipe data enrichment and ingredient parsing.\n    resources:\n    - path: /v1/ingredients/parse\n      name: ingredient-parser\n      description: Parse raw recipe ingredient strings into structured data\n      operations:\n      - method: POST\n\
  \        name: parse-ingredients\n        description: Parse a list of raw recipe ingredient strings (up to 100 per request) into structured data with quantity,\n          unit, product name, preparation notes, and USDA FoodData Central database matches.\n        call: zestful.parse-ingredients\n        with:\n          ingredients: rest.ingredients\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: recipe-enrichment-mcp\n    transport: http\n    description: MCP server for AI-assisted recipe data enrichment and ingredient analysis.\n    tools:\n    - name: parse-recipe-ingredients\n      description: Parse a list of raw recipe ingredient strings into structured JSON data. Extracts quantity, measurement\n        unit, product name, preparation notes, and matches each ingredient against the USDA FoodData Central database. Supports\n        up to 100 ingredients per request. Use for building searchable recipes, shopping\
  \ list generation, and nutritional\n        analysis.\n      hints:\n        readOnly: false\n        openWorld: true\n      call: zestful.parse-ingredients\n      with:\n        ingredients: tools.ingredients\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
