---
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
- device status, roaming, and qos management
- App Developer
- Enterprise Developer
- verify number
- check if a sim swap has occurred for an at&t phone number to detect fraud
- camara network-based fraud prevention using sim swap and number verification
- oauth and network-based authentication
- 5g
- retrieve the most recent sim swap date for an at&t phone number
- sim swap fraud detection
- mobile or web developer building consumer applications on at&t apis
- mobile virtual network operator managing subscribers on at&t infrastructure
- Security Developer
- silent phone number verification
- developer implementing frictionless mobile authentication via at&t network
- network
- enterprise
- verify device phone number silently
- sim swap
- camara
- fraud prevention
- broadband
- sms and in-app messaging services
- att check sim swap
- fortune 100
- wireline service ordering and qualification
- telecommunications
- wireless
- silently verify that a device is using a specific at&t phone number without otp
- att verify phone number
- check if sim swap has occurred
- developer integrating at&t enterprise connectivity and ebonding apis
- security
- check sim swap
- sms messaging and oauth authentication for consumer and business applications
- number verification
- Identity Developer
- wireline
- engineer integrating enterprise wireline services and ebonding systems
- network-based fraud detection and threat intelligence
- att retrieve sim swap date
- developer building fraud prevention and identity verification using at&t network signals
- at&t
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
