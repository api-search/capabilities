---
categories: []
consumed_apis:
- ll2
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
- list agencies
- space agencies.
- list astronauts.
- get data for a specific astronaut.
- list celestial bodies (planets, moons, asteroids) in the database.
- get astronaut
- space stations.
- list recently completed rocket launches with outcome and mission data.
- list upcoming launches
- mission tracking
- list astronauts
- list celestial bodies
- individual launch data.
- astronaut database.
- list evas and spacewalks.
- rockets
- upcoming rocket launches worldwide.
- past rocket launches.
- list astronauts from the global space database with career, agency, and mission data.
- list previously completed launches.
- list upcoming space events including launches, landings, announcements, and milestones.
- list orbital space stations with status, orbit, and ownership information.
- list space agencies and launch providers.
- launches
- list upcoming events
- list space agencies and launch providers with launch statistics.
- spacecraft database.
- spacecraft
- list spacecraft.
- list spacecraft with configuration, status, and flight history.
- list spacecraft
- satellites
- get detailed data for a specific launch.
- upcoming space events.
- list orbital space stations.
- spacewalk records.
- list spacewalks
- list extravehicular activities (evas/spacewalks) with crew, duration, and purpose.
- get detailed career profile for a specific astronaut including flights and spacewalks.
- get comprehensive data for a specific rocket launch including rocket, mission, pad, and crew information.
- list space stations
- list previous launches
- space stations
- list upcoming rocket launches worldwide with date, vehicle, mission, and launch site details.
- astronauts
- individual astronaut data.
- get launch
- list upcoming space events.
- list upcoming rocket launches.
slug: launch-tracking
source_filename: launch-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TheSpaceDevs Space Mission Tracking\"\n  description: \"Workflow capability for tracking space missions combining launch schedules, astronaut data, spacecraft telemetry, space station operations, and space event monitoring from the Launch Library 2 API.\"\n  tags:\n    - Space\n    - Launches\n    - Rockets\n    - Astronauts\n    - Spacecraft\n    - Space Stations\n    - Mission Tracking\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPACEDEVS_TOKEN: SPACEDEVS_TOKEN\n\ncapability:\n  consumes:\n    - import: ll2\n      location: ./shared/ll2-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spacedevs-tracking-api\n      description: \"Unified REST API for space mission tracking using TheSpaceDevs Launch Library 2.\"\n      resources:\n        - path: /v1/launches/upcoming\n          name: upcoming-launches\n          description: \"Upcoming rocket\
  \ launches worldwide.\"\n          operations:\n            - method: GET\n              name: list-upcoming-launches\n              description: \"List upcoming rocket launches.\"\n              call: \"ll2.list-upcoming-launches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/launches/previous\n          name: previous-launches\n          description: \"Past rocket launches.\"\n          operations:\n            - method: GET\n              name: list-previous-launches\n              description: \"List previously completed launches.\"\n              call: \"ll2.list-previous-launches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/launches/{id}\n          name: launch\n          description: \"Individual launch data.\"\n          operations:\n            - method: GET\n              name: get-launch\n              description: \"Get\
  \ detailed data for a specific launch.\"\n              call: \"ll2.get-launch\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/upcoming\n          name: upcoming-events\n          description: \"Upcoming space events.\"\n          operations:\n            - method: GET\n              name: list-upcoming-events\n              description: \"List upcoming space events.\"\n              call: \"ll2.list-upcoming-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/astronauts\n          name: astronauts\n          description: \"Astronaut database.\"\n          operations:\n            - method: GET\n              name: list-astronauts\n              description: \"List astronauts.\"\n              call: \"ll2.list-astronauts\"\n              outputParameters:\n              \
  \  - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/astronauts/{id}\n          name: astronaut\n          description: \"Individual astronaut data.\"\n          operations:\n            - method: GET\n              name: get-astronaut\n              description: \"Get data for a specific astronaut.\"\n              call: \"ll2.get-astronaut\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/space-stations\n          name: space-stations\n          description: \"Space stations.\"\n          operations:\n            - method: GET\n              name: list-space-stations\n              description: \"List orbital space stations.\"\n              call: \"ll2.list-space-stations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/agencies\n          name: agencies\n  \
  \        description: \"Space agencies.\"\n          operations:\n            - method: GET\n              name: list-agencies\n              description: \"List space agencies and launch providers.\"\n              call: \"ll2.list-agencies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/spacecraft\n          name: spacecraft\n          description: \"Spacecraft database.\"\n          operations:\n            - method: GET\n              name: list-spacecraft\n              description: \"List spacecraft.\"\n              call: \"ll2.list-spacecraft\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/spacewalks\n          name: spacewalks\n          description: \"Spacewalk records.\"\n          operations:\n            - method: GET\n              name: list-spacewalks\n              description: \"List EVAs and spacewalks.\"\n        \
  \      call: \"ll2.list-spacewalks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spacedevs-tracking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted space mission tracking and space news.\"\n      tools:\n        - name: list-upcoming-launches\n          description: \"List upcoming rocket launches worldwide with date, vehicle, mission, and launch site details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-upcoming-launches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-previous-launches\n          description: \"List recently completed rocket launches with outcome and mission data.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-previous-launches\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-launch\n          description: \"Get comprehensive data for a specific rocket launch including rocket, mission, pad, and crew information.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.get-launch\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-upcoming-events\n          description: \"List upcoming space events including launches, landings, announcements, and milestones.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-upcoming-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-astronauts\n          description: \"List astronauts from the global space database with career, agency, and mission data.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"ll2.list-astronauts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-astronaut\n          description: \"Get detailed career profile for a specific astronaut including flights and spacewalks.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.get-astronaut\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-space-stations\n          description: \"List orbital space stations with status, orbit, and ownership information.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-space-stations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-agencies\n          description: \"List\
  \ space agencies and launch providers with launch statistics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-agencies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-spacecraft\n          description: \"List spacecraft with configuration, status, and flight history.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-spacecraft\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-spacewalks\n          description: \"List extravehicular activities (EVAs/spacewalks) with crew, duration, and purpose.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-spacewalks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-celestial-bodies\n       \
  \   description: \"List celestial bodies (planets, moons, asteroids) in the database.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ll2.list-celestial-bodies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
