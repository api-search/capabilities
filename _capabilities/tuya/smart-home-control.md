---
categories: []
consumed_apis:
- tuya-devices
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
- get device
- send control commands to a device
- get device logs
- get details and current state of a specific iot device
- device management
- retrieve a specific device
- query device operation logs
- update device name
- devices
- list all devices in the project
- tuya
- list devices
- send control commands to an iot device. specify code/value pairs for data points (e.g., switch_led=true, bright_value=500)
- list and search iot devices
- query operation and event logs for a device over a time range
- get device data point status
- industrial iot
- remove device
- send commands
- get the current value of all data points for a device (e.g., switch state, brightness, temperature)
- smart home
- get device details and current state
- update the friendly display name of a device
- remove and deregister a device from the cloud account
- get operation logs for a device
- device control
- iot
- control device
- cloud platform
- control a device
- automation
- list all iot devices registered to the tuya project
- get device status
- get current status of all data points
slug: smart-home-control
source_filename: smart-home-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tuya Smart Home Control\"\n  description: >-\n    IoT device management and control capability for smart home applications.\n    Combines device querying, real-time status monitoring, device commands,\n    and operation log analysis. Used by smart home app developers, facility\n    managers, and IoT platform integrators to monitor and control devices\n    such as lights, thermostats, sensors, and appliances.\n  tags:\n    - Tuya\n    - IoT\n    - Smart Home\n    - Device Control\n    - Automation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TUYA_ACCESS_ID: TUYA_ACCESS_ID\n      TUYA_ACCESS_SECRET: TUYA_ACCESS_SECRET\n\ncapability:\n  consumes:\n    - import: tuya-devices\n      location: ./shared/device-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tuya-smart-home-api\n      description: \"Unified REST API for Tuya smart home device\
  \ control.\"\n      resources:\n        - path: /v1/devices\n          name: devices\n          description: \"List and search IoT devices\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List all devices in the project\"\n              call: \"tuya-devices.list-devices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{device_id}\n          name: device\n          description: \"Retrieve a specific device\"\n          operations:\n            - method: GET\n              name: get-device\n              description: \"Get device details and current state\"\n              call: \"tuya-devices.get-device\"\n              with:\n                device_id: \"rest.device_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{device_id}/status\n          name: device-status\n\
  \          description: \"Get device data point status\"\n          operations:\n            - method: GET\n              name: get-device-status\n              description: \"Get current status of all data points\"\n              call: \"tuya-devices.get-device-status\"\n              with:\n                device_id: \"rest.device_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{device_id}/commands\n          name: device-commands\n          description: \"Send control commands to a device\"\n          operations:\n            - method: POST\n              name: send-commands\n              description: \"Control a device\"\n              call: \"tuya-devices.send-commands\"\n              with:\n                device_id: \"rest.device_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{device_id}/logs\n        \
  \  name: device-logs\n          description: \"Query device operation logs\"\n          operations:\n            - method: GET\n              name: get-device-logs\n              description: \"Get operation logs for a device\"\n              call: \"tuya-devices.get-device-logs\"\n              with:\n                device_id: \"rest.device_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tuya-smart-home-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tuya smart home device control.\"\n      tools:\n        - name: list-devices\n          description: \"List all IoT devices registered to the Tuya project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tuya-devices.list-devices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-device\n   \
  \       description: \"Get details and current state of a specific IoT device\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tuya-devices.get-device\"\n          with:\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-device-status\n          description: \"Get the current value of all data points for a device (e.g., switch state, brightness, temperature)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tuya-devices.get-device-status\"\n          with:\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: control-device\n          description: \"Send control commands to an IoT device. Specify code/value pairs for data points (e.g., switch_led=true, bright_value=500)\"\n          hints:\n   \
  \         readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tuya-devices.send-commands\"\n          with:\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-device-name\n          description: \"Update the friendly display name of a device\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tuya-devices.update-device\"\n          with:\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-device-logs\n          description: \"Query operation and event logs for a device over a time range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tuya-devices.get-device-logs\"\n          with:\n            device_id: \"tools.device_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: remove-device\n          description: \"Remove and deregister a device from the cloud account\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tuya-devices.remove-device\"\n          with:\n            device_id: \"tools.device_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
