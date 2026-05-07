---
categories: []
consumed_apis: []
description: Workflow capability for tracking space missions combining launch schedules, astronaut data, spacecraft telemetry, space station operations, and space event monitoring from the Launch Library 2 API.
layout: capability
name: TheSpaceDevs Space Mission Tracking
operations:
- description: List upcoming rocket launches.
  method: GET
  name: list-upcoming-launches
  path: /v1/launches/upcoming
- description: List previously completed launches.
  method: GET
  name: list-previous-launches
  path: /v1/launches/previous
- description: Get detailed data for a specific launch.
  method: GET
  name: get-launch
  path: /v1/launches/{id}
- description: List upcoming space events.
  method: GET
  name: list-upcoming-events
  path: /v1/events/upcoming
- description: List astronauts.
  method: GET
  name: list-astronauts
  path: /v1/astronauts
- description: Get data for a specific astronaut.
  method: GET
  name: get-astronaut
  path: /v1/astronauts/{id}
- description: List orbital space stations.
  method: GET
  name: list-space-stations
  path: /v1/space-stations
- description: List space agencies and launch providers.
  method: GET
  name: list-agencies
  path: /v1/agencies
- description: List spacecraft.
  method: GET
  name: list-spacecraft
  path: /v1/spacecraft
- description: List EVAs and spacewalks.
  method: GET
  name: list-spacewalks
  path: /v1/spacewalks
