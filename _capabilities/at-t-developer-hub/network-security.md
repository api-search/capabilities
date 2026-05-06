---
categories:
- security
consumed_apis: []
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
- Identity Developer
- get date of most recent sim swap
- fraud prevention
- device status
- sim swap get date
- check sim swap
- check if an at&t subscriber's sim card has been swapped recently to detect fraud
- Security Developer
- mobile or web developer building connectivity-aware applications
- security
- 5g
- silently verify device phone number
- sim swap date retrieval
- phone number verification via network
- silently verify that a mobile device is associated with a phone number using the at&t network
- check if a sim card has been swapped recently
- network-based fraud prevention and authentication using sim swap and number verification
- edge computing
- developer building fraud prevention and identity verification using network signals
- connectivity
- retrieve sim swap date
- verify phone number
- sim swap check
- get the exact date and time of the most recent sim swap for a phone number
- network apis
- telecommunications
- network-based security signals for fraud detection and identity verification
- camara
- authentication
- at&t
- 5g network quality monitoring and on-demand qos enhancement
- number verify
- engineer managing iot device connectivity and optimizing 5g performance for industrial applications
- IoT Engineer
- sim swap fraud detection
- App Developer
- 5g connectivity monitoring and qos optimization using device status and quality on demand
- mobile network-based authentication without otp
- developer implementing passwordless or frictionless mobile authentication
- sim swap
slug: network-security
source_filename: network-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AT&T Network Security\n  description: Unified network-based security capability combining SIM Swap detection, Number Verification, and Mobility Threat\n    Detection APIs. Used by developers building fraud prevention, authentication, and security monitoring applications leveraging\n    AT&T network signals.\n  tags:\n  - AT&T\n  - Security\n  - Fraud Prevention\n  - Authentication\n  - CAMARA\n  - 5G\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ATT_NETWORK_API_TOKEN: ATT_NETWORK_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: att-sim-swap\n    baseUri: https://api.att.com/camara/sim-swap/v1\n    description: AT&T SIM Swap detection API\n    authentication:\n      type: bearer\n      token: '{{ATT_NETWORK_API_TOKEN}}'\n    resources:\n    - name: sim-swap-check\n      path: /check\n      description: SIM swap detection\n      operations:\n      - name: check-sim-swap\n  \
  \      method: POST\n        description: Check if SIM has been swapped recently\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n            maxAge: '{{tools.maxAge}}'\n    - name: sim-swap-date\n      path: /retrieve-date\n      description: SIM swap date retrieval\n      operations:\n      - name: retrieve-sim-swap-date\n        method: POST\n        description: Retrieve date of most recent SIM swap\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n  - type: http\n    namespace: att-number-verification\n    baseUri: https://api.att.com/camara/number-verification/v1\n    description: AT&T Number Verification API\n    authentication:\n\
  \      type: bearer\n      token: '{{ATT_NETWORK_API_TOKEN}}'\n    resources:\n    - name: verify\n      path: /verify\n      description: Phone number verification\n      operations:\n      - name: verify-phone-number\n        method: POST\n        description: Silently verify device phone number via network\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: att-network-security-api\n    description: Unified REST API for AT&T network-based security and fraud prevention.\n    resources:\n    - path: /v1/sim-swap/check\n      name: sim-swap\n      description: SIM swap fraud detection\n      operations:\n      - method: POST\n        name: check-sim-swap\n        description: Check if a SIM card has been swapped recently\n        call: att-sim-swap.check-sim-swap\n\
  \        with:\n          phoneNumber: rest.phoneNumber\n          maxAge: rest.maxAge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sim-swap/date\n      name: sim-swap-date\n      description: SIM swap date retrieval\n      operations:\n      - method: POST\n        name: retrieve-sim-swap-date\n        description: Get date of most recent SIM swap\n        call: att-sim-swap.retrieve-sim-swap-date\n        with:\n          phoneNumber: rest.phoneNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/number-verification/verify\n      name: number-verification\n      description: Phone number verification via network\n      operations:\n      - method: POST\n        name: verify-phone-number\n        description: Silently verify device phone number\n        call: att-number-verification.verify-phone-number\n        with:\n          phoneNumber: rest.phoneNumber\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: att-network-security-mcp\n    transport: http\n    description: MCP server for AI-assisted AT&T network security and fraud prevention operations.\n    tools:\n    - name: sim-swap-check\n      description: Check if an AT&T subscriber's SIM card has been swapped recently to detect fraud\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-sim-swap.check-sim-swap\n      with:\n        phoneNumber: tools.phoneNumber\n        maxAge: tools.maxAge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sim-swap-get-date\n      description: Get the exact date and time of the most recent SIM swap for a phone number\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-sim-swap.retrieve-sim-swap-date\n      with:\n        phoneNumber: tools.phoneNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ number-verify\n      description: Silently verify that a mobile device is associated with a phone number using the AT&T network\n      hints:\n        readOnly: true\n        idempotent: true\n      call: att-number-verification.verify-phone-number\n      with:\n        phoneNumber: tools.phoneNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
