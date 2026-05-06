---
categories: []
consumed_apis: []
description: The Smart Device Management (SDM) API is a REST API that allows developers to manage Google Nest devices. It provides access to device traits and commands for thermostats, cameras, doorbells, and displays. The API uses a trait-based model where each device exposes traits that describe its capabilities and current state, and accepts commands to change device settings.
layout: capability
name: Google Nest Smart Device Management API
operations:
- description: Google Nest Smart Device Management List Devices
  method: GET
  name: listdevices
  path: /enterprises/{enterpriseId}/devices
- description: Google Nest Smart Device Management Get Device
  method: GET
  name: getdevice
  path: /enterprises/{enterpriseId}/devices/{deviceId}
- description: Google Nest Smart Device Management Execute Device Command
  method: POST
  name: executedevicecommand
  path: /enterprises/{enterpriseId}/devices/{deviceId}:executeCommand
- description: Google Nest Smart Device Management List Structures
  method: GET
  name: liststructures
  path: /enterprises/{enterpriseId}/structures
- description: Google Nest Smart Device Management List Rooms
  method: GET
  name: listrooms
  path: /enterprises/{enterpriseId}/structures/{structureId}/rooms
personas: []
provider_name: Google Nest Smart Device Management
provider_slug: google-nest
search_terms:
- google nest smart device management get device
- listrooms
- camera
- google nest
- device management
- listdevices
- iot
- google
- google nest smart device management list rooms
- smart home
- google nest smart device management execute device command
- google nest smart device management list structures
- liststructures
- executedevicecommand
- getdevice
- google nest smart device management list devices
- api
- doorbell
- nest
- thermostat
slug: google-nest-capability
source_filename: google-nest-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Nest Smart Device Management API\n  description: The Smart Device Management (SDM) API is a REST API that allows developers to manage Google Nest devices. It\n    provides access to device traits and commands for thermostats, cameras, doorbells, and displays. The API uses a trait-based\n    model where each device exposes traits that describe its capabilities and current state, and accepts commands to change\n    device settings.\n  tags:\n  - Google\n  - Nest\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-nest\n    baseUri: https://smartdevicemanagement.googleapis.com/v1\n    description: Google Nest Smart Device Management API HTTP API.\n    resources:\n    - name: enterprises-enterpriseid-devices\n      path: /enterprises/{enterpriseId}/devices\n      operations:\n      - name: listdevices\n        method: GET\n        description: Google Nest Smart\
  \ Device Management List Devices\n        inputParameters:\n        - name: enterpriseId\n          in: path\n          type: string\n          required: true\n          description: The enterprise (project) ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterpriseid-devices-deviceid\n      path: /enterprises/{enterpriseId}/devices/{deviceId}\n      operations:\n      - name: getdevice\n        method: GET\n        description: Google Nest Smart Device Management Get Device\n        inputParameters:\n        - name: enterpriseId\n          in: path\n          type: string\n          required: true\n        - name: deviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterpriseid-devices-deviceid-execut\n\
  \      path: /enterprises/{enterpriseId}/devices/{deviceId}:executeCommand\n      operations:\n      - name: executedevicecommand\n        method: POST\n        description: Google Nest Smart Device Management Execute Device Command\n        inputParameters:\n        - name: enterpriseId\n          in: path\n          type: string\n          required: true\n        - name: deviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterpriseid-structures\n      path: /enterprises/{enterpriseId}/structures\n      operations:\n      - name: liststructures\n        method: GET\n        description: Google Nest Smart Device Management List Structures\n        inputParameters:\n        - name: enterpriseId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: enterprises-enterpriseid-structures-structureid-\n      path: /enterprises/{enterpriseId}/structures/{structureId}/rooms\n      operations:\n      - name: listrooms\n        method: GET\n        description: Google Nest Smart Device Management List Rooms\n        inputParameters:\n        - name: enterpriseId\n          in: path\n          type: string\n          required: true\n        - name: structureId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-nest-rest\n    description: REST adapter for Google Nest Smart Device Management API.\n    resources:\n    - path: /enterprises/{enterpriseId}/devices\n      name: listdevices\n      operations:\n      - method: GET\n        name: listdevices\n\
  \        description: Google Nest Smart Device Management List Devices\n        call: google-nest.listdevices\n        with:\n          enterpriseId: rest.enterpriseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterpriseId}/devices/{deviceId}\n      name: getdevice\n      operations:\n      - method: GET\n        name: getdevice\n        description: Google Nest Smart Device Management Get Device\n        call: google-nest.getdevice\n        with:\n          enterpriseId: rest.enterpriseId\n          deviceId: rest.deviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterpriseId}/devices/{deviceId}:executeCommand\n      name: executedevicecommand\n      operations:\n      - method: POST\n        name: executedevicecommand\n        description: Google Nest Smart Device Management Execute Device Command\n        call: google-nest.executedevicecommand\n        with:\n     \
  \     enterpriseId: rest.enterpriseId\n          deviceId: rest.deviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterpriseId}/structures\n      name: liststructures\n      operations:\n      - method: GET\n        name: liststructures\n        description: Google Nest Smart Device Management List Structures\n        call: google-nest.liststructures\n        with:\n          enterpriseId: rest.enterpriseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /enterprises/{enterpriseId}/structures/{structureId}/rooms\n      name: listrooms\n      operations:\n      - method: GET\n        name: listrooms\n        description: Google Nest Smart Device Management List Rooms\n        call: google-nest.listrooms\n        with:\n          enterpriseId: rest.enterpriseId\n          structureId: rest.structureId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9090\n    namespace: google-nest-mcp\n    transport: http\n    description: MCP adapter for Google Nest Smart Device Management API for AI agent use.\n    tools:\n    - name: listdevices\n      description: Google Nest Smart Device Management List Devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-nest.listdevices\n      with:\n        enterpriseId: tools.enterpriseId\n      inputParameters:\n      - name: enterpriseId\n        type: string\n        description: The enterprise (project) ID.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdevice\n      description: Google Nest Smart Device Management Get Device\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-nest.getdevice\n      with:\n        enterpriseId: tools.enterpriseId\n        deviceId: tools.deviceId\n      inputParameters:\n\
  \      - name: enterpriseId\n        type: string\n        description: enterpriseId\n        required: true\n      - name: deviceId\n        type: string\n        description: deviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executedevicecommand\n      description: Google Nest Smart Device Management Execute Device Command\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-nest.executedevicecommand\n      with:\n        enterpriseId: tools.enterpriseId\n        deviceId: tools.deviceId\n      inputParameters:\n      - name: enterpriseId\n        type: string\n        description: enterpriseId\n        required: true\n      - name: deviceId\n        type: string\n        description: deviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststructures\n      description: Google Nest Smart Device Management\
  \ List Structures\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-nest.liststructures\n      with:\n        enterpriseId: tools.enterpriseId\n      inputParameters:\n      - name: enterpriseId\n        type: string\n        description: enterpriseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrooms\n      description: Google Nest Smart Device Management List Rooms\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-nest.listrooms\n      with:\n        enterpriseId: tools.enterpriseId\n        structureId: tools.structureId\n      inputParameters:\n      - name: enterpriseId\n        type: string\n        description: enterpriseId\n        required: true\n      - name: structureId\n        type: string\n        description: structureId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-nest/refs/heads/main/capabilities/google-nest-capability.yaml
tags:
- Google
- Nest
- API
tools:
- description: Google Nest Smart Device Management List Devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdevices
- description: Google Nest Smart Device Management Get Device
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdevice
- description: Google Nest Smart Device Management Execute Device Command
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executedevicecommand
- description: Google Nest Smart Device Management List Structures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststructures
- description: Google Nest Smart Device Management List Rooms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrooms
---
