---
categories: []
consumed_apis:
- aeroapi
description: Unified workflow capability for aviation flight operations using FlightAware AeroAPI. Enables airlines, ground handlers, flight departments, and technology providers to track flights in real-time, monitor airport conditions, manage flight alerts, analyze operator fleet activity, and access historical flight data for operational planning, resource management, and maintenance scheduling.
layout: capability
name: Collins Aerospace Flight Operations
operations:
- description: Search for airborne flights by criteria including location, airline, and aircraft type
  method: GET
  name: search-flights
  path: /v1/flights
- description: Get detailed information for a specific flight
  method: GET
  name: get-flight
  path: /v1/flights/{ident}
- description: Get current real-time position for a flight
  method: GET
  name: get-flight-position
  path: /v1/flight-positions/{fa_flight_id}
- description: Get position track of a flight
  method: GET
  name: get-flight-track
  path: /v1/flight-tracks/{fa_flight_id}
- description: Get a list of all airports
  method: GET
  name: list-airports
  path: /v1/airports
- description: Get static information about an airport
  method: GET
  name: get-airport
  path: /v1/airports/{id}
- description: Get delay information for all airports with current delays
  method: GET
  name: get-all-delays
  path: /v1/airport-delays
- description: Get current weather conditions for an airport
  method: GET
  name: get-airport-weather
  path: /v1/airport-weather/{id}
- description: Get information about a specific operator
  method: GET
  name: get-operator
  path: /v1/operators/{id}
- description: List all configured flight alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Create a new flight event alert
  method: POST
  name: create-alert
  path: /v1/alerts
personas: []
provider_name: Rockwell Collins
provider_slug: rockwell-collins
search_terms:
- get detailed information about an airport by icao or iata code
- list all configured flight event alerts
- delete a configured flight event alert
- get the current real-time position and altitude for a flight
- get airport flights
- get all current flights for an operator/airline
- get detailed information for a specific flight
- individual airport information
- flight position track history
- get current weather conditions for an airport
- get all delays
- airport directory and information
- create alert
- get the filed route for a specific flight
- airport weather conditions
- get information about a specific operator
- search flights
- get current delay information for a specific airport
- create a new flight event alert for departure, arrival, or route changes
- airline and operator information
- get current weather conditions and forecast for an airport
- aviation
- get position track of a flight
- flight operations
- flight event alert management
- create a new flight event alert
- flight tracking
- get flight track
- get airport weather
- defense
- flight search and real-time tracking
- get flight route
- list all configured flight alerts
- aerospace
- get airport delays
- get all flights arriving or departing from an airport
- list airports
- get flight position
- flight deck
- get delay information for all airports with current delays
- get a list of all airports
- delete alert
- get current real-time position for a flight
- get detailed information for a specific flight including status, route, and timing
- get static information about an airport
- get the full position track history of a flight
- get information about an airline or operator including fleet and routes
- current flight position data
- get airport
- list alerts
- airport delay monitoring
- flightaware
- search for airborne flights by location, airline, aircraft type, or route
- avionics
- search for airborne flights by criteria including location, airline, and aircraft type
- get operator
- specific flight information
- collins aerospace
- get flight
- get operator flights
slug: flight-operations
source_filename: flight-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Collins Aerospace Flight Operations\"\n  description: >-\n    Unified workflow capability for aviation flight operations using FlightAware\n    AeroAPI. Enables airlines, ground handlers, flight departments, and technology\n    providers to track flights in real-time, monitor airport conditions, manage\n    flight alerts, analyze operator fleet activity, and access historical flight\n    data for operational planning, resource management, and maintenance scheduling.\n  tags:\n    - Aviation\n    - Flight Operations\n    - Aerospace\n    - Collins Aerospace\n    - FlightAware\n    - Flight Tracking\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      FLIGHTAWARE_API_KEY: FLIGHTAWARE_API_KEY\n\ncapability:\n  consumes:\n    - import: aeroapi\n      location: ./shared/aeroapi.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: flight-operations-api\n      description:\
  \ \"Unified REST API for aviation flight operations monitoring and planning.\"\n      resources:\n        - path: /v1/flights\n          name: flights\n          description: \"Flight search and real-time tracking\"\n          operations:\n            - method: GET\n              name: search-flights\n              description: \"Search for airborne flights by criteria including location, airline, and aircraft type\"\n              call: \"aeroapi.search-flights\"\n              with:\n                query: \"rest.query\"\n                max_pages: \"rest.max_pages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flights/{ident}\n          name: flight-detail\n          description: \"Specific flight information\"\n          operations:\n            - method: GET\n              name: get-flight\n              description: \"Get detailed information for a specific flight\"\n              call: \"aeroapi.get-flight\"\
  \n              with:\n                ident: \"rest.ident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flight-positions/{fa_flight_id}\n          name: flight-position\n          description: \"Current flight position data\"\n          operations:\n            - method: GET\n              name: get-flight-position\n              description: \"Get current real-time position for a flight\"\n              call: \"aeroapi.get-flight-position\"\n              with:\n                fa_flight_id: \"rest.fa_flight_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flight-tracks/{fa_flight_id}\n          name: flight-track\n          description: \"Flight position track history\"\n          operations:\n            - method: GET\n              name: get-flight-track\n              description: \"Get position track of a flight\"\n       \
  \       call: \"aeroapi.get-flight-track\"\n              with:\n                fa_flight_id: \"rest.fa_flight_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/airports\n          name: airports\n          description: \"Airport directory and information\"\n          operations:\n            - method: GET\n              name: list-airports\n              description: \"Get a list of all airports\"\n              call: \"aeroapi.get-all-airports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/airports/{id}\n          name: airport-detail\n          description: \"Individual airport information\"\n          operations:\n            - method: GET\n              name: get-airport\n              description: \"Get static information about an airport\"\n              call: \"aeroapi.get-airport\"\n              with:\n                id:\
  \ \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/airport-delays\n          name: airport-delays\n          description: \"Airport delay monitoring\"\n          operations:\n            - method: GET\n              name: get-all-delays\n              description: \"Get delay information for all airports with current delays\"\n              call: \"aeroapi.get-airport-delays\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/airport-weather/{id}\n          name: airport-weather\n          description: \"Airport weather conditions\"\n          operations:\n            - method: GET\n              name: get-airport-weather\n              description: \"Get current weather conditions for an airport\"\n              call: \"aeroapi.get-airport-weather\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/operators/{id}\n          name: operator-detail\n          description: \"Airline and operator information\"\n          operations:\n            - method: GET\n              name: get-operator\n              description: \"Get information about a specific operator\"\n              call: \"aeroapi.get-operator\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts\n          name: alerts\n          description: \"Flight event alert management\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List all configured flight alerts\"\n              call: \"aeroapi.get-all-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n  \
  \            name: create-alert\n              description: \"Create a new flight event alert\"\n              call: \"aeroapi.create-alert\"\n              with:\n                ident: \"rest.ident\"\n                events: \"rest.events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: flight-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted aviation flight operations and planning.\"\n      tools:\n        - name: search-flights\n          description: \"Search for airborne flights by location, airline, aircraft type, or route\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aeroapi.search-flights\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flight\n          description: \"\
  Get detailed information for a specific flight including status, route, and timing\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-flight\"\n          with:\n            ident: \"tools.ident\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flight-position\n          description: \"Get the current real-time position and altitude for a flight\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-flight-position\"\n          with:\n            fa_flight_id: \"tools.fa_flight_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flight-track\n          description: \"Get the full position track history of a flight\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-flight-track\"\n          with:\n\
  \            fa_flight_id: \"tools.fa_flight_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flight-route\n          description: \"Get the filed route for a specific flight\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-flight-route\"\n          with:\n            fa_flight_id: \"tools.fa_flight_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-airport\n          description: \"Get detailed information about an airport by ICAO or IATA code\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-airport\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-airport-delays\n          description: \"Get current delay information for a specific\
  \ airport\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-airport-delays\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-airport-flights\n          description: \"Get all flights arriving or departing from an airport\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-airport-flights\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-airport-weather\n          description: \"Get current weather conditions and forecast for an airport\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-airport-weather\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n\n        - name: get-operator\n          description: \"Get information about an airline or operator including fleet and routes\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-operator\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-operator-flights\n          description: \"Get all current flights for an operator/airline\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"aeroapi.get-operator-flights\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-alerts\n          description: \"List all configured flight event alerts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"aeroapi.get-all-alerts\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-alert\n          description: \"Create a new flight event alert for departure, arrival, or route changes\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"aeroapi.create-alert\"\n          with:\n            ident: \"tools.ident\"\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-alert\n          description: \"Delete a configured flight event alert\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"aeroapi.delete-alert\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rockwell-collins/refs/heads/main/capabilities/flight-operations.yaml
