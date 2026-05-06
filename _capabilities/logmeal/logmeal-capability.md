---
categories: []
consumed_apis: []
description: The LogMeal API is a RESTful service that recognizes foods, drinks, vegetables, fruits, and prepared dishes from images, returns ingredient lists with quantities, computes nutritional information, and tracks user intakes over time. Authentication is by user token in the Authorization header. Images are submitted as multipart/form-data or as a base64-encoded string in JSON.
layout: capability
name: LogMeal Food Recognition API
operations:
- description: Segment and recognize foods in an image
  method: POST
  name: segmentationcomplete
  path: /v2/image/segmentation/complete
- description: Retrieve ingredients for a confirmed intake
  method: POST
  name: recipeingredients
  path: /v2/nutrition/recipe/ingredients
- description: Retrieve nutritional information for a confirmed intake
  method: POST
  name: recipenutritionalinfo
  path: /v2/nutrition/recipe/nutritionalInfo
- description: List user food intakes
  method: GET
  name: getintakeslist
  path: /v2/history/getIntakesList
personas: []
provider_name: LogMeal
provider_slug: logmeal
search_terms:
- retrieve ingredients for a confirmed intake
- computer vision
- retrieve nutritional information for a confirmed intake
- logmeal
- getintakeslist
- nutrition
- recipeingredients
- api
- recipenutritionalinfo
- image recognition
- segmentationcomplete
- list user food intakes
- semantic tagging
- food
- segment and recognize foods in an image
slug: logmeal-capability
source_filename: logmeal-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LogMeal Food Recognition API\n  description: The LogMeal API is a RESTful service that recognizes foods, drinks, vegetables, fruits, and prepared dishes\n    from images, returns ingredient lists with quantities, computes nutritional information, and tracks user intakes over\n    time. Authentication is by user token in the Authorization header. Images are submitted as multipart/form-data or as a\n    base64-encoded string in JSON.\n  tags:\n  - Logmeal\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: logmeal\n    baseUri: https://api.logmeal.com\n    description: LogMeal Food Recognition API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LOGMEAL_TOKEN}}'\n    resources:\n    - name: v2-image-segmentation-complete\n      path: /v2/image/segmentation/complete\n      operations:\n      - name: segmentationcomplete\n        method: POST\n        description:\
  \ Segment and recognize foods in an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-nutrition-recipe-ingredients\n      path: /v2/nutrition/recipe/ingredients\n      operations:\n      - name: recipeingredients\n        method: POST\n        description: Retrieve ingredients for a confirmed intake\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-nutrition-recipe-nutritionalinfo\n      path: /v2/nutrition/recipe/nutritionalInfo\n      operations:\n      - name: recipenutritionalinfo\n        method: POST\n        description: Retrieve nutritional information for a confirmed intake\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-history-getintakeslist\n      path: /v2/history/getIntakesList\n      operations:\n\
  \      - name: getintakeslist\n        method: GET\n        description: List user food intakes\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          description: Start of the time window (ISO 8601 date).\n        - name: endDate\n          in: query\n          type: string\n          description: End of the time window (ISO 8601 date).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: logmeal-rest\n    description: REST adapter for LogMeal Food Recognition API.\n    resources:\n    - path: /v2/image/segmentation/complete\n      name: segmentationcomplete\n      operations:\n      - method: POST\n        name: segmentationcomplete\n        description: Segment and recognize foods in an image\n        call: logmeal.segmentationcomplete\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v2/nutrition/recipe/ingredients\n      name: recipeingredients\n      operations:\n      - method: POST\n        name: recipeingredients\n        description: Retrieve ingredients for a confirmed intake\n        call: logmeal.recipeingredients\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/nutrition/recipe/nutritionalInfo\n      name: recipenutritionalinfo\n      operations:\n      - method: POST\n        name: recipenutritionalinfo\n        description: Retrieve nutritional information for a confirmed intake\n        call: logmeal.recipenutritionalinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/history/getIntakesList\n      name: getintakeslist\n      operations:\n      - method: GET\n        name: getintakeslist\n        description: List user food intakes\n        call: logmeal.getintakeslist\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: logmeal-mcp\n    transport: http\n    description: MCP adapter for LogMeal Food Recognition API for AI agent use.\n    tools:\n    - name: segmentationcomplete\n      description: Segment and recognize foods in an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logmeal.segmentationcomplete\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recipeingredients\n      description: Retrieve ingredients for a confirmed intake\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logmeal.recipeingredients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recipenutritionalinfo\n      description: Retrieve nutritional information for a confirmed intake\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: logmeal.recipenutritionalinfo\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintakeslist\n      description: List user food intakes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: logmeal.getintakeslist\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: startDate\n        type: string\n        description: Start of the time window (ISO 8601 date).\n      - name: endDate\n        type: string\n        description: End of the time window (ISO 8601 date).\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LOGMEAL_TOKEN: LOGMEAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/logmeal/refs/heads/main/capabilities/logmeal-capability.yaml
tags:
- Logmeal
- API
tools:
- description: Segment and recognize foods in an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: segmentationcomplete
- description: Retrieve ingredients for a confirmed intake
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recipeingredients
- description: Retrieve nutritional information for a confirmed intake
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recipenutritionalinfo
- description: List user food intakes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintakeslist
---
