---
categories: []
consumed_apis:
- arinc-messaging
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
- list flights with oooi data.
- airline operations center controller monitoring fleet status and communicating with aircraft
- airline operations
- get aviation weather data including metars, tafs, and sigmets for dispatch and flight operations.
- aviation weather data.
- send message
- send an acars uplink message to an aircraft via the arinc global network (gate changes, operational updates).
- real-time airline and airport operations management
- arinc
- get weather
- pre-flight and in-flight dispatch support
- send aircraft uplink message.
- collins aerospace
- flight tracking and oooi events.
- ground operations manager
- get aviation weather
- acars aircraft messaging.
- list aviation messages.
- airport ground operations manager coordinating arrivals, departures, and gate assignments
- list acars messages for aircraft, filtered by airline code, registration, or flight number.
- operations controller
- defense
- dispatcher responsible for flight planning, weather briefings, and operational communications
- track flights
- dispatcher
- manufacturing
- connectivity
- track flights with real-time oooi event times (out, off, on, in) for operations center monitoring.
- list flights
- dispatch
- get aviation weather.
- aviation operations
- aerospace
- send aircraft message
- list aircraft messages
- aviation
- complete aviation operations workflow combining acars messaging, flight tracking, and weather data
- list messages
slug: aviation-operations
source_filename: aviation-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Collins Aerospace Aviation Operations\"\n  description: >-\n    Workflow capability for airline and airport aviation operations using the Collins\n    Aerospace ARINC Digital Exchange platform. Combines aircraft messaging, flight\n    tracking, and weather data to support operations control centers, dispatch teams,\n    and ground operations managers managing daily flight operations.\n  tags:\n    - Collins Aerospace\n    - ARINC\n    - Aviation Operations\n    - Airline Operations\n    - Dispatch\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      ARINC_BEARER_TOKEN: ARINC_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: arinc-messaging\n      location: ./shared/arinc-messaging.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aviation-operations-api\n      description: \"Unified REST API for Collins Aerospace aviation operations.\"\n      resources:\n\
  \        - path: /v1/messages\n          name: messages\n          description: \"ACARS aircraft messaging.\"\n          operations:\n            - method: GET\n              name: list-messages\n              description: \"List aviation messages.\"\n              call: \"arinc-messaging.list-messages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-message\n              description: \"Send aircraft uplink message.\"\n              call: \"arinc-messaging.send-message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/flights\n          name: flights\n          description: \"Flight tracking and OOOI events.\"\n          operations:\n            - method: GET\n              name: list-flights\n              description: \"List flights with OOOI data.\"\n              call: \"arinc-messaging.list-flights\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/weather\n          name: weather\n          description: \"Aviation weather data.\"\n          operations:\n            - method: GET\n              name: get-weather\n              description: \"Get aviation weather.\"\n              call: \"arinc-messaging.get-weather\"\n              with:\n                stationType: \"rest.stationType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: aviation-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Collins Aerospace aviation operations management.\"\n      tools:\n        - name: list-aircraft-messages\n          description: \"List ACARS messages for aircraft, filtered by airline code, registration, or flight number.\"\n          hints:\n            readOnly: true\n        \
  \    openWorld: true\n          call: \"arinc-messaging.list-messages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-aircraft-message\n          description: \"Send an ACARS uplink message to an aircraft via the ARINC Global Network (gate changes, operational updates).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"arinc-messaging.send-message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-flights\n          description: \"Track flights with real-time OOOI event times (Out, Off, On, In) for operations center monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"arinc-messaging.list-flights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-aviation-weather\n    \
  \      description: \"Get aviation weather data including METARs, TAFs, and SIGMETs for dispatch and flight operations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"arinc-messaging.get-weather\"\n          with:\n            stationType: \"tools.stationType\"\n            station: \"tools.station\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
