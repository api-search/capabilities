---
api_specs:
- filename: transportapi-openapi.yml
  format: yaml
  label: transportapi
  slug: transportapi
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/transportapi/refs/heads/main/openapi/transportapi-openapi.yml
categories: []
consumed_apis:
- transportapi
description: Workflow capability for UK public transport data covering real-time bus and rail departures, multimodal journey planning, and transport places lookup. Used by transit app developers, website builders, and data analytics teams working with UK transport data.
layout: capability
name: TransportAPI UK Transport Information
operations:
- description: Get live bus departures for a stop
  method: GET
  name: get-bus-live-departures
  path: /v1/bus-departures
- description: Get scheduled timetable for a bus stop
  method: GET
  name: get-bus-timetable
  path: /v1/bus-timetables
- description: Get live train departures for a station
  method: GET
  name: get-train-live-departures
  path: /v1/train-departures
- description: Plan a multimodal journey across Great Britain
  method: GET
  name: plan-journey
  path: /v1/journeys
- description: Find transport stops and stations
  method: GET
  name: search-places
  path: /v1/places
personas: []
provider_name: TransportAPI
provider_slug: transportapi
search_terms:
- get live bus departures for a stop
- find uk bus stops, train stations, and transport access points by name or location
- multimodal journey planning
- plan uk journey
- analytics
- search places
- search uk transport places
- get uk bus timetable
- transport
- plan a multimodal journey across great britain by bus, train, or tram
- real-time train departure boards
- bus
- get train live departures
- get live train departures for a station
- transport stops and access points
- get uk bus departures
- get scheduled uk bus timetable for a stop
- get scheduled timetable for a bus stop
- get live uk train departures for a station using its crs code
- get bus live departures
- get live uk bus departure times for a stop using its atco code
- get uk train departures
- plan journey
- get bus timetable
- real-time bus departure boards
- plan a multimodal journey across great britain
- journey planning
- rail
- real-time
- uk transport
- public transit
- find transport stops and stations
- uk
- scheduled bus timetables
slug: uk-transport-information
source_filename: uk-transport-information.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TransportAPI UK Transport Information\"\n  description: >-\n    Workflow capability for UK public transport data covering real-time bus\n    and rail departures, multimodal journey planning, and transport places\n    lookup. Used by transit app developers, website builders, and data\n    analytics teams working with UK transport data.\n  tags:\n    - Public Transit\n    - UK Transport\n    - Bus\n    - Rail\n    - Journey Planning\n    - Real-Time\n    - Analytics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRANSPORTAPI_APP_ID: TRANSPORTAPI_APP_ID\n      TRANSPORTAPI_APP_KEY: TRANSPORTAPI_APP_KEY\n\ncapability:\n  consumes:\n    - import: transportapi\n      location: ./shared/transportapi.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: uk-transport-api\n      description: \"Unified REST API for UK public transport data and journey planning.\"\n\
  \      resources:\n        - path: /v1/bus-departures\n          name: bus-departures\n          description: \"Real-time bus departure boards\"\n          operations:\n            - method: GET\n              name: get-bus-live-departures\n              description: \"Get live bus departures for a stop\"\n              call: \"transportapi.get-bus-stop-live-departures\"\n              with:\n                atcocode: \"rest.atcocode\"\n                group: \"rest.group\"\n                nextbuses: \"rest.nextbuses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bus-timetables\n          name: bus-timetables\n          description: \"Scheduled bus timetables\"\n          operations:\n            - method: GET\n              name: get-bus-timetable\n              description: \"Get scheduled timetable for a bus stop\"\n              call: \"transportapi.get-bus-stop-timetable\"\n              with:\n       \
  \         atcocode: \"rest.atcocode\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/train-departures\n          name: train-departures\n          description: \"Real-time train departure boards\"\n          operations:\n            - method: GET\n              name: get-train-live-departures\n              description: \"Get live train departures for a station\"\n              call: \"transportapi.get-train-station-live-departures\"\n              with:\n                station_code: \"rest.station_code\"\n                train_status: \"rest.train_status\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/journeys\n          name: journeys\n          description: \"Multimodal journey planning\"\n          operations:\n            - method: GET\n              name:\
  \ plan-journey\n              description: \"Plan a multimodal journey across Great Britain\"\n              call: \"transportapi.plan-journey\"\n              with:\n                from_coords: \"rest.from_coords\"\n                to_coords: \"rest.to_coords\"\n                date: \"rest.date\"\n                time: \"rest.time\"\n                time_is: \"rest.time_is\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/places\n          name: places\n          description: \"Transport stops and access points\"\n          operations:\n            - method: GET\n              name: search-places\n              description: \"Find transport stops and stations\"\n              call: \"transportapi.search-places\"\n              with:\n                query: \"rest.query\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                type: \"rest.type\"\n                radius: \"rest.radius\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: uk-transport-mcp\n      transport: http\n      description: \"MCP server for AI-assisted UK transport queries and journey planning.\"\n      tools:\n        - name: get-uk-bus-departures\n          description: \"Get live UK bus departure times for a stop using its ATCO code\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"transportapi.get-bus-stop-live-departures\"\n          with:\n            atcocode: \"tools.atcocode\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-uk-bus-timetable\n          description: \"Get scheduled UK bus timetable for a stop\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"transportapi.get-bus-stop-timetable\"\n \
  \         with:\n            atcocode: \"tools.atcocode\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-uk-train-departures\n          description: \"Get live UK train departures for a station using its CRS code\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"transportapi.get-train-station-live-departures\"\n          with:\n            station_code: \"tools.station_code\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: plan-uk-journey\n          description: \"Plan a multimodal journey across Great Britain by bus, train, or tram\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"transportapi.plan-journey\"\n          with:\n            from_coords: \"tools.from_coords\"\n            to_coords: \"tools.to_coords\"\
  \n            date: \"tools.date\"\n            time: \"tools.time\"\n            time_is: \"tools.time_is\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-uk-transport-places\n          description: \"Find UK bus stops, train stations, and transport access points by name or location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"transportapi.search-places\"\n          with:\n            query: \"tools.query\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/transportapi/refs/heads/main/capabilities/uk-transport-information.yaml
tags:
- Public Transit
- UK Transport
- Bus
- Rail
- Journey Planning
- Real-Time
- Analytics
tools:
- description: Get live UK bus departure times for a stop using its ATCO code
  hints:
    openWorld: true
    readOnly: true
  name: get-uk-bus-departures
- description: Get scheduled UK bus timetable for a stop
  hints:
    openWorld: true
    readOnly: true
  name: get-uk-bus-timetable
- description: Get live UK train departures for a station using its CRS code
  hints:
    openWorld: true
    readOnly: true
  name: get-uk-train-departures
- description: Plan a multimodal journey across Great Britain by bus, train, or tram
  hints:
    openWorld: true
    readOnly: true
  name: plan-uk-journey
- description: Find UK bus stops, train stations, and transport access points by name or location
  hints:
    openWorld: true
    readOnly: true
  name: search-uk-transport-places
---
