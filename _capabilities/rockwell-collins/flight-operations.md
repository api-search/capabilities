---
categories: []
consumed_apis: []
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
- list airports
- get a list of all airports
- flight tracking
- search flights
- get delay information for all airports with current delays
- flight operations
- specific flight information
- get all delays
- list all configured flight alerts
- create a new flight event alert for departure, arrival, or route changes
- defense
- aviation
- get airport
- get position track of a flight
- search for airborne flights by criteria including location, airline, and aircraft type
- flight deck
- current flight position data
- get static information about an airport
- get the current real-time position and altitude for a flight
- airport delay monitoring
- delete a configured flight event alert
- get all current flights for an operator/airline
- flight search and real-time tracking
- get current weather conditions and forecast for an airport
- flight position track history
- get operator flights
- aerospace
- get current delay information for a specific airport
- flightaware
- get current weather conditions for an airport
- delete alert
- flight event alert management
- collins aerospace
- create a new flight event alert
- get information about an airline or operator including fleet and routes
- get airport weather
- get flight route
- airport weather conditions
- get information about a specific operator
- get airport delays
- avionics
- get flight track
- create alert
- airline and operator information
- list all configured flight event alerts
- get flight position
- get the filed route for a specific flight
- get detailed information for a specific flight including status, route, and timing
- get airport flights
- get all flights arriving or departing from an airport
- get flight
- get the full position track history of a flight
- get detailed information about an airport by icao or iata code
- search for airborne flights by location, airline, aircraft type, or route
- individual airport information
- list alerts
- get current real-time position for a flight
- get operator
- airport directory and information
- get detailed information for a specific flight
slug: flight-operations
source_filename: flight-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Collins Aerospace Flight Operations\n  description: Unified workflow capability for aviation flight operations using FlightAware AeroAPI. Enables airlines, ground\n    handlers, flight departments, and technology providers to track flights in real-time, monitor airport conditions, manage\n    flight alerts, analyze operator fleet activity, and access historical flight data for operational planning, resource management,\n    and maintenance scheduling.\n  tags:\n  - Aviation\n  - Flight Operations\n  - Aerospace\n  - Collins Aerospace\n  - FlightAware\n  - Flight Tracking\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FLIGHTAWARE_API_KEY: FLIGHTAWARE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: aeroapi\n    baseUri: https://aeroapi.flightaware.com/aeroapi\n    description: FlightAware AeroAPI for aviation data access\n    authentication:\n      type: apikey\n      key: x-apikey\n\
  \      value: '{{FLIGHTAWARE_API_KEY}}'\n      placement: header\n    resources:\n    - name: flights\n      path: /flights\n      description: Flight search, tracking, and information\n      operations:\n      - name: search-flights\n        method: GET\n        description: Search for airborne flights matching various parameters\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Simplified query string with key-value pairs\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of result pages\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-flights-advanced\n        method: GET\n\
  \        description: Search for flights using advanced query syntax\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Advanced query string\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of result pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flight\n        method: GET\n        description: Get information for a specific flight\n        inputParameters:\n        - name: ident\n          in: path\n          type: string\n          required: true\n          description: Flight identifier (ICAO or IATA)\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of result pages\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-flight-position\n        method: GET\n        description: Get the current position of a flight\n        inputParameters:\n        - name: fa_flight_id\n          in: path\n          type: string\n          required: true\n          description: FlightAware flight ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flight-track\n        method: GET\n        description: Get the position track of a flight\n        inputParameters:\n        - name: fa_flight_id\n          in: path\n          type: string\n          required: true\n          description: FlightAware flight ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-flight-route\n        method: GET\n        description: Get the filed route of a flight\n\
  \        inputParameters:\n        - name: fa_flight_id\n          in: path\n          type: string\n          required: true\n          description: FlightAware flight ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: airports\n      path: /airports\n      description: Airport information and activity\n      operations:\n      - name: get-all-airports\n        method: GET\n        description: Get a list of all airports\n        inputParameters:\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum result pages\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-airport\n        method: GET\n\
  \        description: Get static information about an airport\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Airport code (ICAO or IATA)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-airport-delays\n        method: GET\n        description: Get delay information for an airport\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Airport code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-airport-flights\n        method: GET\n        description: Get all flights for a given airport\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Airport code\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum result pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-airport-weather\n        method: GET\n        description: Get current weather conditions for an airport\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Airport code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operators\n      path: /operators\n      description: Airline and operator information and fleet activity\n      operations:\n      - name: get-all-operators\n        method: GET\n        description: Get a list of all operators\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: get-operator\n        method: GET\n        description: Get information about a specific operator\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Operator ICAO code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-operator-flights\n        method: GET\n        description: Get flights for a specific operator\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Operator ICAO code\n        - name: max_pages\n          in: query\n          type: integer\n          required: false\n          description: Maximum result pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: alerts\n      path: /alerts\n      description: Configure real-time flight event alerts\n      operations:\n      - name: get-all-alerts\n        method: GET\n        description: Get all configured alerts for the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-alert\n        method: POST\n        description: Create a new flight alert configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ident: '{{tools.ident}}'\n            events: '{{tools.events}}'\n      - name: update-alert\n        method: PUT\n        description: Update an existing alert configuration\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Alert ID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-alert\n        method: DELETE\n        description: Delete a flight alert\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Alert ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flight-operations-api\n    description: Unified REST API for aviation flight operations monitoring and planning.\n    resources:\n    - path: /v1/flights\n      name: flights\n      description: Flight search and real-time tracking\n      operations:\n      - method: GET\n        name: search-flights\n        description: Search for airborne flights by criteria including location, airline, and aircraft type\n        call: aeroapi.search-flights\n\
  \        with:\n          query: rest.query\n          max_pages: rest.max_pages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flights/{ident}\n      name: flight-detail\n      description: Specific flight information\n      operations:\n      - method: GET\n        name: get-flight\n        description: Get detailed information for a specific flight\n        call: aeroapi.get-flight\n        with:\n          ident: rest.ident\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flight-positions/{fa_flight_id}\n      name: flight-position\n      description: Current flight position data\n      operations:\n      - method: GET\n        name: get-flight-position\n        description: Get current real-time position for a flight\n        call: aeroapi.get-flight-position\n        with:\n          fa_flight_id: rest.fa_flight_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/flight-tracks/{fa_flight_id}\n      name: flight-track\n      description: Flight position track history\n      operations:\n      - method: GET\n        name: get-flight-track\n        description: Get position track of a flight\n        call: aeroapi.get-flight-track\n        with:\n          fa_flight_id: rest.fa_flight_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airports\n      name: airports\n      description: Airport directory and information\n      operations:\n      - method: GET\n        name: list-airports\n        description: Get a list of all airports\n        call: aeroapi.get-all-airports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airports/{id}\n      name: airport-detail\n      description: Individual airport information\n      operations:\n      - method: GET\n        name: get-airport\n        description: Get static information about an airport\n        call:\
  \ aeroapi.get-airport\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airport-delays\n      name: airport-delays\n      description: Airport delay monitoring\n      operations:\n      - method: GET\n        name: get-all-delays\n        description: Get delay information for all airports with current delays\n        call: aeroapi.get-airport-delays\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airport-weather/{id}\n      name: airport-weather\n      description: Airport weather conditions\n      operations:\n      - method: GET\n        name: get-airport-weather\n        description: Get current weather conditions for an airport\n        call: aeroapi.get-airport-weather\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/operators/{id}\n      name: operator-detail\n      description: Airline\
  \ and operator information\n      operations:\n      - method: GET\n        name: get-operator\n        description: Get information about a specific operator\n        call: aeroapi.get-operator\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Flight event alert management\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List all configured flight alerts\n        call: aeroapi.get-all-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-alert\n        description: Create a new flight event alert\n        call: aeroapi.create-alert\n        with:\n          ident: rest.ident\n          events: rest.events\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: flight-operations-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted aviation flight operations and planning.\n    tools:\n    - name: search-flights\n      description: Search for airborne flights by location, airline, aircraft type, or route\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aeroapi.search-flights\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight\n      description: Get detailed information for a specific flight including status, route, and timing\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-flight\n      with:\n        ident: tools.ident\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight-position\n      description: Get the current real-time position and altitude for a flight\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-flight-position\n      with:\n\
  \        fa_flight_id: tools.fa_flight_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight-track\n      description: Get the full position track history of a flight\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-flight-track\n      with:\n        fa_flight_id: tools.fa_flight_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-flight-route\n      description: Get the filed route for a specific flight\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-flight-route\n      with:\n        fa_flight_id: tools.fa_flight_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airport\n      description: Get detailed information about an airport by ICAO or IATA code\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-airport\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-airport-delays\n      description: Get current delay information for a specific airport\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-airport-delays\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airport-flights\n      description: Get all flights arriving or departing from an airport\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-airport-flights\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airport-weather\n      description: Get current weather conditions and forecast for an airport\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-airport-weather\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-operator\n      description: Get information about an airline or operator including fleet and routes\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-operator\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-operator-flights\n      description: Get all current flights for an operator/airline\n      hints:\n        readOnly: true\n        openWorld: false\n      call: aeroapi.get-operator-flights\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: List all configured flight event alerts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aeroapi.get-all-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-alert\n      description: Create a new flight event alert for departure, arrival, or route changes\n      hints:\n\
  \        readOnly: false\n        destructive: false\n      call: aeroapi.create-alert\n      with:\n        ident: tools.ident\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-alert\n      description: Delete a configured flight event alert\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: aeroapi.delete-alert\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
