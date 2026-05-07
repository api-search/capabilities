---
categories: []
consumed_apis: []
description: Unified capability for USDA Agricultural Research Service data access, combining FoodData Central nutritional data with Ag Data Commons agricultural research dataset discovery. Supports nutritionists, agricultural researchers, food scientists, and data analysts.
layout: capability
name: USDA ARS Agricultural Research Data
operations:
- description: Search USDA FoodData Central for nutritional data
  method: GET
  name: search-foods
  path: /v1/foods/search
- description: Get full nutritional data for a specific food
  method: GET
  name: get-food
  path: /v1/foods/{fdcId}
- description: Search Ag Data Commons for research datasets
  method: GET
  name: search-datasets
  path: /v1/research/datasets
- description: Get full metadata for a research dataset
  method: GET
  name: get-dataset
  path: /v1/research/datasets/{id}
personas: []
provider_name: USDA Agricultural Research Service (ARS)
provider_slug: usda-agricultural-research-service-ars-
search_terms:
- individual food nutritional record
- agricultural research datasets
- get full metadata and download links for a specific usda research dataset
- nutrition
- get full metadata for a research dataset
- food data
- get food
- food safety
- search usda ag data commons for agricultural research datasets covering soil health, crop genetics, animal production, food safety, and more.
- get research dataset
- browse usda foundation foods — the highest quality nutritional data with detailed metadata and extended nutrient values.
- get dataset
- research dataset detail
- agriculture
- search research datasets
- research
- food nutritional data search
- search usda fooddata central for nutritional data
- search foods
- agricultural research
- get detailed nutritional composition (calories, macros, vitamins, minerals) for a specific food item by its usda fdc id.
- search ag data commons for research datasets
- search usda fooddata central for foods by name or keyword. returns nutritional data from foundation, sr legacy, survey, and branded food databases.
- get full nutritional data for a specific food
- browse foundation foods
- search datasets
- query tabular data records within a published usda research dataset (for datasets with structured/tabular data in the ag data commons datastore).
- get food nutrition
- federal government
- open data
- query dataset records
slug: agricultural-research-data
source_filename: agricultural-research-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USDA ARS Agricultural Research Data\n  description: Unified capability for USDA Agricultural Research Service data access, combining FoodData Central nutritional\n    data with Ag Data Commons agricultural research dataset discovery. Supports nutritionists, agricultural researchers, food\n    scientists, and data analysts.\n  tags:\n  - Food Data\n  - Nutrition\n  - Agricultural Research\n  - Open Data\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USDA_FDC_API_KEY: USDA_FDC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: usda-fdc\n    baseUri: https://api.nal.usda.gov/fdc/v1\n    description: USDA FoodData Central REST API.\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{USDA_FDC_API_KEY}}'\n      placement: query\n    resources:\n    - name: food-search\n      path: /foods/search\n      description: Search foods by keywords\n\
  \      operations:\n      - name: search-foods\n        method: GET\n        description: Search for foods matching keywords\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search keywords\n        - name: dataType\n          in: query\n          type: string\n          required: false\n          description: Filter by data type (Foundation, Branded, SR Legacy, etc.)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 200)\n        - name: pageNumber\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: brandOwner\n          in: query\n          type: string\n          required: false\n          description: Filter by brand owner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: food-detail\n      path: /food/{fdcId}\n      description: Individual food record\n      operations:\n      - name: get-food\n        method: GET\n        description: Get detailed nutritional data for a food by FDC ID\n        inputParameters:\n        - name: fdcId\n          in: path\n          type: integer\n          required: true\n          description: FoodData Central ID\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: abridged or full\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: foods-list\n      path: /foods/list\n      description: Browse foods list\n      operations:\n      - name: list-foods\n        method: GET\n        description: Get paginated list of foods in abridged format\n        inputParameters:\n        - name: dataType\n          in: query\n          type: string\n\
  \          required: false\n          description: Filter by data type\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: pageNumber\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  - type: http\n    namespace: usda-adc\n    baseUri: https://data.nal.usda.gov\n    description: USDA Ag Data Commons CKAN API.\n    resources:\n    - name: dataset-search\n      path: /api/action/package_search\n      description: Search agricultural research datasets\n      operations:\n      - name: search-datasets\n        method: GET\n        description: Search Ag Data Commons catalog for agricultural research datasets\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n   \
  \       required: false\n          description: Search query\n        - name: fq\n          in: query\n          type: string\n          required: false\n          description: Filter query\n        - name: rows\n          in: query\n          type: integer\n          required: false\n          description: Number of results (max 1000)\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataset-detail\n      path: /api/action/package_show\n      description: Dataset detail by ID\n      operations:\n      - name: get-dataset\n        method: GET\n        description: Get full metadata for a specific dataset\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Dataset ID or name\
  \ slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datastore-search\n      path: /api/action/datastore_search\n      description: Query data records within a dataset resource\n      operations:\n      - name: query-datastore\n        method: GET\n        description: Query tabular data records within a published dataset\n        inputParameters:\n        - name: resource_id\n          in: query\n          type: string\n          required: true\n          description: Resource ID to query\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Rows to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ars-data-api\n    description: Unified REST API for USDA ARS food and agricultural research data.\n    resources:\n    - path: /v1/foods/search\n      name: food-search\n      description: Food nutritional data search\n      operations:\n      - method: GET\n        name: search-foods\n        description: Search USDA FoodData Central for nutritional data\n        call: usda-fdc.search-foods\n        with:\n          query: rest.query\n          dataType: rest.dataType\n          pageSize: rest.pageSize\n          pageNumber: rest.pageNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/foods/{fdcId}\n      name: food\n      description: Individual food nutritional record\n      operations:\n      - method: GET\n        name: get-food\n        description: Get full\
  \ nutritional data for a specific food\n        call: usda-fdc.get-food\n        with:\n          fdcId: rest.fdcId\n          format: full\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/datasets\n      name: datasets\n      description: Agricultural research datasets\n      operations:\n      - method: GET\n        name: search-datasets\n        description: Search Ag Data Commons for research datasets\n        call: usda-adc.search-datasets\n        with:\n          q: rest.q\n          rows: rest.rows\n          start: rest.start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/research/datasets/{id}\n      name: dataset\n      description: Research dataset detail\n      operations:\n      - method: GET\n        name: get-dataset\n        description: Get full metadata for a research dataset\n        call: usda-adc.get-dataset\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ars-data-mcp\n    transport: http\n    description: MCP server for AI-assisted USDA ARS food and agricultural research data access.\n    tools:\n    - name: search-foods\n      description: Search USDA FoodData Central for foods by name or keyword. Returns nutritional data from Foundation, SR\n        Legacy, Survey, and Branded food databases.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usda-fdc.search-foods\n      with:\n        query: tools.query\n        dataType: tools.dataType\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-food-nutrition\n      description: Get detailed nutritional composition (calories, macros, vitamins, minerals) for a specific food item by\n        its USDA FDC ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usda-fdc.get-food\n     \
  \ with:\n        fdcId: tools.fdcId\n        format: full\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-foundation-foods\n      description: Browse USDA Foundation Foods — the highest quality nutritional data with detailed metadata and extended\n        nutrient values.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usda-fdc.list-foods\n      with:\n        dataType: Foundation\n        pageSize: tools.pageSize\n        pageNumber: tools.pageNumber\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: search-research-datasets\n      description: Search USDA Ag Data Commons for agricultural research datasets covering soil health, crop genetics, animal\n        production, food safety, and more.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usda-adc.search-datasets\n      with:\n        q: tools.q\n        rows: tools.rows\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-research-dataset\n      description: Get full metadata and download links for a specific USDA research dataset\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usda-adc.get-dataset\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-dataset-records\n      description: Query tabular data records within a published USDA research dataset (for datasets with structured/tabular\n        data in the Ag Data Commons datastore).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: usda-adc.query-datastore\n      with:\n        resource_id: tools.resource_id\n        q: tools.q\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/usda-agricultural-research-service-ars-/refs/heads/main/capabilities/agricultural-research-data.yaml
tags:
- Food Data
- Nutrition
- Agricultural Research
- Open Data
- Federal Government
tools:
- description: Search USDA FoodData Central for foods by name or keyword. Returns nutritional data from Foundation, SR Legacy, Survey, and Branded food databases.
  hints:
    openWorld: true
    readOnly: true
  name: search-foods
- description: Get detailed nutritional composition (calories, macros, vitamins, minerals) for a specific food item by its USDA FDC ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-food-nutrition
- description: Browse USDA Foundation Foods — the highest quality nutritional data with detailed metadata and extended nutrient values.
  hints:
    openWorld: true
    readOnly: true
  name: browse-foundation-foods
- description: Search USDA Ag Data Commons for agricultural research datasets covering soil health, crop genetics, animal production, food safety, and more.
  hints:
    openWorld: true
    readOnly: true
  name: search-research-datasets
- description: Get full metadata and download links for a specific USDA research dataset
  hints:
    openWorld: false
    readOnly: true
  name: get-research-dataset
- description: Query tabular data records within a published USDA research dataset (for datasets with structured/tabular data in the Ag Data Commons datastore).
  hints:
    openWorld: false
    readOnly: true
  name: query-dataset-records
---
