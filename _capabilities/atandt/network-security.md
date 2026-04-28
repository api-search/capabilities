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
- fortune 100
- retrieve the most recent sim swap date for an at&t phone number
- developer building fraud prevention and identity verification using at&t network signals
- mobile virtual network operator managing subscribers on at&t infrastructure
- fraud prevention
- check if a sim swap has occurred for an at&t phone number to detect fraud
- network-based fraud detection and threat intelligence
- sms messaging and oauth authentication for consumer and business applications
- App Developer
- silently verify that a device is using a specific at&t phone number without otp
- camara network-based fraud prevention using sim swap and number verification
- mobile or web developer building consumer applications on at&t apis
- oauth and network-based authentication
- at&t
- Enterprise Developer
- wireline
- verify device phone number silently
- Identity Developer
- wireline service ordering and qualification
- att retrieve sim swap date
- wireless
- security
- 5g
- enterprise
- check if sim swap has occurred
- camara
- engineer integrating enterprise wireline services and ebonding systems
- telecommunications
- developer integrating at&t enterprise connectivity and ebonding apis
- silent phone number verification
- verify number
- Security Developer
- att check sim swap
- check sim swap
- number verification
- att verify phone number
- device status, roaming, and qos management
- developer implementing frictionless mobile authentication via at&t network
- sim swap
- network
- sms and in-app messaging services
- broadband
- sim swap fraud detection
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
