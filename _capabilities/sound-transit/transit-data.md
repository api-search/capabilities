---
categories: []
consumed_apis: []
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
- get real time arrivals
- get all currently active trips for a specific route. use to track live service on a route including schedule adherence.
- get all currently active vehicles for an agency
- active vehicle positions
- sound transit
- list all sound transit transit agencies with their geographic coverage areas. use as first step to identify agency ids for subsequent queries.
- gtfs
- find nearby routes
- public transportation
- list active trips
- real-time arrivals and departures for a stop
- stop discovery near a location
- list vehicles
- routes
- list transit agencies
- list routes
- transportation
- get the complete scheduled timetable for a transit stop on a specific date. use for planning trips in advance.
- route discovery near a location
- stop schedules
- stops
- government
- list all sound transit agencies with geographic coverage
- find nearby stops
- real-time data
- list stops
- public transit
- find transit routes near a geographic location. use to discover which bus or rail lines serve an area.
- get real-time arrival and departure predictions for a transit stop. returns next arriving buses and trains with predicted times.
- seattle
- find transit routes near a geographic location
- get arrivals
- get the full schedule for a stop on a given day
- get schedule
- get stop schedule
- get the locations of all currently active vehicles for a transit agency. use for real-time vehicle tracking and fleet monitoring.
- get real-time arrivals and departures for a transit stop
- transit
- find transit stops near a geographic location
- real-time
- find transit stops near a geographic location. use for trip planning, finding the nearest bus stop or light rail station.
- transit agency information and coverage
- track agency vehicles
- list agencies
slug: transit-data
source_filename: transit-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sound Transit Transit Data\n  description: Unified capability for accessing Sound Transit real-time and scheduled transit data for the Puget Sound region.\n    Enables transit app developers, trip planners, and data analysts to query routes, stops, real-time arrivals, vehicle positions,\n    and scheduled service for Sound Transit's light rail and bus network.\n  tags:\n  - Sound Transit\n  - Transit\n  - GTFS\n  - Real-Time Data\n  - Public Transportation\n  - Routes\n  - Stops\n  - Seattle\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SOUND_TRANSIT_API_KEY: SOUND_TRANSIT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sound-transit-oba\n    baseUri: https://api.pugetsound.onebusaway.org/api/where\n    description: Sound Transit OneBusAway API for real-time transit data\n    resources:\n    - name: agencies\n      path: /agencies-with-coverage.json\n      description: Transit\
  \ agency coverage information\n      operations:\n      - name: list-agencies-with-coverage\n        method: GET\n        description: List all supported transit agencies with geographic coverage areas\n        inputParameters:\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agency\n      path: /agency/{id}.json\n      description: Agency details\n      operations:\n      - name: get-agency\n        method: GET\n        description: Get details for a specific transit agency\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Agency identifier\n        - name: key\n          in: query\n          type: string\n          required: true\n          description: API key\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes-for-location\n      path: /routes-for-location.json\n      description: Routes near a location\n      operations:\n      - name: list-routes-for-location\n        method: GET\n        description: Search for transit routes near a geographic location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: stops-for-location\n      path: /stops-for-location.json\n      description: Stops near a location\n      operations:\n      - name: list-stops-for-location\n        method: GET\n        description: Find transit stops near a geographic location\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude\n        - name: lon\n          in: query\n          type: number\n          required: true\n          description: Longitude\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: arrivals-and-departures\n      path: /arrivals-and-departures-for-stop/{id}.json\n\
  \      description: Real-time arrivals and departures for a stop\n      operations:\n      - name: get-arrivals-and-departures-for-stop\n        method: GET\n        description: Get current real-time arrivals and departures for a transit stop\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Stop identifier\n        - name: minutesBefore\n          in: query\n          type: integer\n          required: false\n          description: Minutes before now to include\n        - name: minutesAfter\n          in: query\n          type: integer\n          required: false\n          description: Minutes after now to include\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trips-for-route\n      path: /trips-for-route/{id}.json\n\
  \      description: Active trips for a route\n      operations:\n      - name: list-trips-for-route\n        method: GET\n        description: Get all currently active trips for a specific route\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Route identifier\n        - name: includeStatus\n          in: query\n          type: boolean\n          required: false\n          description: Include real-time status information\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles-for-agency\n      path: /vehicles-for-agency/{id}.json\n      description: Active vehicles for an agency\n      operations:\n      - name: list-vehicles-for-agency\n        method: GET\n        description: Get all currently active vehicles for\
  \ a transit agency\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Agency identifier\n        - name: key\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedule-for-stop\n      path: /schedule-for-stop/{id}.json\n      description: Full schedule for a stop\n      operations:\n      - name: get-schedule-for-stop\n        method: GET\n        description: Get the full schedule for a stop on a particular day\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Stop identifier\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Service date (YYYY-MM-DD)\n        - name: key\n          in:\
  \ query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sound-transit-api\n    description: Unified REST API for Sound Transit transit data including real-time arrivals and routes.\n    resources:\n    - path: /v1/agencies\n      name: agencies\n      description: Transit agency information and coverage\n      operations:\n      - method: GET\n        name: list-agencies\n        description: List all Sound Transit agencies with geographic coverage\n        call: sound-transit-oba.list-agencies-with-coverage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stops\n      name: stops\n      description: Stop discovery near a location\n      operations:\n      - method: GET\n        name: list-stops\n        description: Find transit stops near a geographic location\n\
  \        call: sound-transit-oba.list-stops-for-location\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Route discovery near a location\n      operations:\n      - method: GET\n        name: list-routes\n        description: Find transit routes near a geographic location\n        call: sound-transit-oba.list-routes-for-location\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/arrivals\n      name: arrivals\n      description: Real-time arrivals and departures for a stop\n      operations:\n      - method: GET\n        name: get-arrivals\n        description: Get real-time arrivals and departures for a transit stop\n        call: sound-transit-oba.get-arrivals-and-departures-for-stop\n\
  \        with:\n          id: rest.stop_id\n          minutesBefore: rest.minutes_before\n          minutesAfter: rest.minutes_after\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles\n      name: vehicles\n      description: Active vehicle positions\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: Get all currently active vehicles for an agency\n        call: sound-transit-oba.list-vehicles-for-agency\n        with:\n          id: rest.agency_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schedules\n      name: schedules\n      description: Stop schedules\n      operations:\n      - method: GET\n        name: get-schedule\n        description: Get the full schedule for a stop on a given day\n        call: sound-transit-oba.get-schedule-for-stop\n        with:\n          id: rest.stop_id\n          date: rest.date\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sound-transit-mcp\n    transport: http\n    description: MCP server for AI-assisted transit trip planning using Sound Transit data.\n    tools:\n    - name: list-transit-agencies\n      description: List all Sound Transit transit agencies with their geographic coverage areas. Use as first step to identify\n        agency IDs for subsequent queries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.list-agencies-with-coverage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-stops\n      description: Find transit stops near a geographic location. Use for trip planning, finding the nearest bus stop or light\n        rail station.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.list-stops-for-location\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        radius:\
  \ tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-nearby-routes\n      description: Find transit routes near a geographic location. Use to discover which bus or rail lines serve an area.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.list-routes-for-location\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        radius: tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-real-time-arrivals\n      description: Get real-time arrival and departure predictions for a transit stop. Returns next arriving buses and trains\n        with predicted times.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.get-arrivals-and-departures-for-stop\n      with:\n        id: tools.stop_id\n        minutesBefore: tools.minutes_before\n        minutesAfter: tools.minutes_after\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: get-stop-schedule\n      description: Get the complete scheduled timetable for a transit stop on a specific date. Use for planning trips in advance.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.get-schedule-for-stop\n      with:\n        id: tools.stop_id\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-trips\n      description: Get all currently active trips for a specific route. Use to track live service on a route including schedule\n        adherence.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.list-trips-for-route\n      with:\n        id: tools.route_id\n        includeStatus: tools.include_status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-agency-vehicles\n      description: Get the locations of all currently active vehicles\
  \ for a transit agency. Use for real-time vehicle tracking\n        and fleet monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sound-transit-oba.list-vehicles-for-agency\n      with:\n        id: tools.agency_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
