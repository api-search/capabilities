---
categories:
- security
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
- get the exact date and time of the most recent sim swap for a phone number
- check if an at&t subscriber's sim card has been swapped recently to detect fraud
- mobile network-based authentication without otp
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- verify phone number
- telecommunications
- check sim swap
- silently verify device phone number
- silently verify that a mobile device is associated with a phone number using the at&t network
- authentication
- edge computing
- Security Developer
- sim swap check
- mobile or web developer building connectivity-aware applications
- sim swap get date
- network-based fraud prevention and authentication using sim swap and number verification
- at&t
- 5g
- check if a sim card has been swapped recently
- connectivity
- sim swap date retrieval
- 5g network quality monitoring and on-demand qos enhancement
- device status
- fraud prevention
- App Developer
- retrieve sim swap date
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- network apis
- camara
- Identity Developer
- developer implementing passwordless or frictionless mobile authentication
- get date of most recent sim swap
- IoT Engineer
- network-based security signals for fraud detection and identity verification
- sim swap fraud detection
- phone number verification via network
- number verify
- sim swap
- developer building fraud prevention and identity verification using network signals
- security
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
