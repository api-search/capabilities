---
categories: []
consumed_apis: []
description: Unified location intelligence capability combining TomTom's Search, Routing, and Traffic APIs. Enables applications and AI agents to search for places, calculate optimized routes, monitor real-time traffic conditions, and build location-aware features for navigation, logistics, and smart city applications.
layout: capability
name: TomTom Location Intelligence
operations:
- description: Fuzzy search for addresses and points of interest
  method: GET
  name: fuzzy-search
  path: /v1/search
- description: Convert address to coordinates
  method: GET
  name: geocode
  path: /v1/geocode
- description: Convert coordinates to address
  method: GET
  name: reverse-geocode
  path: /v1/reverse-geocode
- description: Search for nearby points of interest
  method: GET
  name: poi-search
  path: /v1/points-of-interest
- description: Calculate route between locations
  method: GET
  name: calculate-route
  path: /v1/routes
- description: Calculate area reachable within constraints
  method: GET
  name: calculate-reachable-range
  path: /v1/reachable-range
- description: Get real-time traffic incidents
  method: GET
  name: get-traffic-incidents
  path: /v1/traffic-incidents
- description: Get real-time traffic flow for a road segment
  method: GET
  name: get-traffic-flow
  path: /v1/traffic-flow
personas: []
provider_name: TomTom
provider_slug: tomtom
search_terms:
- tomtom
- search for nearby points of interest
- get real-time traffic incidents
- get real-time traffic incidents, accidents, and road closures for a geographic area
- traffic
- get traffic incidents
- geocode address
- geospatial
- reverse geocode
- navigation
- calculate route between locations
- get real-time traffic flow for a road segment
- reverse geocoding
- real-time traffic incidents
- calculate route
- routing
- fuzzy search
- address geocoding
- convert address to coordinates
- poi discovery
- reverse geocode coordinates
- calculate the geographic area reachable from a point within time or distance limits
- get real-time traffic flow speed and travel time for a road segment near a location
- transportation
- convert coordinates to address
- fuzzy search for addresses and points of interest
- reachable area calculation
- convert geographic coordinates to a human-readable street address
- get traffic flow
- search
- find nearby pois
- maps
- search places
- poi search
- location
- convert a street address to geographic coordinates (latitude/longitude)
- location and poi search
- geocode
- calculate reachable range
- location intelligence
- search for addresses and points of interest by name or keyword
- find points of interest (restaurants, gas stations, parking, etc.) near a location
- route calculation
- calculate area reachable within constraints
- geocoding
- calculate the optimal route between two or more locations with optional traffic and vehicle parameters
- real-time traffic flow
slug: location-intelligence
source_filename: location-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TomTom Location Intelligence\n  description: Unified location intelligence capability combining TomTom's Search, Routing, and Traffic APIs. Enables applications\n    and AI agents to search for places, calculate optimized routes, monitor real-time traffic conditions, and build location-aware\n    features for navigation, logistics, and smart city applications.\n  tags:\n  - TomTom\n  - Maps\n  - Routing\n  - Traffic\n  - Search\n  - Navigation\n  - Location Intelligence\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOMTOM_API_KEY: TOMTOM_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: tomtom-routing\n    baseUri: https://api.tomtom.com\n    description: TomTom Routing API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{TOMTOM_API_KEY}}'\n      placement: query\n    resources:\n    - name: routes\n      path: /routing/1\n      description: Route calculation\n\
  \      operations:\n      - name: calculate-route\n        method: GET\n        description: Calculate route between locations\n        inputParameters:\n        - name: locations\n          in: path\n          type: string\n          required: true\n          description: Colon-separated coordinates (lat,lon:lat,lon)\n        - name: routeType\n          in: query\n          type: string\n          required: false\n          description: Route optimization type\n        - name: traffic\n          in: query\n          type: boolean\n          required: false\n          description: Use real-time traffic\n        - name: travelMode\n          in: query\n          type: string\n          required: false\n          description: Mode of travel (car, truck, bicycle, etc.)\n        - name: maxAlternatives\n          in: query\n          type: integer\n          required: false\n          description: Number of alternative routes\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: calculate-reachable-range\n        method: GET\n        description: Calculate area reachable within time or distance constraints\n        inputParameters:\n        - name: origin\n          in: path\n          type: string\n          required: true\n          description: Origin coordinates (lat,lon)\n        - name: timeBudgetInSec\n          in: query\n          type: number\n          required: false\n          description: Maximum travel time in seconds\n        - name: distanceBudgetInMeters\n          in: query\n          type: number\n          required: false\n          description: Maximum distance in meters\n        - name: energyBudgetInkWh\n          in: query\n          type: number\n          required: false\n          description: Energy budget for EV routing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type:\
  \ http\n    namespace: tomtom-search\n    baseUri: https://api.tomtom.com\n    description: TomTom Search API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{TOMTOM_API_KEY}}'\n      placement: query\n    resources:\n    - name: search\n      path: /search/2\n      description: Location search operations\n      operations:\n      - name: fuzzy-search\n        method: GET\n        description: Fuzzy search for addresses and points of interest\n        inputParameters:\n        - name: query\n          in: path\n          type: string\n          required: true\n          description: Search query string\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity bias\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity bias\n        - name: limit\n          in: query\n          type: integer\n   \
  \       required: false\n          description: Maximum number of results\n        - name: countrySet\n          in: query\n          type: string\n          required: false\n          description: Comma-separated ISO country codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: geocode\n        method: GET\n        description: Convert address to geographic coordinates\n        inputParameters:\n        - name: query\n          in: path\n          type: string\n          required: true\n          description: Address to geocode\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reverse-geocode\n        method: GET\n        description: Convert coordinates to address\n        inputParameters:\n        - name: position\n          in: path\n          type: string\n          required: true\n          description:\
  \ Coordinates to reverse geocode (lat,lon)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: poi-search\n        method: GET\n        description: Search for points of interest by name or category\n        inputParameters:\n        - name: query\n          in: path\n          type: string\n          required: true\n          description: POI name or category\n        - name: lat\n          in: query\n          type: number\n          required: false\n        - name: lon\n          in: query\n          type: number\n          required: false\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: tomtom-traffic\n    baseUri: https://api.tomtom.com\n   \
  \ description: TomTom Traffic API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{TOMTOM_API_KEY}}'\n      placement: query\n    resources:\n    - name: incidents\n      path: /traffic/services/5\n      description: Traffic incident data\n      operations:\n      - name: get-incident-details\n        method: GET\n        description: Get real-time traffic incidents within an area\n        inputParameters:\n        - name: bbox\n          in: query\n          type: string\n          required: false\n          description: Bounding box (minLon,minLat,maxLon,maxLat)\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language for incident descriptions\n        - name: categoryFilter\n          in: query\n          type: integer\n          required: false\n          description: Bitmask for incident categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: flow\n      path: /traffic/services/4\n      description: Traffic flow data\n      operations:\n      - name: get-flow-segment-data\n        method: GET\n        description: Get real-time traffic flow for a road segment\n        inputParameters:\n        - name: style\n          in: path\n          type: string\n          required: true\n          description: Flow visualization style\n        - name: zoom\n          in: path\n          type: integer\n          required: true\n          description: Zoom level\n        - name: point\n          in: query\n          type: string\n          required: true\n          description: Coordinates to query (lat,lon)\n        - name: unit\n          in: query\n          type: string\n          required: false\n          description: Speed unit (KMPH or MPH)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: tomtom-location-intelligence-api\n    description: Unified REST API for TomTom location intelligence combining search, routing, and traffic.\n    resources:\n    - path: /v1/search\n      name: search\n      description: Location and POI search\n      operations:\n      - method: GET\n        name: fuzzy-search\n        description: Fuzzy search for addresses and points of interest\n        call: tomtom-search.fuzzy-search\n        with:\n          query: rest.query\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/geocode\n      name: geocode\n      description: Address geocoding\n      operations:\n      - method: GET\n        name: geocode\n        description: Convert address to coordinates\n        call: tomtom-search.geocode\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/reverse-geocode\n      name: reverse-geocode\n      description: Reverse geocoding\n      operations:\n      - method: GET\n        name: reverse-geocode\n        description: Convert coordinates to address\n        call: tomtom-search.reverse-geocode\n        with:\n          position: rest.position\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/points-of-interest\n      name: points-of-interest\n      description: POI discovery\n      operations:\n      - method: GET\n        name: poi-search\n        description: Search for nearby points of interest\n        call: tomtom-search.poi-search\n        with:\n          query: rest.query\n          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Route calculation\n      operations:\n      - method: GET\n        name: calculate-route\n\
  \        description: Calculate route between locations\n        call: tomtom-routing.calculate-route\n        with:\n          locations: rest.locations\n          routeType: rest.routeType\n          traffic: rest.traffic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reachable-range\n      name: reachable-range\n      description: Reachable area calculation\n      operations:\n      - method: GET\n        name: calculate-reachable-range\n        description: Calculate area reachable within constraints\n        call: tomtom-routing.calculate-reachable-range\n        with:\n          origin: rest.origin\n          timeBudgetInSec: rest.timeBudgetInSec\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traffic-incidents\n      name: traffic-incidents\n      description: Real-time traffic incidents\n      operations:\n      - method: GET\n        name: get-traffic-incidents\n        description: Get real-time\
  \ traffic incidents\n        call: tomtom-traffic.get-incident-details\n        with:\n          bbox: rest.bbox\n          language: rest.language\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traffic-flow\n      name: traffic-flow\n      description: Real-time traffic flow\n      operations:\n      - method: GET\n        name: get-traffic-flow\n        description: Get real-time traffic flow for a road segment\n        call: tomtom-traffic.get-flow-segment-data\n        with:\n          point: rest.point\n          unit: rest.unit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: tomtom-location-mcp\n    transport: http\n    description: MCP server for AI-assisted location intelligence with TomTom APIs.\n    tools:\n    - name: search-places\n      description: Search for addresses and points of interest by name or keyword\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: tomtom-search.fuzzy-search\n      with:\n        query: tools.query\n        lat: tools.lat\n        lon: tools.lon\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geocode-address\n      description: Convert a street address to geographic coordinates (latitude/longitude)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-search.geocode\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reverse-geocode-coordinates\n      description: Convert geographic coordinates to a human-readable street address\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-search.reverse-geocode\n      with:\n        position: tools.position\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-pois\n      description: Find points of interest (restaurants,\
  \ gas stations, parking, etc.) near a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-search.poi-search\n      with:\n        query: tools.query\n        lat: tools.lat\n        lon: tools.lon\n        radius: tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: calculate-route\n      description: Calculate the optimal route between two or more locations with optional traffic and vehicle parameters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-routing.calculate-route\n      with:\n        locations: tools.locations\n        routeType: tools.routeType\n        traffic: tools.traffic\n        travelMode: tools.travelMode\n        maxAlternatives: tools.maxAlternatives\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: calculate-reachable-range\n      description: Calculate the geographic area reachable from a point within time or distance\
  \ limits\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-routing.calculate-reachable-range\n      with:\n        origin: tools.origin\n        timeBudgetInSec: tools.timeBudgetInSec\n        distanceBudgetInMeters: tools.distanceBudgetInMeters\n        energyBudgetInkWh: tools.energyBudgetInkWh\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-traffic-incidents\n      description: Get real-time traffic incidents, accidents, and road closures for a geographic area\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tomtom-traffic.get-incident-details\n      with:\n        bbox: tools.bbox\n        language: tools.language\n        categoryFilter: tools.categoryFilter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-traffic-flow\n      description: Get real-time traffic flow speed and travel time for a road segment near a location\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: tomtom-traffic.get-flow-segment-data\n      with:\n        point: tools.point\n        style: tools.style\n        zoom: tools.zoom\n        unit: tools.unit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tomtom/refs/heads/main/capabilities/location-intelligence.yaml
tags:
- TomTom
- Maps
- Routing
- Traffic
- Search
- Navigation
- Location Intelligence
tools:
- description: Search for addresses and points of interest by name or keyword
  hints:
    openWorld: true
    readOnly: true
  name: search-places
- description: Convert a street address to geographic coordinates (latitude/longitude)
  hints:
    openWorld: true
    readOnly: true
  name: geocode-address
- description: Convert geographic coordinates to a human-readable street address
  hints:
    openWorld: true
    readOnly: true
  name: reverse-geocode-coordinates
- description: Find points of interest (restaurants, gas stations, parking, etc.) near a location
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-pois
- description: Calculate the optimal route between two or more locations with optional traffic and vehicle parameters
  hints:
    openWorld: true
    readOnly: true
  name: calculate-route
- description: Calculate the geographic area reachable from a point within time or distance limits
  hints:
    openWorld: true
    readOnly: true
  name: calculate-reachable-range
- description: Get real-time traffic incidents, accidents, and road closures for a geographic area
  hints:
    openWorld: true
    readOnly: true
  name: get-traffic-incidents
- description: Get real-time traffic flow speed and travel time for a road segment near a location
  hints:
    openWorld: true
    readOnly: true
  name: get-traffic-flow
---
