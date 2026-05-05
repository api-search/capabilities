---
categories: []
consumed_apis:
- smartthings
description: Smart home control and automation workflow capability using the Samsung SmartThings REST API. Provides unified access to connected device control, location and room management, scene activation, and automation rule management. Designed for smart home application developers, IoT integration engineers, and home automation enthusiasts building SmartThings-connected experiences.
layout: capability
name: Samsung SmartThings Smart Home Control
operations:
- description: List all SmartThings connected devices, optionally filtered by location or capability.
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get details for a specific connected device.
  method: GET
  name: get-device
  path: /v1/devices/{deviceId}
- description: Get current attribute values for all device components and capabilities.
  method: GET
  name: get-device-status
  path: /v1/devices/{deviceId}/status
- description: Execute capability commands on a device (e.g., switch.on, lock.lock, thermostat.setCoolingSetpoint).
  method: POST
  name: execute-device-commands
  path: /v1/devices/{deviceId}/commands
- description: List all SmartThings locations.
  method: GET
  name: list-locations
  path: /v1/locations
- description: Create a new SmartThings location.
  method: POST
  name: create-location
  path: /v1/locations
- description: List all rooms in a SmartThings location.
  method: GET
  name: list-rooms
  path: /v1/locations/{locationId}/rooms
- description: Create a new room within a location.
  method: POST
  name: create-room
  path: /v1/locations/{locationId}/rooms
- description: List all SmartThings scenes.
  method: GET
  name: list-scenes
  path: /v1/scenes
- description: Activate a SmartThings scene, applying its saved device configuration.
  method: POST
  name: execute-scene
  path: /v1/scenes/{sceneId}/execute
- description: List SmartThings automation rules.
  method: GET
  name: list-rules
  path: /v1/rules
- description: Create a new automation rule.
  method: POST
  name: create-rule
  path: /v1/rules
- description: List active event subscriptions.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Subscribe to device capability events.
  method: POST
  name: create-subscription
  path: /v1/subscriptions
