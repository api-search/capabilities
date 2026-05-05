---
api_specs:
- filename: spacex-api-openapi.yml
  format: yaml
  label: spacex
  slug: spacex
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spacex-api/refs/heads/main/openapi/spacex-api-openapi.yml
categories: []
consumed_apis:
- spacex
description: Workflow capability for tracking SpaceX missions end-to-end — from upcoming launches through vehicle reuse history. Combines launch data, rocket specs, crew assignments, capsule and core reuse, payload manifests, launchpad and landing pad status, fleet vessel locations, and Starlink constellation data.
layout: capability
name: SpaceX Mission Tracking
operations:
- description: List all SpaceX launches (past and upcoming)
  method: GET
  name: list-launches
  path: /v1/launches
- description: Get the most recent SpaceX launch
  method: GET
  name: get-latest-launch
  path: /v1/launches/latest
- description: List all upcoming SpaceX launches
  method: GET
  name: list-upcoming-launches
  path: /v1/launches/upcoming
- description: List all SpaceX rocket vehicles
  method: GET
  name: list-rockets
  path: /v1/rockets
- description: List all Dragon capsules with reuse history
  method: GET
  name: list-capsules
  path: /v1/capsules
- description: List all first-stage booster cores
  method: GET
  name: list-cores
  path: /v1/cores
- description: List all SpaceX crew members
  method: GET
  name: list-crew
  path: /v1/crew
- description: List all SpaceX launch sites and their status
  method: GET
  name: list-launchpads
  path: /v1/launchpads
- description: List all SpaceX landing pads and drone ships
  method: GET
  name: list-landpads
  path: /v1/landing-pads
- description: List all SpaceX payloads
  method: GET
  name: list-payloads
  path: /v1/payloads
- description: List all SpaceX fleet vessels with real-time position
  method: GET
  name: list-ships
  path: /v1/ships
- description: List all Starlink satellites with orbital data
  method: GET
  name: list-starlink
  path: /v1/starlink
- description: Get real-time Roadster orbital tracking data
  method: GET
  name: get-roadster
  path: /v1/roadster
