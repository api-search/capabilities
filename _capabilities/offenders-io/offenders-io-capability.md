---
categories: []
consumed_apis: []
description: Industry-leading database of National Registered Sex Offenders for the United States. Supports criteria-based search by name, date of birth, city, zip, state, and geospatial radius queries. Returns rich JSON records including identity, photo, address, GPS coordinates, crimes, and risk level.
layout: capability
name: Offenders.io API
operations:
- description: Search sex offender registry
  method: GET
  name: searchsexoffenders
  path: /sexoffender
personas: []
provider_name: Offenders.io
provider_slug: offenders-io
search_terms:
- offenders
- public safety
- io
- search sex offender registry
- criminal records
- sex offenders
- api
- searchsexoffenders
slug: offenders-io-capability
source_filename: offenders-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Offenders.io API\n  description: Industry-leading database of National Registered Sex Offenders for the United States. Supports criteria-based\n    search by name, date of birth, city, zip, state, and geospatial radius queries. Returns rich JSON records including identity,\n    photo, address, GPS coordinates, crimes, and risk level.\n  tags:\n  - Offenders\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: offenders-io\n    baseUri: https://api.offenders.io\n    description: Offenders.io API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{OFFENDERS_IO_TOKEN}}'\n    resources:\n    - name: sexoffender\n      path: /sexoffender\n      operations:\n      - name: searchsexoffenders\n        method: GET\n        description: Search sex offender registry\n        inputParameters:\n        - name: firstName\n     \
  \     in: query\n          type: string\n          description: Offender first name (structured search).\n        - name: lastName\n          in: query\n          type: string\n          description: Offender last name (structured search).\n        - name: zipcode\n          in: query\n          type: string\n          description: ZIP code for location-based filtering.\n        - name: lat\n          in: query\n          type: number\n          description: Latitude for geospatial search.\n        - name: lng\n          in: query\n          type: number\n          description: Longitude for geospatial search.\n        - name: radius\n          in: query\n          type: number\n          description: Search radius in miles (used with lat/lng).\n        - name: fuzzy\n          in: query\n          type: boolean\n          description: Enable typo-tolerant fuzzy matching.\n        - name: key\n          in: query\n          type: string\n          required: true\n          description:\
  \ API key for authentication.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: offenders-io-rest\n    description: REST adapter for Offenders.io API.\n    resources:\n    - path: /sexoffender\n      name: searchsexoffenders\n      operations:\n      - method: GET\n        name: searchsexoffenders\n        description: Search sex offender registry\n        call: offenders-io.searchsexoffenders\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: offenders-io-mcp\n    transport: http\n    description: MCP adapter for Offenders.io API for AI agent use.\n    tools:\n    - name: searchsexoffenders\n      description: Search sex offender registry\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: offenders-io.searchsexoffenders\n      with:\n\
  \        firstName: tools.firstName\n        lastName: tools.lastName\n        zipcode: tools.zipcode\n        lat: tools.lat\n        lng: tools.lng\n        radius: tools.radius\n        fuzzy: tools.fuzzy\n        key: tools.key\n      inputParameters:\n      - name: firstName\n        type: string\n        description: Offender first name (structured search).\n      - name: lastName\n        type: string\n        description: Offender last name (structured search).\n      - name: zipcode\n        type: string\n        description: ZIP code for location-based filtering.\n      - name: lat\n        type: number\n        description: Latitude for geospatial search.\n      - name: lng\n        type: number\n        description: Longitude for geospatial search.\n      - name: radius\n        type: number\n        description: Search radius in miles (used with lat/lng).\n      - name: fuzzy\n        type: boolean\n        description: Enable typo-tolerant fuzzy matching.\n      - name: key\n\
  \        type: string\n        description: API key for authentication.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OFFENDERS_IO_TOKEN: OFFENDERS_IO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/offenders-io/refs/heads/main/capabilities/offenders-io-capability.yaml
tags:
- Offenders
- Io
- API
tools:
- description: Search sex offender registry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsexoffenders
---