personas: []
provider_name: TheSpaceDevs LL2 API
provider_slug: thespacedevs-ll2-api
search_terms:
- space
- get launch
- list spacecraft.
- list extravehicular activities (evas/spacewalks) with crew, duration, and purpose.
- get comprehensive data for a specific rocket launch including rocket, mission, pad, and crew information.
- get detailed data for a specific launch.
- list upcoming rocket launches worldwide with date, vehicle, mission, and launch site details.
- list space agencies and launch providers with launch statistics.
- rockets
- list spacecraft with configuration, status, and flight history.
- past rocket launches.
- list upcoming space events.
- list astronauts
- list upcoming space events including launches, landings, announcements, and milestones.
- list evas and spacewalks.
- spacewalk records.
- astronauts
- satellites
- list upcoming events
- list upcoming rocket launches.
- space stations.
- individual launch data.
- get data for a specific astronaut.
- launches
- list recently completed rocket launches with outcome and mission data.
- list astronauts.
- individual astronaut data.
- list orbital space stations with status, orbit, and ownership information.
- list orbital space stations.
- get astronaut
- list previous launches
- list astronauts from the global space database with career, agency, and mission data.
- mission tracking
- list previously completed launches.
- list celestial bodies (planets, moons, asteroids) in the database.
- spacecraft
- space stations
- list upcoming launches
- list spacewalks
- space agencies.
- list space agencies and launch providers.
- spacecraft database.
- upcoming rocket launches worldwide.
- upcoming space events.
- get detailed career profile for a specific astronaut including flights and spacewalks.
- list space stations
- list spacecraft
- list celestial bodies
- astronaut database.
- list agencies
slug: launch-tracking
source_filename: launch-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TheSpaceDevs Space Mission Tracking\n  description: Workflow capability for tracking space missions combining launch schedules, astronaut data, spacecraft telemetry,\n    space station operations, and space event monitoring from the Launch Library 2 API.\n  tags:\n  - Space\n  - Launches\n  - Rockets\n  - Astronauts\n  - Spacecraft\n  - Space Stations\n  - Mission Tracking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPACEDEVS_TOKEN: SPACEDEVS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ll2\n    baseUri: https://ll.thespacedevs.com\n    description: TheSpaceDevs Launch Library 2 API v2.3.0.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Token {{SPACEDEVS_TOKEN}}\n      placement: header\n    resources:\n    - name: launches-upcoming\n      path: /2.3.0/launches/upcoming/\n      description: Upcoming rocket launches.\n      operations:\n\
  \      - name: list-upcoming-launches\n        method: GET\n        description: List upcoming rocket launches worldwide.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results (max 100).\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by launch name.\n        - name: mode\n          in: query\n          type: string\n          required: false\n          description: Response detail level (list, normal, detailed).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: launches-previous\n      path: /2.3.0/launches/previous/\n      description: Previous rocket launches.\n      operations:\n\
  \      - name: list-previous-launches\n        method: GET\n        description: List previously completed rocket launches.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: launches\n      path: /2.3.0/launches/\n      description: All rocket launches.\n      operations:\n      - name: list-launches\n        method: GET\n        description: List all rocket launches with filtering.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: offset\n          in: query\n       \
  \   type: integer\n          required: false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: launch-by-id\n      path: /2.3.0/launches/{id}/\n      description: A specific rocket launch.\n      operations:\n      - name: get-launch\n        method: GET\n        description: Get detailed data for a specific launch.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Launch UUID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-upcoming\n      path: /2.3.0/events/upcoming/\n      description: Upcoming space events.\n      operations:\n      - name: list-upcoming-events\n        method: GET\n        description: List upcoming space events (launches, landings, announcements).\n\
  \        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: astronauts\n      path: /2.3.0/astronauts/\n      description: Astronaut database.\n      operations:\n      - name: list-astronauts\n        method: GET\n        description: List astronauts with filtering by status, agency, nationality.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by astronaut name.\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: astronaut-by-id\n      path: /2.3.0/astronauts/{id}/\n      description: Individual astronaut data.\n      operations:\n      - name: get-astronaut\n        method: GET\n        description: Get detailed data for a specific astronaut.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Astronaut ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: space-stations\n      path: /2.3.0/space_stations/\n      description: Space stations database.\n      operations:\n      - name: list-space-stations\n        method: GET\n        description: List space stations with status and ownership data.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agencies\n      path: /2.3.0/agencies/\n      description: Space agencies database.\n      operations:\n      - name: list-agencies\n        method: GET\n        description: List space agencies and launch providers.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by agency name or abbreviation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pads\n      path: /2.3.0/pads/\n      description: Launch pad database.\n      operations:\n      - name: list-pads\n\
  \        method: GET\n        description: List launch pads worldwide.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spacecraft\n      path: /2.3.0/spacecraft/\n      description: Spacecraft database.\n      operations:\n      - name: list-spacecraft\n        method: GET\n        description: List spacecraft with status and configuration data.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: celestial-bodies\n      path: /2.3.0/celestial_bodies/\n      description: Celestial bodies\
  \ database.\n      operations:\n      - name: list-celestial-bodies\n        method: GET\n        description: List celestial bodies (planets, moons, asteroids).\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spacewalks\n      path: /2.3.0/spacewalks/\n      description: Spacewalk (EVA) records.\n      operations:\n      - name: list-spacewalks\n        method: GET\n        description: List extravehicular activities (spacewalks/EVAs).\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: spacedevs-tracking-api\n    description: Unified REST API for space mission tracking using TheSpaceDevs Launch Library 2.\n    resources:\n    - path: /v1/launches/upcoming\n      name: upcoming-launches\n      description: Upcoming rocket launches worldwide.\n      operations:\n      - method: GET\n        name: list-upcoming-launches\n        description: List upcoming rocket launches.\n        call: ll2.list-upcoming-launches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/launches/previous\n      name: previous-launches\n      description: Past rocket launches.\n      operations:\n      - method: GET\n        name: list-previous-launches\n        description: List previously completed launches.\n        call: ll2.list-previous-launches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/launches/{id}\n      name: launch\n      description: Individual launch\
  \ data.\n      operations:\n      - method: GET\n        name: get-launch\n        description: Get detailed data for a specific launch.\n        call: ll2.get-launch\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/upcoming\n      name: upcoming-events\n      description: Upcoming space events.\n      operations:\n      - method: GET\n        name: list-upcoming-events\n        description: List upcoming space events.\n        call: ll2.list-upcoming-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/astronauts\n      name: astronauts\n      description: Astronaut database.\n      operations:\n      - method: GET\n        name: list-astronauts\n        description: List astronauts.\n        call: ll2.list-astronauts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/astronauts/{id}\n      name: astronaut\n      description:\
  \ Individual astronaut data.\n      operations:\n      - method: GET\n        name: get-astronaut\n        description: Get data for a specific astronaut.\n        call: ll2.get-astronaut\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/space-stations\n      name: space-stations\n      description: Space stations.\n      operations:\n      - method: GET\n        name: list-space-stations\n        description: List orbital space stations.\n        call: ll2.list-space-stations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/agencies\n      name: agencies\n      description: Space agencies.\n      operations:\n      - method: GET\n        name: list-agencies\n        description: List space agencies and launch providers.\n        call: ll2.list-agencies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spacecraft\n      name:\
  \ spacecraft\n      description: Spacecraft database.\n      operations:\n      - method: GET\n        name: list-spacecraft\n        description: List spacecraft.\n        call: ll2.list-spacecraft\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spacewalks\n      name: spacewalks\n      description: Spacewalk records.\n      operations:\n      - method: GET\n        name: list-spacewalks\n        description: List EVAs and spacewalks.\n        call: ll2.list-spacewalks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spacedevs-tracking-mcp\n    transport: http\n    description: MCP server for AI-assisted space mission tracking and space news.\n    tools:\n    - name: list-upcoming-launches\n      description: List upcoming rocket launches worldwide with date, vehicle, mission, and launch site details.\n      hints:\n        readOnly: true\n        idempotent: true\n     \
  \ call: ll2.list-upcoming-launches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-previous-launches\n      description: List recently completed rocket launches with outcome and mission data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-previous-launches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-launch\n      description: Get comprehensive data for a specific rocket launch including rocket, mission, pad, and crew information.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.get-launch\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-upcoming-events\n      description: List upcoming space events including launches, landings, announcements, and milestones.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-upcoming-events\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-astronauts\n      description: List astronauts from the global space database with career, agency, and mission data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-astronauts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-astronaut\n      description: Get detailed career profile for a specific astronaut including flights and spacewalks.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.get-astronaut\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-space-stations\n      description: List orbital space stations with status, orbit, and ownership information.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-space-stations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-agencies\n\
  \      description: List space agencies and launch providers with launch statistics.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-agencies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spacecraft\n      description: List spacecraft with configuration, status, and flight history.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-spacecraft\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spacewalks\n      description: List extravehicular activities (EVAs/spacewalks) with crew, duration, and purpose.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ll2.list-spacewalks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-celestial-bodies\n      description: List celestial bodies (planets, moons, asteroids) in the database.\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: ll2.list-celestial-bodies\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thespacedevs-ll2-api/refs/heads/main/capabilities/launch-tracking.yaml
