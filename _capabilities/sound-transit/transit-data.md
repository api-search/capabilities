---
api_specs:
- filename: sound-transit-onebusaway-openapi.yml
  format: yaml
  label: sound-transit-oba
  slug: sound-transit-oba
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sound-transit/refs/heads/main/openapi/sound-transit-onebusaway-openapi.yml
categories: []
consumed_apis:
- sound-transit-oba
description: Unified capability for accessing Sound Transit real-time and scheduled transit data for the Puget Sound region. Enables transit app developers, trip planners, and data analysts to query routes, stops, real-time arrivals, vehicle positions, and scheduled service for Sound Transit's light rail and bus network.
layout: capability
name: Sound Transit Transit Data
operations:
- description: List all Sound Transit agencies with geographic coverage
  method: GET
  name: list-agencies
  path: /v1/agencies
- description: Find transit stops near a geographic location
  method: GET
  name: list-stops
  path: /v1/stops
- description: Find transit routes near a geographic location
  method: GET
  name: list-routes
  path: /v1/routes
- description: Get real-time arrivals and departures for a transit stop
  method: GET
  name: get-arrivals
  path: /v1/arrivals
- description: Get all currently active vehicles for an agency
  method: GET
  name: list-vehicles
  path: /v1/vehicles
- description: Get the full schedule for a stop on a given day
  method: GET
  name: get-schedule
  path: /v1/schedules
