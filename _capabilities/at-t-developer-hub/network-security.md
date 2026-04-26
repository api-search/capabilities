---
consumed_apis:
- att-sim-swap
- att-number-verification
description: Unified network-based security capability combining SIM Swap detection, Number Verification, and Mobility Threat Detection APIs. Used by developers building fraud prevention, authentication, and security monitoring applications leveraging AT&T network signals.
layout: capability
name: AT&T Network Security
operations:
- description: Check if a SIM card has been swapped recently
  method: POST
  name: check-sim-swap
  path: /v1/sim-swap/check
- description: Get date of most recent SIM swap
  method: POST
  name: retrieve-sim-swap-date
  path: /v1/sim-swap/date
- description: Silently verify device phone number
  method: POST
  name: verify-phone-number
  path: /v1/number-verification/verify
personas: []
provider_name: AT&T Developer Hub
provider_slug: at-t-developer-hub
search_terms:
- retrieve sim swap date
- check if a sim card has been swapped recently
- phone number verification via network
- Identity Developer
- silently verify device phone number
- camara
- authentication
- fraud prevention
- check if an at&t subscriber's sim card has been swapped recently to detect fraud
- silently verify that a mobile device is associated with a phone number using the at&t network
- IoT Engineer
- 5g
- App Developer
- mobile or web developer building connectivity-aware applications
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- network-based security signals for fraud detection and identity verification
- telecommunications
- sim swap check
- edge computing
- sim swap fraud detection
- network apis
- verify phone number
- sim swap date retrieval
- 5g network quality monitoring and on-demand qos enhancement
- device status
- at&t
- connectivity
- network-based fraud prevention and authentication using sim swap and number verification
- get date of most recent sim swap
- check sim swap
- security
- number verify
- Security Developer
- get the exact date and time of the most recent sim swap for a phone number
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- developer implementing passwordless or frictionless mobile authentication
- sim swap
- mobile network-based authentication without otp
- developer building fraud prevention and identity verification using network signals
- sim swap get date
slug: network-security
tags:
- AT&T
- Security
- Fraud Prevention
- Authentication
- CAMARA
- 5G
tools:
- description: Check if an AT&T subscriber's SIM card has been swapped recently to detect fraud
  hints:
    idempotent: true
    readOnly: true
  name: sim-swap-check
- description: Get the exact date and time of the most recent SIM swap for a phone number
  hints:
    idempotent: true
    readOnly: true
  name: sim-swap-get-date
- description: Silently verify that a mobile device is associated with a phone number using the AT&T network
  hints:
    idempotent: true
    readOnly: true
  name: number-verify
---
