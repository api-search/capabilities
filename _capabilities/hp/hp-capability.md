---
categories: []
consumed_apis: []
description: The HP PrintOS Device API enables device manufacturers and print shop IT developers to attach their devices to the PrintOS Cloud Platform and interact with platform services.
layout: capability
name: HP PrintOS Device API
operations:
- description: List Devices
  method: GET
  name: listdevices
  path: /devices
- description: Provision Device
  method: POST
  name: provisiondevice
  path: /devices
- description: Update Device Status
  method: PUT
  name: updatedevicestatus
  path: /devices/{deviceId}/status
personas: []
provider_name: HP
provider_slug: hp
search_terms:
- device management
- listdevices
- update device status
- technology
- list devices
- provisiondevice
- api
- printing
- hp
- updatedevicestatus
- computer hardware
- provision device
slug: hp-capability
source_filename: hp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HP PrintOS Device API\n  description: The HP PrintOS Device API enables device manufacturers and print shop IT developers to attach their devices\n    to the PrintOS Cloud Platform and interact with platform services.\n  tags:\n  - Hp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hp\n    baseUri: https://printos.api.hp.com\n    description: HP PrintOS Device API HTTP API.\n    resources:\n    - name: devices\n      path: /devices\n      operations:\n      - name: listdevices\n        method: GET\n        description: List Devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: provisiondevice\n        method: POST\n        description: Provision Device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: devices-deviceid-status\n      path: /devices/{deviceId}/status\n      operations:\n      - name: updatedevicestatus\n        method: PUT\n        description: Update Device Status\n        inputParameters:\n        - name: deviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hp-rest\n    description: REST adapter for HP PrintOS Device API.\n    resources:\n    - path: /devices\n      name: listdevices\n      operations:\n      - method: GET\n        name: listdevices\n        description: List Devices\n        call: hp.listdevices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /devices\n      name: provisiondevice\n      operations:\n      - method: POST\n        name: provisiondevice\n        description: Provision Device\n\
  \        call: hp.provisiondevice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /devices/{deviceId}/status\n      name: updatedevicestatus\n      operations:\n      - method: PUT\n        name: updatedevicestatus\n        description: Update Device Status\n        call: hp.updatedevicestatus\n        with:\n          deviceId: rest.deviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hp-mcp\n    transport: http\n    description: MCP adapter for HP PrintOS Device API for AI agent use.\n    tools:\n    - name: listdevices\n      description: List Devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: hp.listdevices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provisiondevice\n      description: Provision Device\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: hp.provisiondevice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedevicestatus\n      description: Update Device Status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: hp.updatedevicestatus\n      with:\n        deviceId: tools.deviceId\n      inputParameters:\n      - name: deviceId\n        type: string\n        description: deviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hp/refs/heads/main/capabilities/hp-capability.yaml
tags:
- Hp
- API
tools:
- description: List Devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevices
- description: Provision Device
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provisiondevice
- description: Update Device Status
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedevicestatus
---