personas: []
provider_name: SpaceX API
provider_slug: spacex-api
search_terms:
- list payloads
- list starlink satellites
- list all starlink satellites with orbital data
- space
- spacex astronaut and crew roster
- list launches
- list all spacex launches (past and upcoming)
- get latest launch
- list all upcoming spacex launches
- spacex rocket vehicle catalog
- spacex launch sites
- list all spacex astronaut crew members with agency affiliations and launch history
- all spacex mission launches
- spacex dragon capsule fleet with reuse history
- list all spacex landing pads and drone ships
- get roadster
- list all first-stage booster cores
- list all first-stage booster cores with landing attempt and success history
- list upcoming launches
- starlink satellite constellation
- mission tracking
- list all spacex payloads
- list all spacex fleet vessels with real-time position
- list starlink
- list all future scheduled spacex launches
- list landpads
- spacex landing pads and drone ships
- get roadster tracking
- list landing pads
- list all spacex launch sites and their status
- list all spacex fleet vessels including drone ships with real-time position data
- spacex
- list launchpads
- list all spacex crew members
- future scheduled spacex launches
- list all spacex launches including past and upcoming missions with full metadata
- list all starlink constellation satellites with orbital parameters
- list all spacex payload manifests with customer, orbit, and mass data
- most recent spacex launch
- list cores
- spacex fleet vessels
- get real-time orbital tracking data for elon musk's tesla roadster in space
- launches
- get the most recent spacex launch with mission details and outcome
- spacex payload manifests
- list all dragon capsules with reuse history
- tesla roadster orbital tracking
- list crew
- list all spacex rocket vehicles
- list ships
- list all spacex launch sites with location and launch statistics
- list all dragon capsules with serial numbers and reuse history
- get the most recent spacex launch
- list all spacex landing pads and autonomous drone ships with success statistics
- aerospace
- spacex booster cores with landing history
- get real-time roadster orbital tracking data
- list rockets
- list capsules
- list all spacex rocket vehicles (falcon 9, falcon heavy, starship) with specifications
slug: mission-tracking
source_filename: mission-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: SpaceX Mission Tracking\n  description: >-\n    Workflow capability for tracking SpaceX missions end-to-end — from upcoming launches\n    through vehicle reuse history. Combines launch data, rocket specs, crew assignments,\n    capsule and core reuse, payload manifests, launchpad and landing pad status, fleet\n    vessel locations, and Starlink constellation data.\n  tags:\n    - Space\n    - Aerospace\n    - Launches\n    - SpaceX\n    - Mission Tracking\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: spacex\n      location: ./shared/spacex-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spacex-mission-api\n      description: Unified REST API for SpaceX mission tracking and fleet data.\n      resources:\n        - path: /v1/launches\n          name: launches\n          description: All SpaceX mission launches\n          operations:\n            - method:\
  \ GET\n              name: list-launches\n              description: List all SpaceX launches (past and upcoming)\n              call: \"spacex.list-launches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/launches/latest\n          name: latest-launch\n          description: Most recent SpaceX launch\n          operations:\n            - method: GET\n              name: get-latest-launch\n              description: Get the most recent SpaceX launch\n              call: \"spacex.get-latest-launch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/launches/upcoming\n          name: upcoming-launches\n          description: Future scheduled SpaceX launches\n          operations:\n            - method: GET\n              name: list-upcoming-launches\n              description: List all upcoming SpaceX launches\n              call: \"spacex.list-upcoming-launches\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rockets\n          name: rockets\n          description: SpaceX rocket vehicle catalog\n          operations:\n            - method: GET\n              name: list-rockets\n              description: List all SpaceX rocket vehicles\n              call: \"spacex.list-rockets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/capsules\n          name: capsules\n          description: SpaceX Dragon capsule fleet with reuse history\n          operations:\n            - method: GET\n              name: list-capsules\n              description: List all Dragon capsules with reuse history\n              call: \"spacex.list-capsules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cores\n          name: cores\n          description:\
  \ SpaceX booster cores with landing history\n          operations:\n            - method: GET\n              name: list-cores\n              description: List all first-stage booster cores\n              call: \"spacex.list-cores\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crew\n          name: crew\n          description: SpaceX astronaut and crew roster\n          operations:\n            - method: GET\n              name: list-crew\n              description: List all SpaceX crew members\n              call: \"spacex.list-crew\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/launchpads\n          name: launchpads\n          description: SpaceX launch sites\n          operations:\n            - method: GET\n              name: list-launchpads\n              description: List all SpaceX launch sites and their status\n              call:\
  \ \"spacex.list-launchpads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/landing-pads\n          name: landing-pads\n          description: SpaceX landing pads and drone ships\n          operations:\n            - method: GET\n              name: list-landpads\n              description: List all SpaceX landing pads and drone ships\n              call: \"spacex.list-landpads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payloads\n          name: payloads\n          description: SpaceX payload manifests\n          operations:\n            - method: GET\n              name: list-payloads\n              description: List all SpaceX payloads\n              call: \"spacex.list-payloads\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ships\n          name: ships\n  \
  \        description: SpaceX fleet vessels\n          operations:\n            - method: GET\n              name: list-ships\n              description: List all SpaceX fleet vessels with real-time position\n              call: \"spacex.list-ships\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/starlink\n          name: starlink\n          description: Starlink satellite constellation\n          operations:\n            - method: GET\n              name: list-starlink\n              description: List all Starlink satellites with orbital data\n              call: \"spacex.list-starlink\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roadster\n          name: roadster\n          description: Tesla Roadster orbital tracking\n          operations:\n            - method: GET\n              name: get-roadster\n              description: Get real-time\
  \ Roadster orbital tracking data\n              call: \"spacex.get-roadster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spacex-mission-mcp\n      transport: http\n      description: MCP server for AI-assisted SpaceX mission tracking and space data research.\n      tools:\n        - name: list-launches\n          description: List all SpaceX launches including past and upcoming missions with full metadata\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spacex.list-launches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-latest-launch\n          description: Get the most recent SpaceX launch with mission details and outcome\n          hints:\n            readOnly: true\n          call: \"spacex.get-latest-launch\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-upcoming-launches\n          description: List all future scheduled SpaceX launches\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spacex.list-upcoming-launches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rockets\n          description: List all SpaceX rocket vehicles (Falcon 9, Falcon Heavy, Starship) with specifications\n          hints:\n            readOnly: true\n          call: \"spacex.list-rockets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-capsules\n          description: List all Dragon capsules with serial numbers and reuse history\n          hints:\n            readOnly: true\n          call: \"spacex.list-capsules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cores\n         \
  \ description: List all first-stage booster cores with landing attempt and success history\n          hints:\n            readOnly: true\n          call: \"spacex.list-cores\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-crew\n          description: List all SpaceX astronaut crew members with agency affiliations and launch history\n          hints:\n            readOnly: true\n          call: \"spacex.list-crew\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-launchpads\n          description: List all SpaceX launch sites with location and launch statistics\n          hints:\n            readOnly: true\n          call: \"spacex.list-launchpads\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-landing-pads\n          description: List all SpaceX landing pads and autonomous drone ships with success statistics\n\
  \          hints:\n            readOnly: true\n          call: \"spacex.list-landpads\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payloads\n          description: List all SpaceX payload manifests with customer, orbit, and mass data\n          hints:\n            readOnly: true\n          call: \"spacex.list-payloads\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ships\n          description: List all SpaceX fleet vessels including drone ships with real-time position data\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spacex.list-ships\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-starlink-satellites\n          description: List all Starlink constellation satellites with orbital parameters\n          hints:\n            readOnly: true\n       \
  \     openWorld: true\n          call: \"spacex.list-starlink\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-roadster-tracking\n          description: Get real-time orbital tracking data for Elon Musk's Tesla Roadster in space\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spacex.get-roadster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spacex-api/refs/heads/main/capabilities/mission-tracking.yaml
