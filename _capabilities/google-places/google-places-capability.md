---
categories: []
consumed_apis: []
description: The Places API is a service that accepts HTTP requests for location data through a variety of methods. It returns formatted location data and imagery about establishments, geographic locations, or prominent points of interest.
layout: capability
name: Google Places API (New)
operations:
- description: Google Places Nearby Search
  method: POST
  name: searchnearbyplaces
  path: /places:searchNearby
- description: Google Places Text Search
  method: POST
  name: searchtextplaces
  path: /places:searchText
- description: Google Places Place Details
  method: GET
  name: getplacedetails
  path: /places/{placeId}
- description: Google Places Place Photo
  method: GET
  name: getplacephoto
  path: /places/{placeId}/photos/{photoReference}/media
- description: Google Places Autocomplete
  method: POST
  name: autocompleteplaces
  path: /places:autocomplete
personas: []
provider_name: Google Places
provider_slug: google-places
search_terms:
- google places place details
- google places text search
- getplacedetails
- google
- api
- google places autocomplete
- google places place photo
- geolocation
- google places nearby search
- places
- getplacephoto
- searchtextplaces
- locations
- autocompleteplaces
- maps
- searchnearbyplaces
- points of interest
slug: google-places-capability
source_filename: google-places-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Places API (New)\n  description: The Places API is a service that accepts HTTP requests for location data through a variety of methods. It returns\n    formatted location data and imagery about establishments, geographic locations, or prominent points of interest.\n  tags:\n  - Google\n  - Places\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-places\n    baseUri: https://places.googleapis.com/v1\n    description: Google Places API (New) HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_PLACES_TOKEN}}'\n    resources:\n    - name: places-searchnearby\n      path: /places:searchNearby\n      operations:\n      - name: searchnearbyplaces\n        method: POST\n        description: Google Places Nearby Search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: places-searchtext\n      path: /places:searchText\n      operations:\n      - name: searchtextplaces\n        method: POST\n        description: Google Places Text Search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: places-placeid\n      path: /places/{placeId}\n      operations:\n      - name: getplacedetails\n        method: GET\n        description: Google Places Place Details\n        inputParameters:\n        - name: placeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: places-placeid-photos-photoreference-media\n      path: /places/{placeId}/photos/{photoReference}/media\n      operations:\n      - name: getplacephoto\n        method: GET\n        description: Google Places\
  \ Place Photo\n        inputParameters:\n        - name: placeId\n          in: path\n          type: string\n          required: true\n        - name: photoReference\n          in: path\n          type: string\n          required: true\n        - name: maxHeightPx\n          in: query\n          type: integer\n        - name: maxWidthPx\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: places-autocomplete\n      path: /places:autocomplete\n      operations:\n      - name: autocompleteplaces\n        method: POST\n        description: Google Places Autocomplete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-places-rest\n    description: REST adapter for Google Places API (New).\n    resources:\n    - path: /places:searchNearby\n\
  \      name: searchnearbyplaces\n      operations:\n      - method: POST\n        name: searchnearbyplaces\n        description: Google Places Nearby Search\n        call: google-places.searchnearbyplaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /places:searchText\n      name: searchtextplaces\n      operations:\n      - method: POST\n        name: searchtextplaces\n        description: Google Places Text Search\n        call: google-places.searchtextplaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /places/{placeId}\n      name: getplacedetails\n      operations:\n      - method: GET\n        name: getplacedetails\n        description: Google Places Place Details\n        call: google-places.getplacedetails\n        with:\n          placeId: rest.placeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /places/{placeId}/photos/{photoReference}/media\n      name:\
  \ getplacephoto\n      operations:\n      - method: GET\n        name: getplacephoto\n        description: Google Places Place Photo\n        call: google-places.getplacephoto\n        with:\n          placeId: rest.placeId\n          photoReference: rest.photoReference\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /places:autocomplete\n      name: autocompleteplaces\n      operations:\n      - method: POST\n        name: autocompleteplaces\n        description: Google Places Autocomplete\n        call: google-places.autocompleteplaces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-places-mcp\n    transport: http\n    description: MCP adapter for Google Places API (New) for AI agent use.\n    tools:\n    - name: searchnearbyplaces\n      description: Google Places Nearby Search\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: google-places.searchnearbyplaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchtextplaces\n      description: Google Places Text Search\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-places.searchtextplaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getplacedetails\n      description: Google Places Place Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-places.getplacedetails\n      with:\n        placeId: tools.placeId\n      inputParameters:\n      - name: placeId\n        type: string\n        description: placeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getplacephoto\n      description: Google Places Place Photo\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: google-places.getplacephoto\n      with:\n        placeId: tools.placeId\n        photoReference: tools.photoReference\n        maxHeightPx: tools.maxHeightPx\n        maxWidthPx: tools.maxWidthPx\n      inputParameters:\n      - name: placeId\n        type: string\n        description: placeId\n        required: true\n      - name: photoReference\n        type: string\n        description: photoReference\n        required: true\n      - name: maxHeightPx\n        type: integer\n        description: maxHeightPx\n      - name: maxWidthPx\n        type: integer\n        description: maxWidthPx\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: autocompleteplaces\n      description: Google Places Autocomplete\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-places.autocompleteplaces\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n\
  \  keys:\n    GOOGLE_PLACES_TOKEN: GOOGLE_PLACES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-places/refs/heads/main/capabilities/google-places-capability.yaml
tags:
- Google
- Places
- API
tools:
- description: Google Places Nearby Search
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchnearbyplaces
- description: Google Places Text Search
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchtextplaces
- description: Google Places Place Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getplacedetails
- description: Google Places Place Photo
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getplacephoto
- description: Google Places Autocomplete
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: autocompleteplaces
---
