---
categories: []
consumed_apis:
- att-device-status
- att-qod
description: Unified network performance capability combining Device Status, Network Insights, and Quality on Demand APIs. Used by developers building connectivity-aware applications, real-time streaming platforms, and IoT systems requiring AT&T 5G performance optimization.
layout: capability
name: AT&T Network Performance
operations:
- description: Check device connectivity and network connection type
  method: POST
  name: check-connectivity
  path: /v1/devices/connectivity
- description: Check if device is roaming
  method: POST
  name: check-roaming
  path: /v1/devices/roaming
- description: Request enhanced QoS for a device
  method: POST
  name: create-qod-session
  path: /v1/qod/sessions
- description: List active QoD sessions
  method: GET
  name: list-qod-sessions
  path: /v1/qod/sessions
- description: Get QoD session status
  method: GET
  name: get-qod-session
  path: /v1/qod/sessions/{sessionId}
- description: Terminate QoD session
  method: DELETE
  name: delete-qod-session
  path: /v1/qod/sessions/{sessionId}
personas: []
provider_name: AT&T Developer Hub
provider_slug: at-t-developer-hub
search_terms:
- check if device is roaming
- 5g network quality monitoring and on-demand qos enhancement
- check if an at&t subscriber device is connected to the network and get connection type (4g/5g)
- Identity Developer
- developer building fraud prevention and identity verification using network signals
- qod terminate session
- device connectivity status
- terminate an active quality on demand session and restore normal network quality
- device status
- connectivity
- terminate qod session
- edge computing
- network-based fraud prevention and authentication using sim swap and number verification
- device check roaming
- network apis
- IoT Engineer
- get qod session
- camara
- create qod session
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- list qod sessions
- get the current status of a quality on demand session
- network-based security signals for fraud detection and identity verification
- get qod session status
- mobile or web developer building connectivity-aware applications
- check if an at&t subscriber device is roaming on a partner network and get location
- list active quality on demand sessions for the application
- at&t
- Security Developer
- telecommunications
- request enhanced qos for a device
- delete qod session
- device roaming status
- qod get session
- 5g
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- create a 5g quality on demand session to enhance throughput or reduce latency for a device application
- quality of service
- check connectivity
- network performance
- sim swap
- check device connectivity and network connection type
- device check connectivity
- individual qod session
- qod create session
- App Developer
- developer implementing passwordless or frictionless mobile authentication
- list active qod sessions
- mobile network-based authentication without otp
- qod list sessions
- check roaming
- quality on demand session management
slug: network-performance
source_filename: network-performance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T Network Performance\"\n  description: \"Unified network performance capability combining Device Status, Network Insights, and Quality on Demand APIs. Used by developers building connectivity-aware applications, real-time streaming platforms, and IoT systems requiring AT&T 5G performance optimization.\"\n  tags:\n    - AT&T\n    - 5G\n    - Quality of Service\n    - Device Status\n    - Network Performance\n    - CAMARA\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_NETWORK_API_TOKEN: ATT_NETWORK_API_TOKEN\n\ncapability:\n  consumes:\n    - import: att-device-status\n      location: ./shared/device-status-api.yaml\n    - import: att-qod\n      location: ./shared/quality-on-demand-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: att-network-performance-api\n      description: \"Unified REST API for AT&T 5G network performance and device connectivity\
  \ management.\"\n      resources:\n        - path: /v1/devices/connectivity\n          name: device-connectivity\n          description: \"Device connectivity status\"\n          operations:\n            - method: POST\n              name: check-connectivity\n              description: \"Check device connectivity and network connection type\"\n              call: \"att-device-status.get-connectivity-status\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices/roaming\n          name: device-roaming\n          description: \"Device roaming status\"\n          operations:\n            - method: POST\n              name: check-roaming\n              description: \"Check if device is roaming\"\n              call: \"att-device-status.get-roaming-status\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/qod/sessions\n          name: qod-sessions\n          description: \"Quality on Demand session management\"\n          operations:\n            - method: POST\n              name: create-qod-session\n              description: \"Request enhanced QoS for a device\"\n              call: \"att-qod.create-session\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n                qosProfile: \"rest.qosProfile\"\n                duration: \"rest.duration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-qod-sessions\n              description: \"List active QoD sessions\"\n              call: \"att-qod.list-sessions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/qod/sessions/{sessionId}\n          name:\
  \ qod-session-detail\n          description: \"Individual QoD session\"\n          operations:\n            - method: GET\n              name: get-qod-session\n              description: \"Get QoD session status\"\n              call: \"att-qod.get-session\"\n              with:\n                sessionId: \"rest.sessionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-qod-session\n              description: \"Terminate QoD session\"\n              call: \"att-qod.delete-session\"\n              with:\n                sessionId: \"rest.sessionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: att-network-performance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AT&T network performance monitoring and QoS management.\"\n      tools:\n    \
  \    - name: device-check-connectivity\n          description: \"Check if an AT&T subscriber device is connected to the network and get connection type (4G/5G)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-device-status.get-connectivity-status\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: device-check-roaming\n          description: \"Check if an AT&T subscriber device is roaming on a partner network and get location\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-device-status.get-roaming-status\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: qod-create-session\n          description: \"Create a 5G Quality on Demand session to enhance\
  \ throughput or reduce latency for a device application\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"att-qod.create-session\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n            qosProfile: \"tools.qosProfile\"\n            duration: \"tools.duration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: qod-list-sessions\n          description: \"List active Quality on Demand sessions for the application\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-qod.list-sessions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: qod-get-session\n          description: \"Get the current status of a Quality on Demand session\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-qod.get-session\"\n          with:\n\
  \            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: qod-terminate-session\n          description: \"Terminate an active Quality on Demand session and restore normal network quality\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"att-qod.delete-session\"\n          with:\n            sessionId: \"tools.sessionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/at-t-developer-hub/refs/heads/main/capabilities/network-performance.yaml
tags:
- AT&T
- 5G
- Quality of Service
- Device Status
- Network Performance
- CAMARA
tools:
- description: Check if an AT&T subscriber device is connected to the network and get connection type (4G/5G)
  hints:
    idempotent: true
    readOnly: true
  name: device-check-connectivity
- description: Check if an AT&T subscriber device is roaming on a partner network and get location
  hints:
    idempotent: true
    readOnly: true
  name: device-check-roaming
- description: Create a 5G Quality on Demand session to enhance throughput or reduce latency for a device application
  hints:
    destructive: false
    readOnly: false
  name: qod-create-session
- description: List active Quality on Demand sessions for the application
  hints:
    idempotent: true
    readOnly: true
  name: qod-list-sessions
- description: Get the current status of a Quality on Demand session
  hints:
    idempotent: true
    readOnly: true
  name: qod-get-session
- description: Terminate an active Quality on Demand session and restore normal network quality
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: qod-terminate-session
---