tags:
- Space
- Aerospace
- Launches
- SpaceX
- Mission Tracking
tools:
- description: List all SpaceX launches including past and upcoming missions with full metadata
  hints:
    openWorld: true
    readOnly: true
  name: list-launches
- description: Get the most recent SpaceX launch with mission details and outcome
  hints:
    readOnly: true
  name: get-latest-launch
- description: List all future scheduled SpaceX launches
  hints:
    openWorld: true
    readOnly: true
  name: list-upcoming-launches
- description: List all SpaceX rocket vehicles (Falcon 9, Falcon Heavy, Starship) with specifications
  hints:
    readOnly: true
  name: list-rockets
- description: List all Dragon capsules with serial numbers and reuse history
  hints:
    readOnly: true
  name: list-capsules
- description: List all first-stage booster cores with landing attempt and success history
  hints:
    readOnly: true
  name: list-cores
- description: List all SpaceX astronaut crew members with agency affiliations and launch history
  hints:
    readOnly: true
  name: list-crew
- description: List all SpaceX launch sites with location and launch statistics
  hints:
    readOnly: true
  name: list-launchpads
- description: List all SpaceX landing pads and autonomous drone ships with success statistics
  hints:
    readOnly: true
  name: list-landing-pads
- description: List all SpaceX payload manifests with customer, orbit, and mass data
  hints:
    readOnly: true
  name: list-payloads
- description: List all SpaceX fleet vessels including drone ships with real-time position data
  hints:
    openWorld: true
    readOnly: true
  name: list-ships
- description: List all Starlink constellation satellites with orbital parameters
  hints:
    openWorld: true
    readOnly: true
  name: list-starlink-satellites
- description: Get real-time orbital tracking data for Elon Musk's Tesla Roadster in space
  hints:
    openWorld: true
    readOnly: true
  name: get-roadster-tracking
---
