---
categories: []
consumed_apis: []
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
- search dealer inventory by make, model, and location
- list model years
- list available model years and trim styles for a make and model
- edmunds
- get true market value pricing
- list models for a vehicle make
- get vehicle photos
- inventory
- get complete vehicle style details including specs, options, and pricing
- search dealer inventory
- vehicles
- list all vehicle makes available in the edmunds catalog
- list all vehicle makes with optional year and availability filtering
- get tmv price
- list all models for a given vehicle make
- get complete specs, options, and pricing for a vehicle style
- pricing
- get photo assets for a vehicle style
- list model years and trim styles
- cars
- list models
- search dealer inventory near a zip code for a specific make, model, and year
- automotive
- get edmunds true market value price for a vehicle style at a given zip code
- get style
- get vehicle style details
- list makes
- list available years and trim styles for a make/model
- get photo assets for a vehicle style in multiple sizes
- list all models for a specific vehicle make
- list vehicle makes
- get edmunds tmv price for a vehicle style by zip code
- search inventory
slug: vehicle-data
source_filename: vehicle-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vehicle Data Workflow\n  description: Customer workflow capability for automotive vehicle data research and shopping. Combines Edmunds vehicle catalog\n    (makes, models, styles), TMV pricing, media assets, and dealer inventory into a unified interface for car shoppers, dealer\n    platforms, and automotive application developers.\n  tags:\n  - Automotive\n  - Cars\n  - Edmunds\n  - Inventory\n  - Pricing\n  - Vehicles\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    EDMUNDS_API_KEY: EDMUNDS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vehicle-api\n    baseUri: https://api.edmunds.com/api\n    description: Edmunds Vehicle API v2\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{env.EDMUNDS_API_KEY}}'\n      placement: query\n    resources:\n    - name: makes\n      path: /vehicle/v2/makes\n      description: List all vehicle makes with optional\
  \ year and state filtering\n      operations:\n      - name: list-makes\n        method: GET\n        description: Return all vehicle makes filtered by state and year\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: new, used, or future\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: 4-digit model year\n        - name: view\n          in: query\n          type: string\n          required: false\n          description: basic or full\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: models\n      path: /vehicle/v2/makes/{makeNiceName}/models\n      description: List vehicle models for a given make\n      operations:\n      - name: list-models\n        method: GET\n        description: Return all models for a vehicle make\n        inputParameters:\n\
  \        - name: makeNiceName\n          in: path\n          type: string\n          required: true\n          description: URL-friendly make name (e.g. toyota)\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: new, used, or future\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: 4-digit model year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-years\n      path: /vehicle/v2/makes/{makeNiceName}/models/{modelNiceName}/years\n      description: List available model years and styles for a make/model\n      operations:\n      - name: list-model-years\n        method: GET\n        description: Return all model years and trims for a make and model\n        inputParameters:\n        - name: makeNiceName\n          in: path\n          type: string\n         \
  \ required: true\n          description: URL-friendly make name\n        - name: modelNiceName\n          in: path\n          type: string\n          required: true\n          description: URL-friendly model name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: style\n      path: /vehicle/v2/styles/{styleId}\n      description: Get complete details for a vehicle style (trim)\n      operations:\n      - name: get-style\n        method: GET\n        description: Return complete vehicle style data including specs and pricing\n        inputParameters:\n        - name: styleId\n          in: path\n          type: integer\n          required: true\n          description: Edmunds style ID\n        - name: view\n          in: query\n          type: string\n          required: false\n          description: basic or full\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: tmv-price\n      path: /vehicle/v2/price/tmv/simple\n      description: Get True Market Value pricing for a vehicle style\n      operations:\n      - name: get-tmv-price\n        method: GET\n        description: Return TMV pricing for a vehicle style by zip code\n        inputParameters:\n        - name: styleId\n          in: query\n          type: integer\n          required: true\n          description: Edmunds style ID\n        - name: zip\n          in: query\n          type: string\n          required: true\n          description: 5-digit US ZIP code\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: new or used\n        - name: mileage\n          in: query\n          type: integer\n          required: false\n          description: Mileage for used vehicle pricing\n        - name: condition\n          in: query\n          type: string\n          required: false\n\
  \          description: Outstanding, Clean, Average, or Rough\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: photos\n      path: /vehicle/v2/media/{styleId}/photos\n      description: Get vehicle photos for a style\n      operations:\n      - name: get-style-photos\n        method: GET\n        description: Return photo assets for a vehicle style in multiple sizes\n        inputParameters:\n        - name: styleId\n          in: path\n          type: integer\n          required: true\n          description: Edmunds style ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory\n      path: /vehicle/v2/inventory\n      description: Search dealer inventory by make, model, and location\n      operations:\n      - name: search-inventory\n        method: GET\n        description: Search dealer inventory with\
  \ make, model, year, and zip code filters\n        inputParameters:\n        - name: make\n          in: query\n          type: string\n          required: true\n          description: Make nice name (e.g. toyota)\n        - name: model\n          in: query\n          type: string\n          required: true\n          description: Model nice name (e.g. camry)\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Model year\n        - name: zip\n          in: query\n          type: string\n          required: true\n          description: 5-digit ZIP code\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in miles\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: pageNum\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vehicle-data-api\n    description: Unified REST API for vehicle data research and automotive shopping workflows.\n    resources:\n    - path: /v1/makes\n      name: makes\n      description: List vehicle makes\n      operations:\n      - method: GET\n        name: list-makes\n        description: List all vehicle makes with optional year and availability filtering\n        call: vehicle-api.list-makes\n        with:\n          state: rest.state\n          year: rest.year\n          view: rest.view\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/makes/{makeNiceName}/models\n      name: models\n      description: List models for a vehicle make\n      operations:\n      - method: GET\n        name: list-models\n       \
  \ description: List all models for a given vehicle make\n        call: vehicle-api.list-models\n        with:\n          makeNiceName: rest.makeNiceName\n          state: rest.state\n          year: rest.year\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/makes/{makeNiceName}/models/{modelNiceName}/years\n      name: model-years\n      description: List model years and trim styles\n      operations:\n      - method: GET\n        name: list-model-years\n        description: List available years and trim styles for a make/model\n        call: vehicle-api.list-model-years\n        with:\n          makeNiceName: rest.makeNiceName\n          modelNiceName: rest.modelNiceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/styles/{styleId}\n      name: style\n      description: Get vehicle style details\n      operations:\n      - method: GET\n        name: get-style\n        description: Get complete specs,\
  \ options, and pricing for a vehicle style\n        call: vehicle-api.get-style\n        with:\n          styleId: rest.styleId\n          view: rest.view\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing/tmv\n      name: tmv-pricing\n      description: Get True Market Value pricing\n      operations:\n      - method: GET\n        name: get-tmv-price\n        description: Get Edmunds TMV price for a vehicle style by zip code\n        call: vehicle-api.get-tmv-price\n        with:\n          styleId: rest.styleId\n          zip: rest.zip\n          state: rest.state\n          mileage: rest.mileage\n          condition: rest.condition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/styles/{styleId}/photos\n      name: photos\n      description: Get vehicle photos\n      operations:\n      - method: GET\n        name: get-style-photos\n        description: Get photo assets for a vehicle style\n  \
  \      call: vehicle-api.get-style-photos\n        with:\n          styleId: rest.styleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Search dealer inventory\n      operations:\n      - method: GET\n        name: search-inventory\n        description: Search dealer inventory by make, model, and location\n        call: vehicle-api.search-inventory\n        with:\n          make: rest.make\n          model: rest.model\n          year: rest.year\n          zip: rest.zip\n          radius: rest.radius\n          pageSize: rest.pageSize\n          pageNum: rest.pageNum\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vehicle-data-mcp\n    transport: http\n    description: MCP server for AI-assisted automotive vehicle research and shopping.\n    tools:\n    - name: list-makes\n      description: List all vehicle makes available\
  \ in the Edmunds catalog\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-api.list-makes\n      with:\n        state: tools.state\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-models\n      description: List all models for a specific vehicle make\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-api.list-models\n      with:\n        makeNiceName: tools.makeNiceName\n        state: tools.state\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-model-years\n      description: List available model years and trim styles for a make and model\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-api.list-model-years\n      with:\n        makeNiceName: tools.makeNiceName\n        modelNiceName: tools.modelNiceName\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: get-style\n      description: Get complete vehicle style details including specs, options, and pricing\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-api.get-style\n      with:\n        styleId: tools.styleId\n        view: tools.view\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tmv-price\n      description: Get Edmunds True Market Value price for a vehicle style at a given zip code\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vehicle-api.get-tmv-price\n      with:\n        styleId: tools.styleId\n        zip: tools.zip\n        state: tools.state\n        mileage: tools.mileage\n        condition: tools.condition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-style-photos\n      description: Get photo assets for a vehicle style in multiple sizes\n      hints:\n        readOnly: true\n        openWorld: false\n \
  \     call: vehicle-api.get-style-photos\n      with:\n        styleId: tools.styleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-inventory\n      description: Search dealer inventory near a zip code for a specific make, model, and year\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vehicle-api.search-inventory\n      with:\n        make: tools.make\n        model: tools.model\n        year: tools.year\n        zip: tools.zip\n        radius: tools.radius\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
