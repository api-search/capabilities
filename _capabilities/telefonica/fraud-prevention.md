---
categories: []
consumed_apis: []
description: Fraud prevention capability combining Telefónica's Number Verification, SIM Swap, KYC Match, and Location Verification APIs into a unified workflow. Enables financial services, e-commerce, and insurance companies to verify user identity, detect account takeover attempts, and validate location claims using Telefónica's carrier network data without compromising privacy.
layout: capability
name: Telefónica Fraud Prevention
operations:
- description: Verify a phone number matches the device's SIM connection.
  method: POST
  name: verify-phone-number
  path: /v1/verification/phone-number
- description: Check for recent SIM swap on a phone number.
  method: POST
  name: check-sim-swap
  path: /v1/verification/sim-swap
- description: Validate identity data against carrier records.
  method: POST
  name: match-kyc
  path: /v1/verification/kyc
- description: Verify device is within a geographic area.
  method: POST
  name: verify-location
  path: /v1/verification/location
personas: []
provider_name: Telefónica
provider_slug: telefonica
search_terms:
- check for recent sim swap on a phone number.
- phone number verification using carrier data.
- device location verification.
- kyc
- get the phone number associated with the user's current device connection (for passwordless login).
- check sim swap
- identity verification
- mobile network
- validate user identity data (name, birthdate, address, email) against telefónica carrier records for kyc compliance.
- get the date of the most recent sim swap for detailed fraud investigation.
- authentication
- verify phone number
- get device phone number
- location services
- validate identity data against carrier records.
- verify device location
- get sim swap date
- telecommunications
- verify location
- financial services
- check if a sim swap fraud attempt occurred recently on a phone number.
- fraud prevention
- camara
- match kyc identity
- verify that a user's device is present within a specified geographic area using network data.
- open gateway
- telefónica
- kyc identity data matching.
- verify a phone number matches the device's sim connection.
- verify that a user's phone number matches their device's sim card connection using telefónica carrier data.
- verify device is within a geographic area.
- sim swap fraud detection.
- match kyc
slug: fraud-prevention
source_filename: fraud-prevention.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefónica Fraud Prevention\n  description: Fraud prevention capability combining Telefónica's Number Verification, SIM Swap, KYC Match, and Location Verification\n    APIs into a unified workflow. Enables financial services, e-commerce, and insurance companies to verify user identity,\n    detect account takeover attempts, and validate location claims using Telefónica's carrier network data without compromising\n    privacy.\n  tags:\n  - Telefónica\n  - Fraud Prevention\n  - Authentication\n  - Identity Verification\n  - KYC\n  - Financial Services\n  - CAMARA\n  - Open Gateway\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFONICA_ACCESS_TOKEN: TELEFONICA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: telefonica-number-verification\n    baseUri: https://opengateway.telefonica.com/v1\n    description: Telefónica Number Verification API via Open Gateway.\n    authentication:\n\
  \      type: bearer\n      token: '{{TELEFONICA_ACCESS_TOKEN}}'\n    resources:\n    - name: number-verification\n      path: /number-verification\n      description: Mobile number verification endpoints.\n      operations:\n      - name: verify-phone-number\n        method: POST\n        description: Verify that the device is connected via the specified phone number.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-phone-number\n        method: POST\n        description: Get the phone number associated with the device connection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telefonica-sim-swap\n    baseUri: https://opengateway.telefonica.com/v1\n    description: Telefónica SIM\
  \ Swap API via Open Gateway.\n    authentication:\n      type: bearer\n      token: '{{TELEFONICA_ACCESS_TOKEN}}'\n    resources:\n    - name: sim-swap\n      path: /sim-swap\n      description: SIM swap detection endpoints.\n      operations:\n      - name: check-sim-swap\n        method: POST\n        description: Check whether a recent SIM swap occurred on a phone number.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n            maxAge: '{{tools.maxAge}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sim-swap-date\n        method: POST\n        description: Get the date of the most recent SIM swap.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  - type: http\n    namespace: telefonica-kyc\n    baseUri: https://opengateway.telefonica.com/v1\n    description: Telefónica KYC Match API via Open Gateway.\n    authentication:\n      type: bearer\n      token: '{{TELEFONICA_ACCESS_TOKEN}}'\n    resources:\n    - name: kyc-match\n      path: /kyc-match\n      description: Know Your Customer identity matching endpoint.\n      operations:\n      - name: match-kyc\n        method: POST\n        description: Validate identity data against carrier records.\n        body:\n          type: json\n          data:\n            phoneNumber: '{{tools.phoneNumber}}'\n            givenName: '{{tools.givenName}}'\n            familyName: '{{tools.familyName}}'\n            birthdate: '{{tools.birthdate}}'\n            email: '{{tools.email}}'\n            address: '{{tools.address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: telefonica-location\n\
  \    baseUri: https://opengateway.telefonica.com/v1\n    description: Telefónica Location Verification API via Open Gateway.\n    authentication:\n      type: bearer\n      token: '{{TELEFONICA_ACCESS_TOKEN}}'\n    resources:\n    - name: location-verification\n      path: /location-verification\n      description: Device location verification endpoint.\n      operations:\n      - name: verify-device-location\n        method: POST\n        description: Verify whether a device is within a specified geographic area.\n        body:\n          type: json\n          data:\n            device: '{{tools.device}}'\n            area: '{{tools.area}}'\n            maxAge: '{{tools.maxAge}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: telefonica-fraud-api\n    description: Unified REST API for Telefónica fraud prevention workflows.\n    resources:\n    - path:\
  \ /v1/verification/phone-number\n      name: phone-number-verification\n      description: Phone number verification using carrier data.\n      operations:\n      - method: POST\n        name: verify-phone-number\n        description: Verify a phone number matches the device's SIM connection.\n        call: telefonica-number-verification.verify-phone-number\n        with:\n          phoneNumber: rest.phoneNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verification/sim-swap\n      name: sim-swap-check\n      description: SIM swap fraud detection.\n      operations:\n      - method: POST\n        name: check-sim-swap\n        description: Check for recent SIM swap on a phone number.\n        call: telefonica-sim-swap.check-sim-swap\n        with:\n          phoneNumber: rest.phoneNumber\n          maxAge: rest.maxAge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verification/kyc\n      name: kyc-match\n\
  \      description: KYC identity data matching.\n      operations:\n      - method: POST\n        name: match-kyc\n        description: Validate identity data against carrier records.\n        call: telefonica-kyc.match-kyc\n        with:\n          phoneNumber: rest.phoneNumber\n          givenName: rest.givenName\n          familyName: rest.familyName\n          birthdate: rest.birthdate\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/verification/location\n      name: location-verification\n      description: Device location verification.\n      operations:\n      - method: POST\n        name: verify-location\n        description: Verify device is within a geographic area.\n        call: telefonica-location.verify-device-location\n        with:\n          device: rest.device\n          area: rest.area\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace:\
  \ telefonica-fraud-mcp\n    transport: http\n    description: MCP server for AI-assisted Telefónica fraud prevention workflows.\n    tools:\n    - name: verify-phone-number\n      description: Verify that a user's phone number matches their device's SIM card connection using Telefónica carrier data.\n      hints:\n        readOnly: true\n      call: telefonica-number-verification.verify-phone-number\n      with:\n        phoneNumber: tools.phoneNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device-phone-number\n      description: Get the phone number associated with the user's current device connection (for passwordless login).\n      hints:\n        readOnly: true\n      call: telefonica-number-verification.get-phone-number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-sim-swap\n      description: Check if a SIM swap fraud attempt occurred recently on a phone number.\n      hints:\n        readOnly:\
  \ true\n      call: telefonica-sim-swap.check-sim-swap\n      with:\n        phoneNumber: tools.phoneNumber\n        maxAge: tools.maxAge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sim-swap-date\n      description: Get the date of the most recent SIM swap for detailed fraud investigation.\n      hints:\n        readOnly: true\n      call: telefonica-sim-swap.get-sim-swap-date\n      with:\n        phoneNumber: tools.phoneNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: match-kyc-identity\n      description: Validate user identity data (name, birthdate, address, email) against Telefónica carrier records for KYC\n        compliance.\n      hints:\n        readOnly: true\n      call: telefonica-kyc.match-kyc\n      with:\n        phoneNumber: tools.phoneNumber\n        givenName: tools.givenName\n        familyName: tools.familyName\n        birthdate: tools.birthdate\n        email: tools.email\n        address:\
  \ tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-device-location\n      description: Verify that a user's device is present within a specified geographic area using network data.\n      hints:\n        readOnly: true\n      call: telefonica-location.verify-device-location\n      with:\n        device: tools.device\n        area: tools.area\n        maxAge: tools.maxAge\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefonica/refs/heads/main/capabilities/fraud-prevention.yaml
tags:
- Telefónica
- Fraud Prevention
- Authentication
- Identity Verification
- KYC
- Financial Services
- CAMARA
- Open Gateway
tools:
- description: Verify that a user's phone number matches their device's SIM card connection using Telefónica carrier data.
  hints:
    readOnly: true
  name: verify-phone-number
- description: Get the phone number associated with the user's current device connection (for passwordless login).
  hints:
    readOnly: true
  name: get-device-phone-number
- description: Check if a SIM swap fraud attempt occurred recently on a phone number.
  hints:
    readOnly: true
  name: check-sim-swap
- description: Get the date of the most recent SIM swap for detailed fraud investigation.
  hints:
    readOnly: true
  name: get-sim-swap-date
- description: Validate user identity data (name, birthdate, address, email) against Telefónica carrier records for KYC compliance.
  hints:
    readOnly: true
  name: match-kyc-identity
- description: Verify that a user's device is present within a specified geographic area using network data.
  hints:
    readOnly: true
  name: verify-device-location
---
