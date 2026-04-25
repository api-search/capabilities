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
- sim swap date retrieval
- IoT Engineer
- fraud prevention
- connectivity
- sim swap fraud detection
- App Developer
- 5g network quality monitoring and on-demand qos enhancement
- retrieve sim swap date
- developer building fraud prevention and identity verification using network signals
- phone number verification via network
- sim swap get date
- number verify
- network-based fraud prevention and authentication using sim swap and number verification
- get the exact date and time of the most recent sim swap for a phone number
- network-based security signals for fraud detection and identity verification
- authentication
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- verify phone number
- sim swap check
- mobile or web developer building connectivity-aware applications
- get date of most recent sim swap
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- check if a sim card has been swapped recently
- device status
- security
- 5g
- check if an at&t subscriber's sim card has been swapped recently to detect fraud
- telecommunications
- developer implementing passwordless or frictionless mobile authentication
- silently verify device phone number
- silently verify that a mobile device is associated with a phone number using the at&t network
- mobile network-based authentication without otp
- check sim swap
- sim swap
- camara
- at&t
- Security Developer
- network apis
- Identity Developer
- edge computing
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
