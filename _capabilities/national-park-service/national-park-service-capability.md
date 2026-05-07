---
categories: []
consumed_apis: []
description: The NPS Data API provides official, authoritative data and content about United States national parks, monuments, and historic sites. The API delivers information about parks, alerts, news releases, events, places, visitor centers, campgrounds, articles, people, and more.
layout: capability
name: National Park Service Data API
operations:
- description: Retrieve parks
  method: GET
  name: get-parks
  path: /parks
- description: Retrieve alerts
  method: GET
  name: get-alerts
  path: /alerts
- description: Retrieve news releases
  method: GET
  name: get-newsreleases
  path: /newsreleases
- description: Retrieve events
  method: GET
  name: get-events
  path: /events
- description: Retrieve places
  method: GET
  name: get-places
  path: /places
- description: Retrieve visitor centers
  method: GET
  name: get-visitorcenters
  path: /visitorcenters
- description: Retrieve campgrounds
  method: GET
  name: get-campgrounds
  path: /campgrounds
- description: Retrieve articles
  method: GET
  name: get-articles
  path: /articles
- description: Retrieve historical people
  method: GET
  name: get-people
  path: /people
- description: List activities available within parks
  method: GET
  name: get-activities
  path: /activities
- description: List topics covered by NPS
  method: GET
  name: get-topics
  path: /topics
