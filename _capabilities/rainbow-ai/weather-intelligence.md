---
categories: []
consumed_apis:
- nowcast
- tiles
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
- retrieve a precipitation map tile at a specific zoom level and xyz tile coordinates for embedding in map visualizations.
- get a static precipitation map image for a geographic bounding box, useful for report generation or preview thumbnails.
- get weather map tile
- nowcast
- xyz precipitation map tiles for visualization
- get timestamps for animated weather map
- tiles
- get nowcast
- geospatial
- get static precipitation map image
- get map tile
- radar
- get radar data
- get precipitation nowcast
- minute-by-minute precipitation forecasts for any location
- get the list of available weather tile timestamps for building animated precipitation visualizations.
- get real-time weather radar reflectivity data showing current precipitation intensity and type for a location.
- get precipitation forecast for the next 4 hours
- get weather map tile for a specific zoom and coordinate
- real-time radar observations
- get map snapshot
- precipitation
- available tile timestamps for animation
- get available timestamps
- get available tile timestamps
- forecasting
- get minute-by-minute precipitation forecast for any global location for the next 4 hours at 1 km resolution.
- get precipitation map snapshot
- mapping
- get current radar reflectivity data
- weather
- static precipitation map images for a bounding box
slug: weather-intelligence
source_filename: weather-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Rainbow.AI Weather Intelligence\n  description: >-\n    Unified weather intelligence capability combining Rainbow.AI's Nowcast API\n    for minute-by-minute precipitation forecasts and the Tiles API for map\n    visualization. Used by operations teams, logistics platforms, outdoor event\n    planners, and any application requiring precise, real-time precipitation\n    awareness.\n  tags:\n    - Weather\n    - Nowcast\n    - Precipitation\n    - Tiles\n    - Mapping\n    - Geospatial\n    - Forecasting\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAINBOW_AI_API_KEY: RAINBOW_AI_API_KEY\n\ncapability:\n  consumes:\n    - import: nowcast\n      location: ./shared/nowcast.yaml\n    - import: tiles\n      location: ./shared/tiles.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: weather-intelligence-api\n      description: Unified REST API for hyperlocal precipitation\
  \ intelligence.\n      resources:\n        - path: /v1/nowcast\n          name: nowcast\n          description: Minute-by-minute precipitation forecasts for any location\n          operations:\n            - method: GET\n              name: get-nowcast\n              description: Get precipitation forecast for the next 4 hours\n              call: \"nowcast.get-nowcast\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                timezone: \"rest.timezone\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/radar\n          name: radar\n          description: Real-time radar observations\n          operations:\n            - method: GET\n              name: get-radar-data\n              description: Get current radar reflectivity data\n              call: \"nowcast.get-radar-data\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/map/tiles/{z}/{x}/{y}\n          name: map-tiles\n          description: XYZ precipitation map tiles for visualization\n          operations:\n            - method: GET\n              name: get-map-tile\n              description: Get weather map tile for a specific zoom and coordinate\n              call: \"tiles.get-map-tile\"\n              with:\n                z: \"rest.z\"\n                x: \"rest.x\"\n                y: \"rest.y\"\n                timestamp: \"rest.timestamp\"\n                layer: \"rest.layer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/map/snapshots\n          name: map-snapshots\n          description: Static precipitation map images for a bounding box\n          operations:\n            - method: GET\n              name: get-map-snapshot\n              description:\
  \ Get static precipitation map image\n              call: \"tiles.get-map-snapshot\"\n              with:\n                bbox: \"rest.bbox\"\n                width: \"rest.width\"\n                height: \"rest.height\"\n                timestamp: \"rest.timestamp\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/map/timestamps\n          name: map-timestamps\n          description: Available tile timestamps for animation\n          operations:\n            - method: GET\n              name: get-available-timestamps\n              description: Get timestamps for animated weather map\n              call: \"tiles.get-available-timestamps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: weather-intelligence-mcp\n      transport: http\n      description: MCP server for AI-assisted hyperlocal precipitation intelligence.\n\
  \      tools:\n        - name: get-precipitation-nowcast\n          description: >-\n            Get minute-by-minute precipitation forecast for any global location\n            for the next 4 hours at 1 km resolution.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nowcast.get-nowcast\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            timezone: \"tools.timezone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-radar-data\n          description: >-\n            Get real-time weather radar reflectivity data showing current\n            precipitation intensity and type for a location.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"nowcast.get-radar-data\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-weather-map-tile\n          description: >-\n            Retrieve a precipitation map tile at a specific zoom level and\n            XYZ tile coordinates for embedding in map visualizations.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tiles.get-map-tile\"\n          with:\n            z: \"tools.z\"\n            x: \"tools.x\"\n            y: \"tools.y\"\n            timestamp: \"tools.timestamp\"\n            layer: \"tools.layer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-precipitation-map-snapshot\n          description: >-\n            Get a static precipitation map image for a geographic bounding box,\n            useful for report generation or preview thumbnails.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tiles.get-map-snapshot\"\n          with:\n            bbox:\
  \ \"tools.bbox\"\n            width: \"tools.width\"\n            height: \"tools.height\"\n            timestamp: \"tools.timestamp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-available-tile-timestamps\n          description: >-\n            Get the list of available weather tile timestamps for building\n            animated precipitation visualizations.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiles.get-available-timestamps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
