---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Commercial Routing
operations: []
personas: []
provider_name: Trimble
provider_slug: trimble
search_terms:
- mapping
- construction
- transportation
- gps
- bim
- geospatial
- fleet management
- agriculture
- collaboration
slug: commercial-routing
source_filename: commercial-routing.yaml
source_heading: Capability Spec
source_yaml: "name: Commercial Vehicle Routing\ndescription: >-\n  Workflow capability for commercial vehicle route planning and geocoding using\n  Trimble Maps / PC*MILER. Supports truck-specific route optimization with weight,\n  height, and hazmat restrictions, toll cost estimation, and address geocoding\n  for logistics and transportation operations.\nversion: \"1.0\"\n\nimports:\n  - capabilities/shared/trimble-maps.yaml\n\ntools:\n  - name: plan-truck-route\n    description: Calculate an optimized route for a commercial vehicle between multiple stops with toll costs and fuel estimates\n    operationRef: trimble-maps/calculateRoute\n    inputs:\n      - name: stops\n        description: Semicolon-delimited list of stops (e.g., \"Dallas,TX;Oklahoma City,OK;Kansas City,MO\")\n        required: true\n      - name: vehicleType\n        description: \"Vehicle class: Truck, LightTruck, Auto\"\n        required: false\n      - name: routeType\n        description: \"Optimization: Practical,\
  \ Shortest, Fastest, Tolls\"\n        required: false\n      - name: vehicleHeight\n        description: Vehicle height in feet (for clearance restrictions)\n        required: false\n      - name: vehicleWeight\n        description: Gross vehicle weight in pounds (for weight limit restrictions)\n        required: false\n\n  - name: calculate-mileage\n    description: Get mileage-only calculation between stops without full routing details\n    operationRef: trimble-maps/getRouteMileage\n    inputs:\n      - name: stops\n        description: Semicolon-delimited list of stops\n        required: true\n      - name: vehicleType\n        description: Vehicle class for mileage calculation\n        required: false\n\n  - name: geocode-address\n    description: Convert a street address or city/state to latitude/longitude coordinates\n    operationRef: trimble-maps/geocodeAddress\n    inputs:\n      - name: addr\n        description: Full address string to geocode (e.g., \"1 Sylvan Way, Parsippany,\
  \ NJ 07054\")\n        required: true\n\n  - name: reverse-geocode\n    description: Convert geographic coordinates to a street address\n    operationRef: trimble-maps/reverseGeocode\n    inputs:\n      - name: coords\n        description: \"Coordinate pair as lat,lng (e.g., 40.8735,-74.4284)\"\n        required: true\n\n  - name: get-map-tile\n    description: Retrieve a raster map tile for rendering in web or mobile applications\n    operationRef: trimble-maps/getMapTile\n    inputs:\n      - name: zoom\n        description: Zoom level (0-20)\n        required: true\n      - name: x\n        description: Tile column (X coordinate)\n        required: true\n      - name: y\n        description: Tile row (Y coordinate)\n        required: true\n      - name: style\n        description: \"Map style: default, satellite, hybrid\"\n        required: false\n\n  - name: get-location-timezone\n    description: Get the timezone for a geographic coordinate to support driver HOS scheduling\n    operationRef:\
  \ trimble-maps/getTimezone\n    inputs:\n      - name: coords\n        description: \"Coordinate pair as lat,lng\"\n        required: true\n\nadapters:\n  rest:\n    port: 8081\n    basePath: /commercial-routing\n\n  mcp:\n    port: 9091\n    serverName: commercial-routing\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trimble/refs/heads/main/capabilities/commercial-routing.yaml
tags: []
tools: []
---