personas: []
provider_name: Samsung
provider_slug: samsung
search_terms:
- get device
- create room
- list scenes
- create a new room within a location.
- subscribe to smartthings device capability events for real-time updates.
- list all smartthings locations.
- smartthings
- list rules
- create rule
- mobile
- developer platform
- list all rooms in a smartthings location.
- automation rule management.
- create subscription
- list active event subscriptions.
- activate a smartthings scene to apply a saved configuration to multiple devices at once.
- create a new automation rule.
- get the current real-time status of all device attributes (e.g., switch state, temperature, lock status).
- list all rooms within a smartthings location.
- room management within a location.
- subscribe to device capability events.
- list all smartthings connected devices. use to discover available iot devices in a location.
- samsung
- rules
- locations
- list devices
- get details for a specific connected device.
- real-time device attribute status.
- execute device commands
- get details for a specific smartthings device including its components and capabilities.
- consumer electronics
- connected iot device inventory and status.
- list all smartthings locations (homes, offices) accessible to the user.
- list smartthings automation rules.
- device event subscriptions for real-time automation.
- list locations
- device capability command execution.
- list smartthings scenes (saved device state configurations like 'movie time' or 'away mode').
- automations
- smart tv
- activate a smartthings scene, applying its saved device configuration.
- create a new smartthings location.
- smart home
- execute commands on a smartthings device to control it (e.g., turn on a light, lock a door, set thermostat).
- create location
- list all smartthings scenes.
- smartthings location management.
- scene activation.
- create a new smartthings automation rule that triggers device actions based on conditions.
- list subscriptions
- scenes
- device control
- wearables
- iot
- list rooms
- execute scene
- get current attribute values for all device components and capabilities.
- list smartthings automation rules (if-this-then-that conditions).
- individual device management.
- get device status
- list all smartthings connected devices, optionally filtered by location or capability.
- scene (saved device state configuration) management.
- execute capability commands on a device (e.g., switch.on, lock.lock, thermostat.setcoolingsetpoint).
slug: smart-home-control
source_filename: smart-home-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Samsung SmartThings Smart Home Control\"\n  description: >-\n    Smart home control and automation workflow capability using the Samsung\n    SmartThings REST API. Provides unified access to connected device control,\n    location and room management, scene activation, and automation rule management.\n    Designed for smart home application developers, IoT integration engineers,\n    and home automation enthusiasts building SmartThings-connected experiences.\n  tags:\n    - Automations\n    - Device Control\n    - IoT\n    - Locations\n    - Rules\n    - Samsung\n    - Scenes\n    - Smart Home\n    - SmartThings\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMARTTHINGS_PAT: SMARTTHINGS_PAT\n\ncapability:\n  consumes:\n    - import: smartthings\n      location: ./shared/smartthings.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: smart-home-control-api\n\
  \      description: \"Unified REST API for Samsung SmartThings smart home device control and automation.\"\n      resources:\n        - path: /v1/devices\n          name: devices\n          description: \"Connected IoT device inventory and status.\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List all SmartThings connected devices, optionally filtered by location or capability.\"\n              call: \"smartthings.list-devices\"\n              with:\n                locationId: \"rest.locationId\"\n                capabilityId: \"rest.capabilityId\"\n                max: \"rest.max\"\n                pageToken: \"rest.pageToken\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices/{deviceId}\n          name: device-detail\n          description: \"Individual device management.\"\n          operations:\n            - method: GET\n           \
  \   name: get-device\n              description: \"Get details for a specific connected device.\"\n              call: \"smartthings.get-device\"\n              with:\n                deviceId: \"rest.deviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices/{deviceId}/status\n          name: device-status\n          description: \"Real-time device attribute status.\"\n          operations:\n            - method: GET\n              name: get-device-status\n              description: \"Get current attribute values for all device components and capabilities.\"\n              call: \"smartthings.get-device-status\"\n              with:\n                deviceId: \"rest.deviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices/{deviceId}/commands\n          name: device-commands\n          description: \"Device capability command\
  \ execution.\"\n          operations:\n            - method: POST\n              name: execute-device-commands\n              description: \"Execute capability commands on a device (e.g., switch.on, lock.lock, thermostat.setCoolingSetpoint).\"\n              call: \"smartthings.execute-device-commands\"\n              with:\n                deviceId: \"rest.deviceId\"\n                commands: \"rest.commands\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations\n          name: locations\n          description: \"SmartThings location management.\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"List all SmartThings locations.\"\n              call: \"smartthings.list-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-location\n\
  \              description: \"Create a new SmartThings location.\"\n              call: \"smartthings.create-location\"\n              with:\n                name: \"rest.name\"\n                countryCode: \"rest.countryCode\"\n                timeZoneId: \"rest.timeZoneId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations/{locationId}/rooms\n          name: rooms\n          description: \"Room management within a location.\"\n          operations:\n            - method: GET\n              name: list-rooms\n              description: \"List all rooms in a SmartThings location.\"\n              call: \"smartthings.list-rooms\"\n              with:\n                locationId: \"rest.locationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-room\n              description: \"Create a new room within\
  \ a location.\"\n              call: \"smartthings.create-room\"\n              with:\n                locationId: \"rest.locationId\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scenes\n          name: scenes\n          description: \"Scene (saved device state configuration) management.\"\n          operations:\n            - method: GET\n              name: list-scenes\n              description: \"List all SmartThings scenes.\"\n              call: \"smartthings.list-scenes\"\n              with:\n                locationId: \"rest.locationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/scenes/{sceneId}/execute\n          name: scene-execute\n          description: \"Scene activation.\"\n          operations:\n            - method: POST\n              name: execute-scene\n              description:\
  \ \"Activate a SmartThings scene, applying its saved device configuration.\"\n              call: \"smartthings.execute-scene\"\n              with:\n                sceneId: \"rest.sceneId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rules\n          name: rules\n          description: \"Automation rule management.\"\n          operations:\n            - method: GET\n              name: list-rules\n              description: \"List SmartThings automation rules.\"\n              call: \"smartthings.list-rules\"\n              with:\n                locationId: \"rest.locationId\"\n                max: \"rest.max\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-rule\n              description: \"Create a new automation rule.\"\n              call: \"smartthings.create-rule\"\n              with:\n     \
  \           locationId: \"rest.locationId\"\n                name: \"rest.name\"\n                actions: \"rest.actions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Device event subscriptions for real-time automation.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List active event subscriptions.\"\n              call: \"smartthings.list-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-subscription\n              description: \"Subscribe to device capability events.\"\n              call: \"smartthings.create-subscription\"\n              with:\n                sourceType: \"rest.sourceType\"\n                device: \"rest.device\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: smart-home-control-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Samsung SmartThings smart home control and automation.\"\n      tools:\n        - name: list-devices\n          description: \"List all SmartThings connected devices. Use to discover available IoT devices in a location.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartthings.list-devices\"\n          with:\n            locationId: \"tools.locationId\"\n            capabilityId: \"tools.capabilityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-device\n          description: \"Get details for a specific SmartThings device including its components and capabilities.\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"smartthings.get-device\"\n          with:\n            deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-device-status\n          description: \"Get the current real-time status of all device attributes (e.g., switch state, temperature, lock status).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartthings.get-device-status\"\n          with:\n            deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-device-commands\n          description: \"Execute commands on a SmartThings device to control it (e.g., turn on a light, lock a door, set thermostat).\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"smartthings.execute-device-commands\"\n          with:\n\
  \            deviceId: \"tools.deviceId\"\n            commands: \"tools.commands\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-locations\n          description: \"List all SmartThings locations (homes, offices) accessible to the user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartthings.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rooms\n          description: \"List all rooms within a SmartThings location.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartthings.list-rooms\"\n          with:\n            locationId: \"tools.locationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-scenes\n          description: \"List SmartThings scenes (saved device state configurations\
  \ like 'Movie Time' or 'Away Mode').\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartthings.list-scenes\"\n          with:\n            locationId: \"tools.locationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-scene\n          description: \"Activate a SmartThings scene to apply a saved configuration to multiple devices at once.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"smartthings.execute-scene\"\n          with:\n            sceneId: \"tools.sceneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rules\n          description: \"List SmartThings automation rules (if-this-then-that conditions).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartthings.list-rules\"\
  \n          with:\n            locationId: \"tools.locationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-rule\n          description: \"Create a new SmartThings automation rule that triggers device actions based on conditions.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"smartthings.create-rule\"\n          with:\n            locationId: \"tools.locationId\"\n            name: \"tools.name\"\n            actions: \"tools.actions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscription\n          description: \"Subscribe to SmartThings device capability events for real-time updates.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"smartthings.create-subscription\"\n          with:\n\
  \            sourceType: \"tools.sourceType\"\n            device: \"tools.device\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/samsung/refs/heads/main/capabilities/smart-home-control.yaml
