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
- sim swap fraud detection
- sms and in-app messaging services
- enterprise
- Enterprise Developer
- oauth and network-based authentication
- sms messaging and oauth authentication for consumer and business applications
- Identity Developer
- sim swap
- developer building fraud prevention and identity verification using at&t network signals
- wireline service ordering and qualification
- telecommunications
- wireless
- att check sim swap
- verify number
- at&t
- silent phone number verification
- engineer integrating enterprise wireline services and ebonding systems
- broadband
- att retrieve sim swap date
- security
- mobile or web developer building consumer applications on at&t apis
- network
- App Developer
- camara
- check sim swap
- developer integrating at&t enterprise connectivity and ebonding apis
- check if sim swap has occurred
- number verification
- fortune 100
- Security Developer
- wireline
- fraud prevention
- developer implementing frictionless mobile authentication via at&t network
- camara network-based fraud prevention using sim swap and number verification
- att verify phone number
- mobile virtual network operator managing subscribers on at&t infrastructure
- silently verify that a device is using a specific at&t phone number without otp
- check if a sim swap has occurred for an at&t phone number to detect fraud
- 5g
- device status, roaming, and qos management
- verify device phone number silently
- network-based fraud detection and threat intelligence
- retrieve the most recent sim swap date for an at&t phone number
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
