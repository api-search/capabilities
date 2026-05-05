---
api_specs:
- filename: usda-fooddata-central-openapi.yml
  format: yaml
  label: fdc
  slug: fdc
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-department-of-agriculture/refs/heads/main/openapi/usda-fooddata-central-openapi.yml
- filename: usda-nass-quickstats-openapi.yml
  format: yaml
  label: nass
  slug: nass
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-department-of-agriculture/refs/heads/main/openapi/usda-nass-quickstats-openapi.yml
categories: []
consumed_apis:
- fdc
- nass
description: Unified capability for food and agricultural data research workflows combining USDA FoodData Central nutrient data with NASS agricultural production statistics. Used by nutritionists, food researchers, public health analysts, and agricultural economists to access comprehensive USDA food and farm data.
layout: capability
name: USDA Food and Agriculture Data Research
operations:
- description: Search for foods by keyword across all USDA food data types
  method: GET
  name: search-foods
  path: /v1/foods/search
- description: Get food item with complete nutrient data
  method: GET
  name: get-food
  path: /v1/foods/{fdcId}
- description: Get all available nutrients
  method: GET
  name: list-nutrients
  path: /v1/nutrients
- description: Get agricultural commodity production statistics
  method: GET
  name: get-ag-statistics
  path: /v1/agriculture/statistics
- description: Get valid values for a NASS statistics parameter
  method: GET
  name: get-parameter-values
  path: /v1/agriculture/parameters
