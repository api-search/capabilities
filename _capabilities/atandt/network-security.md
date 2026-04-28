---
categories:
- security
consumed_apis:
- att-network-apis
description: Workflow capability combining AT&T CAMARA network APIs for fraud prevention and identity verification. Integrates SIM Swap detection and Number Verification for developers building secure authentication flows.
layout: capability
name: AT&T Network Security
operations:
- description: Check if SIM swap has occurred
  method: POST
  name: check-sim-swap
  path: /v1/security/sim-swap/check
- description: Verify device phone number silently
  method: POST
  name: verify-number
  path: /v1/security/number/verify
personas: []
provider_name: AT&T
provider_slug: atandt
search_terms:
- retrieve the most recent sim swap date for an at&t phone number
- fortune 100
- engineer integrating enterprise wireline services and ebonding systems
- check sim swap
- Security Developer
- wireline service ordering and qualification
- developer integrating at&t enterprise connectivity and ebonding apis
- at&t
- sms messaging and oauth authentication for consumer and business applications
- camara
- Identity Developer
- device status, roaming, and qos management
- silently verify that a device is using a specific at&t phone number without otp
- mobile or web developer building consumer applications on at&t apis
- telecommunications
- silent phone number verification
- Enterprise Developer
- developer building fraud prevention and identity verification using at&t network signals
- enterprise
- check if sim swap has occurred
- att retrieve sim swap date
- check if a sim swap has occurred for an at&t phone number to detect fraud
- mobile virtual network operator managing subscribers on at&t infrastructure
- network-based fraud detection and threat intelligence
- att check sim swap
- verify number
- 5g
- security
- fraud prevention
- att verify phone number
- verify device phone number silently
- network
- developer implementing frictionless mobile authentication via at&t network
- broadband
- App Developer
- camara network-based fraud prevention using sim swap and number verification
- number verification
- sim swap
- oauth and network-based authentication
- sim swap fraud detection
- wireline
- sms and in-app messaging services
- wireless
slug: network-security
tags:
- AT&T
- Security
- Fraud Prevention
- SIM Swap
- Number Verification
- CAMARA
tools:
- description: Check if a SIM swap has occurred for an AT&T phone number to detect fraud
  hints:
    idempotent: true
    readOnly: true
  name: att-check-sim-swap
- description: Retrieve the most recent SIM swap date for an AT&T phone number
  hints:
    idempotent: true
    readOnly: true
  name: att-retrieve-sim-swap-date
- description: Silently verify that a device is using a specific AT&T phone number without OTP
  hints:
    idempotent: true
    readOnly: true
  name: att-verify-phone-number
---
