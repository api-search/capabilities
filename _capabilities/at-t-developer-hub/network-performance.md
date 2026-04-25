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
- check device connectivity and network connection type
- network-based fraud prevention and authentication using sim swap and number verification
- check if an at&t subscriber device is connected to the network and get connection type (4g/5g)
- Identity Developer
- device check connectivity
- sim swap
- network performance
- connectivity
- network apis
- telecommunications
- qod get session
- at&t
- device check roaming
- check connectivity
- check roaming
- individual qod session
- App Developer
- edge computing
- camara
- mobile or web developer building connectivity-aware applications
- IoT Engineer
- device roaming status
- terminate an active quality on demand session and restore normal network quality
- device connectivity status
- get qod session status
- delete qod session
- check if device is roaming
- quality on demand session management
- qod terminate session
- Security Developer
- request enhanced qos for a device
- get qod session
- developer building fraud prevention and identity verification using network signals
- list active qod sessions
- get the current status of a quality on demand session
- qod create session
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- network-based security signals for fraud detection and identity verification
- check if an at&t subscriber device is roaming on a partner network and get location
- list qod sessions
- 5g
- quality of service
- create qod session
- terminate qod session
- create a 5g quality on demand session to enhance throughput or reduce latency for a device application
- list active quality on demand sessions for the application
- qod list sessions
- developer implementing passwordless or frictionless mobile authentication
- mobile network-based authentication without otp
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- device status
- 5g network quality monitoring and on-demand qos enhancement
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
