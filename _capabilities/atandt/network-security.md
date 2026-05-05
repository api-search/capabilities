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
- sms messaging and oauth authentication for consumer and business applications
- App Developer
- oauth and network-based authentication
- security
- fortune 100
- silent phone number verification
- enterprise
- wireline service ordering and qualification
- check if sim swap has occurred
- att check sim swap
- att retrieve sim swap date
- broadband
- network
- att verify phone number
- number verification
- check sim swap
- Enterprise Developer
- mobile or web developer building consumer applications on at&t apis
- Identity Developer
- telecommunications
- fraud prevention
- wireless
- check if a sim swap has occurred for an at&t phone number to detect fraud
- device status, roaming, and qos management
- wireline
- network-based fraud detection and threat intelligence
- sms and in-app messaging services
- verify number
- retrieve the most recent sim swap date for an at&t phone number
- developer implementing frictionless mobile authentication via at&t network
- sim swap fraud detection
- camara
- Security Developer
- camara network-based fraud prevention using sim swap and number verification
- developer building fraud prevention and identity verification using at&t network signals
- mobile virtual network operator managing subscribers on at&t infrastructure
- developer integrating at&t enterprise connectivity and ebonding apis
- 5g
- verify device phone number silently
- sim swap
- at&t
- silently verify that a device is using a specific at&t phone number without otp
- engineer integrating enterprise wireline services and ebonding systems
slug: network-security
source_filename: network-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T Network Security\"\n  description: \"Workflow capability combining AT&T CAMARA network APIs for fraud prevention and identity verification. Integrates SIM Swap detection and Number Verification for developers building secure authentication flows.\"\n  tags:\n    - AT&T\n    - Security\n    - Fraud Prevention\n    - SIM Swap\n    - Number Verification\n    - CAMARA\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_NETWORK_API_TOKEN: ATT_NETWORK_API_TOKEN\n\ncapability:\n  consumes:\n    - import: att-network-apis\n      location: ./shared/network-apis.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: att-network-security-api\n      description: \"Unified REST API for AT&T network security and fraud prevention.\"\n      resources:\n        - path: /v1/security/sim-swap/check\n          name: sim-swap-check\n          description: \"SIM swap fraud\
  \ detection\"\n          operations:\n            - method: POST\n              name: check-sim-swap\n              description: \"Check if SIM swap has occurred\"\n              call: \"att-network-apis.check-sim-swap\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n                maxAge: \"rest.maxAge\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/security/number/verify\n          name: number-verify\n          description: \"Silent phone number verification\"\n          operations:\n            - method: POST\n              name: verify-number\n              description: \"Verify device phone number silently\"\n              call: \"att-network-apis.verify-number\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace:\
  \ att-network-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AT&T network security and fraud prevention.\"\n      tools:\n        - name: att-check-sim-swap\n          description: \"Check if a SIM swap has occurred for an AT&T phone number to detect fraud\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-network-apis.check-sim-swap\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n            maxAge: \"tools.maxAge\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: att-retrieve-sim-swap-date\n          description: \"Retrieve the most recent SIM swap date for an AT&T phone number\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-network-apis.retrieve-sim-swap-date\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: att-verify-phone-number\n          description: \"Silently verify that a device is using a specific AT&T phone number without OTP\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-network-apis.verify-number\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atandt/refs/heads/main/capabilities/network-security.yaml
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
