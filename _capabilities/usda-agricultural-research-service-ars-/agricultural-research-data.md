---
categories: []
consumed_apis:
- usda-fdc
- usda-adc
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
- get research dataset
- open data
- nutrition
- agricultural research datasets
- get full metadata for a research dataset
- food safety
- get food
- research
- search ag data commons for research datasets
- get food nutrition
- federal government
- get full metadata and download links for a specific usda research dataset
- get full nutritional data for a specific food
- research dataset detail
- agriculture
- search foods
- get dataset
- food data
- query dataset records
- agricultural research
- browse usda foundation foods — the highest quality nutritional data with detailed metadata and extended nutrient values.
- search research datasets
- query tabular data records within a published usda research dataset (for datasets with structured/tabular data in the ag data commons datastore).
- food nutritional data search
- search datasets
- search usda fooddata central for nutritional data
- individual food nutritional record
- search usda ag data commons for agricultural research datasets covering soil health, crop genetics, animal production, food safety, and more.
- search usda fooddata central for foods by name or keyword. returns nutritional data from foundation, sr legacy, survey, and branded food databases.
- get detailed nutritional composition (calories, macros, vitamins, minerals) for a specific food item by its usda fdc id.
- browse foundation foods
slug: agricultural-research-data
source_filename: agricultural-research-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USDA ARS Agricultural Research Data\"\n  description: >-\n    Unified capability for USDA Agricultural Research Service data access,\n    combining FoodData Central nutritional data with Ag Data Commons agricultural\n    research dataset discovery. Supports nutritionists, agricultural researchers,\n    food scientists, and data analysts.\n  tags:\n    - Food Data\n    - Nutrition\n    - Agricultural Research\n    - Open Data\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USDA_FDC_API_KEY: USDA_FDC_API_KEY\n\ncapability:\n  consumes:\n    - import: usda-fdc\n      location: ./shared/fooddata-central.yaml\n    - import: usda-adc\n      location: ./shared/ag-data-commons.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ars-data-api\n      description: \"Unified REST API for USDA ARS food and agricultural research data.\"\n   \
  \   resources:\n        - path: /v1/foods/search\n          name: food-search\n          description: \"Food nutritional data search\"\n          operations:\n            - method: GET\n              name: search-foods\n              description: \"Search USDA FoodData Central for nutritional data\"\n              call: \"usda-fdc.search-foods\"\n              with:\n                query: \"rest.query\"\n                dataType: \"rest.dataType\"\n                pageSize: \"rest.pageSize\"\n                pageNumber: \"rest.pageNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/foods/{fdcId}\n          name: food\n          description: \"Individual food nutritional record\"\n          operations:\n            - method: GET\n              name: get-food\n              description: \"Get full nutritional data for a specific food\"\n              call: \"usda-fdc.get-food\"\n              with:\n         \
  \       fdcId: \"rest.fdcId\"\n                format: \"full\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/research/datasets\n          name: datasets\n          description: \"Agricultural research datasets\"\n          operations:\n            - method: GET\n              name: search-datasets\n              description: \"Search Ag Data Commons for research datasets\"\n              call: \"usda-adc.search-datasets\"\n              with:\n                q: \"rest.q\"\n                rows: \"rest.rows\"\n                start: \"rest.start\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/research/datasets/{id}\n          name: dataset\n          description: \"Research dataset detail\"\n          operations:\n            - method: GET\n              name: get-dataset\n              description: \"Get full metadata for a research dataset\"\
  \n              call: \"usda-adc.get-dataset\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ars-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USDA ARS food and agricultural research data access.\"\n      tools:\n        - name: search-foods\n          description: >-\n            Search USDA FoodData Central for foods by name or keyword. Returns\n            nutritional data from Foundation, SR Legacy, Survey, and Branded food databases.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usda-fdc.search-foods\"\n          with:\n            query: \"tools.query\"\n            dataType: \"tools.dataType\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ get-food-nutrition\n          description: >-\n            Get detailed nutritional composition (calories, macros, vitamins, minerals)\n            for a specific food item by its USDA FDC ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usda-fdc.get-food\"\n          with:\n            fdcId: \"tools.fdcId\"\n            format: \"full\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-foundation-foods\n          description: >-\n            Browse USDA Foundation Foods — the highest quality nutritional data with\n            detailed metadata and extended nutrient values.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usda-fdc.list-foods\"\n          with:\n            dataType: \"Foundation\"\n            pageSize: \"tools.pageSize\"\n            pageNumber: \"tools.pageNumber\"\n          outputParameters:\n            - type:\
  \ array\n              mapping: \"$.\"\n        - name: search-research-datasets\n          description: >-\n            Search USDA Ag Data Commons for agricultural research datasets covering\n            soil health, crop genetics, animal production, food safety, and more.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usda-adc.search-datasets\"\n          with:\n            q: \"tools.q\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-research-dataset\n          description: \"Get full metadata and download links for a specific USDA research dataset\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usda-adc.get-dataset\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-dataset-records\n  \
  \        description: >-\n            Query tabular data records within a published USDA research dataset\n            (for datasets with structured/tabular data in the Ag Data Commons datastore).\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"usda-adc.query-datastore\"\n          with:\n            resource_id: \"tools.resource_id\"\n            q: \"tools.q\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
