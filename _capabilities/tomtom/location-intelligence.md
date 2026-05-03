---
api_specs:
- filename: tomtom-routing-openapi.yml
  format: yaml
  label: tomtom-routing
  slug: tomtom-routing
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tomtom/refs/heads/main/openapi/tomtom-routing-openapi.yml
- filename: tomtom-search-openapi.yml
  format: yaml
  label: tomtom-search
  slug: tomtom-search
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tomtom/refs/heads/main/openapi/tomtom-search-openapi.yml
- filename: tomtom-traffic-openapi.yml
  format: yaml
  label: tomtom-traffic
  slug: tomtom-traffic
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tomtom/refs/heads/main/openapi/tomtom-traffic-openapi.yml
categories: []
consumed_apis:
- tomtom-routing
- tomtom-search
- tomtom-traffic
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
- search for addresses and points of interest by name or keyword
- route calculation
- navigation
- poi discovery
- get real-time traffic incidents
- geocode address
- convert a street address to geographic coordinates (latitude/longitude)
- location intelligence
- convert coordinates to address
- geospatial
- convert geographic coordinates to a human-readable street address
- calculate area reachable within constraints
- get real-time traffic flow for a road segment
- search places
- real-time traffic flow
- calculate route between locations
- calculate the optimal route between two or more locations with optional traffic and vehicle parameters
- get traffic flow
- calculate the geographic area reachable from a point within time or distance limits
- poi search
- reverse geocode
- calculate reachable range
- geocode
- get traffic incidents
- search
- location and poi search
- fuzzy search for addresses and points of interest
- find nearby pois
- get real-time traffic incidents, accidents, and road closures for a geographic area
- real-time traffic incidents
- reachable area calculation
- routing
- tomtom
- location
- convert address to coordinates
- reverse geocoding
- transportation
- maps
- traffic
- geocoding
- get real-time traffic flow speed and travel time for a road segment near a location
- address geocoding
- reverse geocode coordinates
- calculate route
- find points of interest (restaurants, gas stations, parking, etc.) near a location
- search for nearby points of interest
- fuzzy search
slug: location-intelligence
source_filename: location-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TomTom Location Intelligence\"\n  description: >-\n    Unified location intelligence capability combining TomTom's Search, Routing, and\n    Traffic APIs. Enables applications and AI agents to search for places, calculate\n    optimized routes, monitor real-time traffic conditions, and build location-aware\n    features for navigation, logistics, and smart city applications.\n  tags:\n    - TomTom\n    - Maps\n    - Routing\n    - Traffic\n    - Search\n    - Navigation\n    - Location Intelligence\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOMTOM_API_KEY: TOMTOM_API_KEY\n\ncapability:\n  consumes:\n    - import: tomtom-routing\n      location: ./shared/tomtom-routing.yaml\n    - import: tomtom-search\n      location: ./shared/tomtom-search.yaml\n    - import: tomtom-traffic\n      location: ./shared/tomtom-traffic.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n\
  \      namespace: tomtom-location-intelligence-api\n      description: \"Unified REST API for TomTom location intelligence combining search, routing, and traffic.\"\n      resources:\n        - path: /v1/search\n          name: search\n          description: \"Location and POI search\"\n          operations:\n            - method: GET\n              name: fuzzy-search\n              description: \"Fuzzy search for addresses and points of interest\"\n              call: \"tomtom-search.fuzzy-search\"\n              with:\n                query: \"rest.query\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/geocode\n          name: geocode\n          description: \"Address geocoding\"\n          operations:\n            - method: GET\n              name: geocode\n              description: \"Convert address to coordinates\"\n              call: \"\
  tomtom-search.geocode\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reverse-geocode\n          name: reverse-geocode\n          description: \"Reverse geocoding\"\n          operations:\n            - method: GET\n              name: reverse-geocode\n              description: \"Convert coordinates to address\"\n              call: \"tomtom-search.reverse-geocode\"\n              with:\n                position: \"rest.position\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/points-of-interest\n          name: points-of-interest\n          description: \"POI discovery\"\n          operations:\n            - method: GET\n              name: poi-search\n              description: \"Search for nearby points of interest\"\n              call: \"tomtom-search.poi-search\"\n        \
  \      with:\n                query: \"rest.query\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                radius: \"rest.radius\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name: routes\n          description: \"Route calculation\"\n          operations:\n            - method: GET\n              name: calculate-route\n              description: \"Calculate route between locations\"\n              call: \"tomtom-routing.calculate-route\"\n              with:\n                locations: \"rest.locations\"\n                routeType: \"rest.routeType\"\n                traffic: \"rest.traffic\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reachable-range\n          name: reachable-range\n          description: \"Reachable area calculation\"\n          operations:\n            - method: GET\n\
  \              name: calculate-reachable-range\n              description: \"Calculate area reachable within constraints\"\n              call: \"tomtom-routing.calculate-reachable-range\"\n              with:\n                origin: \"rest.origin\"\n                timeBudgetInSec: \"rest.timeBudgetInSec\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traffic-incidents\n          name: traffic-incidents\n          description: \"Real-time traffic incidents\"\n          operations:\n            - method: GET\n              name: get-traffic-incidents\n              description: \"Get real-time traffic incidents\"\n              call: \"tomtom-traffic.get-incident-details\"\n              with:\n                bbox: \"rest.bbox\"\n                language: \"rest.language\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traffic-flow\n   \
  \       name: traffic-flow\n          description: \"Real-time traffic flow\"\n          operations:\n            - method: GET\n              name: get-traffic-flow\n              description: \"Get real-time traffic flow for a road segment\"\n              call: \"tomtom-traffic.get-flow-segment-data\"\n              with:\n                point: \"rest.point\"\n                unit: \"rest.unit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: tomtom-location-mcp\n      transport: http\n      description: \"MCP server for AI-assisted location intelligence with TomTom APIs.\"\n      tools:\n        - name: search-places\n          description: \"Search for addresses and points of interest by name or keyword\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-search.fuzzy-search\"\n          with:\n            query: \"tools.query\"\
  \n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: geocode-address\n          description: \"Convert a street address to geographic coordinates (latitude/longitude)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-search.geocode\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reverse-geocode-coordinates\n          description: \"Convert geographic coordinates to a human-readable street address\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-search.reverse-geocode\"\n          with:\n            position: \"tools.position\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: find-nearby-pois\n          description: \"Find points of interest (restaurants, gas stations, parking, etc.) near a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-search.poi-search\"\n          with:\n            query: \"tools.query\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            radius: \"tools.radius\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: calculate-route\n          description: \"Calculate the optimal route between two or more locations with optional traffic and vehicle parameters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-routing.calculate-route\"\n          with:\n            locations: \"tools.locations\"\n            routeType: \"tools.routeType\"\n            traffic: \"tools.traffic\"\n            travelMode: \"tools.travelMode\"\n            maxAlternatives:\
  \ \"tools.maxAlternatives\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: calculate-reachable-range\n          description: \"Calculate the geographic area reachable from a point within time or distance limits\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-routing.calculate-reachable-range\"\n          with:\n            origin: \"tools.origin\"\n            timeBudgetInSec: \"tools.timeBudgetInSec\"\n            distanceBudgetInMeters: \"tools.distanceBudgetInMeters\"\n            energyBudgetInkWh: \"tools.energyBudgetInkWh\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-traffic-incidents\n          description: \"Get real-time traffic incidents, accidents, and road closures for a geographic area\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-traffic.get-incident-details\"\
  \n          with:\n            bbox: \"tools.bbox\"\n            language: \"tools.language\"\n            categoryFilter: \"tools.categoryFilter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-traffic-flow\n          description: \"Get real-time traffic flow speed and travel time for a road segment near a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tomtom-traffic.get-flow-segment-data\"\n          with:\n            point: \"tools.point\"\n            style: \"tools.style\"\n            zoom: \"tools.zoom\"\n            unit: \"tools.unit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
