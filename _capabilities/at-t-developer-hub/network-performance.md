---
categories: []
consumed_apis: []
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
- network performance
- device roaming status
- qod create session
- Identity Developer
- device connectivity status
- qod get session
- list active qod sessions
- check if an at&t subscriber device is roaming on a partner network and get location
- create qod session
- check roaming
- delete qod session
- device status
- individual qod session
- Security Developer
- mobile or web developer building connectivity-aware applications
- 5g
- list active quality on demand sessions for the application
- network-based fraud prevention and authentication using sim swap and number verification
- edge computing
- list qod sessions
- check device connectivity and network connection type
- quality of service
- terminate an active quality on demand session and restore normal network quality
- create a 5g quality on demand session to enhance throughput or reduce latency for a device application
- developer building fraud prevention and identity verification using network signals
- connectivity
- device check connectivity
- qod list sessions
- telecommunications
- network apis
- quality on demand session management
- check if an at&t subscriber device is connected to the network and get connection type (4g/5g)
- network-based security signals for fraud detection and identity verification
- camara
- device check roaming
- at&t
- 5g network quality monitoring and on-demand qos enhancement
- terminate qod session
- check connectivity
- get the current status of a quality on demand session
- check if device is roaming
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- IoT Engineer
- get qod session status
- App Developer
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- qod terminate session
- request enhanced qos for a device
- mobile network-based authentication without otp
- get qod session
- developer implementing passwordless or frictionless mobile authentication
- sim swap
slug: network-performance
source_filename: network-performance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AT&T Network Performance\n  description: Unified network performance capability combining Device Status, Network Insights, and Quality on Demand APIs.\n    Used by developers building connectivity-aware applications, real-time streaming platforms, and IoT systems requiring\n    AT&T 5G performance optimization.\n  tags:\n  - AT&T\n  - 5G\n  - Quality of Service\n  - Device Status\n  - Network Performance\n  - CAMARA\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATT_NETWORK_API_TOKEN: ATT_NETWORK_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: att-device-status\n    baseUri: https://api.att.com/camara/device-status/v1\n    description: AT&T Device Status API\n    authentication:\n      type: bearer\n      token: '{{ATT_NETWORK_API_TOKEN}}'\n    resources:\n    - name: connectivity\n      path: /connectivity\n      description: Device connectivity status\n      operations:\n\
  \      - name: get-connectivity-status\n        method: POST\n        description: Get device connectivity status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n    - name: roaming\n      path: /roaming\n      description: Device roaming status\n      operations:\n      - name: get-roaming-status\n        method: POST\n        description: Get device roaming status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n  - type: http\n    namespace: att-qod\n    baseUri: https://api.att.com/camara/qod/v1\n    description: AT&T Quality on Demand API\n    authentication:\n      type: bearer\n      token: '{{ATT_NETWORK_API_TOKEN}}'\n\
  \    resources:\n    - name: sessions\n      path: /sessions\n      description: QoD session management\n      operations:\n      - name: create-session\n        method: POST\n        description: Create QoD session for enhanced network quality\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n            qosProfile: '{{tools.qosProfile}}'\n            duration: '{{tools.duration}}'\n      - name: list-sessions\n        method: GET\n        description: List active QoD sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: session-detail\n      path: /sessions/{sessionId}\n      description: Individual QoD session\n      operations:\n      - name: get-session\n        method: GET\n        description: Get QoD session\
  \ details\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-session\n        method: DELETE\n        description: Terminate QoD session\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: att-network-performance-api\n    description: Unified REST API for AT&T 5G network performance and device connectivity management.\n    resources:\n    - path: /v1/devices/connectivity\n      name: device-connectivity\n      description: Device connectivity status\n\
  \      operations:\n      - method: POST\n        name: check-connectivity\n        description: Check device connectivity and network connection type\n        call: att-device-status.get-connectivity-status\n        with:\n          phoneNumber: rest.phoneNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/roaming\n      name: device-roaming\n      description: Device roaming status\n      operations:\n      - method: POST\n        name: check-roaming\n        description: Check if device is roaming\n        call: att-device-status.get-roaming-status\n        with:\n          phoneNumber: rest.phoneNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/qod/sessions\n      name: qod-sessions\n      description: Quality on Demand session management\n      operations:\n      - method: POST\n        name: create-qod-session\n        description: Request enhanced QoS for a device\n        call:\
  \ att-qod.create-session\n        with:\n          phoneNumber: rest.phoneNumber\n          qosProfile: rest.qosProfile\n          duration: rest.duration\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-qod-sessions\n        description: List active QoD sessions\n        call: att-qod.list-sessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/qod/sessions/{sessionId}\n      name: qod-session-detail\n      description: Individual QoD session\n      operations:\n      - method: GET\n        name: get-qod-session\n        description: Get QoD session status\n        call: att-qod.get-session\n        with:\n          sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-qod-session\n        description: Terminate QoD session\n        call: att-qod.delete-session\n        with:\n        \
  \  sessionId: rest.sessionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: att-network-performance-mcp\n    transport: http\n    description: MCP server for AI-assisted AT&T network performance monitoring and QoS management.\n    tools:\n    - name: device-check-connectivity\n      description: Check if an AT&T subscriber device is connected to the network and get connection type (4G/5G)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-device-status.get-connectivity-status\n      with:\n        phoneNumber: tools.phoneNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: device-check-roaming\n      description: Check if an AT&T subscriber device is roaming on a partner network and get location\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-device-status.get-roaming-status\n      with:\n        phoneNumber: tools.phoneNumber\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: qod-create-session\n      description: Create a 5G Quality on Demand session to enhance throughput or reduce latency for a device application\n      hints:\n        readOnly: false\n        destructive: false\n      call: att-qod.create-session\n      with:\n        phoneNumber: tools.phoneNumber\n        qosProfile: tools.qosProfile\n        duration: tools.duration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: qod-list-sessions\n      description: List active Quality on Demand sessions for the application\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-qod.list-sessions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: qod-get-session\n      description: Get the current status of a Quality on Demand session\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-qod.get-session\n  \
  \    with:\n        sessionId: tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: qod-terminate-session\n      description: Terminate an active Quality on Demand session and restore normal network quality\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: att-qod.delete-session\n      with:\n        sessionId: tools.sessionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
