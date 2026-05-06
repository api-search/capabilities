---
categories: []
consumed_apis: []
description: MeteoSource provides an Air Quality API delivering hour-by-hour pollution data for any location on Earth, with forecasts up to 5 days ahead. The API also offers weather forecast data, location lookup, weather maps, and historical Time Machine data.
layout: capability
name: MeteoSource Air Quality Data API
operations:
- description: Get point weather forecast (free tier)
  method: GET
  name: getfreepointweather
  path: /free/point
- description: Get point weather forecast (flexi tier)
  method: GET
  name: getflexipointweather
  path: /flexi/point
- description: Get point air quality forecast
  method: GET
  name: getairquality
  path: /flexi/air_quality
- description: Find places by name or ZIP
  method: GET
  name: findplaces
  path: /free/find_places
- description: Find places by prefix
  method: GET
  name: findplacesbyprefix
  path: /free/find_places_prefix
- description: Find nearest place to coordinates
  method: GET
  name: findnearestplace
  path: /free/nearest_place
- description: Get weather or pollution map
  method: GET
  name: getmap
  path: /flexi/map
- description: Get historical Time Machine data
  method: GET
  name: gettimemachine
  path: /flexi/time_machine
personas: []
provider_name: MeteoSource Air Quality Data API
provider_slug: meteosource-air-quality-data-api
search_terms:
- find nearest place to coordinates
- findplaces
- weather
- air
- meteosource
- findplacesbyprefix
- gettimemachine
- find places by prefix
- findnearestplace
- forecasting
- getflexipointweather
- air quality
- getairquality
- get point air quality forecast
- get point weather forecast (flexi tier)
- api
- get point weather forecast (free tier)
- get historical time machine data
- find places by name or zip
- getfreepointweather
- quality
- data
- environmental data
- get weather or pollution map
- getmap
slug: meteosource-air-quality-data-api-capability
source_filename: meteosource-air-quality-data-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MeteoSource Air Quality Data API\n  description: MeteoSource provides an Air Quality API delivering hour-by-hour pollution data for any location on Earth, with\n    forecasts up to 5 days ahead. The API also offers weather forecast data, location lookup, weather maps, and historical\n    Time Machine data.\n  tags:\n  - Meteosource\n  - Air\n  - Quality\n  - Data\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: meteosource-air-quality-data-api\n    baseUri: https://www.meteosource.com/api/v1\n    description: MeteoSource Air Quality Data API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{METEOSOURCE_AIR_QUALITY_DATA_API_TOKEN}}'\n    resources:\n    - name: free-point\n      path: /free/point\n      operations:\n      - name: getfreepointweather\n        method: GET\n        description: Get point weather\
  \ forecast (free tier)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flexi-point\n      path: /flexi/point\n      operations:\n      - name: getflexipointweather\n        method: GET\n        description: Get point weather forecast (flexi tier)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flexi-air-quality\n      path: /flexi/air_quality\n      operations:\n      - name: getairquality\n        method: GET\n        description: Get point air quality forecast\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: free-find-places\n      path: /free/find_places\n      operations:\n      - name: findplaces\n        method: GET\n        description: Find places by name or ZIP\n        inputParameters:\n        - name: text\n\
  \          in: query\n          type: string\n          required: true\n        - name: language\n          in: query\n          type: string\n        - name: area\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: free-find-places-prefix\n      path: /free/find_places_prefix\n      operations:\n      - name: findplacesbyprefix\n        method: GET\n        description: Find places by prefix\n        inputParameters:\n        - name: text\n          in: query\n          type: string\n          required: true\n        - name: language\n          in: query\n          type: string\n        - name: area\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: free-nearest-place\n      path: /free/nearest_place\n      operations:\n \
  \     - name: findnearestplace\n        method: GET\n        description: Find nearest place to coordinates\n        inputParameters:\n        - name: language\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flexi-map\n      path: /flexi/map\n      operations:\n      - name: getmap\n        method: GET\n        description: Get weather or pollution map\n        inputParameters:\n        - name: tile_x\n          in: query\n          type: integer\n        - name: tile_y\n          in: query\n          type: integer\n        - name: tile_zoom\n          in: query\n          type: integer\n        - name: min_lat\n          in: query\n          type: number\n        - name: min_lon\n          in: query\n          type: number\n        - name: max_lat\n          in: query\n          type: number\n        - name: max_lon\n          in: query\n          type:\
  \ number\n        - name: variable\n          in: query\n          type: string\n          required: true\n        - name: datetime\n          in: query\n          type: string\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flexi-time-machine\n      path: /flexi/time_machine\n      operations:\n      - name: gettimemachine\n        method: GET\n        description: Get historical Time Machine data\n        inputParameters:\n        - name: date\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: meteosource-air-quality-data-api-rest\n    description: REST adapter for MeteoSource Air Quality Data API.\n    resources:\n    - path:\
  \ /free/point\n      name: getfreepointweather\n      operations:\n      - method: GET\n        name: getfreepointweather\n        description: Get point weather forecast (free tier)\n        call: meteosource-air-quality-data-api.getfreepointweather\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flexi/point\n      name: getflexipointweather\n      operations:\n      - method: GET\n        name: getflexipointweather\n        description: Get point weather forecast (flexi tier)\n        call: meteosource-air-quality-data-api.getflexipointweather\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flexi/air_quality\n      name: getairquality\n      operations:\n      - method: GET\n        name: getairquality\n        description: Get point air quality forecast\n        call: meteosource-air-quality-data-api.getairquality\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /free/find_places\n\
  \      name: findplaces\n      operations:\n      - method: GET\n        name: findplaces\n        description: Find places by name or ZIP\n        call: meteosource-air-quality-data-api.findplaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /free/find_places_prefix\n      name: findplacesbyprefix\n      operations:\n      - method: GET\n        name: findplacesbyprefix\n        description: Find places by prefix\n        call: meteosource-air-quality-data-api.findplacesbyprefix\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /free/nearest_place\n      name: findnearestplace\n      operations:\n      - method: GET\n        name: findnearestplace\n        description: Find nearest place to coordinates\n        call: meteosource-air-quality-data-api.findnearestplace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flexi/map\n      name: getmap\n      operations:\n    \
  \  - method: GET\n        name: getmap\n        description: Get weather or pollution map\n        call: meteosource-air-quality-data-api.getmap\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flexi/time_machine\n      name: gettimemachine\n      operations:\n      - method: GET\n        name: gettimemachine\n        description: Get historical Time Machine data\n        call: meteosource-air-quality-data-api.gettimemachine\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: meteosource-air-quality-data-api-mcp\n    transport: http\n    description: MCP adapter for MeteoSource Air Quality Data API for AI agent use.\n    tools:\n    - name: getfreepointweather\n      description: Get point weather forecast (free tier)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.getfreepointweather\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: getflexipointweather\n      description: Get point weather forecast (flexi tier)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.getflexipointweather\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getairquality\n      description: Get point air quality forecast\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.getairquality\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: findplaces\n      description: Find places by name or ZIP\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.findplaces\n      with:\n        text: tools.text\n        language: tools.language\n        area: tools.area\n\
  \      inputParameters:\n      - name: text\n        type: string\n        description: text\n        required: true\n      - name: language\n        type: string\n        description: language\n      - name: area\n        type: string\n        description: area\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: findplacesbyprefix\n      description: Find places by prefix\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.findplacesbyprefix\n      with:\n        text: tools.text\n        language: tools.language\n        area: tools.area\n      inputParameters:\n      - name: text\n        type: string\n        description: text\n        required: true\n      - name: language\n        type: string\n        description: language\n      - name: area\n        type: string\n        description: area\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ findnearestplace\n      description: Find nearest place to coordinates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.findnearestplace\n      with:\n        language: tools.language\n      inputParameters:\n      - name: language\n        type: string\n        description: language\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmap\n      description: Get weather or pollution map\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: meteosource-air-quality-data-api.getmap\n      with:\n        tile_x: tools.tile_x\n        tile_y: tools.tile_y\n        tile_zoom: tools.tile_zoom\n        min_lat: tools.min_lat\n        min_lon: tools.min_lon\n        max_lat: tools.max_lat\n        max_lon: tools.max_lon\n        variable: tools.variable\n        datetime: tools.datetime\n        format: tools.format\n     \
  \ inputParameters:\n      - name: tile_x\n        type: integer\n        description: tile_x\n      - name: tile_y\n        type: integer\n        description: tile_y\n      - name: tile_zoom\n        type: integer\n        description: tile_zoom\n      - name: min_lat\n        type: number\n        description: min_lat\n      - name: min_lon\n        type: number\n        description: min_lon\n      - name: max_lat\n        type: number\n        description: max_lat\n      - name: max_lon\n        type: number\n        description: max_lon\n      - name: variable\n        type: string\n        description: variable\n        required: true\n      - name: datetime\n        type: string\n        description: datetime\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettimemachine\n      description: Get historical Time Machine data\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: meteosource-air-quality-data-api.gettimemachine\n      with:\n        date: tools.date\n      inputParameters:\n      - name: date\n        type: string\n        description: date\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    METEOSOURCE_AIR_QUALITY_DATA_API_TOKEN: METEOSOURCE_AIR_QUALITY_DATA_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/meteosource-air-quality-data-api/refs/heads/main/capabilities/meteosource-air-quality-data-api-capability.yaml
tags:
- Meteosource
- Air
- Quality
- Data
- Api
- API
tools:
- description: Get point weather forecast (free tier)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfreepointweather
- description: Get point weather forecast (flexi tier)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getflexipointweather
- description: Get point air quality forecast
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getairquality
- description: Find places by name or ZIP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findplaces
- description: Find places by prefix
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findplacesbyprefix
- description: Find nearest place to coordinates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: findnearestplace
- description: Get weather or pollution map
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmap
- description: Get historical Time Machine data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettimemachine
---
