---
categories: []
consumed_apis: []
description: Consent management API for the Chase FDX aggregation platform. Supports requesting, retrieving, updating, and revoking user consent for sharing account data with authorized data recipients.
layout: capability
name: Chase Account Aggregation User Consent API
operations:
- description: Create a consent request
  method: POST
  name: createconsent
  path: /consents
- description: List consents
  method: GET
  name: listconsents
  path: /consents
- description: Get a consent record
  method: GET
  name: getconsent
  path: /consents/{consentId}
- description: Revoke a consent
  method: DELETE
  name: revokeconsent
  path: /consents/{consentId}
personas: []
provider_name: Chase
provider_slug: chase
search_terms:
- listconsents
- revokeconsent
- revoke a consent
- fdx
- loyalty
- api
- rewards
- create a consent request
- getconsent
- account aggregation
- financial services
- credit cards
- list consents
- open banking
- banking
- get a consent record
- chase
- createconsent
- consent
- pay with points
slug: chase-capability
source_filename: chase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Chase Account Aggregation User Consent API\n  description: Consent management API for the Chase FDX aggregation platform. Supports requesting, retrieving, updating, and\n    revoking user consent for sharing account data with authorized data recipients.\n  tags:\n  - Chase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chase\n    baseUri: https://api.chase.com/aggregation/consent\n    description: Chase Account Aggregation User Consent API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHASE_TOKEN}}'\n    resources:\n    - name: consents\n      path: /consents\n      operations:\n      - name: createconsent\n        method: POST\n        description: Create a consent request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listconsents\n        method: GET\n\
  \        description: List consents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consents-consentid\n      path: /consents/{consentId}\n      operations:\n      - name: getconsent\n        method: GET\n        description: Get a consent record\n        inputParameters:\n        - name: consentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokeconsent\n        method: DELETE\n        description: Revoke a consent\n        inputParameters:\n        - name: consentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chase-rest\n\
  \    description: REST adapter for Chase Account Aggregation User Consent API.\n    resources:\n    - path: /consents\n      name: createconsent\n      operations:\n      - method: POST\n        name: createconsent\n        description: Create a consent request\n        call: chase.createconsent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consents\n      name: listconsents\n      operations:\n      - method: GET\n        name: listconsents\n        description: List consents\n        call: chase.listconsents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consents/{consentId}\n      name: getconsent\n      operations:\n      - method: GET\n        name: getconsent\n        description: Get a consent record\n        call: chase.getconsent\n        with:\n          consentId: rest.consentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consents/{consentId}\n     \
  \ name: revokeconsent\n      operations:\n      - method: DELETE\n        name: revokeconsent\n        description: Revoke a consent\n        call: chase.revokeconsent\n        with:\n          consentId: rest.consentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chase-mcp\n    transport: http\n    description: MCP adapter for Chase Account Aggregation User Consent API for AI agent use.\n    tools:\n    - name: createconsent\n      description: Create a consent request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chase.createconsent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconsents\n      description: List consents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chase.listconsents\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: getconsent\n      description: Get a consent record\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chase.getconsent\n      with:\n        consentId: tools.consentId\n      inputParameters:\n      - name: consentId\n        type: string\n        description: consentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeconsent\n      description: Revoke a consent\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: chase.revokeconsent\n      with:\n        consentId: tools.consentId\n      inputParameters:\n      - name: consentId\n        type: string\n        description: consentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHASE_TOKEN: CHASE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chase/refs/heads/main/capabilities/chase-capability.yaml
tags:
- Chase
- API
tools:
- description: Create a consent request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconsent
- description: List consents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconsents
- description: Get a consent record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsent
- description: Revoke a consent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeconsent
---
