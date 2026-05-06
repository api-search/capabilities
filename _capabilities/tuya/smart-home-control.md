---
categories: []
consumed_apis: []
description: IoT device management and control capability for smart home applications. Combines device querying, real-time status monitoring, device commands, and operation log analysis. Used by smart home app developers, facility managers, and IoT platform integrators to monitor and control devices such as lights, thermostats, sensors, and appliances.
layout: capability
name: Tuya Smart Home Control
operations:
- description: List all devices in the project
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get device details and current state
  method: GET
  name: get-device
  path: /v1/devices/{device_id}
- description: Get current status of all data points
  method: GET
  name: get-device-status
  path: /v1/devices/{device_id}/status
- description: Control a device
  method: POST
  name: send-commands
  path: /v1/devices/{device_id}/commands
- description: Get operation logs for a device
  method: GET
  name: get-device-logs
  path: /v1/devices/{device_id}/logs
personas: []
provider_name: Tuya
provider_slug: tuya
search_terms:
- send control commands to an iot device. specify code/value pairs for data points (e.g., switch_led=true, bright_value=500)
- list all iot devices registered to the tuya project
- update device name
- list all devices in the project
- remove and deregister a device from the cloud account
- device management
- remove device
- iot
- tuya
- list devices
- industrial iot
- smart home
- query operation and event logs for a device over a time range
- get device logs
- query device operation logs
- device control
- get device status
- control a device
- get current status of all data points
- update the friendly display name of a device
- get details and current state of a specific iot device
- send control commands to a device
- get device
- get device data point status
- cloud platform
- get device details and current state
- control device
- devices
- get the current value of all data points for a device (e.g., switch state, brightness, temperature)
- send commands
- retrieve a specific device
- get operation logs for a device
- list and search iot devices
- automation
slug: smart-home-control
source_filename: smart-home-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tuya Smart Home Control\n  description: IoT device management and control capability for smart home applications. Combines device querying, real-time\n    status monitoring, device commands, and operation log analysis. Used by smart home app developers, facility managers,\n    and IoT platform integrators to monitor and control devices such as lights, thermostats, sensors, and appliances.\n  tags:\n  - Tuya\n  - IoT\n  - Smart Home\n  - Device Control\n  - Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TUYA_ACCESS_ID: TUYA_ACCESS_ID\n    TUYA_ACCESS_SECRET: TUYA_ACCESS_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: tuya-devices\n    baseUri: https://openapi.tuyaus.com\n    description: Tuya Device Management API\n    authentication:\n      type: apikey\n      key: client_id\n      value: '{{TUYA_ACCESS_ID}}'\n      placement: header\n    resources:\n    - name: devices\n\
  \      path: /v1.0/devices/{device_id}\n      description: Manage individual devices\n      operations:\n      - name: get-device\n        method: GET\n        description: Get device details including status and attributes\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-device\n        method: PUT\n        description: Update device name\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \      - name: remove-device\n        method: DELETE\n        description: Remove a device from the account\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-list\n      path: /v1.0/devices\n      description: List and search devices\n      operations:\n      - name: list-devices\n        method: GET\n        description: Query devices by project\n        inputParameters:\n        - name: device_ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated device IDs\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: device-commands\n      path: /v1.0/devices/{device_id}/commands\n      description: Send device control commands\n      operations:\n      - name: send-commands\n        method: POST\n        description: Send control commands to a device\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            commands: '{{tools.commands}}'\n    - name: device-status\n      path: /v1.0/devices/{device_id}/status\n      description: Get device data point status\n      operations:\n      - name: get-device-status\n        method: GET\n        description: Get current status of all device data points\n        inputParameters:\n\
  \        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-logs\n      path: /v1.0/devices/{device_id}/logs\n      description: Query device operation logs\n      operations:\n      - name: get-device-logs\n        method: GET\n        description: Get device operation and event logs\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: Unique device identifier\n        - name: type\n          in: query\n          type: integer\n          required: true\n          description: Log type (1=device, 7=automation)\n        - name: start_time\n          in: query\n          type: integer\n          required: false\n          description: Start timestamp in milliseconds\n\
  \        - name: end_time\n          in: query\n          type: integer\n          required: false\n          description: End timestamp in milliseconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tuya-smart-home-api\n    description: Unified REST API for Tuya smart home device control.\n    resources:\n    - path: /v1/devices\n      name: devices\n      description: List and search IoT devices\n      operations:\n      - method: GET\n        name: list-devices\n        description: List all devices in the project\n        call: tuya-devices.list-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/{device_id}\n      name: device\n      description: Retrieve a specific device\n      operations:\n      - method: GET\n        name: get-device\n        description: Get device details and current\
  \ state\n        call: tuya-devices.get-device\n        with:\n          device_id: rest.device_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/{device_id}/status\n      name: device-status\n      description: Get device data point status\n      operations:\n      - method: GET\n        name: get-device-status\n        description: Get current status of all data points\n        call: tuya-devices.get-device-status\n        with:\n          device_id: rest.device_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices/{device_id}/commands\n      name: device-commands\n      description: Send control commands to a device\n      operations:\n      - method: POST\n        name: send-commands\n        description: Control a device\n        call: tuya-devices.send-commands\n        with:\n          device_id: rest.device_id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/devices/{device_id}/logs\n      name: device-logs\n      description: Query device operation logs\n      operations:\n      - method: GET\n        name: get-device-logs\n        description: Get operation logs for a device\n        call: tuya-devices.get-device-logs\n        with:\n          device_id: rest.device_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tuya-smart-home-mcp\n    transport: http\n    description: MCP server for AI-assisted Tuya smart home device control.\n    tools:\n    - name: list-devices\n      description: List all IoT devices registered to the Tuya project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tuya-devices.list-devices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device\n      description: Get details and current state of a specific IoT device\n      hints:\n        readOnly: true\n \
  \       openWorld: false\n      call: tuya-devices.get-device\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device-status\n      description: Get the current value of all data points for a device (e.g., switch state, brightness, temperature)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tuya-devices.get-device-status\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: control-device\n      description: Send control commands to an IoT device. Specify code/value pairs for data points (e.g., switch_led=true,\n        bright_value=500)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tuya-devices.send-commands\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-device-name\n\
  \      description: Update the friendly display name of a device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tuya-devices.update-device\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-device-logs\n      description: Query operation and event logs for a device over a time range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tuya-devices.get-device-logs\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-device\n      description: Remove and deregister a device from the cloud account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tuya-devices.remove-device\n      with:\n        device_id: tools.device_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tuya/refs/heads/main/capabilities/smart-home-control.yaml
tags:
- Tuya
- IoT
- Smart Home
- Device Control
- Automation
tools:
- description: List all IoT devices registered to the Tuya project
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get details and current state of a specific IoT device
  hints:
    openWorld: false
    readOnly: true
  name: get-device
- description: Get the current value of all data points for a device (e.g., switch state, brightness, temperature)
  hints:
    openWorld: false
    readOnly: true
  name: get-device-status
- description: Send control commands to an IoT device. Specify code/value pairs for data points (e.g., switch_led=true, bright_value=500)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: control-device
- description: Update the friendly display name of a device
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-device-name
- description: Query operation and event logs for a device over a time range
  hints:
    openWorld: true
    readOnly: true
  name: get-device-logs
- description: Remove and deregister a device from the cloud account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-device
---
