---
categories: []
consumed_apis: []
description: Workflow capability for airline and airport aviation operations using the Collins Aerospace ARINC Digital Exchange platform. Combines aircraft messaging, flight tracking, and weather data to support operations control centers, dispatch teams, and ground operations managers managing daily flight operations.
layout: capability
name: Collins Aerospace Aviation Operations
operations:
- description: List aviation messages.
  method: GET
  name: list-messages
  path: /v1/messages
- description: Send aircraft uplink message.
  method: POST
  name: send-message
  path: /v1/messages
- description: List flights with OOOI data.
  method: GET
  name: list-flights
  path: /v1/flights
- description: Get aviation weather.
  method: GET
  name: get-weather
  path: /v1/weather
personas: []
provider_name: United Technologies
provider_slug: united-technologies
search_terms:
- aerospace
- aviation operations
- pre-flight and in-flight dispatch support
- flight tracking and oooi events.
- airport ground operations manager coordinating arrivals, departures, and gate assignments
- dispatch
- connectivity
- real-time airline and airport operations management
- airline operations
- dispatcher responsible for flight planning, weather briefings, and operational communications
- airline operations center controller monitoring fleet status and communicating with aircraft
- operations controller
- send an acars uplink message to an aircraft via the arinc global network (gate changes, operational updates).
- send aircraft message
- ground operations manager
- collins aerospace
- list aviation messages.
- send aircraft uplink message.
- list flights
- list flights with oooi data.
- track flights with real-time oooi event times (out, off, on, in) for operations center monitoring.
- send message
- arinc
- manufacturing
- track flights
- list messages
- complete aviation operations workflow combining acars messaging, flight tracking, and weather data
- aviation
- get aviation weather
- get aviation weather.
- get aviation weather data including metars, tafs, and sigmets for dispatch and flight operations.
- defense
- list aircraft messages
- list acars messages for aircraft, filtered by airline code, registration, or flight number.
- get weather
- acars aircraft messaging.
- dispatcher
- aviation weather data.
slug: aviation-operations
source_filename: aviation-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Collins Aerospace Aviation Operations\n  description: Workflow capability for airline and airport aviation operations using the Collins Aerospace ARINC Digital Exchange\n    platform. Combines aircraft messaging, flight tracking, and weather data to support operations control centers, dispatch\n    teams, and ground operations managers managing daily flight operations.\n  tags:\n  - Collins Aerospace\n  - ARINC\n  - Aviation Operations\n  - Airline Operations\n  - Dispatch\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ARINC_BEARER_TOKEN: ARINC_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: arinc-messaging\n    baseUri: https://api.arinconline.collinsaerospace.com\n    description: Collins Aerospace ARINC Online API.\n    authentication:\n      type: bearer\n      token: '{{ARINC_BEARER_TOKEN}}'\n    resources:\n    - name: messages\n      path: /messages\n      description:\
  \ ARINC aviation messages.\n      operations:\n      - name: list-messages\n        method: GET\n        description: List aviation messages with optional filters.\n        inputParameters:\n        - name: messageType\n          in: query\n          type: string\n          required: false\n          description: Filter by message type.\n        - name: registration\n          in: query\n          type: string\n          required: false\n          description: Aircraft registration.\n        - name: airlineCode\n          in: query\n          type: string\n          required: false\n          description: IATA airline code.\n        - name: flightNumber\n          in: query\n          type: string\n          required: false\n          description: Flight number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send an uplink message to an\
  \ aircraft.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            messageType: '{{tools.messageType}}'\n            registration: '{{tools.registration}}'\n            content: '{{tools.content}}'\n    - name: flights\n      path: /flights\n      description: Flight information and OOOI events.\n      operations:\n      - name: list-flights\n        method: GET\n        description: List flights with OOOI event times.\n        inputParameters:\n        - name: airlineCode\n          in: query\n          type: string\n          required: false\n          description: IATA airline code.\n        - name: flightNumber\n          in: query\n          type: string\n          required: false\n          description: Flight number.\n        - name: departureDate\n          in: query\n          type: string\n          required: false\n          description:\
  \ Departure date.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: weather\n      path: /weather\n      description: Aviation weather data.\n      operations:\n      - name: get-weather\n        method: GET\n        description: Get aviation weather for a station.\n        inputParameters:\n        - name: stationType\n          in: query\n          type: string\n          required: true\n          description: Weather report type.\n        - name: station\n          in: query\n          type: string\n          required: false\n          description: ICAO station identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aviation-operations-api\n    description: Unified REST API for Collins Aerospace aviation operations.\n    resources:\n    - path: /v1/messages\n\
  \      name: messages\n      description: ACARS aircraft messaging.\n      operations:\n      - method: GET\n        name: list-messages\n        description: List aviation messages.\n        call: arinc-messaging.list-messages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send aircraft uplink message.\n        call: arinc-messaging.send-message\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flights\n      name: flights\n      description: Flight tracking and OOOI events.\n      operations:\n      - method: GET\n        name: list-flights\n        description: List flights with OOOI data.\n        call: arinc-messaging.list-flights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/weather\n      name: weather\n      description: Aviation weather data.\n      operations:\n      - method: GET\n        name:\
  \ get-weather\n        description: Get aviation weather.\n        call: arinc-messaging.get-weather\n        with:\n          stationType: rest.stationType\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aviation-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Collins Aerospace aviation operations management.\n    tools:\n    - name: list-aircraft-messages\n      description: List ACARS messages for aircraft, filtered by airline code, registration, or flight number.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: arinc-messaging.list-messages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-aircraft-message\n      description: Send an ACARS uplink message to an aircraft via the ARINC Global Network (gate changes, operational updates).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: arinc-messaging.send-message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-flights\n      description: Track flights with real-time OOOI event times (Out, Off, On, In) for operations center monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: arinc-messaging.list-flights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-aviation-weather\n      description: Get aviation weather data including METARs, TAFs, and SIGMETs for dispatch and flight operations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: arinc-messaging.get-weather\n      with:\n        stationType: tools.stationType\n        station: tools.station\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-technologies/refs/heads/main/capabilities/aviation-operations.yaml
tags:
- Collins Aerospace
- ARINC
- Aviation Operations
- Airline Operations
- Dispatch
tools:
- description: List ACARS messages for aircraft, filtered by airline code, registration, or flight number.
  hints:
    openWorld: true
    readOnly: true
  name: list-aircraft-messages
- description: Send an ACARS uplink message to an aircraft via the ARINC Global Network (gate changes, operational updates).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-aircraft-message
- description: Track flights with real-time OOOI event times (Out, Off, On, In) for operations center monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: track-flights
- description: Get aviation weather data including METARs, TAFs, and SIGMETs for dispatch and flight operations.
  hints:
    openWorld: true
    readOnly: true
  name: get-aviation-weather
---
