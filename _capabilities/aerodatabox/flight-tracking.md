---
categories:
- travel-booking
consumed_apis: []
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
- look up aircraft details by tail number or icao24 hex code.
- aerospace
- airport operations
- find nearby airports.
- find airports near a geographic location.
- get fids for an airport.
- flight data
- get flight status data.
- get all departures and arrivals at an airport for a time window.
- get airport departures and arrivals.
- get airport departures arrivals
- retrieve airport details.
- get all aircraft in an airline's fleet.
- get airport
- real-time and historical flight tracking, status monitoring, and fids data.
- flights
- get fleet for an airline.
- get airport information.
- airport data
- flight tracking
- aircraft registrations, fleet composition, and aircraft imagery.
- delay statistics, route performance, and trend analysis.
- analyzes aviation performance, delay patterns, and route statistics using historical data.
- search airports by location.
- aerodatabox
- travel
- aviation
- airport information, runway data, and location search.
- search airports
- get details for an airport by iata or icao code.
- get airline fleet.
- get flight status
- search airports near location
- unified capability combining flight status, aircraft data, and airport information for real-time aviation intelligence.
- get airport fids
- track a flight in real-time by flight number or callsign.
- track a flight by number.
- get aircraft data.
- integrates flight data into travel booking and notification systems.
- look up an aircraft.
- get aircraft
- builds flight tracking, travel, and aviation applications using aerodatabox apis.
- get airline fleet
slug: flight-tracking
source_filename: flight-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AeroDataBox Flight Tracking\n  description: 'Unified capability for real-time aviation intelligence combining flight status, aircraft data, and airport\n    information. Enables developers and travel platforms to build comprehensive flight tracking, airport operations monitoring,\n    and aircraft research applications. Primary persona: Developer or Travel Platform Engineer.'\n  tags:\n  - AeroDataBox\n  - Aviation\n  - Flight Tracking\n  - Travel\n  - Airport Operations\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AERODATABOX_API_KEY: AERODATABOX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: flight\n    baseUri: https://prod.api.market/api/v1/aedbx/aerodatabox\n    description: AeroDataBox Flight API for real-time and historical flight data.\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{AERODATABOX_API_KEY}}'\n      placement: header\n\
  \    resources:\n    - name: flight-status\n      path: /flights/{searchBy}/{searchParam}\n      description: Get current day flight status.\n      operations:\n      - name: get-flight-status\n        method: GET\n        description: Get flight status for the current day by flight number or other identifier.\n        inputParameters:\n        - name: searchBy\n          in: path\n          type: string\n          required: true\n          description: 'Search type: number, callsign, squawk.'\n        - name: searchParam\n          in: path\n          type: string\n          required: true\n          description: The search value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: airport-fids\n      path: /flights/airports/{codeType}/{code}/{fromLocal}/{toLocal}\n      description: Get FIDS (departures and arrivals) for an airport.\n      operations:\n      - name: get-airport-fids\n        method:\
  \ GET\n        description: Get all flights departing and arriving at an airport in a time window.\n        inputParameters:\n        - name: codeType\n          in: path\n          type: string\n          required: true\n          description: 'Airport code type: iata or icao.'\n        - name: code\n          in: path\n          type: string\n          required: true\n          description: The airport code.\n        - name: fromLocal\n          in: path\n          type: string\n          required: true\n          description: Start of time window in local airport time.\n        - name: toLocal\n          in: path\n          type: string\n          required: true\n          description: End of time window in local airport time.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: aircraft\n    baseUri: https://prod.api.market/api/v1/aedbx/aerodatabox\n    description: AeroDataBox\
  \ Aircraft API for aircraft data and fleet information.\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{AERODATABOX_API_KEY}}'\n      placement: header\n    resources:\n    - name: aircraft\n      path: /aircrafts/{searchBy}/{searchParam}\n      description: Get aircraft information.\n      operations:\n      - name: get-aircraft\n        method: GET\n        description: Retrieve aircraft data by tail number, registration, or ICAO24.\n        inputParameters:\n        - name: searchBy\n          in: path\n          type: string\n          required: true\n          description: 'Search type: reg, hex, or similar.'\n        - name: searchParam\n          in: path\n          type: string\n          required: true\n          description: The search value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: airline-fleet\n      path: /airlines/{airlineCode}/aircrafts\n  \
  \    description: Get airline fleet.\n      operations:\n      - name: get-airline-fleet\n        method: GET\n        description: Get all aircraft in an airline's fleet.\n        inputParameters:\n        - name: airlineCode\n          in: path\n          type: string\n          required: true\n          description: IATA airline code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: airport\n    baseUri: https://prod.api.market/api/v1/aedbx/aerodatabox\n    description: AeroDataBox Airport API for airport data and location search.\n    authentication:\n      type: apikey\n      key: x-api-key\n      value: '{{AERODATABOX_API_KEY}}'\n      placement: header\n    resources:\n    - name: airport\n      path: /airports/{codeType}/{code}\n      description: Get airport data by code.\n      operations:\n      - name: get-airport\n        method: GET\n        description: Retrieve\
  \ airport information by IATA or ICAO code.\n        inputParameters:\n        - name: codeType\n          in: path\n          type: string\n          required: true\n          description: 'Airport code type: iata or icao.'\n        - name: code\n          in: path\n          type: string\n          required: true\n          description: Airport code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: airport-search\n      path: /airports/search/location\n      description: Search airports by location.\n      operations:\n      - name: search-airports-by-location\n        method: GET\n        description: Find airports near a geographic coordinate.\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: true\n          description: Latitude.\n        - name: lon\n          in: query\n          type: number\n          required: true\n       \
  \   description: Longitude.\n        - name: radiusKm\n          in: query\n          type: number\n          required: false\n          description: Search radius in kilometers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aerodatabox-flight-tracking-api\n    description: Unified REST API for AeroDataBox aviation data.\n    resources:\n    - path: /v1/flights/{searchBy}/{searchParam}\n      name: flight-status\n      description: Get flight status data.\n      operations:\n      - method: GET\n        name: get-flight-status\n        description: Track a flight by number.\n        call: flight.get-flight-status\n        with:\n          searchBy: rest.searchBy\n          searchParam: rest.searchParam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airports/{codeType}/{code}/flights\n      name: airport-fids\n\
  \      description: Get FIDS for an airport.\n      operations:\n      - method: GET\n        name: get-airport-fids\n        description: Get airport departures and arrivals.\n        call: flight.get-airport-fids\n        with:\n          codeType: rest.codeType\n          code: rest.code\n          fromLocal: rest.fromLocal\n          toLocal: rest.toLocal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airports/{codeType}/{code}\n      name: airport\n      description: Get airport information.\n      operations:\n      - method: GET\n        name: get-airport\n        description: Retrieve airport details.\n        call: airport.get-airport\n        with:\n          codeType: rest.codeType\n          code: rest.code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airports/search/location\n      name: airport-search\n      description: Search airports by location.\n      operations:\n      - method:\
  \ GET\n        name: search-airports\n        description: Find nearby airports.\n        call: airport.search-airports-by-location\n        with:\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aircrafts/{searchBy}/{searchParam}\n      name: aircraft\n      description: Get aircraft data.\n      operations:\n      - method: GET\n        name: get-aircraft\n        description: Look up an aircraft.\n        call: aircraft.get-aircraft\n        with:\n          searchBy: rest.searchBy\n          searchParam: rest.searchParam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/airlines/{airlineCode}/aircrafts\n      name: airline-fleet\n      description: Get airline fleet.\n      operations:\n      - method: GET\n        name: get-airline-fleet\n        description: Get fleet for an airline.\n        call: aircraft.get-airline-fleet\n        with:\n       \
  \   airlineCode: rest.airlineCode\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: aerodatabox-flight-tracking-mcp\n    transport: http\n    description: MCP server for AI-assisted aviation data queries using AeroDataBox.\n    tools:\n    - name: get-flight-status\n      description: Track a flight in real-time by flight number or callsign.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flight.get-flight-status\n      with:\n        searchBy: tools.searchBy\n        searchParam: tools.searchParam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airport-departures-arrivals\n      description: Get all departures and arrivals at an airport for a time window.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: flight.get-airport-fids\n      with:\n        codeType: tools.codeType\n        code: tools.code\n        fromLocal: tools.fromLocal\n\
  \        toLocal: tools.toLocal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airport\n      description: Get details for an airport by IATA or ICAO code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airport.get-airport\n      with:\n        codeType: tools.codeType\n        code: tools.code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-airports-near-location\n      description: Find airports near a geographic location.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: airport.search-airports-by-location\n      with:\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-aircraft\n      description: Look up aircraft details by tail number or ICAO24 hex code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aircraft.get-aircraft\n      with:\n    \
  \    searchBy: tools.searchBy\n        searchParam: tools.searchParam\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-airline-fleet\n      description: Get all aircraft in an airline's fleet.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: aircraft.get-airline-fleet\n      with:\n        airlineCode: tools.airlineCode\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
