---
categories: []
consumed_apis:
- google-maps-directions
- google-maps-geocoding
- google-maps-places
description: Unified workflow combining Google Maps Directions, Geocoding, and Places APIs for location-aware applications. Enables developers to geocode addresses, compute routes, search for places, and retrieve place details in a single integration.
layout: capability
name: Google Maps Location Intelligence
operations:
- description: Geocode an address or reverse geocode coordinates
  method: GET
  name: geocode
  path: /v1/geocode
- description: Get directions between two or more locations
  method: GET
  name: get-directions
  path: /v1/directions
- description: Get detailed information about a place
  method: GET
  name: get-place-details
  path: /v1/places/{placeId}
- description: Search for places using a text query
  method: POST
  name: search-places-text
  path: /v1/places/search-text
- description: Search for places near a location
  method: POST
  name: search-places-nearby
  path: /v1/places/search-nearby
- description: Get place predictions for input text
  method: POST
  name: autocomplete-places
  path: /v1/places/autocomplete
personas: []
provider_name: Google Maps Platform
provider_slug: google-maps
search_terms:
- geocoding
- get directions between two or more locations
- get a photo for a place by place id and photo reference
- google maps
- get detailed information about a place including address, rating, hours, and reviews
- place details retrieval
- search for places using a natural language text query like 'pizza in new york'
- location-based place search
- routing
- get place details
- navigation
- text-based place search
- get directions
- address to coordinate conversion and reverse geocoding
- location
- search for places using a text query
- place autocomplete predictions
- autocomplete places
- geocode an address to coordinates or reverse geocode coordinates to an address
- get place photo
- solar
- route computation between locations
- places
- maps
- environment
- search places text
- geocode an address or reverse geocode coordinates
- get place predictions for input text
- search places nearby
- search for places near a specific location with type filters
- geolocation
- get directions between two or more locations with support for driving, walking, bicycling, and transit
- directions
- search for places near a location
- get detailed information about a place
- geocode
- get place autocomplete predictions as the user types
slug: location-intelligence
source_filename: location-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Maps Location Intelligence\"\n  description: \"Unified workflow combining Google Maps Directions, Geocoding, and Places APIs for location-aware applications. Enables developers to geocode addresses, compute routes, search for places, and retrieve place details in a single integration.\"\n  tags:\n    - Google Maps\n    - Location\n    - Geocoding\n    - Directions\n    - Places\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_MAPS_API_KEY: GOOGLE_MAPS_API_KEY\n\ncapability:\n  consumes:\n    - import: google-maps-directions\n      location: ./shared/directions.yaml\n    - import: google-maps-geocoding\n      location: ./shared/geocoding.yaml\n    - import: google-maps-places\n      location: ./shared/places.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: location-intelligence-api\n      description: \"Unified REST API for location intelligence\
  \ combining geocoding, directions, and places.\"\n      resources:\n        - path: /v1/geocode\n          name: geocoding\n          description: \"Address to coordinate conversion and reverse geocoding\"\n          operations:\n            - method: GET\n              name: geocode\n              description: \"Geocode an address or reverse geocode coordinates\"\n              call: \"google-maps-geocoding.geocode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/directions\n          name: directions\n          description: \"Route computation between locations\"\n          operations:\n            - method: GET\n              name: get-directions\n              description: \"Get directions between two or more locations\"\n              call: \"google-maps-directions.get-directions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/places/{placeId}\n\
  \          name: place-details\n          description: \"Place details retrieval\"\n          operations:\n            - method: GET\n              name: get-place-details\n              description: \"Get detailed information about a place\"\n              call: \"google-maps-places.get-place-details\"\n              with:\n                placeId: \"rest.placeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/places/search-text\n          name: text-search\n          description: \"Text-based place search\"\n          operations:\n            - method: POST\n              name: search-places-text\n              description: \"Search for places using a text query\"\n              call: \"google-maps-places.search-places-text\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/places/search-nearby\n          name: nearby-search\n          description:\
  \ \"Location-based place search\"\n          operations:\n            - method: POST\n              name: search-places-nearby\n              description: \"Search for places near a location\"\n              call: \"google-maps-places.search-places-nearby\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/places/autocomplete\n          name: autocomplete\n          description: \"Place autocomplete predictions\"\n          operations:\n            - method: POST\n              name: autocomplete-places\n              description: \"Get place predictions for input text\"\n              call: \"google-maps-places.autocomplete-places\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: location-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted location intelligence combining geocoding,\
  \ directions, and places search.\"\n      tools:\n        - name: geocode\n          description: \"Geocode an address to coordinates or reverse geocode coordinates to an address\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-maps-geocoding.geocode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-directions\n          description: \"Get directions between two or more locations with support for driving, walking, bicycling, and transit\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-maps-directions.get-directions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-place-details\n          description: \"Get detailed information about a place including address, rating, hours, and reviews\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"google-maps-places.get-place-details\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-places-text\n          description: \"Search for places using a natural language text query like 'pizza in New York'\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-maps-places.search-places-text\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-places-nearby\n          description: \"Search for places near a specific location with type filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-maps-places.search-places-nearby\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: autocomplete-places\n          description: \"Get place autocomplete predictions as the user types\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"google-maps-places.autocomplete-places\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-place-photo\n          description: \"Get a photo for a place by place ID and photo reference\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-maps-places.get-place-photo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-maps/refs/heads/main/capabilities/location-intelligence.yaml
tags:
- Google Maps
- Location
- Geocoding
- Directions
- Places
tools:
- description: Geocode an address to coordinates or reverse geocode coordinates to an address
  hints:
    openWorld: true
    readOnly: true
  name: geocode
- description: Get directions between two or more locations with support for driving, walking, bicycling, and transit
  hints:
    openWorld: true
    readOnly: true
  name: get-directions
- description: Get detailed information about a place including address, rating, hours, and reviews
  hints:
    openWorld: true
    readOnly: true
  name: get-place-details
- description: Search for places using a natural language text query like 'pizza in New York'
  hints:
    openWorld: true
    readOnly: true
  name: search-places-text
- description: Search for places near a specific location with type filters
  hints:
    openWorld: true
    readOnly: true
  name: search-places-nearby
- description: Get place autocomplete predictions as the user types
  hints:
    openWorld: true
    readOnly: true
  name: autocomplete-places
- description: Get a photo for a place by place ID and photo reference
  hints:
    openWorld: true
    readOnly: true
  name: get-place-photo
---
