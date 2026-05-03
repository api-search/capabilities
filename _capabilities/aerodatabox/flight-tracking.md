---
categories:
- travel-booking
consumed_apis:
- flight
- aircraft
- airport
description: 'Unified capability for real-time aviation intelligence combining flight status, aircraft data, and airport information. Enables developers and travel platforms to build comprehensive flight tracking, airport operations monitoring, and aircraft research applications. Primary persona: Developer or Travel Platform Engineer.'
layout: capability
name: AeroDataBox Flight Tracking
operations:
- description: Track a flight by number.
  method: GET
  name: get-flight-status
  path: /v1/flights/{searchBy}/{searchParam}
- description: Get airport departures and arrivals.
  method: GET
  name: get-airport-fids
  path: /v1/airports/{codeType}/{code}/flights
- description: Retrieve airport details.
  method: GET
  name: get-airport
  path: /v1/airports/{codeType}/{code}
- description: Find nearby airports.
  method: GET
  name: search-airports
  path: /v1/airports/search/location
- description: Look up an aircraft.
  method: GET
  name: get-aircraft
  path: /v1/aircrafts/{searchBy}/{searchParam}
- description: Get fleet for an airline.
  method: GET
  name: get-airline-fleet
  path: /v1/airlines/{airlineCode}/aircrafts
