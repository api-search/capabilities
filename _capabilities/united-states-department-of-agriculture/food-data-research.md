---
categories: []
consumed_apis: []
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
- get valid values for a nass statistics parameter
- search usda fooddata central for food items using keywords
- nutrition
- retrieve full nutrient profile for a specific food
- query usda nass for crop production statistics by commodity, year, and state
- look up valid values for nass statistics query parameters to build accurate queries
- get ag statistics
- query usda nass agricultural production statistics
- get food
- search foods
- agriculture
- get nass parameter values
- list all nutrients tracked in usda fooddata central including ids, names, and units
- query usda nass for livestock and animal production statistics
- get crop production statistics
- rural development
- get livestock statistics
- climate
- list nutrients
- get all available nutrients
- food
- get food nutrition
- list all nutrients tracked in fooddata central
- federal government
- usda
- food safety
- get food item with complete nutrient data
- get detailed nutrient profile for a specific food item from usda fooddata central
- get parameter values
- search for foods by keyword across all usda food data types
- statistics
- look up valid values for statistics query parameters
- get agricultural commodity production statistics
- search usda fooddata central for food items
slug: food-data-research
source_filename: food-data-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USDA Food and Agriculture Data Research\n  description: Unified capability for food and agricultural data research workflows combining USDA FoodData Central nutrient\n    data with NASS agricultural production statistics. Used by nutritionists, food researchers, public health analysts, and\n    agricultural economists to access comprehensive USDA food and farm data.\n  tags:\n  - Food\n  - Nutrition\n  - Agriculture\n  - Statistics\n  - USDA\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FDC_API_KEY: FDC_API_KEY\n    NASS_API_KEY: NASS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: fdc\n    baseUri: https://api.nal.usda.gov/fdc/v1\n    description: USDA FoodData Central REST API\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{FDC_API_KEY}}'\n      placement: query\n    resources:\n    - name: food-search\n      path: /foods/search\n\
  \      description: Search for foods by keywords and filters\n      operations:\n      - name: search-foods\n        method: GET\n        description: Search Foods\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search terms\n        - name: dataType\n          in: query\n          type: string\n          required: false\n          description: Food data type filter\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: pageNumber\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: food-detail\n      path: /food/{fdcId}\n      description: Get detailed food item with nutrient data\n      operations:\n\
  \      - name: get-food-by-id\n        method: GET\n        description: Get Food By FDC ID\n        inputParameters:\n        - name: fdcId\n          in: path\n          type: integer\n          required: true\n          description: FoodData Central food ID\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: abridged or full nutrient format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nutrients\n      path: /nutrients\n      description: List all available nutrients\n      operations:\n      - name: get-nutrients\n        method: GET\n        description: Get All Nutrients\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: nass\n    baseUri: https://quickstats.nass.usda.gov/api\n    description:\
  \ USDA NASS Quick Stats API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{NASS_API_KEY}}'\n      placement: query\n    resources:\n    - name: statistics\n      path: /api_GET/\n      description: Query agricultural statistics data\n      operations:\n      - name: get-agricultural-statistics\n        method: GET\n        description: Get Agricultural Statistics\n        inputParameters:\n        - name: commodity_desc\n          in: query\n          type: string\n          required: false\n          description: Commodity name (e.g. CORN, WHEAT)\n        - name: statisticcat_desc\n          in: query\n          type: string\n          required: false\n          description: Statistics category\n        - name: year\n          in: query\n          type: string\n          required: false\n          description: Survey year\n        - name: state_name\n          in: query\n          type: string\n          required: false\n          description: State name\n \
  \       - name: agg_level_desc\n          in: query\n          type: string\n          required: false\n          description: Geographic aggregation level\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (JSON, CSV, XML)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parameter-values\n      path: /get_param_values/\n      description: Look up valid values for a query parameter\n      operations:\n      - name: get-parameter-values\n        method: GET\n        description: Get Valid Parameter Values\n        inputParameters:\n        - name: param\n          in: query\n          type: string\n          required: true\n          description: Parameter name to look up values for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: counts\n      path: /get_counts/\n      description: Get record count for a query\n      operations:\n      - name: get-record-count\n        method: GET\n        description: Get Record Count\n        inputParameters:\n        - name: commodity_desc\n          in: query\n          type: string\n          required: false\n          description: Commodity to count records for\n        - name: year\n          in: query\n          type: string\n          required: false\n          description: Year filter\n        - name: state_name\n          in: query\n          type: string\n          required: false\n          description: State filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: usda-food-ag-api\n    description: Unified REST API for USDA food nutrition and agricultural statistics research.\n    resources:\n    - path: /v1/foods/search\n\
  \      name: food-search\n      description: Search USDA FoodData Central for food items\n      operations:\n      - method: GET\n        name: search-foods\n        description: Search for foods by keyword across all USDA food data types\n        call: fdc.search-foods\n        with:\n          query: rest.query\n          dataType: rest.dataType\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/foods/{fdcId}\n      name: food-detail\n      description: Retrieve full nutrient profile for a specific food\n      operations:\n      - method: GET\n        name: get-food\n        description: Get food item with complete nutrient data\n        call: fdc.get-food-by-id\n        with:\n          fdcId: rest.fdcId\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nutrients\n      name: nutrients\n      description: List all nutrients tracked in FoodData\
  \ Central\n      operations:\n      - method: GET\n        name: list-nutrients\n        description: Get all available nutrients\n        call: fdc.get-nutrients\n        with: {}\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/agriculture/statistics\n      name: ag-statistics\n      description: Query USDA NASS agricultural production statistics\n      operations:\n      - method: GET\n        name: get-ag-statistics\n        description: Get agricultural commodity production statistics\n        call: nass.get-agricultural-statistics\n        with:\n          commodity_desc: rest.commodity\n          statisticcat_desc: rest.category\n          year: rest.year\n          state_name: rest.state\n          agg_level_desc: rest.aggLevel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agriculture/parameters\n      name: ag-parameters\n      description: Look up valid values for statistics query parameters\n\
  \      operations:\n      - method: GET\n        name: get-parameter-values\n        description: Get valid values for a NASS statistics parameter\n        call: nass.get-parameter-values\n        with:\n          param: rest.param\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: usda-food-ag-mcp\n    transport: http\n    description: MCP server for AI-assisted food nutrition and agricultural data research.\n    tools:\n    - name: search-foods\n      description: Search USDA FoodData Central for food items using keywords\n      hints:\n        readOnly: true\n        idempotent: true\n      call: fdc.search-foods\n      with:\n        query: tools.query\n        dataType: tools.data_type\n        pageSize: tools.page_size\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-food-nutrition\n      description: Get detailed nutrient profile for a specific food item from USDA FoodData Central\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: fdc.get-food-by-id\n      with:\n        fdcId: tools.fdc_id\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nutrients\n      description: List all nutrients tracked in USDA FoodData Central including IDs, names, and units\n      hints:\n        readOnly: true\n        idempotent: true\n      call: fdc.get-nutrients\n      with: {}\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-crop-production-statistics\n      description: Query USDA NASS for crop production statistics by commodity, year, and state\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nass.get-agricultural-statistics\n      with:\n        commodity_desc: tools.commodity\n        statisticcat_desc: tools.category\n        year: tools.year\n        state_name: tools.state\n        agg_level_desc: tools.agg_level\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-livestock-statistics\n      description: Query USDA NASS for livestock and animal production statistics\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nass.get-agricultural-statistics\n      with:\n        commodity_desc: tools.commodity\n        statisticcat_desc: tools.category\n        year: tools.year\n        state_name: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nass-parameter-values\n      description: Look up valid values for NASS statistics query parameters to build accurate queries\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nass.get-parameter-values\n      with:\n        param: tools.param_name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
