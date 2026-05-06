---
categories: []
consumed_apis: []
description: Get nutrition and recipe data for 100,000 foods and beverages.
layout: capability
name: CalorieNinjas
operations:
- description: CalorieNinjas Get nutrition information
  method: GET
  name: get-nutrition
  path: /nutrition
- description: CalorieNinjas Get nutrition information from an image
  method: POST
  name: post-imagetextnutrition
  path: /imagetextnutrition
- description: CalorieNinjas Get recipes
  method: GET
  name: get-recipe
  path: /recipe
personas: []
provider_name: CalorieNinjas
provider_slug: calorie-ninjas
search_terms:
- post imagetextnutrition
- ninjas
- calorie
- nutrition
- api
- foods
- image recognition
- get nutrition
- get recipe
- calorieninjas get recipes
- calorieninjas get nutrition information
- beverages
- calorieninjas get nutrition information from an image
- recipes
slug: calorie-ninjas-capability
source_filename: calorie-ninjas-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CalorieNinjas\n  description: Get nutrition and recipe data for 100,000 foods and beverages.\n  tags:\n  - Calorie\n  - Ninjas\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: calorie-ninjas\n    baseUri: https://api.calorieninjas.com/v1\n    description: CalorieNinjas HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Key\n      value: '{{CALORIE_NINJAS_TOKEN}}'\n    resources:\n    - name: nutrition\n      path: /nutrition\n      operations:\n      - name: get-nutrition\n        method: GET\n        description: CalorieNinjas Get nutrition information\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: A string containing food or drink items. Prefix a quantity before an item to calculate for that quantity.\n            Default is 100 grams\
  \ if unspecified.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: imagetextnutrition\n      path: /imagetextnutrition\n      operations:\n      - name: post-imagetextnutrition\n        method: POST\n        description: CalorieNinjas Get nutrition information from an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipe\n      path: /recipe\n      operations:\n      - name: get-recipe\n        method: GET\n        description: CalorieNinjas Get recipes\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: A string containing a dish name. Partial match is supported.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: calorie-ninjas-rest\n    description: REST adapter for CalorieNinjas.\n    resources:\n    - path: /nutrition\n      name: get-nutrition\n      operations:\n      - method: GET\n        name: get-nutrition\n        description: CalorieNinjas Get nutrition information\n        call: calorie-ninjas.get-nutrition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /imagetextnutrition\n      name: post-imagetextnutrition\n      operations:\n      - method: POST\n        name: post-imagetextnutrition\n        description: CalorieNinjas Get nutrition information from an image\n        call: calorie-ninjas.post-imagetextnutrition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recipe\n      name: get-recipe\n      operations:\n      - method: GET\n        name: get-recipe\n        description: CalorieNinjas Get recipes\n        call: calorie-ninjas.get-recipe\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: calorie-ninjas-mcp\n    transport: http\n    description: MCP adapter for CalorieNinjas for AI agent use.\n    tools:\n    - name: get-nutrition\n      description: CalorieNinjas Get nutrition information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: calorie-ninjas.get-nutrition\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: A string containing food or drink items. Prefix a quantity before an item to calculate for that quantity.\n          Default is 100 grams if unspecified.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-imagetextnutrition\n      description: CalorieNinjas Get nutrition information from an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: calorie-ninjas.post-imagetextnutrition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recipe\n      description: CalorieNinjas Get recipes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: calorie-ninjas.get-recipe\n      with:\n        query: tools.query\n      inputParameters:\n      - name: query\n        type: string\n        description: A string containing a dish name. Partial match is supported.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CALORIE_NINJAS_TOKEN: CALORIE_NINJAS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/calorie-ninjas/refs/heads/main/capabilities/calorie-ninjas-capability.yaml
tags:
- Calorie
- Ninjas
- API
tools:
- description: CalorieNinjas Get nutrition information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-nutrition
- description: CalorieNinjas Get nutrition information from an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-imagetextnutrition
- description: CalorieNinjas Get recipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-recipe
---
