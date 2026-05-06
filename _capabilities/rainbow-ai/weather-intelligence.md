---
categories: []
consumed_apis: []
description: Unified weather intelligence capability combining Rainbow.AI's Nowcast API for minute-by-minute precipitation forecasts and the Tiles API for map visualization. Used by operations teams, logistics platforms, outdoor event planners, and any application requiring precise, real-time precipitation awareness.
layout: capability
name: Rainbow.AI Weather Intelligence
operations:
- description: Get precipitation forecast for the next 4 hours
  method: GET
  name: get-nowcast
  path: /v1/nowcast
- description: Get current radar reflectivity data
  method: GET
  name: get-radar-data
  path: /v1/radar
- description: Get weather map tile for a specific zoom and coordinate
  method: GET
  name: get-map-tile
  path: /v1/map/tiles/{z}/{x}/{y}
- description: Get static precipitation map image
  method: GET
  name: get-map-snapshot
  path: /v1/map/snapshots
- description: Get timestamps for animated weather map
  method: GET
  name: get-available-timestamps
  path: /v1/map/timestamps
personas: []
provider_name: Rainbow.AI
provider_slug: rainbow-ai
search_terms:
- get real-time weather radar reflectivity data showing current precipitation intensity and type for a location.
- mapping
- get available tile timestamps
- get weather map tile for a specific zoom and coordinate
- get precipitation nowcast
- get the list of available weather tile timestamps for building animated precipitation visualizations.
- geospatial
- available tile timestamps for animation
- weather
- nowcast
- get nowcast
- get a static precipitation map image for a geographic bounding box, useful for report generation or preview thumbnails.
- tiles
- precipitation
- get current radar reflectivity data
- get radar data
- get map snapshot
- forecasting
- get weather map tile
- get minute-by-minute precipitation forecast for any global location for the next 4 hours at 1 km resolution.
- get precipitation forecast for the next 4 hours
- get map tile
- radar
- xyz precipitation map tiles for visualization
- minute-by-minute precipitation forecasts for any location
- get timestamps for animated weather map
- static precipitation map images for a bounding box
- retrieve a precipitation map tile at a specific zoom level and xyz tile coordinates for embedding in map visualizations.
- real-time radar observations
- get available timestamps
- get precipitation map snapshot
- get static precipitation map image
slug: weather-intelligence
source_filename: weather-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rainbow.AI Weather Intelligence\n  description: Unified weather intelligence capability combining Rainbow.AI's Nowcast API for minute-by-minute precipitation\n    forecasts and the Tiles API for map visualization. Used by operations teams, logistics platforms, outdoor event planners,\n    and any application requiring precise, real-time precipitation awareness.\n  tags:\n  - Weather\n  - Nowcast\n  - Precipitation\n  - Tiles\n  - Mapping\n  - Geospatial\n  - Forecasting\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RAINBOW_AI_API_KEY: RAINBOW_AI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: nowcast\n    baseUri: https://api.rainbow.ai/v1\n    description: Rainbow.AI Nowcast API for hyperlocal precipitation forecasting\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{RAINBOW_AI_API_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: nowcast\n      path: /weather/nowcast\n      description: Minute-by-minute precipitation forecasts\n      operations:\n      - name: get-nowcast\n        method: GET\n        description: Get precipitation nowcast for a location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude (-90 to 90)\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude (-180 to 180)\n        - name: timezone\n          in: query\n          type: string\n          required: false\n          description: IANA timezone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: radar\n      path: /weather/radar\n      description: Real-time radar data\n      operations:\n      - name: get-radar-data\n        method: GET\n        description: Get\
  \ real-time radar data for a location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude (-90 to 90)\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude (-180 to 180)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: tiles\n    baseUri: https://api.rainbow.ai/v1\n    description: Rainbow.AI Tiles API for weather map visualization\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{RAINBOW_AI_API_KEY}}'\n      placement: header\n    resources:\n    - name: map-tiles\n      path: /map/tile/{z}/{x}/{y}\n      description: XYZ weather map tiles\n      operations:\n      - name: get-map-tile\n        method: GET\n        description: Get a 256x256 precipitation map tile\n\
  \        inputParameters:\n        - name: z\n          in: path\n          type: integer\n          required: true\n          description: Zoom level (0-18)\n        - name: x\n          in: path\n          type: integer\n          required: true\n          description: Tile X coordinate\n        - name: y\n          in: path\n          type: integer\n          required: true\n          description: Tile Y coordinate\n        - name: timestamp\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 forecast timestamp\n        - name: layer\n          in: query\n          type: string\n          required: false\n          description: Layer type (precipitation or radar)\n        outputRawFormat: binary\n    - name: map-snapshot\n      path: /map/snapshot\n      description: Static precipitation map images\n      operations:\n      - name: get-map-snapshot\n        method: GET\n        description: Get a static precipitation map snapshot\
  \ for a bounding box\n        inputParameters:\n        - name: bbox\n          in: query\n          type: string\n          required: true\n          description: Bounding box as minLon,minLat,maxLon,maxLat\n        - name: width\n          in: query\n          type: integer\n          required: false\n          description: Output image width in pixels\n        - name: height\n          in: query\n          type: integer\n          required: false\n          description: Output image height in pixels\n        - name: timestamp\n          in: query\n          type: string\n          required: false\n          description: ISO 8601 forecast timestamp\n        outputRawFormat: binary\n    - name: map-timestamps\n      path: /map/timestamps\n      description: Available tile timestamps\n      operations:\n      - name: get-available-timestamps\n        method: GET\n        description: Get list of available tile timestamps for animation\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: weather-intelligence-api\n    description: Unified REST API for hyperlocal precipitation intelligence.\n    resources:\n    - path: /v1/nowcast\n      name: nowcast\n      description: Minute-by-minute precipitation forecasts for any location\n      operations:\n      - method: GET\n        name: get-nowcast\n        description: Get precipitation forecast for the next 4 hours\n        call: nowcast.get-nowcast\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          timezone: rest.timezone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/radar\n      name: radar\n      description: Real-time radar observations\n      operations:\n      - method: GET\n        name: get-radar-data\n        description: Get current radar reflectivity data\n        call: nowcast.get-radar-data\n        with:\n        \
  \  lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/map/tiles/{z}/{x}/{y}\n      name: map-tiles\n      description: XYZ precipitation map tiles for visualization\n      operations:\n      - method: GET\n        name: get-map-tile\n        description: Get weather map tile for a specific zoom and coordinate\n        call: tiles.get-map-tile\n        with:\n          z: rest.z\n          x: rest.x\n          y: rest.y\n          timestamp: rest.timestamp\n          layer: rest.layer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/map/snapshots\n      name: map-snapshots\n      description: Static precipitation map images for a bounding box\n      operations:\n      - method: GET\n        name: get-map-snapshot\n        description: Get static precipitation map image\n        call: tiles.get-map-snapshot\n        with:\n          bbox: rest.bbox\n          width: rest.width\n\
  \          height: rest.height\n          timestamp: rest.timestamp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/map/timestamps\n      name: map-timestamps\n      description: Available tile timestamps for animation\n      operations:\n      - method: GET\n        name: get-available-timestamps\n        description: Get timestamps for animated weather map\n        call: tiles.get-available-timestamps\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: weather-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted hyperlocal precipitation intelligence.\n    tools:\n    - name: get-precipitation-nowcast\n      description: Get minute-by-minute precipitation forecast for any global location for the next 4 hours at 1 km resolution.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nowcast.get-nowcast\n      with:\n        lat:\
  \ tools.lat\n        lon: tools.lon\n        timezone: tools.timezone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-radar-data\n      description: Get real-time weather radar reflectivity data showing current precipitation intensity and type for a location.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: nowcast.get-radar-data\n      with:\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-weather-map-tile\n      description: Retrieve a precipitation map tile at a specific zoom level and XYZ tile coordinates for embedding in map\n        visualizations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tiles.get-map-tile\n      with:\n        z: tools.z\n        x: tools.x\n        y: tools.y\n        timestamp: tools.timestamp\n        layer: tools.layer\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-precipitation-map-snapshot\n      description: Get a static precipitation map image for a geographic bounding box, useful for report generation or preview\n        thumbnails.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tiles.get-map-snapshot\n      with:\n        bbox: tools.bbox\n        width: tools.width\n        height: tools.height\n        timestamp: tools.timestamp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-available-tile-timestamps\n      description: Get the list of available weather tile timestamps for building animated precipitation visualizations.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiles.get-available-timestamps\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rainbow-ai/refs/heads/main/capabilities/weather-intelligence.yaml
tags:
- Weather
- Nowcast
- Precipitation
- Tiles
- Mapping
- Geospatial
- Forecasting
tools:
- description: Get minute-by-minute precipitation forecast for any global location for the next 4 hours at 1 km resolution.
  hints:
    openWorld: true
    readOnly: true
  name: get-precipitation-nowcast
- description: Get real-time weather radar reflectivity data showing current precipitation intensity and type for a location.
  hints:
    openWorld: true
    readOnly: true
  name: get-radar-data
- description: Retrieve a precipitation map tile at a specific zoom level and XYZ tile coordinates for embedding in map visualizations.
  hints:
    openWorld: true
    readOnly: true
  name: get-weather-map-tile
- description: Get a static precipitation map image for a geographic bounding box, useful for report generation or preview thumbnails.
  hints:
    openWorld: true
    readOnly: true
  name: get-precipitation-map-snapshot
- description: Get the list of available weather tile timestamps for building animated precipitation visualizations.
  hints:
    openWorld: false
    readOnly: true
  name: get-available-tile-timestamps
---