personas: []
provider_name: United States Department of Agriculture
provider_slug: united-states-department-of-agriculture
search_terms:
- food
- federal government
- query usda nass agricultural production statistics
- search usda fooddata central for food items
- query usda nass for livestock and animal production statistics
- usda
- get all available nutrients
- get food nutrition
- get valid values for a nass statistics parameter
- food safety
- get agricultural commodity production statistics
- list all nutrients tracked in fooddata central
- list nutrients
- get ag statistics
- nutrition
- rural development
- statistics
- list all nutrients tracked in usda fooddata central including ids, names, and units
- search for foods by keyword across all usda food data types
- get food
- look up valid values for nass statistics query parameters to build accurate queries
- retrieve full nutrient profile for a specific food
- agriculture
- climate
- search foods
- look up valid values for statistics query parameters
- get parameter values
- get nass parameter values
- get livestock statistics
- query usda nass for crop production statistics by commodity, year, and state
- get detailed nutrient profile for a specific food item from usda fooddata central
- search usda fooddata central for food items using keywords
- get food item with complete nutrient data
- get crop production statistics
slug: food-data-research
source_filename: food-data-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USDA Food and Agriculture Data Research\"\n  description: >-\n    Unified capability for food and agricultural data research workflows\n    combining USDA FoodData Central nutrient data with NASS agricultural\n    production statistics. Used by nutritionists, food researchers, public\n    health analysts, and agricultural economists to access comprehensive USDA\n    food and farm data.\n  tags:\n    - Food\n    - Nutrition\n    - Agriculture\n    - Statistics\n    - USDA\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      FDC_API_KEY: FDC_API_KEY\n      NASS_API_KEY: NASS_API_KEY\n\ncapability:\n  consumes:\n    - import: fdc\n      location: ./shared/usda-fooddata-central.yaml\n    - import: nass\n      location: ./shared/usda-nass-quickstats.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: usda-food-ag-api\n      description:\
  \ \"Unified REST API for USDA food nutrition and agricultural statistics research.\"\n      resources:\n        - path: /v1/foods/search\n          name: food-search\n          description: \"Search USDA FoodData Central for food items\"\n          operations:\n            - method: GET\n              name: search-foods\n              description: \"Search for foods by keyword across all USDA food data types\"\n              call: \"fdc.search-foods\"\n              with:\n                query: \"rest.query\"\n                dataType: \"rest.dataType\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/foods/{fdcId}\n          name: food-detail\n          description: \"Retrieve full nutrient profile for a specific food\"\n          operations:\n            - method: GET\n              name: get-food\n              description: \"Get food item with complete nutrient data\"\
  \n              call: \"fdc.get-food-by-id\"\n              with:\n                fdcId: \"rest.fdcId\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nutrients\n          name: nutrients\n          description: \"List all nutrients tracked in FoodData Central\"\n          operations:\n            - method: GET\n              name: list-nutrients\n              description: \"Get all available nutrients\"\n              call: \"fdc.get-nutrients\"\n              with: {}\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/agriculture/statistics\n          name: ag-statistics\n          description: \"Query USDA NASS agricultural production statistics\"\n          operations:\n            - method: GET\n              name: get-ag-statistics\n              description: \"Get agricultural commodity production\
  \ statistics\"\n              call: \"nass.get-agricultural-statistics\"\n              with:\n                commodity_desc: \"rest.commodity\"\n                statisticcat_desc: \"rest.category\"\n                year: \"rest.year\"\n                state_name: \"rest.state\"\n                agg_level_desc: \"rest.aggLevel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/agriculture/parameters\n          name: ag-parameters\n          description: \"Look up valid values for statistics query parameters\"\n          operations:\n            - method: GET\n              name: get-parameter-values\n              description: \"Get valid values for a NASS statistics parameter\"\n              call: \"nass.get-parameter-values\"\n              with:\n                param: \"rest.param\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n     \
  \ port: 9090\n      namespace: usda-food-ag-mcp\n      transport: http\n      description: \"MCP server for AI-assisted food nutrition and agricultural data research.\"\n      tools:\n        - name: search-foods\n          description: \"Search USDA FoodData Central for food items using keywords\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"fdc.search-foods\"\n          with:\n            query: \"tools.query\"\n            dataType: \"tools.data_type\"\n            pageSize: \"tools.page_size\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-food-nutrition\n          description: \"Get detailed nutrient profile for a specific food item from USDA FoodData Central\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"fdc.get-food-by-id\"\n          with:\n            fdcId: \"tools.fdc_id\"\n            format: \"tools.format\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nutrients\n          description: \"List all nutrients tracked in USDA FoodData Central including IDs, names, and units\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"fdc.get-nutrients\"\n          with: {}\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-crop-production-statistics\n          description: \"Query USDA NASS for crop production statistics by commodity, year, and state\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nass.get-agricultural-statistics\"\n          with:\n            commodity_desc: \"tools.commodity\"\n            statisticcat_desc: \"tools.category\"\n            year: \"tools.year\"\n            state_name: \"tools.state\"\n            agg_level_desc: \"tools.agg_level\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-livestock-statistics\n          description: \"Query USDA NASS for livestock and animal production statistics\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nass.get-agricultural-statistics\"\n          with:\n            commodity_desc: \"tools.commodity\"\n            statisticcat_desc: \"tools.category\"\n            year: \"tools.year\"\n            state_name: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-nass-parameter-values\n          description: \"Look up valid values for NASS statistics query parameters to build accurate queries\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nass.get-parameter-values\"\n          with:\n            param: \"tools.param_name\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-department-of-agriculture/refs/heads/main/capabilities/food-data-research.yaml
tags:
- Food
- Nutrition
- Agriculture
- Statistics
- USDA
- Federal Government
tools:
- description: Search USDA FoodData Central for food items using keywords
  hints:
    idempotent: true
    readOnly: true
  name: search-foods
- description: Get detailed nutrient profile for a specific food item from USDA FoodData Central
  hints:
    idempotent: true
    readOnly: true
  name: get-food-nutrition
- description: List all nutrients tracked in USDA FoodData Central including IDs, names, and units
  hints:
    idempotent: true
    readOnly: true
  name: list-nutrients
- description: Query USDA NASS for crop production statistics by commodity, year, and state
  hints:
    idempotent: true
    readOnly: true
  name: get-crop-production-statistics
- description: Query USDA NASS for livestock and animal production statistics
  hints:
    idempotent: true
    readOnly: true
  name: get-livestock-statistics
- description: Look up valid values for NASS statistics query parameters to build accurate queries
  hints:
    idempotent: true
    readOnly: true
  name: get-nass-parameter-values
---
