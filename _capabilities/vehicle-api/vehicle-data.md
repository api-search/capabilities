---
api_specs:
- filename: vehicle-api-openapi.yml
  format: yaml
  label: vehicle-api
  slug: vehicle-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vehicle-api/refs/heads/main/openapi/vehicle-api-openapi.yml
categories: []
consumed_apis:
- vehicle-api
description: Customer workflow capability for automotive vehicle data research and shopping. Combines Edmunds vehicle catalog (makes, models, styles), TMV pricing, media assets, and dealer inventory into a unified interface for car shoppers, dealer platforms, and automotive application developers.
layout: capability
name: Vehicle Data Workflow
operations:
- description: List all vehicle makes with optional year and availability filtering
  method: GET
  name: list-makes
  path: /v1/makes
- description: List all models for a given vehicle make
  method: GET
  name: list-models
  path: /v1/makes/{makeNiceName}/models
- description: List available years and trim styles for a make/model
  method: GET
  name: list-model-years
  path: /v1/makes/{makeNiceName}/models/{modelNiceName}/years
- description: Get complete specs, options, and pricing for a vehicle style
  method: GET
  name: get-style
  path: /v1/styles/{styleId}
- description: Get Edmunds TMV price for a vehicle style by zip code
  method: GET
  name: get-tmv-price
  path: /v1/pricing/tmv
- description: Get photo assets for a vehicle style
  method: GET
  name: get-style-photos
  path: /v1/styles/{styleId}/photos
- description: Search dealer inventory by make, model, and location
  method: GET
  name: search-inventory
  path: /v1/inventory
