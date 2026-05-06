---
categories: []
consumed_apis: []
description: The N2YO REST API provides data for software and web developers to build satellite tracking and prediction applications. The REST API v1 is free but transaction limited. All endpoints require an apiKey query parameter.
layout: capability
name: N2YO Satellite Tracking API
operations:
- description: Get TLE for a satellite
  method: GET
  name: gettle
  path: /tle/{id}
- description: Get satellite positions
  method: GET
  name: getpositions
  path: /positions/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{seconds}
- description: Get visual passes
  method: GET
  name: getvisualpasses
  path: /visualpasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_visibility}
- description: Get radio passes
  method: GET
  name: getradiopasses
  path: /radiopasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_elevation}
- description: What's up - satellites overhead
  method: GET
  name: getabove
  path: /above/{observer_lat}/{observer_lng}/{observer_alt}/{search_radius}/{category_id}
personas: []
provider_name: N2YO
provider_slug: n2yo
search_terms:
- getpositions
- gettle
- satellites
- get satellite positions
- get tle for a satellite
- api
- get radio passes
- space
- get visual passes
- getabove
- getvisualpasses
- n2yo
- tracking
- getradiopasses
- what's up - satellites overhead
slug: n2yo-capability
source_filename: n2yo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: N2YO Satellite Tracking API\n  description: The N2YO REST API provides data for software and web developers to build satellite tracking and prediction\n    applications. The REST API v1 is free but transaction limited. All endpoints require an apiKey query parameter.\n  tags:\n  - N2yo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: n2yo\n    baseUri: https://api.n2yo.com/rest/v1/satellite\n    description: N2YO Satellite Tracking API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: apiKey\n      value: '{{N2YO_TOKEN}}'\n    resources:\n    - name: tle-id\n      path: /tle/{id}\n      operations:\n      - name: gettle\n        method: GET\n        description: Get TLE for a satellite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions-id-observer-lat-observer-lng-observer-\n\
  \      path: /positions/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{seconds}\n      operations:\n      - name: getpositions\n        method: GET\n        description: Get satellite positions\n        inputParameters:\n        - name: seconds\n          in: path\n          type: integer\n          required: true\n          description: Number of future seconds to return (max 300).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: visualpasses-id-observer-lat-observer-lng-observ\n      path: /visualpasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_visibility}\n      operations:\n      - name: getvisualpasses\n        method: GET\n        description: Get visual passes\n        inputParameters:\n        - name: days\n          in: path\n          type: integer\n          required: true\n          description: Days of prediction (max 10).\n        - name: min_visibility\n   \
  \       in: path\n          type: integer\n          required: true\n          description: Minimum visible seconds for a returned pass.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: radiopasses-id-observer-lat-observer-lng-observe\n      path: /radiopasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_elevation}\n      operations:\n      - name: getradiopasses\n        method: GET\n        description: Get radio passes\n        inputParameters:\n        - name: days\n          in: path\n          type: integer\n          required: true\n          description: Days of prediction (max 10).\n        - name: min_elevation\n          in: path\n          type: integer\n          required: true\n          description: Minimum elevation in degrees.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ above-observer-lat-observer-lng-observer-alt-sea\n      path: /above/{observer_lat}/{observer_lng}/{observer_alt}/{search_radius}/{category_id}\n      operations:\n      - name: getabove\n        method: GET\n        description: What's up - satellites overhead\n        inputParameters:\n        - name: search_radius\n          in: path\n          type: integer\n          required: true\n          description: Search radius in degrees (0-90).\n        - name: category_id\n          in: path\n          type: integer\n          required: true\n          description: Satellite category id (0 returns all categories).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: n2yo-rest\n    description: REST adapter for N2YO Satellite Tracking API.\n    resources:\n    - path: /tle/{id}\n      name: gettle\n      operations:\n      - method: GET\n        name: gettle\n\
  \        description: Get TLE for a satellite\n        call: n2yo.gettle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /positions/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{seconds}\n      name: getpositions\n      operations:\n      - method: GET\n        name: getpositions\n        description: Get satellite positions\n        call: n2yo.getpositions\n        with:\n          seconds: rest.seconds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /visualpasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_visibility}\n      name: getvisualpasses\n      operations:\n      - method: GET\n        name: getvisualpasses\n        description: Get visual passes\n        call: n2yo.getvisualpasses\n        with:\n          days: rest.days\n          min_visibility: rest.min_visibility\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /radiopasses/{id}/{observer_lat}/{observer_lng}/{observer_alt}/{days}/{min_elevation}\n\
  \      name: getradiopasses\n      operations:\n      - method: GET\n        name: getradiopasses\n        description: Get radio passes\n        call: n2yo.getradiopasses\n        with:\n          days: rest.days\n          min_elevation: rest.min_elevation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /above/{observer_lat}/{observer_lng}/{observer_alt}/{search_radius}/{category_id}\n      name: getabove\n      operations:\n      - method: GET\n        name: getabove\n        description: What's up - satellites overhead\n        call: n2yo.getabove\n        with:\n          search_radius: rest.search_radius\n          category_id: rest.category_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: n2yo-mcp\n    transport: http\n    description: MCP adapter for N2YO Satellite Tracking API for AI agent use.\n    tools:\n    - name: gettle\n      description: Get TLE for a satellite\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: n2yo.gettle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpositions\n      description: Get satellite positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: n2yo.getpositions\n      with:\n        seconds: tools.seconds\n      inputParameters:\n      - name: seconds\n        type: integer\n        description: Number of future seconds to return (max 300).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvisualpasses\n      description: Get visual passes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: n2yo.getvisualpasses\n      with:\n        days: tools.days\n        min_visibility: tools.min_visibility\n      inputParameters:\n      - name: days\n        type: integer\n\
  \        description: Days of prediction (max 10).\n        required: true\n      - name: min_visibility\n        type: integer\n        description: Minimum visible seconds for a returned pass.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getradiopasses\n      description: Get radio passes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: n2yo.getradiopasses\n      with:\n        days: tools.days\n        min_elevation: tools.min_elevation\n      inputParameters:\n      - name: days\n        type: integer\n        description: Days of prediction (max 10).\n        required: true\n      - name: min_elevation\n        type: integer\n        description: Minimum elevation in degrees.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getabove\n      description: What's up - satellites overhead\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: n2yo.getabove\n      with:\n        search_radius: tools.search_radius\n        category_id: tools.category_id\n      inputParameters:\n      - name: search_radius\n        type: integer\n        description: Search radius in degrees (0-90).\n        required: true\n      - name: category_id\n        type: integer\n        description: Satellite category id (0 returns all categories).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    N2YO_TOKEN: N2YO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/n2yo/refs/heads/main/capabilities/n2yo-capability.yaml
tags:
- N2yo
- API
tools:
- description: Get TLE for a satellite
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettle
- description: Get satellite positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpositions
- description: Get visual passes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvisualpasses
- description: Get radio passes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getradiopasses
- description: What's up - satellites overhead
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getabove
---
