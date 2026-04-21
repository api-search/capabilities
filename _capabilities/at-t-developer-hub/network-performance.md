---
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
- check connectivity
- delete qod session
- network-based fraud prevention and authentication using sim swap and number verification
- check roaming
- App Developer
- device check connectivity
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- IoT Engineer
- connectivity
- qod create session
- list active quality on demand sessions for the application
- edge computing
- developer building fraud prevention and identity verification using network signals
- device status
- 5g
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- 5g network quality monitoring and on-demand qos enhancement
- at&t
- qod terminate session
- get the current status of a quality on demand session
- developer implementing passwordless or frictionless mobile authentication
- list qod sessions
- Security Developer
- mobile network-based authentication without otp
- create a 5g quality on demand session to enhance throughput or reduce latency for a device application
- get qod session
- network performance
- sim swap
- camara
- network apis
- telecommunications
- get qod session status
- request enhanced qos for a device
- device roaming status
- check if an at&t subscriber device is roaming on a partner network and get location
- network-based security signals for fraud detection and identity verification
- terminate an active quality on demand session and restore normal network quality
- list active qod sessions
- mobile or web developer building connectivity-aware applications
- quality of service
- create qod session
- Identity Developer
- check if an at&t subscriber device is connected to the network and get connection type (4g/5g)
- individual qod session
- qod list sessions
- device connectivity status
- check if device is roaming
- quality on demand session management
- check device connectivity and network connection type
- device check roaming
- terminate qod session
- qod get session
slug: network-performance
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