personas: []
provider_name: Vehicle API
provider_slug: vehicle-api
search_terms:
- get style photos
- list makes
- list models
- automotive
- search dealer inventory
- get vehicle style details
- get vehicle photos
- list all models for a given vehicle make
- inventory
- list available years and trim styles for a make/model
- search inventory
- get true market value pricing
- get photo assets for a vehicle style in multiple sizes
- pricing
- list models for a vehicle make
- search dealer inventory by make, model, and location
- list vehicle makes
- vehicles
- list all vehicle makes available in the edmunds catalog
- get complete vehicle style details including specs, options, and pricing
- get edmunds true market value price for a vehicle style at a given zip code
- list model years and trim styles
- list all vehicle makes with optional year and availability filtering
- edmunds
- list model years
- get edmunds tmv price for a vehicle style by zip code
- list available model years and trim styles for a make and model
- cars
- list all models for a specific vehicle make
- get photo assets for a vehicle style
- get complete specs, options, and pricing for a vehicle style
- get tmv price
- get style
- search dealer inventory near a zip code for a specific make, model, and year
slug: vehicle-data
source_filename: vehicle-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vehicle Data Workflow\"\n  description: >-\n    Customer workflow capability for automotive vehicle data research and shopping.\n    Combines Edmunds vehicle catalog (makes, models, styles), TMV pricing,\n    media assets, and dealer inventory into a unified interface for car\n    shoppers, dealer platforms, and automotive application developers.\n  tags:\n    - Automotive\n    - Cars\n    - Edmunds\n    - Inventory\n    - Pricing\n    - Vehicles\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      EDMUNDS_API_KEY: EDMUNDS_API_KEY\n\ncapability:\n  consumes:\n    - import: vehicle-api\n      location: ./shared/vehicle-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vehicle-data-api\n      description: \"Unified REST API for vehicle data research and automotive shopping workflows.\"\n      resources:\n        - path: /v1/makes\n          name: makes\n\
  \          description: \"List vehicle makes\"\n          operations:\n            - method: GET\n              name: list-makes\n              description: \"List all vehicle makes with optional year and availability filtering\"\n              call: \"vehicle-api.list-makes\"\n              with:\n                state: \"rest.state\"\n                year: \"rest.year\"\n                view: \"rest.view\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/makes/{makeNiceName}/models\n          name: models\n          description: \"List models for a vehicle make\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List all models for a given vehicle make\"\n              call: \"vehicle-api.list-models\"\n              with:\n                makeNiceName: \"rest.makeNiceName\"\n                state: \"rest.state\"\n                year: \"rest.year\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/makes/{makeNiceName}/models/{modelNiceName}/years\n          name: model-years\n          description: \"List model years and trim styles\"\n          operations:\n            - method: GET\n              name: list-model-years\n              description: \"List available years and trim styles for a make/model\"\n              call: \"vehicle-api.list-model-years\"\n              with:\n                makeNiceName: \"rest.makeNiceName\"\n                modelNiceName: \"rest.modelNiceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/styles/{styleId}\n          name: style\n          description: \"Get vehicle style details\"\n          operations:\n            - method: GET\n              name: get-style\n              description: \"Get complete specs, options, and pricing for a vehicle\
  \ style\"\n              call: \"vehicle-api.get-style\"\n              with:\n                styleId: \"rest.styleId\"\n                view: \"rest.view\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pricing/tmv\n          name: tmv-pricing\n          description: \"Get True Market Value pricing\"\n          operations:\n            - method: GET\n              name: get-tmv-price\n              description: \"Get Edmunds TMV price for a vehicle style by zip code\"\n              call: \"vehicle-api.get-tmv-price\"\n              with:\n                styleId: \"rest.styleId\"\n                zip: \"rest.zip\"\n                state: \"rest.state\"\n                mileage: \"rest.mileage\"\n                condition: \"rest.condition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/styles/{styleId}/photos\n          name: photos\n\
  \          description: \"Get vehicle photos\"\n          operations:\n            - method: GET\n              name: get-style-photos\n              description: \"Get photo assets for a vehicle style\"\n              call: \"vehicle-api.get-style-photos\"\n              with:\n                styleId: \"rest.styleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/inventory\n          name: inventory\n          description: \"Search dealer inventory\"\n          operations:\n            - method: GET\n              name: search-inventory\n              description: \"Search dealer inventory by make, model, and location\"\n              call: \"vehicle-api.search-inventory\"\n              with:\n                make: \"rest.make\"\n                model: \"rest.model\"\n                year: \"rest.year\"\n                zip: \"rest.zip\"\n                radius: \"rest.radius\"\n                pageSize: \"\
  rest.pageSize\"\n                pageNum: \"rest.pageNum\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vehicle-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted automotive vehicle research and shopping.\"\n      tools:\n        - name: list-makes\n          description: \"List all vehicle makes available in the Edmunds catalog\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-api.list-makes\"\n          with:\n            state: \"tools.state\"\n            year: \"tools.year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-models\n          description: \"List all models for a specific vehicle make\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-api.list-models\"\n      \
  \    with:\n            makeNiceName: \"tools.makeNiceName\"\n            state: \"tools.state\"\n            year: \"tools.year\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-model-years\n          description: \"List available model years and trim styles for a make and model\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-api.list-model-years\"\n          with:\n            makeNiceName: \"tools.makeNiceName\"\n            modelNiceName: \"tools.modelNiceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-style\n          description: \"Get complete vehicle style details including specs, options, and pricing\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-api.get-style\"\n          with:\n            styleId: \"tools.styleId\"\n            view:\
  \ \"tools.view\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tmv-price\n          description: \"Get Edmunds True Market Value price for a vehicle style at a given zip code\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vehicle-api.get-tmv-price\"\n          with:\n            styleId: \"tools.styleId\"\n            zip: \"tools.zip\"\n            state: \"tools.state\"\n            mileage: \"tools.mileage\"\n            condition: \"tools.condition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-style-photos\n          description: \"Get photo assets for a vehicle style in multiple sizes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-api.get-style-photos\"\n          with:\n            styleId: \"tools.styleId\"\n          outputParameters:\n      \
  \      - type: object\n              mapping: \"$.\"\n\n        - name: search-inventory\n          description: \"Search dealer inventory near a zip code for a specific make, model, and year\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vehicle-api.search-inventory\"\n          with:\n            make: \"tools.make\"\n            model: \"tools.model\"\n            year: \"tools.year\"\n            zip: \"tools.zip\"\n            radius: \"tools.radius\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vehicle-api/refs/heads/main/capabilities/vehicle-data.yaml
tags:
- Automotive
- Cars
- Edmunds
- Inventory
- Pricing
- Vehicles
tools:
- description: List all vehicle makes available in the Edmunds catalog
  hints:
    openWorld: false
    readOnly: true
  name: list-makes
- description: List all models for a specific vehicle make
  hints:
    openWorld: false
    readOnly: true
  name: list-models
- description: List available model years and trim styles for a make and model
  hints:
    openWorld: false
    readOnly: true
  name: list-model-years
- description: Get complete vehicle style details including specs, options, and pricing
  hints:
    openWorld: false
    readOnly: true
  name: get-style
- description: Get Edmunds True Market Value price for a vehicle style at a given zip code
  hints:
    openWorld: true
    readOnly: true
  name: get-tmv-price
- description: Get photo assets for a vehicle style in multiple sizes
  hints:
    openWorld: false
    readOnly: true
  name: get-style-photos
- description: Search dealer inventory near a zip code for a specific make, model, and year
  hints:
    openWorld: true
    readOnly: true
  name: search-inventory
---