tags:
- Aviation
- Flight Operations
- Aerospace
- Collins Aerospace
- FlightAware
- Flight Tracking
tools:
- description: Search for airborne flights by location, airline, aircraft type, or route
  hints:
    openWorld: true
    readOnly: true
  name: search-flights
- description: Get detailed information for a specific flight including status, route, and timing
  hints:
    openWorld: false
    readOnly: true
  name: get-flight
- description: Get the current real-time position and altitude for a flight
  hints:
    openWorld: false
    readOnly: true
  name: get-flight-position
- description: Get the full position track history of a flight
  hints:
    openWorld: false
    readOnly: true
  name: get-flight-track
- description: Get the filed route for a specific flight
  hints:
    openWorld: false
    readOnly: true
  name: get-flight-route
- description: Get detailed information about an airport by ICAO or IATA code
  hints:
    openWorld: false
    readOnly: true
  name: get-airport
- description: Get current delay information for a specific airport
  hints:
    openWorld: false
    readOnly: true
  name: get-airport-delays
- description: Get all flights arriving or departing from an airport
  hints:
    openWorld: false
    readOnly: true
  name: get-airport-flights
- description: Get current weather conditions and forecast for an airport
  hints:
    openWorld: false
    readOnly: true
  name: get-airport-weather
- description: Get information about an airline or operator including fleet and routes
  hints:
    openWorld: false
    readOnly: true
  name: get-operator
- description: Get all current flights for an operator/airline
  hints:
    openWorld: false
    readOnly: true
  name: get-operator-flights
- description: List all configured flight event alerts
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: Create a new flight event alert for departure, arrival, or route changes
  hints:
    destructive: false
    readOnly: false
  name: create-alert
- description: Delete a configured flight event alert
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-alert
---