tags:
- Space
- Launches
- Rockets
- Astronauts
- Spacecraft
- Space Stations
- Mission Tracking
tools:
- description: List upcoming rocket launches worldwide with date, vehicle, mission, and launch site details.
  hints:
    idempotent: true
    readOnly: true
  name: list-upcoming-launches
- description: List recently completed rocket launches with outcome and mission data.
  hints:
    idempotent: true
    readOnly: true
  name: list-previous-launches
- description: Get comprehensive data for a specific rocket launch including rocket, mission, pad, and crew information.
  hints:
    idempotent: true
    readOnly: true
  name: get-launch
- description: List upcoming space events including launches, landings, announcements, and milestones.
  hints:
    idempotent: true
    readOnly: true
  name: list-upcoming-events
- description: List astronauts from the global space database with career, agency, and mission data.
  hints:
    idempotent: true
    readOnly: true
  name: list-astronauts
- description: Get detailed career profile for a specific astronaut including flights and spacewalks.
  hints:
    idempotent: true
    readOnly: true
  name: get-astronaut
- description: List orbital space stations with status, orbit, and ownership information.
  hints:
    idempotent: true
    readOnly: true
  name: list-space-stations
- description: List space agencies and launch providers with launch statistics.
  hints:
    idempotent: true
    readOnly: true
  name: list-agencies
- description: List spacecraft with configuration, status, and flight history.
  hints:
    idempotent: true
    readOnly: true
  name: list-spacecraft
- description: List extravehicular activities (EVAs/spacewalks) with crew, duration, and purpose.
  hints:
    idempotent: true
    readOnly: true
  name: list-spacewalks
- description: List celestial bodies (planets, moons, asteroids) in the database.
  hints:
    idempotent: true
    readOnly: true
  name: list-celestial-bodies
---
