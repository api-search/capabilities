---
categories: []
consumed_apis: []
description: Workflow capability combining Walk Score and Transit APIs for comprehensive location intelligence. Enables applications to assess any location's walkability, transit accessibility, and bikeability in a unified workflow. Used by real estate platforms, city planners, commute calculators, and property search applications to provide complete transportation accessibility scoring.
layout: capability
name: Walk Score Location Intelligence
operations:
- description: Get all walkability scores for a location
  method: GET
  name: get-walk-score
  path: /v1/scores
- description: Get Transit Score with route summary for a city location
  method: GET
  name: get-transit-score
  path: /v1/transit-scores
- description: Get transit stops near a location
  method: GET
  name: search-transit-stops
  path: /v1/transit-stops
- description: Get all routes and stops within one mile
  method: GET
  name: search-transit-network
  path: /v1/transit-network
- description: Get transit stop details
  method: GET
  name: get-transit-stop
  path: /v1/transit-stops/{stopId}
- description: Get transit route details and geometry
  method: GET
  name: get-transit-route
  path: /v1/transit-routes/{routeId}
- description: Get all cities supported by Transit API
  method: GET
  name: list-supported-cities
  path: /v1/cities
personas: []
provider_name: Walk Score
provider_slug: walk-score
search_terms:
- get transit route details
- bikeability
- get transit score with route summary for a city location
- get transit stops near a location
- get transit stop details
- get details for a specific transit stop by id
- get all transit routes and stops within one mile of a location
- search transit stops
- get all routes and stops within one mile
- get all cities supported by transit api
- get details for a transit route including stops and route geometry
- get transit route details and geometry
- get transit stop
- get walk score
- get a specific transit stop
- get walk score, transit score, and bike score for any address or coordinates. returns walkability, transit accessibility, and bikeability in one call.
- get walk score, transit score, and bike score for a location
- get location scores
- get the list of all cities supported by the walk score transit api
- get detailed transit score for a city location
- location intelligence
- get transit score
- get transit network
- find public transit stops near any location with route details
- list transit cities
- get detailed transit score with route count summary for a city location
- get a specific transit route
- get all walkability scores for a location
- transportation
- get transit network within one mile
- location
- real estate
- walk score
- get transit route
- walkability
- find nearby transit stops
- list supported cities
- transit
- list cities with transit score support
- search transit network
- urban planning
slug: location-intelligence
source_filename: location-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Walk Score Location Intelligence\n  description: Workflow capability combining Walk Score and Transit APIs for comprehensive location intelligence. Enables\n    applications to assess any location's walkability, transit accessibility, and bikeability in a unified workflow. Used\n    by real estate platforms, city planners, commute calculators, and property search applications to provide complete transportation\n    accessibility scoring.\n  tags:\n  - Walk Score\n  - Location Intelligence\n  - Walkability\n  - Transit\n  - Bikeability\n  - Real Estate\n  - Urban Planning\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WALKSCORE_API_KEY: WALKSCORE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: walk-score-api\n    baseUri: https://api.walkscore.com\n    description: Walk Score API for walkability, transit, and bike scores\n    authentication:\n      type: apikey\n      key: wsapikey\n\
  \      value: '{{WALKSCORE_API_KEY}}'\n      placement: query\n    resources:\n    - name: scores\n      path: /score\n      description: Get Walk Score, Transit Score, and Bike Score for a location\n      operations:\n      - name: get-walk-score\n        method: GET\n        description: Get walkability, transit, and bike scores for a lat/lon location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude coordinate\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude coordinate\n        - name: address\n          in: query\n          type: string\n          required: true\n          description: URL-encoded street address\n        - name: transit\n          in: query\n          type: integer\n          required: false\n          description: Set to 1 to include Transit Score\n        - name: bike\n          in: query\n\
  \          type: integer\n          required: false\n          description: Set to 1 to include Bike Score\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Response format: json or xml'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: walk-score-transit\n    baseUri: https://transit.walkscore.com\n    description: Walk Score Public Transit API for detailed transit data\n    authentication:\n      type: apikey\n      key: wsapikey\n      value: '{{WALKSCORE_API_KEY}}'\n      placement: query\n    resources:\n    - name: transit-score\n      path: /transit/score/\n      description: Get Transit Score for a location\n      operations:\n      - name: get-transit-score\n        method: GET\n        description: Get Transit Score for a city location\n        inputParameters:\n        - name: lat\n          in: query\n\
  \          type: number\n          required: true\n          description: Latitude to score\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude to score\n        - name: city\n          in: query\n          type: string\n          required: true\n          description: City name\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Two-letter state code (US cities)\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: ISO-3166 country code (non-US cities)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stops-search\n      path: /transit/search/stops/\n      description: Search for nearby transit stops\n      operations:\n      - name: search-transit-stops\n        method: GET\n        description:\
  \ Get up to 16 transit stops near a location with route info\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Search latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Search longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: network-search\n      path: /transit/search/network/\n      description: Get all transit routes and stops within one mile\n      operations:\n      - name: search-transit-network\n        method: GET\n        description: Get all routes and stops within one mile of a location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Search latitude\n        - name: lon\n          in: query\n          type: number\n      \
  \    required: true\n          description: Search longitude\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stop-details\n      path: /transit/stop/{stopId}/\n      description: Get details for a specific transit stop\n      operations:\n      - name: get-transit-stop\n        method: GET\n        description: Get details for a transit stop by ID\n        inputParameters:\n        - name: stopId\n          in: path\n          type: string\n          required: true\n          description: Stop identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-details\n      path: /transit/route/{routeId}/\n      description: Get details for a specific transit route\n      operations:\n      - name: get-transit-route\n        method: GET\n        description: Get details for a transit route by ID\n        inputParameters:\n\
  \        - name: routeId\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supported-cities\n      path: /transit/supported/cities/\n      description: Get list of supported cities\n      operations:\n      - name: list-supported-cities\n        method: GET\n        description: Get all cities supported by the Transit API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: walk-score-location-intelligence-api\n    description: Unified REST API for Walk Score location intelligence and transit data.\n    resources:\n    - path: /v1/scores\n      name: scores\n      description: Get Walk Score, Transit Score, and Bike Score for a location\n      operations:\n\
  \      - method: GET\n        name: get-walk-score\n        description: Get all walkability scores for a location\n        call: walk-score-api.get-walk-score\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          address: rest.address\n          transit: rest.transit\n          bike: rest.bike\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transit-scores\n      name: transit-scores\n      description: Get detailed Transit Score for a city location\n      operations:\n      - method: GET\n        name: get-transit-score\n        description: Get Transit Score with route summary for a city location\n        call: walk-score-transit.get-transit-score\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          city: rest.city\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transit-stops\n      name: transit-stops\n      description: Find\
  \ nearby transit stops\n      operations:\n      - method: GET\n        name: search-transit-stops\n        description: Get transit stops near a location\n        call: walk-score-transit.search-transit-stops\n        with:\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/transit-network\n      name: transit-network\n      description: Get transit network within one mile\n      operations:\n      - method: GET\n        name: search-transit-network\n        description: Get all routes and stops within one mile\n        call: walk-score-transit.search-transit-network\n        with:\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transit-stops/{stopId}\n      name: transit-stop-detail\n      description: Get a specific transit stop\n      operations:\n      - method: GET\n        name: get-transit-stop\n  \
  \      description: Get transit stop details\n        call: walk-score-transit.get-transit-stop\n        with:\n          stopId: rest.stopId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transit-routes/{routeId}\n      name: transit-route-detail\n      description: Get a specific transit route\n      operations:\n      - method: GET\n        name: get-transit-route\n        description: Get transit route details and geometry\n        call: walk-score-transit.get-transit-route\n        with:\n          routeId: rest.routeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cities\n      name: supported-cities\n      description: List cities with transit score support\n      operations:\n      - method: GET\n        name: list-supported-cities\n        description: Get all cities supported by Transit API\n        call: walk-score-transit.list-supported-cities\n        outputParameters:\n        - type:\
  \ array\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: walk-score-location-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted Walk Score location intelligence workflows.\n    tools:\n    - name: get-location-scores\n      description: Get Walk Score, Transit Score, and Bike Score for any address or coordinates. Returns walkability, transit\n        accessibility, and bikeability in one call.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walk-score-api.get-walk-score\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        address: tools.address\n        transit: tools.transit\n        bike: tools.bike\n        format: json\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transit-score\n      description: Get detailed Transit Score with route count summary for a city location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walk-score-transit.get-transit-score\n\
  \      with:\n        lat: tools.lat\n        lon: tools.lon\n        city: tools.city\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-transit-stops\n      description: Find public transit stops near any location with route details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walk-score-transit.search-transit-stops\n      with:\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-transit-network\n      description: Get all transit routes and stops within one mile of a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: walk-score-transit.search-transit-network\n      with:\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transit-stop-details\n      description: Get details for a specific transit\
  \ stop by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walk-score-transit.get-transit-stop\n      with:\n        stopId: tools.stopId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transit-route-details\n      description: Get details for a transit route including stops and route geometry\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walk-score-transit.get-transit-route\n      with:\n        routeId: tools.routeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transit-cities\n      description: Get the list of all cities supported by the Walk Score Transit API\n      hints:\n        readOnly: true\n        openWorld: false\n      call: walk-score-transit.list-supported-cities\n      outputParameters:\n      - type: array\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/walk-score/refs/heads/main/capabilities/location-intelligence.yaml
tags:
- Walk Score
- Location Intelligence
- Walkability
- Transit
- Bikeability
- Real Estate
- Urban Planning
tools:
- description: Get Walk Score, Transit Score, and Bike Score for any address or coordinates. Returns walkability, transit accessibility, and bikeability in one call.
  hints:
    openWorld: true
    readOnly: true
  name: get-location-scores
- description: Get detailed Transit Score with route count summary for a city location
  hints:
    openWorld: true
    readOnly: true
  name: get-transit-score
- description: Find public transit stops near any location with route details
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-transit-stops
- description: Get all transit routes and stops within one mile of a location
  hints:
    openWorld: true
    readOnly: true
  name: get-transit-network
- description: Get details for a specific transit stop by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-transit-stop-details
- description: Get details for a transit route including stops and route geometry
  hints:
    openWorld: false
    readOnly: true
  name: get-transit-route-details
- description: Get the list of all cities supported by the Walk Score Transit API
  hints:
    openWorld: false
    readOnly: true
  name: list-transit-cities
---