personas: []
provider_name: AeroDataBox
provider_slug: aerodatabox
search_terms:
- search airports
- look up an aircraft.
- get flight status
- aircraft registrations, fleet composition, and aircraft imagery.
- delay statistics, route performance, and trend analysis.
- travel
- track a flight by number.
- find nearby airports.
- get all departures and arrivals at an airport for a time window.
- track a flight in real-time by flight number or callsign.
- airport data
- get aircraft
- real-time and historical flight tracking, status monitoring, and fids data.
- airport information, runway data, and location search.
- find airports near a geographic location.
- get airline fleet.
- get fleet for an airline.
- analyzes aviation performance, delay patterns, and route statistics using historical data.
- retrieve airport details.
- get all aircraft in an airline's fleet.
- aviation
- look up aircraft details by tail number or icao24 hex code.
- flight tracking
- get aircraft data.
- get details for an airport by iata or icao code.
- aerospace
- get airport information.
- unified capability combining flight status, aircraft data, and airport information for real-time aviation intelligence.
- builds flight tracking, travel, and aviation applications using aerodatabox apis.
- get flight status data.
- flights
- get airport departures and arrivals.
- aerodatabox
- get airport departures arrivals
- airport operations
- get airport fids
- get fids for an airport.
- get airline fleet
- get airport
- flight data
- search airports by location.
- integrates flight data into travel booking and notification systems.
- search airports near location
slug: flight-tracking
source_filename: flight-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AeroDataBox Flight Tracking\"\n  description: \"Unified capability for real-time aviation intelligence combining flight status, aircraft data, and airport information. Enables developers and travel platforms to build comprehensive flight tracking, airport operations monitoring, and aircraft research applications. Primary persona: Developer or Travel Platform Engineer.\"\n  tags:\n    - AeroDataBox\n    - Aviation\n    - Flight Tracking\n    - Travel\n    - Airport Operations\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AERODATABOX_API_KEY: AERODATABOX_API_KEY\n\ncapability:\n  consumes:\n    - import: flight\n      location: ./shared/flight.yaml\n    - import: aircraft\n      location: ./shared/aircraft.yaml\n    - import: airport\n      location: ./shared/airport.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aerodatabox-flight-tracking-api\n \
  \     description: \"Unified REST API for AeroDataBox aviation data.\"\n      resources:\n        - path: /v1/flights/{searchBy}/{searchParam}\n          name: flight-status\n          description: \"Get flight status data.\"\n          operations:\n            - method: GET\n              name: get-flight-status\n              description: \"Track a flight by number.\"\n              call: \"flight.get-flight-status\"\n              with:\n                searchBy: \"rest.searchBy\"\n                searchParam: \"rest.searchParam\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/airports/{codeType}/{code}/flights\n          name: airport-fids\n          description: \"Get FIDS for an airport.\"\n          operations:\n            - method: GET\n              name: get-airport-fids\n              description: \"Get airport departures and arrivals.\"\n              call: \"flight.get-airport-fids\"\n             \
  \ with:\n                codeType: \"rest.codeType\"\n                code: \"rest.code\"\n                fromLocal: \"rest.fromLocal\"\n                toLocal: \"rest.toLocal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/airports/{codeType}/{code}\n          name: airport\n          description: \"Get airport information.\"\n          operations:\n            - method: GET\n              name: get-airport\n              description: \"Retrieve airport details.\"\n              call: \"airport.get-airport\"\n              with:\n                codeType: \"rest.codeType\"\n                code: \"rest.code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/airports/search/location\n          name: airport-search\n          description: \"Search airports by location.\"\n          operations:\n            - method: GET\n              name:\
  \ search-airports\n              description: \"Find nearby airports.\"\n              call: \"airport.search-airports-by-location\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/aircrafts/{searchBy}/{searchParam}\n          name: aircraft\n          description: \"Get aircraft data.\"\n          operations:\n            - method: GET\n              name: get-aircraft\n              description: \"Look up an aircraft.\"\n              call: \"aircraft.get-aircraft\"\n              with:\n                searchBy: \"rest.searchBy\"\n                searchParam: \"rest.searchParam\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/airlines/{airlineCode}/aircrafts\n          name: airline-fleet\n          description: \"Get airline fleet.\"\n          operations:\n\
  \            - method: GET\n              name: get-airline-fleet\n              description: \"Get fleet for an airline.\"\n              call: \"aircraft.get-airline-fleet\"\n              with:\n                airlineCode: \"rest.airlineCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: aerodatabox-flight-tracking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted aviation data queries using AeroDataBox.\"\n      tools:\n        - name: get-flight-status\n          description: \"Track a flight in real-time by flight number or callsign.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight.get-flight-status\"\n          with:\n            searchBy: \"tools.searchBy\"\n            searchParam: \"tools.searchParam\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: get-airport-departures-arrivals\n          description: \"Get all departures and arrivals at an airport for a time window.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flight.get-airport-fids\"\n          with:\n            codeType: \"tools.codeType\"\n            code: \"tools.code\"\n            fromLocal: \"tools.fromLocal\"\n            toLocal: \"tools.toLocal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-airport\n          description: \"Get details for an airport by IATA or ICAO code.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airport.get-airport\"\n          with:\n            codeType: \"tools.codeType\"\n            code: \"tools.code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-airports-near-location\n          description:\
  \ \"Find airports near a geographic location.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airport.search-airports-by-location\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-aircraft\n          description: \"Look up aircraft details by tail number or ICAO24 hex code.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aircraft.get-aircraft\"\n          with:\n            searchBy: \"tools.searchBy\"\n            searchParam: \"tools.searchParam\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-airline-fleet\n          description: \"Get all aircraft in an airline's fleet.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aircraft.get-airline-fleet\"\
  \n          with:\n            airlineCode: \"tools.airlineCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aerodatabox/refs/heads/main/capabilities/flight-tracking.yaml
tags:
- AeroDataBox
- Aviation
- Flight Tracking
- Travel
- Airport Operations
tools:
- description: Track a flight in real-time by flight number or callsign.
  hints:
    openWorld: true
    readOnly: true
  name: get-flight-status
- description: Get all departures and arrivals at an airport for a time window.
  hints:
    openWorld: true
    readOnly: true
  name: get-airport-departures-arrivals
- description: Get details for an airport by IATA or ICAO code.
  hints:
    openWorld: true
    readOnly: true
  name: get-airport
- description: Find airports near a geographic location.
  hints:
    openWorld: true
    readOnly: true
  name: search-airports-near-location
- description: Look up aircraft details by tail number or ICAO24 hex code.
  hints:
    openWorld: true
    readOnly: true
  name: get-aircraft
- description: Get all aircraft in an airline's fleet.
  hints:
    openWorld: true
    readOnly: true
  name: get-airline-fleet
---
