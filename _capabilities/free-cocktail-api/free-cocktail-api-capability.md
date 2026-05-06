---
categories: []
consumed_apis: []
description: TheCocktailDB Free API provides access to a vast database of cocktail recipes, ingredients, glassware, and images. Search by name, ingredient, category, glass, or alcohol content, look up details by ID, list available filters, or fetch a random cocktail.
layout: capability
name: Free Cocktail API
operations:
- description: Search cocktails or ingredients
  method: GET
  name: searchcocktails
  path: /search.php
- description: Lookup cocktail or ingredient by ID
  method: GET
  name: lookupbyid
  path: /lookup.php
- description: Get a random cocktail
  method: GET
  name: randomcocktail
  path: /random.php
- description: Filter cocktails
  method: GET
  name: filtercocktails
  path: /filter.php
- description: List filter values
  method: GET
  name: listfilters
  path: /list.php
personas: []
provider_name: Free Cocktail API
provider_slug: free-cocktail-api
search_terms:
- cocktails
- get a random cocktail
- lookupbyid
- list filter values
- ingredients
- searchcocktails
- filter cocktails
- listfilters
- randomcocktail
- api
- lookup cocktail or ingredient by id
- search cocktails or ingredients
- filtercocktails
- drinks
- recipes
- beverages
- cocktail
- free
slug: free-cocktail-api-capability
source_filename: free-cocktail-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Free Cocktail API\n  description: TheCocktailDB Free API provides access to a vast database of cocktail recipes, ingredients, glassware, and\n    images. Search by name, ingredient, category, glass, or alcohol content, look up details by ID, list available filters,\n    or fetch a random cocktail.\n  tags:\n  - Free\n  - Cocktail\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: free-cocktail-api\n    baseUri: https://www.thecocktaildb.com/api/json/v1/1\n    description: Free Cocktail API HTTP API.\n    resources:\n    - name: search-php\n      path: /search.php\n      operations:\n      - name: searchcocktails\n        method: GET\n        description: Search cocktails or ingredients\n        inputParameters:\n        - name: s\n          in: query\n          type: string\n          description: Cocktail name to search for.\n        - name: f\n          in: query\n\
  \          type: string\n          description: First letter to list cocktails by.\n        - name: i\n          in: query\n          type: string\n          description: Ingredient name to search for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookup-php\n      path: /lookup.php\n      operations:\n      - name: lookupbyid\n        method: GET\n        description: Lookup cocktail or ingredient by ID\n        inputParameters:\n        - name: i\n          in: query\n          type: string\n          description: Cocktail ID.\n        - name: iid\n          in: query\n          type: string\n          description: Ingredient ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: random-php\n      path: /random.php\n      operations:\n      - name: randomcocktail\n        method: GET\n        description:\
  \ Get a random cocktail\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filter-php\n      path: /filter.php\n      operations:\n      - name: filtercocktails\n        method: GET\n        description: Filter cocktails\n        inputParameters:\n        - name: i\n          in: query\n          type: string\n          description: Ingredient to filter by.\n        - name: a\n          in: query\n          type: string\n          description: Alcoholic or Non_Alcoholic.\n        - name: c\n          in: query\n          type: string\n          description: Category to filter by.\n        - name: g\n          in: query\n          type: string\n          description: Glass type to filter by.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-php\n      path: /list.php\n      operations:\n      - name: listfilters\n\
  \        method: GET\n        description: List filter values\n        inputParameters:\n        - name: c\n          in: query\n          type: string\n          description: List categories.\n        - name: g\n          in: query\n          type: string\n          description: List glasses.\n        - name: i\n          in: query\n          type: string\n          description: List ingredients.\n        - name: a\n          in: query\n          type: string\n          description: List alcoholic filters.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: free-cocktail-api-rest\n    description: REST adapter for Free Cocktail API.\n    resources:\n    - path: /search.php\n      name: searchcocktails\n      operations:\n      - method: GET\n        name: searchcocktails\n        description: Search cocktails or ingredients\n        call: free-cocktail-api.searchcocktails\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lookup.php\n      name: lookupbyid\n      operations:\n      - method: GET\n        name: lookupbyid\n        description: Lookup cocktail or ingredient by ID\n        call: free-cocktail-api.lookupbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /random.php\n      name: randomcocktail\n      operations:\n      - method: GET\n        name: randomcocktail\n        description: Get a random cocktail\n        call: free-cocktail-api.randomcocktail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filter.php\n      name: filtercocktails\n      operations:\n      - method: GET\n        name: filtercocktails\n        description: Filter cocktails\n        call: free-cocktail-api.filtercocktails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /list.php\n      name: listfilters\n      operations:\n\
  \      - method: GET\n        name: listfilters\n        description: List filter values\n        call: free-cocktail-api.listfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: free-cocktail-api-mcp\n    transport: http\n    description: MCP adapter for Free Cocktail API for AI agent use.\n    tools:\n    - name: searchcocktails\n      description: Search cocktails or ingredients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-cocktail-api.searchcocktails\n      with:\n        s: tools.s\n        f: tools.f\n        i: tools.i\n      inputParameters:\n      - name: s\n        type: string\n        description: Cocktail name to search for.\n      - name: f\n        type: string\n        description: First letter to list cocktails by.\n      - name: i\n        type: string\n        description: Ingredient name to search for.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: lookupbyid\n      description: Lookup cocktail or ingredient by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-cocktail-api.lookupbyid\n      with:\n        i: tools.i\n        iid: tools.iid\n      inputParameters:\n      - name: i\n        type: string\n        description: Cocktail ID.\n      - name: iid\n        type: string\n        description: Ingredient ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: randomcocktail\n      description: Get a random cocktail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-cocktail-api.randomcocktail\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filtercocktails\n      description: Filter cocktails\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ free-cocktail-api.filtercocktails\n      with:\n        i: tools.i\n        a: tools.a\n        c: tools.c\n        g: tools.g\n      inputParameters:\n      - name: i\n        type: string\n        description: Ingredient to filter by.\n      - name: a\n        type: string\n        description: Alcoholic or Non_Alcoholic.\n      - name: c\n        type: string\n        description: Category to filter by.\n      - name: g\n        type: string\n        description: Glass type to filter by.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfilters\n      description: List filter values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-cocktail-api.listfilters\n      with:\n        c: tools.c\n        g: tools.g\n        i: tools.i\n        a: tools.a\n      inputParameters:\n      - name: c\n        type: string\n        description: List categories.\n      - name: g\n        type: string\n\
  \        description: List glasses.\n      - name: i\n        type: string\n        description: List ingredients.\n      - name: a\n        type: string\n        description: List alcoholic filters.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/free-cocktail-api/refs/heads/main/capabilities/free-cocktail-api-capability.yaml
tags:
- Free
- Cocktail
- Api
- API
tools:
- description: Search cocktails or ingredients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcocktails
- description: Lookup cocktail or ingredient by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: lookupbyid
- description: Get a random cocktail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: randomcocktail
- description: Filter cocktails
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: filtercocktails
- description: List filter values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilters
---