personas: []
provider_name: Sound Transit
provider_slug: sound-transit
search_terms:
- find transit stops near a geographic location
- find transit stops near a geographic location. use for trip planning, finding the nearest bus stop or light rail station.
- list agencies
- public transit
- government
- gtfs
- get all currently active trips for a specific route. use to track live service on a route including schedule adherence.
- find transit routes near a geographic location
- route discovery near a location
- list transit agencies
- real-time arrivals and departures for a stop
- find nearby routes
- routes
- get all currently active vehicles for an agency
- get real time arrivals
- real-time data
- transportation
- list vehicles
- list stops
- find transit routes near a geographic location. use to discover which bus or rail lines serve an area.
- get real-time arrival and departure predictions for a transit stop. returns next arriving buses and trains with predicted times.
- get the complete scheduled timetable for a transit stop on a specific date. use for planning trips in advance.
- public transportation
- get real-time arrivals and departures for a transit stop
- stops
- list active trips
- transit
- get arrivals
- stop discovery near a location
- list all sound transit transit agencies with their geographic coverage areas. use as first step to identify agency ids for subsequent queries.
- get schedule
- find nearby stops
- get the locations of all currently active vehicles for a transit agency. use for real-time vehicle tracking and fleet monitoring.
- real-time
- get the full schedule for a stop on a given day
- list routes
- active vehicle positions
- get stop schedule
- seattle
- list all sound transit agencies with geographic coverage
- stop schedules
- track agency vehicles
- sound transit
- transit agency information and coverage
slug: transit-data
source_filename: transit-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sound Transit Transit Data\"\n  description: >-\n    Unified capability for accessing Sound Transit real-time and scheduled transit\n    data for the Puget Sound region. Enables transit app developers, trip planners,\n    and data analysts to query routes, stops, real-time arrivals, vehicle positions,\n    and scheduled service for Sound Transit's light rail and bus network.\n  tags:\n    - Sound Transit\n    - Transit\n    - GTFS\n    - Real-Time Data\n    - Public Transportation\n    - Routes\n    - Stops\n    - Seattle\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOUND_TRANSIT_API_KEY: SOUND_TRANSIT_API_KEY\n\ncapability:\n  consumes:\n    - import: sound-transit-oba\n      location: ./shared/sound-transit-onebusaway.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sound-transit-api\n      description: \"Unified REST API for Sound Transit transit\
  \ data including real-time arrivals and routes.\"\n      resources:\n        - path: /v1/agencies\n          name: agencies\n          description: Transit agency information and coverage\n          operations:\n            - method: GET\n              name: list-agencies\n              description: List all Sound Transit agencies with geographic coverage\n              call: \"sound-transit-oba.list-agencies-with-coverage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/stops\n          name: stops\n          description: Stop discovery near a location\n          operations:\n            - method: GET\n              name: list-stops\n              description: Find transit stops near a geographic location\n              call: \"sound-transit-oba.list-stops-for-location\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                radius: \"rest.radius\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/routes\n          name: routes\n          description: Route discovery near a location\n          operations:\n            - method: GET\n              name: list-routes\n              description: Find transit routes near a geographic location\n              call: \"sound-transit-oba.list-routes-for-location\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                radius: \"rest.radius\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/arrivals\n          name: arrivals\n          description: Real-time arrivals and departures for a stop\n          operations:\n            - method: GET\n              name: get-arrivals\n              description: Get real-time arrivals and departures for a transit stop\n              call: \"sound-transit-oba.get-arrivals-and-departures-for-stop\"\
  \n              with:\n                id: \"rest.stop_id\"\n                minutesBefore: \"rest.minutes_before\"\n                minutesAfter: \"rest.minutes_after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vehicles\n          name: vehicles\n          description: Active vehicle positions\n          operations:\n            - method: GET\n              name: list-vehicles\n              description: Get all currently active vehicles for an agency\n              call: \"sound-transit-oba.list-vehicles-for-agency\"\n              with:\n                id: \"rest.agency_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schedules\n          name: schedules\n          description: Stop schedules\n          operations:\n            - method: GET\n              name: get-schedule\n              description: Get the full schedule\
  \ for a stop on a given day\n              call: \"sound-transit-oba.get-schedule-for-stop\"\n              with:\n                id: \"rest.stop_id\"\n                date: \"rest.date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sound-transit-mcp\n      transport: http\n      description: \"MCP server for AI-assisted transit trip planning using Sound Transit data.\"\n      tools:\n        - name: list-transit-agencies\n          description: >-\n            List all Sound Transit transit agencies with their geographic coverage areas.\n            Use as first step to identify agency IDs for subsequent queries.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.list-agencies-with-coverage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-nearby-stops\n\
  \          description: >-\n            Find transit stops near a geographic location. Use for trip planning,\n            finding the nearest bus stop or light rail station.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.list-stops-for-location\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            radius: \"tools.radius\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-nearby-routes\n          description: >-\n            Find transit routes near a geographic location. Use to discover which\n            bus or rail lines serve an area.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.list-routes-for-location\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            radius: \"tools.radius\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-real-time-arrivals\n          description: >-\n            Get real-time arrival and departure predictions for a transit stop.\n            Returns next arriving buses and trains with predicted times.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.get-arrivals-and-departures-for-stop\"\n          with:\n            id: \"tools.stop_id\"\n            minutesBefore: \"tools.minutes_before\"\n            minutesAfter: \"tools.minutes_after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-stop-schedule\n          description: >-\n            Get the complete scheduled timetable for a transit stop on a specific date.\n            Use for planning trips in advance.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.get-schedule-for-stop\"\
  \n          with:\n            id: \"tools.stop_id\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-active-trips\n          description: >-\n            Get all currently active trips for a specific route. Use to track\n            live service on a route including schedule adherence.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sound-transit-oba.list-trips-for-route\"\n          with:\n            id: \"tools.route_id\"\n            includeStatus: \"tools.include_status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-agency-vehicles\n          description: >-\n            Get the locations of all currently active vehicles for a transit agency.\n            Use for real-time vehicle tracking and fleet monitoring.\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"sound-transit-oba.list-vehicles-for-agency\"\n          with:\n            id: \"tools.agency_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sound-transit/refs/heads/main/capabilities/transit-data.yaml
tags:
- Sound Transit
- Transit
- GTFS
- Real-Time Data
- Public Transportation
- Routes
- Stops
- Seattle
tools:
- description: List all Sound Transit transit agencies with their geographic coverage areas. Use as first step to identify agency IDs for subsequent queries.
  hints:
    openWorld: true
    readOnly: true
  name: list-transit-agencies
- description: Find transit stops near a geographic location. Use for trip planning, finding the nearest bus stop or light rail station.
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-stops
- description: Find transit routes near a geographic location. Use to discover which bus or rail lines serve an area.
  hints:
    openWorld: true
    readOnly: true
  name: find-nearby-routes
- description: Get real-time arrival and departure predictions for a transit stop. Returns next arriving buses and trains with predicted times.
  hints:
    openWorld: true
    readOnly: true
  name: get-real-time-arrivals
- description: Get the complete scheduled timetable for a transit stop on a specific date. Use for planning trips in advance.
  hints:
    openWorld: true
    readOnly: true
  name: get-stop-schedule
- description: Get all currently active trips for a specific route. Use to track live service on a route including schedule adherence.
  hints:
    openWorld: true
    readOnly: true
  name: list-active-trips
- description: Get the locations of all currently active vehicles for a transit agency. Use for real-time vehicle tracking and fleet monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: track-agency-vehicles
---
