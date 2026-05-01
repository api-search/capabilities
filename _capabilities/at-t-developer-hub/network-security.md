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
- get date of most recent sim swap
- Identity Developer
- at&t
- fraud prevention
- check sim swap
- developer building fraud prevention and identity verification using network signals
- silently verify that a mobile device is associated with a phone number using the at&t network
- developer implementing passwordless or frictionless mobile authentication
- camara
- sim swap check
- network-based security signals for fraud detection and identity verification
- network apis
- telecommunications
- authentication
- device status
- mobile network-based authentication without otp
- check if a sim card has been swapped recently
- App Developer
- number verify
- Security Developer
- check if an at&t subscriber's sim card has been swapped recently to detect fraud
- silently verify device phone number
- sim swap
- network-based fraud prevention and authentication using sim swap and number verification
- retrieve sim swap date
- sim swap fraud detection
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- connectivity
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- sim swap date retrieval
- edge computing
- security
- sim swap get date
- IoT Engineer
- phone number verification via network
- get the exact date and time of the most recent sim swap for a phone number
- 5g
- mobile or web developer building connectivity-aware applications
- verify phone number
- 5g network quality monitoring and on-demand qos enhancement
slug: network-security
source_filename: network-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AT&T Network Security\"\n  description: \"Unified network-based security capability combining SIM Swap detection, Number Verification, and Mobility Threat Detection APIs. Used by developers building fraud prevention, authentication, and security monitoring applications leveraging AT&T network signals.\"\n  tags:\n    - AT&T\n    - Security\n    - Fraud Prevention\n    - Authentication\n    - CAMARA\n    - 5G\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ATT_NETWORK_API_TOKEN: ATT_NETWORK_API_TOKEN\n\ncapability:\n  consumes:\n    - import: att-sim-swap\n      location: ./shared/sim-swap-api.yaml\n    - import: att-number-verification\n      location: ./shared/number-verification-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: att-network-security-api\n      description: \"Unified REST API for AT&T network-based security and fraud prevention.\"\
  \n      resources:\n        - path: /v1/sim-swap/check\n          name: sim-swap\n          description: \"SIM swap fraud detection\"\n          operations:\n            - method: POST\n              name: check-sim-swap\n              description: \"Check if a SIM card has been swapped recently\"\n              call: \"att-sim-swap.check-sim-swap\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n                maxAge: \"rest.maxAge\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sim-swap/date\n          name: sim-swap-date\n          description: \"SIM swap date retrieval\"\n          operations:\n            - method: POST\n              name: retrieve-sim-swap-date\n              description: \"Get date of most recent SIM swap\"\n              call: \"att-sim-swap.retrieve-sim-swap-date\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/number-verification/verify\n          name: number-verification\n          description: \"Phone number verification via network\"\n          operations:\n            - method: POST\n              name: verify-phone-number\n              description: \"Silently verify device phone number\"\n              call: \"att-number-verification.verify-phone-number\"\n              with:\n                phoneNumber: \"rest.phoneNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: att-network-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AT&T network security and fraud prevention operations.\"\n      tools:\n        - name: sim-swap-check\n          description: \"Check if an AT&T subscriber's SIM card has been swapped recently to detect fraud\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"att-sim-swap.check-sim-swap\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n            maxAge: \"tools.maxAge\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sim-swap-get-date\n          description: \"Get the exact date and time of the most recent SIM swap for a phone number\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-sim-swap.retrieve-sim-swap-date\"\n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: number-verify\n          description: \"Silently verify that a mobile device is associated with a phone number using the AT&T network\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"att-number-verification.verify-phone-number\"\
  \n          with:\n            phoneNumber: \"tools.phoneNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/at-t-developer-hub/refs/heads/main/capabilities/network-security.yaml
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
