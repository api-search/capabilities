---
categories: []
consumed_apis: []
description: Geoapify's Forward Geocoding API for searching addresses worldwide. This API accepts both structured and free-form addresses and returns results in JSON, GeoJSON, or XML formats.
layout: capability
name: Geoapify Forward Geocoding API
operations:
- description: Forward Geocoding
  method: GET
  name: get-geocode-search
  path: /geocode/search
personas: []
provider_name: Geoapify
provider_slug: geoapify
search_terms:
- forward geocoding
- get geocode search
- location
- geocoding
- maps
- api
- geospatial
- geoapify
slug: geoapify-capability
source_filename: geoapify-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Geoapify Forward Geocoding API\n  description: Geoapify's Forward Geocoding API for searching addresses worldwide. This API accepts both structured and free-form\n    addresses and returns results in JSON, GeoJSON, or XML formats.\n  tags:\n  - Geoapify\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: geoapify\n    baseUri: https://api.geoapify.com/v1\n    description: Geoapify Forward Geocoding API HTTP API.\n    resources:\n    - name: geocode-search\n      path: /geocode/search\n      operations:\n      - name: get-geocode-search\n        method: GET\n        description: Forward Geocoding\n        inputParameters:\n        - name: apiKey\n          in: query\n          type: string\n          required: true\n          description: Your API key for accessing the Geoapify API.\n        - name: text\n          in: query\n          type: string\n          description:\
  \ Free-form address input.\n        - name: name\n          in: query\n          type: string\n          description: Amenity or place name as part of a structured address.\n        - name: housenumber\n          in: query\n          type: string\n          description: House number for a structured address.\n        - name: street\n          in: query\n          type: string\n          description: Street name for a structured address.\n        - name: postcode\n          in: query\n          type: string\n          description: Postal code or ZIP code.\n        - name: city\n          in: query\n          type: string\n          description: City name.\n        - name: state\n          in: query\n          type: string\n          description: State name.\n        - name: country\n          in: query\n          type: string\n          description: Country name.\n        - name: type\n          in: query\n          type: string\n          description: Location type filter to narrow down\
  \ search by type.\n        - name: lang\n          in: query\n          type: string\n          description: Language code for the response (2-character ISO 639-1).\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: filter\n          in: query\n          type: string\n          description: Filter results by location constraints (e.g., country, boundary).\n        - name: bias\n          in: query\n          type: string\n          description: Location bias to prioritize search results by proximity or area.\n        - name: format\n          in: query\n          type: string\n          description: Response format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: geoapify-rest\n    description: REST adapter for Geoapify Forward Geocoding API.\n    resources:\n\
  \    - path: /geocode/search\n      name: get-geocode-search\n      operations:\n      - method: GET\n        name: get-geocode-search\n        description: Forward Geocoding\n        call: geoapify.get-geocode-search\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: geoapify-mcp\n    transport: http\n    description: MCP adapter for Geoapify Forward Geocoding API for AI agent use.\n    tools:\n    - name: get-geocode-search\n      description: Forward Geocoding\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: geoapify.get-geocode-search\n      with:\n        apiKey: tools.apiKey\n        text: tools.text\n        name: tools.name\n        housenumber: tools.housenumber\n        street: tools.street\n        postcode: tools.postcode\n        city: tools.city\n        state: tools.state\n        country: tools.country\n        type: tools.type\n        lang: tools.lang\n\
  \        limit: tools.limit\n        filter: tools.filter\n        bias: tools.bias\n        format: tools.format\n      inputParameters:\n      - name: apiKey\n        type: string\n        description: Your API key for accessing the Geoapify API.\n        required: true\n      - name: text\n        type: string\n        description: Free-form address input.\n      - name: name\n        type: string\n        description: Amenity or place name as part of a structured address.\n      - name: housenumber\n        type: string\n        description: House number for a structured address.\n      - name: street\n        type: string\n        description: Street name for a structured address.\n      - name: postcode\n        type: string\n        description: Postal code or ZIP code.\n      - name: city\n        type: string\n        description: City name.\n      - name: state\n        type: string\n        description: State name.\n      - name: country\n        type: string\n        description:\
  \ Country name.\n      - name: type\n        type: string\n        description: Location type filter to narrow down search by type.\n      - name: lang\n        type: string\n        description: Language code for the response (2-character ISO 639-1).\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      - name: filter\n        type: string\n        description: Filter results by location constraints (e.g., country, boundary).\n      - name: bias\n        type: string\n        description: Location bias to prioritize search results by proximity or area.\n      - name: format\n        type: string\n        description: Response format.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/geoapify/refs/heads/main/capabilities/geoapify-capability.yaml
tags:
- Geoapify
- API
tools:
- description: Forward Geocoding
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-geocode-search
---
