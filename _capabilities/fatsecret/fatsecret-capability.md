---
categories: []
consumed_apis: []
description: The FatSecret Platform API provides programmatic access to a global food nutrition database covering more than 1.9 million verified food items across 56 countries. It supports food and recipe search, barcode scanning, image recognition, natural language processing, and full profile-based food diary, exercise diary, and weight tracking management.
layout: capability
name: FatSecret Platform API
operations:
- description: Search foods
  method: GET
  name: searchfoods
  path: /foods/search/v5
- description: Autocomplete food search
  method: GET
  name: autocompletefoods
  path: /foods/autocomplete/v2
- description: Find food by barcode
  method: GET
  name: findfoodbybarcode
  path: /food/barcode/find-by-id/v1
- description: Get food by id
  method: GET
  name: getfood
  path: /food/v4
- description: List food brands
  method: GET
  name: listfoodbrands
  path: /food-brands/v2
- description: List food categories
  method: GET
  name: listfoodcategories
  path: /food-categories/v2
- description: List food sub-categories
  method: GET
  name: listfoodsubcategories
  path: /food-sub-categories/v2
- description: Search recipes
  method: GET
  name: searchrecipes
  path: /recipes/search/v3
- description: Get recipe by id
  method: GET
  name: getrecipe
  path: /recipe/v2
- description: List recipe types
  method: GET
  name: listrecipetypes
  path: /recipe-types/v2
- description: List exercises
  method: GET
  name: listexercises
  path: /exercises/v2
- description: Get favorite foods
  method: GET
  name: getfavoritefoods
  path: /food/favorites/v2
- description: Add favorite food
  method: POST
  name: addfavoritefood
  path: /food/favorite/add/v2
- description: Delete favorite food
  method: POST
  name: deletefavoritefood
  path: /food/favorite/delete/v2
- description: Get food diary entries
  method: GET
  name: getfoodentries
  path: /food-entries/v2
- description: Create food diary entry
  method: POST
  name: createfoodentry
  path: /food-entries/v2
- description: Monthly food diary summary
  method: GET
  name: getfoodentriesmonth
  path: /food-entries/month/v2
- description: Get exercise diary entries
  method: GET
  name: getexerciseentries
  path: /exercise-entries/v2
- description: Commit exercise diary entries
  method: POST
  name: commitexerciseentries
  path: /exercise-entries/v2
- description: Get weight history
  method: GET
  name: getweights
  path: /weights/v2
- description: Update weight entry
  method: POST
  name: updateweight
  path: /weights/v2
- description: List saved meals
  method: GET
  name: listsavedmeals
  path: /saved-meals/v2
- description: Create saved meal
  method: POST
  name: createsavedmeal
  path: /saved-meals/v2