personas: []
provider_name: National Park Service
provider_slug: national-park-service
search_terms:
- get alerts
- api
- retrieve historical people
- get topics
- conservation
- retrieve events
- retrieve places
- service
- get campgrounds
- get visitorcenters
- retrieve parks
- retrieve campgrounds
- park
- get articles
- retrieve articles
- list topics covered by nps
- get events
- get people
- retrieve visitor centers
- get parks
- parks
- retrieve news releases
- list activities available within parks
- retrieve alerts
- federal government
- get newsreleases
- get activities
- get places
- national
slug: national-park-service-capability
source_filename: national-park-service-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: National Park Service Data API\n  description: The NPS Data API provides official, authoritative data and content about United States national parks, monuments,\n    and historic sites. The API delivers information about parks, alerts, news releases, events, places, visitor centers,\n    campgrounds, articles, people, and more.\n  tags:\n  - National\n  - Park\n  - Service\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-park-service\n    baseUri: https://developer.nps.gov/api/v1\n    description: National Park Service Data API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Api-Key\n      value: '{{NATIONAL_PARK_SERVICE_TOKEN}}'\n    resources:\n    - name: parks\n      path: /parks\n      operations:\n      - name: get-parks\n        method: GET\n        description: Retrieve parks\n        inputParameters:\n        - name:\
  \ parkCode\n          in: query\n          type: string\n          description: Comma-delimited list of park codes (e.g., acad,dena).\n        - name: stateCode\n          in: query\n          type: string\n          description: Comma-delimited list of two-letter state codes.\n        - name: q\n          in: query\n          type: string\n          description: Free-text search term.\n        - name: limit\n          in: query\n          type: integer\n        - name: start\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /alerts\n      operations:\n      - name: get-alerts\n        method: GET\n        description: Retrieve alerts\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: stateCode\n          in: query\n          type: string\n        - name: q\n          in:\
  \ query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: start\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: newsreleases\n      path: /newsreleases\n      operations:\n      - name: get-newsreleases\n        method: GET\n        description: Retrieve news releases\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: get-events\n        method: GET\n        description: Retrieve events\n        inputParameters:\n   \
  \     - name: parkCode\n          in: query\n          type: string\n        - name: stateCode\n          in: query\n          type: string\n        - name: dateStart\n          in: query\n          type: string\n        - name: dateEnd\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: places\n      path: /places\n      operations:\n      - name: get-places\n        method: GET\n        description: Retrieve places\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: stateCode\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: visitorcenters\n      path: /visitorcenters\n      operations:\n      - name:\
  \ get-visitorcenters\n        method: GET\n        description: Retrieve visitor centers\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: stateCode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campgrounds\n      path: /campgrounds\n      operations:\n      - name: get-campgrounds\n        method: GET\n        description: Retrieve campgrounds\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: stateCode\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: articles\n      path: /articles\n      operations:\n      - name: get-articles\n        method: GET\n        description: Retrieve articles\n\
  \        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people\n      operations:\n      - name: get-people\n        method: GET\n        description: Retrieve historical people\n        inputParameters:\n        - name: parkCode\n          in: query\n          type: string\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities\n      path: /activities\n      operations:\n      - name: get-activities\n        method: GET\n        description: List activities available within parks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: topics\n      path: /topics\n      operations:\n      - name: get-topics\n        method: GET\n        description: List topics covered by NPS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-park-service-rest\n    description: REST adapter for National Park Service Data API.\n    resources:\n    - path: /parks\n      name: get-parks\n      operations:\n      - method: GET\n        name: get-parks\n        description: Retrieve parks\n        call: national-park-service.get-parks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerts\n      name: get-alerts\n      operations:\n      - method: GET\n        name: get-alerts\n        description: Retrieve alerts\n        call: national-park-service.get-alerts\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /newsreleases\n      name: get-newsreleases\n      operations:\n      - method: GET\n        name: get-newsreleases\n        description: Retrieve news releases\n        call: national-park-service.get-newsreleases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: get-events\n      operations:\n      - method: GET\n        name: get-events\n        description: Retrieve events\n        call: national-park-service.get-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /places\n      name: get-places\n      operations:\n      - method: GET\n        name: get-places\n        description: Retrieve places\n        call: national-park-service.get-places\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /visitorcenters\n      name: get-visitorcenters\n      operations:\n      - method: GET\n        name: get-visitorcenters\n\
  \        description: Retrieve visitor centers\n        call: national-park-service.get-visitorcenters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campgrounds\n      name: get-campgrounds\n      operations:\n      - method: GET\n        name: get-campgrounds\n        description: Retrieve campgrounds\n        call: national-park-service.get-campgrounds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /articles\n      name: get-articles\n      operations:\n      - method: GET\n        name: get-articles\n        description: Retrieve articles\n        call: national-park-service.get-articles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people\n      name: get-people\n      operations:\n      - method: GET\n        name: get-people\n        description: Retrieve historical people\n        call: national-park-service.get-people\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /activities\n      name: get-activities\n      operations:\n      - method: GET\n        name: get-activities\n        description: List activities available within parks\n        call: national-park-service.get-activities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /topics\n      name: get-topics\n      operations:\n      - method: GET\n        name: get-topics\n        description: List topics covered by NPS\n        call: national-park-service.get-topics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-park-service-mcp\n    transport: http\n    description: MCP adapter for National Park Service Data API for AI agent use.\n    tools:\n    - name: get-parks\n      description: Retrieve parks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-parks\n\
  \      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n        q: tools.q\n        limit: tools.limit\n        start: tools.start\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: Comma-delimited list of park codes (e.g., acad,dena).\n      - name: stateCode\n        type: string\n        description: Comma-delimited list of two-letter state codes.\n      - name: q\n        type: string\n        description: Free-text search term.\n      - name: limit\n        type: integer\n        description: limit\n      - name: start\n        type: integer\n        description: start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alerts\n      description: Retrieve alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-alerts\n      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n\
  \        q: tools.q\n        limit: tools.limit\n        start: tools.start\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: stateCode\n        type: string\n        description: stateCode\n      - name: q\n        type: string\n        description: q\n      - name: limit\n        type: integer\n        description: limit\n      - name: start\n        type: integer\n        description: start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-newsreleases\n      description: Retrieve news releases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-newsreleases\n      with:\n        parkCode: tools.parkCode\n        q: tools.q\n        limit: tools.limit\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: q\n        type: string\n        description:\
  \ q\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-events\n      description: Retrieve events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-events\n      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n        dateStart: tools.dateStart\n        dateEnd: tools.dateEnd\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: stateCode\n        type: string\n        description: stateCode\n      - name: dateStart\n        type: string\n        description: dateStart\n      - name: dateEnd\n        type: string\n        description: dateEnd\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-places\n      description: Retrieve places\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: national-park-service.get-places\n      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n        q: tools.q\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: stateCode\n        type: string\n        description: stateCode\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-visitorcenters\n      description: Retrieve visitor centers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-visitorcenters\n      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: stateCode\n        type: string\n        description: stateCode\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-campgrounds\n      description: Retrieve campgrounds\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-campgrounds\n      with:\n        parkCode: tools.parkCode\n        stateCode: tools.stateCode\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: stateCode\n        type: string\n        description: stateCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-articles\n      description: Retrieve articles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-articles\n      with:\n        parkCode: tools.parkCode\n        q: tools.q\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: q\n\
  \        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-people\n      description: Retrieve historical people\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-people\n      with:\n        parkCode: tools.parkCode\n        q: tools.q\n      inputParameters:\n      - name: parkCode\n        type: string\n        description: parkCode\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-activities\n      description: List activities available within parks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-activities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-topics\n      description: List topics covered by NPS\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-park-service.get-topics\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NATIONAL_PARK_SERVICE_TOKEN: NATIONAL_PARK_SERVICE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-park-service/refs/heads/main/capabilities/national-park-service-capability.yaml
tags:
- National
- Park
- Service
- API
tools:
- description: Retrieve parks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-parks
- description: Retrieve alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-alerts
- description: Retrieve news releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-newsreleases
- description: Retrieve events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-events
- description: Retrieve places
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-places
- description: Retrieve visitor centers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-visitorcenters
- description: Retrieve campgrounds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-campgrounds
- description: Retrieve articles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-articles
- description: Retrieve historical people
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-people
- description: List activities available within parks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-activities
- description: List topics covered by NPS
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-topics
---
