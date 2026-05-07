---
categories: []
consumed_apis: []
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
- analytics
- real-time train departure boards
- plan a multimodal journey across great britain
- get live bus departures for a stop
- get uk train departures
- get bus live departures
- search uk transport places
- multimodal journey planning
- get uk bus departures
- get uk bus timetable
- get live uk bus departure times for a stop using its atco code
- get scheduled timetable for a bus stop
- get live train departures for a station
- bus
- scheduled bus timetables
- get scheduled uk bus timetable for a stop
- journey planning
- transport stops and access points
- find uk bus stops, train stations, and transport access points by name or location
- uk
- rail
- get bus timetable
- get live uk train departures for a station using its crs code
- real-time bus departure boards
- plan a multimodal journey across great britain by bus, train, or tram
- search places
- public transit
- plan uk journey
- transport
- uk transport
- find transport stops and stations
- real-time
- plan journey
- get train live departures
slug: uk-transport-information
source_filename: uk-transport-information.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TransportAPI UK Transport Information\n  description: Workflow capability for UK public transport data covering real-time bus and rail departures, multimodal journey\n    planning, and transport places lookup. Used by transit app developers, website builders, and data analytics teams working\n    with UK transport data.\n  tags:\n  - Public Transit\n  - UK Transport\n  - Bus\n  - Rail\n  - Journey Planning\n  - Real-Time\n  - Analytics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRANSPORTAPI_APP_ID: TRANSPORTAPI_APP_ID\n    TRANSPORTAPI_APP_KEY: TRANSPORTAPI_APP_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: transportapi\n    baseUri: https://transportapi.com/v3/uk\n    description: UK public transport data API for bus, rail, journey planning, and places.\n    authentication:\n      type: apikey\n      key: X-App-Key\n      value: '{{TRANSPORTAPI_APP_KEY}}'\n      placement:\
  \ header\n    resources:\n    - name: bus-live\n      path: /bus/stop/{atcocode}/live.json\n      description: Real-time bus departure data for a stop\n      operations:\n      - name: get-bus-stop-live-departures\n        method: GET\n        description: Get real-time bus departures for a stop by ATCO code\n        inputParameters:\n        - name: atcocode\n          in: path\n          type: string\n          required: true\n          description: ATCO code of the bus stop\n        - name: group\n          in: query\n          type: string\n          required: false\n          description: Group departures by route\n        - name: nextbuses\n          in: query\n          type: string\n          required: false\n          description: Include real-time predictions\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum departures to return\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: bus-timetable\n      path: /bus/stop/{atcocode}/timetable.json\n      description: Scheduled bus timetable for a stop\n      operations:\n      - name: get-bus-stop-timetable\n        method: GET\n        description: Get scheduled bus timetable for a stop\n        inputParameters:\n        - name: atcocode\n          in: path\n          type: string\n          required: true\n          description: ATCO code of the bus stop\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Date in YYYY-MM-DD format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: train-live\n      path: /train/station/{station_code}/live.json\n      description: Real-time train departure and arrival data\n      operations:\n      - name: get-train-station-live-departures\n        method: GET\n  \
  \      description: Get real-time train departures for a station\n        inputParameters:\n        - name: station_code\n          in: path\n          type: string\n          required: true\n          description: CRS station code\n        - name: train_status\n          in: query\n          type: string\n          required: false\n          description: Filter by train status\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Arrival, departure, or pass\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: places\n      path: /places.json\n      description: Transport stops, stations, and points of interest\n      operations:\n      - name: search-places\n        method: GET\n        description: Search for transport access points by name or location\n        inputParameters:\n        - name: query\n          in: query\n          type:\
  \ string\n          required: false\n          description: Text search query\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by place type\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journey\n      path: /journey/from/{from_coords}/to/{to_coords}.json\n      description: Multimodal journey planning\n      operations:\n      - name: plan-journey\n        method: GET\n        description:\
  \ Plan a multimodal journey across Great Britain\n        inputParameters:\n        - name: from_coords\n          in: path\n          type: string\n          required: true\n          description: Origin as lat,lon or station code\n        - name: to_coords\n          in: path\n          type: string\n          required: true\n          description: Destination as lat,lon or station code\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Journey date YYYY-MM-DD\n        - name: time\n          in: query\n          type: string\n          required: false\n          description: Journey time HH:MM\n        - name: time_is\n          in: query\n          type: string\n          required: false\n          description: Departing or Arriving\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ uk-transport-api\n    description: Unified REST API for UK public transport data and journey planning.\n    resources:\n    - path: /v1/bus-departures\n      name: bus-departures\n      description: Real-time bus departure boards\n      operations:\n      - method: GET\n        name: get-bus-live-departures\n        description: Get live bus departures for a stop\n        call: transportapi.get-bus-stop-live-departures\n        with:\n          atcocode: rest.atcocode\n          group: rest.group\n          nextbuses: rest.nextbuses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bus-timetables\n      name: bus-timetables\n      description: Scheduled bus timetables\n      operations:\n      - method: GET\n        name: get-bus-timetable\n        description: Get scheduled timetable for a bus stop\n        call: transportapi.get-bus-stop-timetable\n        with:\n          atcocode: rest.atcocode\n          date: rest.date\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/train-departures\n      name: train-departures\n      description: Real-time train departure boards\n      operations:\n      - method: GET\n        name: get-train-live-departures\n        description: Get live train departures for a station\n        call: transportapi.get-train-station-live-departures\n        with:\n          station_code: rest.station_code\n          train_status: rest.train_status\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journeys\n      name: journeys\n      description: Multimodal journey planning\n      operations:\n      - method: GET\n        name: plan-journey\n        description: Plan a multimodal journey across Great Britain\n        call: transportapi.plan-journey\n        with:\n          from_coords: rest.from_coords\n          to_coords: rest.to_coords\n          date: rest.date\n          time: rest.time\n      \
  \    time_is: rest.time_is\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/places\n      name: places\n      description: Transport stops and access points\n      operations:\n      - method: GET\n        name: search-places\n        description: Find transport stops and stations\n        call: transportapi.search-places\n        with:\n          query: rest.query\n          lat: rest.lat\n          lon: rest.lon\n          type: rest.type\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: uk-transport-mcp\n    transport: http\n    description: MCP server for AI-assisted UK transport queries and journey planning.\n    tools:\n    - name: get-uk-bus-departures\n      description: Get live UK bus departure times for a stop using its ATCO code\n      hints:\n        readOnly: true\n        openWorld: true\n      call: transportapi.get-bus-stop-live-departures\n\
  \      with:\n        atcocode: tools.atcocode\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-uk-bus-timetable\n      description: Get scheduled UK bus timetable for a stop\n      hints:\n        readOnly: true\n        openWorld: true\n      call: transportapi.get-bus-stop-timetable\n      with:\n        atcocode: tools.atcocode\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-uk-train-departures\n      description: Get live UK train departures for a station using its CRS code\n      hints:\n        readOnly: true\n        openWorld: true\n      call: transportapi.get-train-station-live-departures\n      with:\n        station_code: tools.station_code\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: plan-uk-journey\n      description: Plan a multimodal journey across Great Britain by bus, train, or tram\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: transportapi.plan-journey\n      with:\n        from_coords: tools.from_coords\n        to_coords: tools.to_coords\n        date: tools.date\n        time: tools.time\n        time_is: tools.time_is\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-uk-transport-places\n      description: Find UK bus stops, train stations, and transport access points by name or location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: transportapi.search-places\n      with:\n        query: tools.query\n        lat: tools.lat\n        lon: tools.lon\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