personas: []
provider_name: FatSecret
provider_slug: fatsecret
search_terms:
- commitexerciseentries
- nutrition
- get food by id
- getexerciseentries
- getfood
- list food brands
- createfoodentry
- barcode scanning
- searchrecipes
- api
- autocomplete food search
- create saved meal
- get exercise diary entries
- listrecipetypes
- search recipes
- listfoodcategories
- health
- get food diary entries
- recipes
- listfoodbrands
- update weight entry
- exercise
- getfoodentries
- get recipe by id
- get weight history
- fitness
- list recipe types
- delete favorite food
- listsavedmeals
- search foods
- createsavedmeal
- findfoodbybarcode
- macronutrients
- deletefavoritefood
- searchfoods
- list food categories
- diets
- autocompletefoods
- getrecipe
- find food by barcode
- listfoodsubcategories
- monthly food diary summary
- getfavoritefoods
- list saved meals
- commit exercise diary entries
- getfoodentriesmonth
- listexercises
- getweights
- get favorite foods
- add favorite food
- list exercises
- addfavoritefood
- updateweight
- food diary
- weight tracking
- create food diary entry
- calories
- list food sub-categories
- fatsecret
slug: fatsecret-capability
source_filename: fatsecret-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FatSecret Platform API\n  description: The FatSecret Platform API provides programmatic access to a global food nutrition database covering more than\n    1.9 million verified food items across 56 countries. It supports food and recipe search, barcode scanning, image recognition,\n    natural language processing, and full profile-based food diary, exercise diary, and weight tracking management.\n  tags:\n  - Fatsecret\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fatsecret\n    baseUri: https://platform.fatsecret.com/rest\n    description: FatSecret Platform API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FATSECRET_TOKEN}}'\n    resources:\n    - name: foods-search-v5\n      path: /foods/search/v5\n      operations:\n      - name: searchfoods\n        method: GET\n        description: Search foods\n        inputParameters:\n        - name: search_expression\n\
  \          in: query\n          type: string\n          required: true\n        - name: page_number\n          in: query\n          type: integer\n        - name: max_results\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foods-autocomplete-v2\n      path: /foods/autocomplete/v2\n      operations:\n      - name: autocompletefoods\n        method: GET\n        description: Autocomplete food search\n        inputParameters:\n        - name: expression\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-barcode-find-by-id-v1\n      path: /food/barcode/find-by-id/v1\n      operations:\n      - name: findfoodbybarcode\n        method: GET\n        description: Find food by barcode\n        inputParameters:\n\
  \        - name: barcode\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-v4\n      path: /food/v4\n      operations:\n      - name: getfood\n        method: GET\n        description: Get food by id\n        inputParameters:\n        - name: food_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-brands-v2\n      path: /food-brands/v2\n      operations:\n      - name: listfoodbrands\n        method: GET\n        description: List food brands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-categories-v2\n      path: /food-categories/v2\n      operations:\n      -\
  \ name: listfoodcategories\n        method: GET\n        description: List food categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-sub-categories-v2\n      path: /food-sub-categories/v2\n      operations:\n      - name: listfoodsubcategories\n        method: GET\n        description: List food sub-categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes-search-v3\n      path: /recipes/search/v3\n      operations:\n      - name: searchrecipes\n        method: GET\n        description: Search recipes\n        inputParameters:\n        - name: search_expression\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe-v2\n      path: /recipe/v2\n      operations:\n\
  \      - name: getrecipe\n        method: GET\n        description: Get recipe by id\n        inputParameters:\n        - name: recipe_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe-types-v2\n      path: /recipe-types/v2\n      operations:\n      - name: listrecipetypes\n        method: GET\n        description: List recipe types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exercises-v2\n      path: /exercises/v2\n      operations:\n      - name: listexercises\n        method: GET\n        description: List exercises\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-favorites-v2\n      path: /food/favorites/v2\n      operations:\n\
  \      - name: getfavoritefoods\n        method: GET\n        description: Get favorite foods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-favorite-add-v2\n      path: /food/favorite/add/v2\n      operations:\n      - name: addfavoritefood\n        method: POST\n        description: Add favorite food\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-favorite-delete-v2\n      path: /food/favorite/delete/v2\n      operations:\n      - name: deletefavoritefood\n        method: POST\n        description: Delete favorite food\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-entries-v2\n      path: /food-entries/v2\n      operations:\n      - name: getfoodentries\n        method: GET\n        description:\
  \ Get food diary entries\n        inputParameters:\n        - name: date\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfoodentry\n        method: POST\n        description: Create food diary entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-entries-month-v2\n      path: /food-entries/month/v2\n      operations:\n      - name: getfoodentriesmonth\n        method: GET\n        description: Monthly food diary summary\n        inputParameters:\n        - name: month\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exercise-entries-v2\n      path: /exercise-entries/v2\n      operations:\n      - name: getexerciseentries\n\
  \        method: GET\n        description: Get exercise diary entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: commitexerciseentries\n        method: POST\n        description: Commit exercise diary entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: weights-v2\n      path: /weights/v2\n      operations:\n      - name: getweights\n        method: GET\n        description: Get weight history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateweight\n        method: POST\n        description: Update weight entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: saved-meals-v2\n      path: /saved-meals/v2\n    \
  \  operations:\n      - name: listsavedmeals\n        method: GET\n        description: List saved meals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsavedmeal\n        method: POST\n        description: Create saved meal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fatsecret-rest\n    description: REST adapter for FatSecret Platform API.\n    resources:\n    - path: /foods/search/v5\n      name: searchfoods\n      operations:\n      - method: GET\n        name: searchfoods\n        description: Search foods\n        call: fatsecret.searchfoods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /foods/autocomplete/v2\n      name: autocompletefoods\n      operations:\n      - method: GET\n        name: autocompletefoods\n\
  \        description: Autocomplete food search\n        call: fatsecret.autocompletefoods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food/barcode/find-by-id/v1\n      name: findfoodbybarcode\n      operations:\n      - method: GET\n        name: findfoodbybarcode\n        description: Find food by barcode\n        call: fatsecret.findfoodbybarcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food/v4\n      name: getfood\n      operations:\n      - method: GET\n        name: getfood\n        description: Get food by id\n        call: fatsecret.getfood\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food-brands/v2\n      name: listfoodbrands\n      operations:\n      - method: GET\n        name: listfoodbrands\n        description: List food brands\n        call: fatsecret.listfoodbrands\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /food-categories/v2\n      name: listfoodcategories\n      operations:\n      - method: GET\n        name: listfoodcategories\n        description: List food categories\n        call: fatsecret.listfoodcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food-sub-categories/v2\n      name: listfoodsubcategories\n      operations:\n      - method: GET\n        name: listfoodsubcategories\n        description: List food sub-categories\n        call: fatsecret.listfoodsubcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipes/search/v3\n      name: searchrecipes\n      operations:\n      - method: GET\n        name: searchrecipes\n        description: Search recipes\n        call: fatsecret.searchrecipes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipe/v2\n      name: getrecipe\n      operations:\n      - method: GET\n        name: getrecipe\n\
  \        description: Get recipe by id\n        call: fatsecret.getrecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipe-types/v2\n      name: listrecipetypes\n      operations:\n      - method: GET\n        name: listrecipetypes\n        description: List recipe types\n        call: fatsecret.listrecipetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exercises/v2\n      name: listexercises\n      operations:\n      - method: GET\n        name: listexercises\n        description: List exercises\n        call: fatsecret.listexercises\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food/favorites/v2\n      name: getfavoritefoods\n      operations:\n      - method: GET\n        name: getfavoritefoods\n        description: Get favorite foods\n        call: fatsecret.getfavoritefoods\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /food/favorite/add/v2\n      name: addfavoritefood\n      operations:\n      - method: POST\n        name: addfavoritefood\n        description: Add favorite food\n        call: fatsecret.addfavoritefood\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food/favorite/delete/v2\n      name: deletefavoritefood\n      operations:\n      - method: POST\n        name: deletefavoritefood\n        description: Delete favorite food\n        call: fatsecret.deletefavoritefood\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food-entries/v2\n      name: getfoodentries\n      operations:\n      - method: GET\n        name: getfoodentries\n        description: Get food diary entries\n        call: fatsecret.getfoodentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food-entries/v2\n      name: createfoodentry\n      operations:\n      - method: POST\n        name: createfoodentry\n\
  \        description: Create food diary entry\n        call: fatsecret.createfoodentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /food-entries/month/v2\n      name: getfoodentriesmonth\n      operations:\n      - method: GET\n        name: getfoodentriesmonth\n        description: Monthly food diary summary\n        call: fatsecret.getfoodentriesmonth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exercise-entries/v2\n      name: getexerciseentries\n      operations:\n      - method: GET\n        name: getexerciseentries\n        description: Get exercise diary entries\n        call: fatsecret.getexerciseentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /exercise-entries/v2\n      name: commitexerciseentries\n      operations:\n      - method: POST\n        name: commitexerciseentries\n        description: Commit exercise diary entries\n        call: fatsecret.commitexerciseentries\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /weights/v2\n      name: getweights\n      operations:\n      - method: GET\n        name: getweights\n        description: Get weight history\n        call: fatsecret.getweights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /weights/v2\n      name: updateweight\n      operations:\n      - method: POST\n        name: updateweight\n        description: Update weight entry\n        call: fatsecret.updateweight\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /saved-meals/v2\n      name: listsavedmeals\n      operations:\n      - method: GET\n        name: listsavedmeals\n        description: List saved meals\n        call: fatsecret.listsavedmeals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /saved-meals/v2\n      name: createsavedmeal\n      operations:\n      - method: POST\n     \
  \   name: createsavedmeal\n        description: Create saved meal\n        call: fatsecret.createsavedmeal\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fatsecret-mcp\n    transport: http\n    description: MCP adapter for FatSecret Platform API for AI agent use.\n    tools:\n    - name: searchfoods\n      description: Search foods\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.searchfoods\n      with:\n        search_expression: tools.search_expression\n        page_number: tools.page_number\n        max_results: tools.max_results\n      inputParameters:\n      - name: search_expression\n        type: string\n        description: search_expression\n        required: true\n      - name: page_number\n        type: integer\n        description: page_number\n      - name: max_results\n        type: integer\n        description: max_results\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: autocompletefoods\n      description: Autocomplete food search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.autocompletefoods\n      with:\n        expression: tools.expression\n      inputParameters:\n      - name: expression\n        type: string\n        description: expression\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: findfoodbybarcode\n      description: Find food by barcode\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.findfoodbybarcode\n      with:\n        barcode: tools.barcode\n      inputParameters:\n      - name: barcode\n        type: string\n        description: barcode\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfood\n      description: Get food by id\n \
  \     hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getfood\n      with:\n        food_id: tools.food_id\n      inputParameters:\n      - name: food_id\n        type: string\n        description: food_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfoodbrands\n      description: List food brands\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listfoodbrands\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfoodcategories\n      description: List food categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listfoodcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfoodsubcategories\n      description: List food sub-categories\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listfoodsubcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchrecipes\n      description: Search recipes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.searchrecipes\n      with:\n        search_expression: tools.search_expression\n      inputParameters:\n      - name: search_expression\n        type: string\n        description: search_expression\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecipe\n      description: Get recipe by id\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getrecipe\n      with:\n        recipe_id: tools.recipe_id\n      inputParameters:\n      - name: recipe_id\n        type: string\n        description: recipe_id\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listrecipetypes\n      description: List recipe types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listrecipetypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listexercises\n      description: List exercises\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listexercises\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfavoritefoods\n      description: Get favorite foods\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getfavoritefoods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addfavoritefood\n      description: Add favorite food\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: fatsecret.addfavoritefood\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefavoritefood\n      description: Delete favorite food\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fatsecret.deletefavoritefood\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfoodentries\n      description: Get food diary entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getfoodentries\n      with:\n        date: tools.date\n      inputParameters:\n      - name: date\n        type: string\n        description: date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfoodentry\n      description: Create food diary entry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fatsecret.createfoodentry\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getfoodentriesmonth\n      description: Monthly food diary summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getfoodentriesmonth\n      with:\n        month: tools.month\n      inputParameters:\n      - name: month\n        type: string\n        description: month\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexerciseentries\n      description: Get exercise diary entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getexerciseentries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: commitexerciseentries\n      description: Commit exercise diary entries\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fatsecret.commitexerciseentries\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: getweights\n      description: Get weight history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.getweights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateweight\n      description: Update weight entry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fatsecret.updateweight\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsavedmeals\n      description: List saved meals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fatsecret.listsavedmeals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsavedmeal\n      description: Create saved meal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fatsecret.createsavedmeal\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FATSECRET_TOKEN: FATSECRET_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fatsecret/refs/heads/main/capabilities/fatsecret-capability.yaml
tags:
- Fatsecret
- API
tools:
- description: Search foods
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchfoods
- description: Autocomplete food search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: autocompletefoods
- description: Find food by barcode
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findfoodbybarcode
- description: Get food by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfood
- description: List food brands
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfoodbrands
- description: List food categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfoodcategories
- description: List food sub-categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfoodsubcategories
- description: Search recipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchrecipes
- description: Get recipe by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecipe
- description: List recipe types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecipetypes
- description: List exercises
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexercises
- description: Get favorite foods
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfavoritefoods
- description: Add favorite food
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addfavoritefood
- description: Delete favorite food
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletefavoritefood
- description: Get food diary entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfoodentries
- description: Create food diary entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfoodentry
- description: Monthly food diary summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfoodentriesmonth
- description: Get exercise diary entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexerciseentries
- description: Commit exercise diary entries
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: commitexerciseentries
- description: Get weight history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getweights
- description: Update weight entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateweight
- description: List saved meals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsavedmeals
- description: Create saved meal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsavedmeal
---
