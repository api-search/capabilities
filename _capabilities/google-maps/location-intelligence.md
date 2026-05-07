---
categories: []
consumed_apis: []
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
- place autocomplete predictions
- environment
- location-based place search
- geocoding
- get detailed information about a place
- search for places near a location
- get directions
- geocode an address or reverse geocode coordinates
- navigation
- search for places using a natural language text query like 'pizza in new york'
- geocode
- text-based place search
- search places nearby
- get directions between two or more locations with support for driving, walking, bicycling, and transit
- directions
- autocomplete places
- get place details
- route computation between locations
- geolocation
- get place predictions for input text
- get directions between two or more locations
- search for places near a specific location with type filters
- routing
- address to coordinate conversion and reverse geocoding
- place details retrieval
- location
- get a photo for a place by place id and photo reference
- search places text
- places
- get place photo
- maps
- solar
- search for places using a text query
- geocode an address to coordinates or reverse geocode coordinates to an address
- google maps
- get detailed information about a place including address, rating, hours, and reviews
- get place autocomplete predictions as the user types
slug: location-intelligence
source_filename: location-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Maps Location Intelligence\n  description: Unified workflow combining Google Maps Directions, Geocoding, and Places APIs for location-aware applications.\n    Enables developers to geocode addresses, compute routes, search for places, and retrieve place details in a single integration.\n  tags:\n  - Google Maps\n  - Location\n  - Geocoding\n  - Directions\n  - Places\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_MAPS_API_KEY: GOOGLE_MAPS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: google-maps-directions\n    baseUri: https://maps.googleapis.com/maps/api\n    description: Google Maps Directions API for computing routes between locations.\n    authentication:\n      type: apikey\n      key: key\n      value: '{{GOOGLE_MAPS_API_KEY}}'\n      placement: query\n    resources:\n    - name: directions\n      path: /directions/json\n      description: Route computation\
  \ between origin and destination\n      operations:\n      - name: get-directions\n        method: GET\n        description: Calculates directions between an origin and a destination with support for waypoints, travel modes, and\n          traffic awareness.\n        inputParameters:\n        - name: origin\n          in: query\n          type: string\n          required: true\n          description: The starting point address, place ID, or coordinates\n        - name: destination\n          in: query\n          type: string\n          required: true\n          description: The ending point address, place ID, or coordinates\n        - name: mode\n          in: query\n          type: string\n          required: false\n          description: 'Travel mode: driving, walking, bicycling, or transit'\n        - name: waypoints\n          in: query\n          type: string\n          required: false\n          description: Intermediate locations as pipe-separated values\n        - name: alternatives\n\
  \          in: query\n          type: boolean\n          required: false\n          description: Return alternative routes when available\n        - name: avoid\n          in: query\n          type: string\n          required: false\n          description: 'Features to avoid: tolls, highways, ferries'\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code for results\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: 'Unit system: metric or imperial'\n        - name: departure_time\n          in: query\n          type: string\n          required: false\n          description: Desired departure time as epoch seconds or 'now'\n        - name: traffic_model\n          in: query\n          type: string\n          required: false\n          description: 'Traffic model: best_guess, pessimistic, or optimistic'\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: google-maps-geocoding\n    baseUri: https://maps.googleapis.com/maps/api\n    description: Google Maps Geocoding API for converting addresses to coordinates and vice versa.\n    authentication:\n      type: apikey\n      key: key\n      value: '{{GOOGLE_MAPS_API_KEY}}'\n      placement: query\n    resources:\n    - name: geocoding\n      path: /geocode/json\n      description: Forward and reverse geocoding operations\n      operations:\n      - name: geocode\n        method: GET\n        description: Converts an address to coordinates or coordinates to an address.\n        inputParameters:\n        - name: address\n          in: query\n          type: string\n          required: false\n          description: The street address or plus code to geocode\n        - name: latlng\n          in: query\n          type: string\n          required: false\n          description:\
  \ Latitude and longitude for reverse geocoding\n        - name: place_id\n          in: query\n          type: string\n          required: false\n          description: The place ID to obtain the address for\n        - name: components\n          in: query\n          type: string\n          required: false\n          description: Component filter as pipe-separated pairs\n        - name: bounds\n          in: query\n          type: string\n          required: false\n          description: Bounding box to bias geocode results\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: Region code for biasing results\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code for results\n        - name: result_type\n          in: query\n          type: string\n          required: false\n          description: Filter by address type for reverse geocoding\n\
  \        - name: location_type\n          in: query\n          type: string\n          required: false\n          description: Filter by location type for reverse geocoding\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: google-maps-places\n    baseUri: https://places.googleapis.com/v1\n    description: Google Maps Places API (New) for searching and retrieving place information.\n    authentication:\n      type: apikey\n      key: X-Goog-Api-Key\n      value: '{{GOOGLE_MAPS_API_KEY}}'\n      placement: header\n    resources:\n    - name: place-details\n      path: /places\n      description: Get detailed information about a specific place\n      operations:\n      - name: get-place-details\n        method: GET\n        path: /{placeId}\n        description: Returns detailed information about a place identified by its resource name.\n        inputParameters:\n        - name: placeId\n\
  \          in: path\n          type: string\n          required: true\n          description: The resource name of a place\n        - name: X-Goog-FieldMask\n          in: header\n          type: string\n          required: true\n          description: Comma-separated list of fields to return\n        - name: languageCode\n          in: query\n          type: string\n          required: false\n          description: BCP-47 language code for results\n        - name: regionCode\n          in: query\n          type: string\n          required: false\n          description: Region code for biasing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: text-search\n      path: /places:searchText\n      description: Search for places using a text query\n      operations:\n      - name: search-places-text\n        method: POST\n        description: Returns places matching a text query like 'pizza in New York'.\n\
  \        inputParameters:\n        - name: X-Goog-FieldMask\n          in: header\n          type: string\n          required: true\n          description: Comma-separated list of fields to return\n        body:\n          type: json\n          data:\n            textQuery: '{{tools.textQuery}}'\n            includedType: '{{tools.includedType}}'\n            languageCode: '{{tools.languageCode}}'\n            maxResultCount: '{{tools.maxResultCount}}'\n            openNow: '{{tools.openNow}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nearby-search\n      path: /places:searchNearby\n      description: Search for places near a specific location\n      operations:\n      - name: search-places-nearby\n        method: POST\n        description: Returns places near a specified location with type and ranking filters.\n        inputParameters:\n        - name: X-Goog-FieldMask\n          in: header\n\
  \          type: string\n          required: true\n          description: Comma-separated list of fields to return\n        body:\n          type: json\n          data:\n            includedTypes: '{{tools.includedTypes}}'\n            maxResultCount: '{{tools.maxResultCount}}'\n            locationRestriction: '{{tools.locationRestriction}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: autocomplete\n      path: /places:autocomplete\n      description: Get place predictions based on text input\n      operations:\n      - name: autocomplete-places\n        method: POST\n        description: Returns place and query predictions for input text.\n        body:\n          type: json\n          data:\n            input: '{{tools.input}}'\n            languageCode: '{{tools.languageCode}}'\n            includeQueryPredictions: '{{tools.includeQueryPredictions}}'\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: photos\n      path: /places/{placeId}/photos\n      description: Access photos associated with places\n      operations:\n      - name: get-place-photo\n        method: GET\n        path: /{photoReference}/media\n        description: Returns a photo for a place.\n        inputParameters:\n        - name: placeId\n          in: path\n          type: string\n          required: true\n          description: The place ID\n        - name: photoReference\n          in: path\n          type: string\n          required: true\n          description: The photo resource reference\n        - name: maxHeightPx\n          in: query\n          type: integer\n          required: false\n          description: Maximum height in pixels (1-4800)\n        - name: maxWidthPx\n          in: query\n          type: integer\n          required: false\n          description: Maximum width in pixels (1-4800)\n\
  \        - name: skipHttpRedirect\n          in: query\n          type: boolean\n          required: false\n          description: Return JSON with URI instead of redirect\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: location-intelligence-api\n    description: Unified REST API for location intelligence combining geocoding, directions, and places.\n    resources:\n    - path: /v1/geocode\n      name: geocoding\n      description: Address to coordinate conversion and reverse geocoding\n      operations:\n      - method: GET\n        name: geocode\n        description: Geocode an address or reverse geocode coordinates\n        call: google-maps-geocoding.geocode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/directions\n      name: directions\n      description: Route computation between locations\n      operations:\n\
  \      - method: GET\n        name: get-directions\n        description: Get directions between two or more locations\n        call: google-maps-directions.get-directions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/places/{placeId}\n      name: place-details\n      description: Place details retrieval\n      operations:\n      - method: GET\n        name: get-place-details\n        description: Get detailed information about a place\n        call: google-maps-places.get-place-details\n        with:\n          placeId: rest.placeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/places/search-text\n      name: text-search\n      description: Text-based place search\n      operations:\n      - method: POST\n        name: search-places-text\n        description: Search for places using a text query\n        call: google-maps-places.search-places-text\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/places/search-nearby\n      name: nearby-search\n      description: Location-based place search\n      operations:\n      - method: POST\n        name: search-places-nearby\n        description: Search for places near a location\n        call: google-maps-places.search-places-nearby\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/places/autocomplete\n      name: autocomplete\n      description: Place autocomplete predictions\n      operations:\n      - method: POST\n        name: autocomplete-places\n        description: Get place predictions for input text\n        call: google-maps-places.autocomplete-places\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: location-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted location intelligence combining geocoding, directions, and places search.\n    tools:\n\
  \    - name: geocode\n      description: Geocode an address to coordinates or reverse geocode coordinates to an address\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-geocoding.geocode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-directions\n      description: Get directions between two or more locations with support for driving, walking, bicycling, and transit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-directions.get-directions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-place-details\n      description: Get detailed information about a place including address, rating, hours, and reviews\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-places.get-place-details\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-places-text\n      description: Search\
  \ for places using a natural language text query like 'pizza in New York'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-places.search-places-text\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-places-nearby\n      description: Search for places near a specific location with type filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-places.search-places-nearby\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: autocomplete-places\n      description: Get place autocomplete predictions as the user types\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-maps-places.autocomplete-places\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-place-photo\n      description: Get a photo for a place by place ID and photo reference\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: google-maps-places.get-place-photo\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