tags:
- Automations
- Device Control
- IoT
- Locations
- Rules
- Samsung
- Scenes
- Smart Home
- SmartThings
tools:
- description: List all SmartThings connected devices. Use to discover available IoT devices in a location.
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get details for a specific SmartThings device including its components and capabilities.
  hints:
    openWorld: false
    readOnly: true
  name: get-device
- description: Get the current real-time status of all device attributes (e.g., switch state, temperature, lock status).
  hints:
    openWorld: false
    readOnly: true
  name: get-device-status
- description: Execute commands on a SmartThings device to control it (e.g., turn on a light, lock a door, set thermostat).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-device-commands
- description: List all SmartThings locations (homes, offices) accessible to the user.
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: List all rooms within a SmartThings location.
  hints:
    openWorld: false
    readOnly: true
  name: list-rooms
- description: List SmartThings scenes (saved device state configurations like 'Movie Time' or 'Away Mode').
  hints:
    openWorld: false
    readOnly: true
  name: list-scenes
- description: Activate a SmartThings scene to apply a saved configuration to multiple devices at once.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: execute-scene
- description: List SmartThings automation rules (if-this-then-that conditions).
  hints:
    openWorld: false
    readOnly: true
  name: list-rules
- description: Create a new SmartThings automation rule that triggers device actions based on conditions.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-rule
- description: Subscribe to SmartThings device capability events for real-time updates.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-subscription
---
