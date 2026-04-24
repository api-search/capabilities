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
- check roaming
- quality on demand session management
- terminate an active quality on demand session and restore normal network quality
- network-based security signals for fraud detection and identity verification
- list active quality on demand sessions for the application
- request enhanced qos for a device
- developer implementing passwordless or frictionless mobile authentication
- device check roaming
- qod terminate session
- check if device is roaming
- connectivity
- network apis
- get qod session
- quality of service
- at&t
- mobile or web developer building connectivity-aware applications
- qod list sessions
- network performance
- 5g
- check connectivity
- telecommunications
- 5g network quality monitoring and on-demand qos enhancement
- Identity Developer
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- device roaming status
- get the current status of a quality on demand session
- get qod session status
- delete qod session
- individual qod session
- device connectivity status
- device status
- network-based fraud prevention and authentication using sim swap and number verification
- App Developer
- create qod session
- edge computing
- check if an at&t subscriber device is roaming on a partner network and get location
- check if an at&t subscriber device is connected to the network and get connection type (4g/5g)
- camara
- qod get session
- Security Developer
- qod create session
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- terminate qod session
- IoT Engineer
- create a 5g quality on demand session to enhance throughput or reduce latency for a device application
- list active qod sessions
- developer building fraud prevention and identity verification using network signals
- mobile network-based authentication without otp
- sim swap
- check device connectivity and network connection type
- list qod sessions
- device check connectivity
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
