---
categories: []
consumed_apis: []
description: The Johnson & Johnson LifeScan API provides programmatic access to blood glucose monitoring data and diabetes management tools. LifeScan develops the OneTouch brand of blood glucose meters, and this API enables developers to integrate glucose monitoring data into health applications and wellness platforms for improved diabetes management.
layout: capability
name: Johnson & Johnson LifeScan API
operations:
- description: List glucose readings
  method: GET
  name: listglucosereadings
  path: /glucose-readings
- description: List devices
  method: GET
  name: listdevices
  path: /devices
- description: List patients
  method: GET
  name: listpatients
  path: /patients
personas: []
provider_name: Johnson & Johnson
provider_slug: johnson-and-johnson
search_terms:
- pharmaceuticals
- medical devices
- listdevices
- healthcare
- listglucosereadings
- diabetes
- blood glucose
- list devices
- api
- and
- johnson
- list patients
- list glucose readings
- listpatients
slug: johnson-and-johnson-capability
source_filename: johnson-and-johnson-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Johnson & Johnson LifeScan API\n  description: The Johnson & Johnson LifeScan API provides programmatic access to blood glucose monitoring data and diabetes\n    management tools. LifeScan develops the OneTouch brand of blood glucose meters, and this API enables developers to integrate\n    glucose monitoring data into health applications and wellness platforms for improved diabetes management.\n  tags:\n  - Johnson\n  - And\n  - Johnson\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: johnson-and-johnson\n    baseUri: https://api.lifescan.com\n    description: Johnson & Johnson LifeScan API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JOHNSON_AND_JOHNSON_TOKEN}}'\n    resources:\n    - name: glucose-readings\n      path: /glucose-readings\n      operations:\n      - name: listglucosereadings\n        method: GET\n        description: List glucose\
  \ readings\n        inputParameters:\n        - name: patientId\n          in: query\n          type: string\n          required: true\n          description: The unique identifier of the patient.\n        - name: startDate\n          in: query\n          type: string\n          description: Filter readings from this date (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          description: Filter readings up to this date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /devices\n      operations:\n      - name: listdevices\n        method: GET\n        description: List devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: patients\n      path: /patients\n      operations:\n      - name: listpatients\n        method: GET\n        description:\
  \ List patients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: johnson-and-johnson-rest\n    description: REST adapter for Johnson & Johnson LifeScan API.\n    resources:\n    - path: /glucose-readings\n      name: listglucosereadings\n      operations:\n      - method: GET\n        name: listglucosereadings\n        description: List glucose readings\n        call: johnson-and-johnson.listglucosereadings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /devices\n      name: listdevices\n      operations:\n      - method: GET\n        name: listdevices\n        description: List devices\n        call: johnson-and-johnson.listdevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /patients\n      name: listpatients\n      operations:\n      - method: GET\n        name: listpatients\n\
  \        description: List patients\n        call: johnson-and-johnson.listpatients\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: johnson-and-johnson-mcp\n    transport: http\n    description: MCP adapter for Johnson & Johnson LifeScan API for AI agent use.\n    tools:\n    - name: listglucosereadings\n      description: List glucose readings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: johnson-and-johnson.listglucosereadings\n      with:\n        patientId: tools.patientId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: patientId\n        type: string\n        description: The unique identifier of the patient.\n        required: true\n      - name: startDate\n        type: string\n        description: Filter readings from this date (ISO 8601).\n      - name: endDate\n        type: string\n    \
  \    description: Filter readings up to this date (ISO 8601).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdevices\n      description: List devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: johnson-and-johnson.listdevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpatients\n      description: List patients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: johnson-and-johnson.listpatients\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JOHNSON_AND_JOHNSON_TOKEN: JOHNSON_AND_JOHNSON_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/johnson-and-johnson/refs/heads/main/capabilities/johnson-and-johnson-capability.yaml
tags:
- Johnson
- And
- Johnson
- API
tools:
- description: List glucose readings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listglucosereadings
- description: List devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevices
- description: List patients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpatients
---
