---
categories: []
consumed_apis:
- tesla-motors
description: Unified workflow capability for Tesla electric vehicle management and monitoring. Enables fleet operators, vehicle owners, and IoT integrations to monitor vehicle telemetry (charge, climate, location, physical state), execute remote commands (wake, lock/unlock, climate control, charging), and manage vehicle settings.
layout: capability
name: Tesla Motors Vehicle Management
operations:
- description: List all Tesla vehicles in the account
  method: GET
  name: list-vehicles
  path: /v1/vehicles
- description: Get specific vehicle details
  method: GET
  name: get-vehicle
  path: /v1/vehicles/{vehicle_id}
- description: Get all vehicle telemetry data
  method: GET
  name: get-vehicle-data
  path: /v1/vehicles/{vehicle_id}/data
- description: Get battery level and charging status
  method: GET
  name: get-charge-state
  path: /v1/vehicles/{vehicle_id}/charge-state
- description: Get climate settings and temperatures
  method: GET
  name: get-climate-state
  path: /v1/vehicles/{vehicle_id}/climate-state
- description: Get GPS location and driving state
  method: GET
  name: get-drive-state
  path: /v1/vehicles/{vehicle_id}/drive-state
- description: Wake the vehicle from sleep mode
  method: POST
  name: wake-up-vehicle
  path: /v1/vehicles/{vehicle_id}/wake-up
- description: Lock all vehicle doors
  method: POST
  name: lock-doors
  path: /v1/vehicles/{vehicle_id}/doors/lock
- description: Unlock all vehicle doors
  method: POST
  name: unlock-doors
  path: /v1/vehicles/{vehicle_id}/doors/unlock
- description: Start auto conditioning
  method: POST
  name: start-climate
  path: /v1/vehicles/{vehicle_id}/climate/start
- description: Start vehicle charging
  method: POST
  name: start-charging
  path: /v1/vehicles/{vehicle_id}/charging/start
- description: Stop vehicle charging
  method: POST
  name: stop-charging
  path: /v1/vehicles/{vehicle_id}/charging/stop
personas: []
provider_name: Tesla Motors
provider_slug: tesla-motors
search_terms:
- vehicle fleet listing
- climate and temperature status
- smart vehicles
- set sentry mode
- stop charging
- get gps location, heading, and speed for a tesla vehicle
- stop climate
- start climate control
- lock vehicle doors
- lock doors
- start climate
- list all tesla vehicles in the owner account
- start auto conditioning
- unlock all vehicle doors
- start vehicle charging
- single vehicle details
- start charging a tesla vehicle
- get gps location and driving state
- electric vehicles
- flash tesla headlights to visually locate the vehicle
- get vehicle data
- unlock vehicle doors
- wake up vehicle
- get climate settings and temperatures
- stop charging a tesla vehicle
- list all tesla vehicles in the account
- wake the vehicle from sleep mode
- telemetry
- list vehicles
- lock all vehicle doors
- flash lights
- automobiles
- start climate control (pre-conditioning) on a tesla vehicle
- get vehicle
- full vehicle telemetry
- get all vehicle telemetry data
- get battery level and charging status
- remote commands
- wake vehicle from sleep
- get complete telemetry snapshot for a tesla vehicle
- get climate state
- get drive state
- get interior temperature and climate control settings for a tesla
- get charge state
- get vehicle state
- get battery percentage, charging status, and charge limit for a tesla
- start charging
- get physical state of a tesla (doors, windows, trunk, odometer)
- lock all doors on a tesla vehicle
- stop vehicle charging
- unlock doors
- tesla
- get details and status for a specific tesla vehicle
- honk horn
- stop climate control on a tesla vehicle
- wake a sleeping tesla from sleep mode to enable commands
- iot
- honk the tesla horn to audibly locate the vehicle
- location and driving state
- cars
- battery and charging status
- get specific vehicle details
- enable or disable tesla sentry mode for security monitoring
- unlock all doors on a tesla vehicle
slug: vehicle-management
source_filename: vehicle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tesla Motors Vehicle Management\"\n  description: >-\n    Unified workflow capability for Tesla electric vehicle management and monitoring.\n    Enables fleet operators, vehicle owners, and IoT integrations to monitor vehicle\n    telemetry (charge, climate, location, physical state), execute remote commands\n    (wake, lock/unlock, climate control, charging), and manage vehicle settings.\n  tags:\n    - Tesla\n    - Electric Vehicles\n    - Automobiles\n    - IoT\n    - Smart Vehicles\n    - Remote Commands\n    - Telemetry\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TESLA_ACCESS_TOKEN: TESLA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tesla-motors\n      location: ./shared/tesla-motors.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tesla-vehicle-management-api\n      description: \"Unified REST API for Tesla vehicle telemetry and\
  \ remote management.\"\n      resources:\n        - path: /v1/vehicles\n          name: vehicles\n          description: \"Vehicle fleet listing\"\n          operations:\n            - method: GET\n              name: list-vehicles\n              description: \"List all Tesla vehicles in the account\"\n              call: \"tesla-motors.list-vehicles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}\n          name: vehicle\n          description: \"Single vehicle details\"\n          operations:\n            - method: GET\n              name: get-vehicle\n              description: \"Get specific vehicle details\"\n              call: \"tesla-motors.get-vehicle\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/data\n          name:\
  \ vehicle-data\n          description: \"Full vehicle telemetry\"\n          operations:\n            - method: GET\n              name: get-vehicle-data\n              description: \"Get all vehicle telemetry data\"\n              call: \"tesla-motors.get-vehicle-data\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/charge-state\n          name: charge-state\n          description: \"Battery and charging status\"\n          operations:\n            - method: GET\n              name: get-charge-state\n              description: \"Get battery level and charging status\"\n              call: \"tesla-motors.get-charge-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/climate-state\n\
  \          name: climate-state\n          description: \"Climate and temperature status\"\n          operations:\n            - method: GET\n              name: get-climate-state\n              description: \"Get climate settings and temperatures\"\n              call: \"tesla-motors.get-climate-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/drive-state\n          name: drive-state\n          description: \"Location and driving state\"\n          operations:\n            - method: GET\n              name: get-drive-state\n              description: \"Get GPS location and driving state\"\n              call: \"tesla-motors.get-drive-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n      \
  \  - path: /v1/vehicles/{vehicle_id}/wake-up\n          name: wake-up\n          description: \"Wake vehicle from sleep\"\n          operations:\n            - method: POST\n              name: wake-up-vehicle\n              description: \"Wake the vehicle from sleep mode\"\n              call: \"tesla-motors.wake-up-vehicle\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/doors/lock\n          name: doors-lock\n          description: \"Lock vehicle doors\"\n          operations:\n            - method: POST\n              name: lock-doors\n              description: \"Lock all vehicle doors\"\n              call: \"tesla-motors.lock-doors\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/vehicles/{vehicle_id}/doors/unlock\n          name: doors-unlock\n          description: \"Unlock vehicle doors\"\n          operations:\n            - method: POST\n              name: unlock-doors\n              description: \"Unlock all vehicle doors\"\n              call: \"tesla-motors.unlock-doors\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/climate/start\n          name: climate-start\n          description: \"Start climate control\"\n          operations:\n            - method: POST\n              name: start-climate\n              description: \"Start auto conditioning\"\n              call: \"tesla-motors.start-climate\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/vehicles/{vehicle_id}/charging/start\n          name: charging-start\n          description: \"Start charging\"\n          operations:\n            - method: POST\n              name: start-charging\n              description: \"Start vehicle charging\"\n              call: \"tesla-motors.start-charging\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/charging/stop\n          name: charging-stop\n          description: \"Stop charging\"\n          operations:\n            - method: POST\n              name: stop-charging\n              description: \"Stop vehicle charging\"\n              call: \"tesla-motors.stop-charging\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n    \
  \  port: 9090\n      namespace: tesla-vehicle-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tesla vehicle management and monitoring.\"\n      tools:\n        - name: list-vehicles\n          description: \"List all Tesla vehicles in the owner account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tesla-motors.list-vehicles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle\n          description: \"Get details and status for a specific Tesla vehicle\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-vehicle\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-data\n          description: \"Get complete telemetry snapshot for a Tesla vehicle\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-vehicle-data\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-charge-state\n          description: \"Get battery percentage, charging status, and charge limit for a Tesla\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-charge-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-climate-state\n          description: \"Get interior temperature and climate control settings for a Tesla\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-climate-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-drive-state\n          description: \"Get GPS location, heading, and speed for a Tesla vehicle\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-drive-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-state\n          description: \"Get physical state of a Tesla (doors, windows, trunk, odometer)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla-motors.get-vehicle-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wake-up-vehicle\n          description: \"Wake a sleeping Tesla from sleep mode to enable commands\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.wake-up-vehicle\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lock-doors\n          description: \"Lock all doors on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.lock-doors\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unlock-doors\n          description: \"Unlock all doors on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.unlock-doors\"\n          with:\n            vehicle_id: \"\
  tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-climate\n          description: \"Start climate control (pre-conditioning) on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.start-climate\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-climate\n          description: \"Stop climate control on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.stop-climate\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-charging\n          description: \"Start\
  \ charging a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.start-charging\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-charging\n          description: \"Stop charging a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.stop-charging\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: flash-lights\n          description: \"Flash Tesla headlights to visually locate the vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tesla-motors.flash-lights\"\
  \n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: honk-horn\n          description: \"Honk the Tesla horn to audibly locate the vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"tesla-motors.honk-horn\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-sentry-mode\n          description: \"Enable or disable Tesla Sentry Mode for security monitoring\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla-motors.set-sentry-mode\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n            on: \"tools.on\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tesla-motors/refs/heads/main/capabilities/vehicle-management.yaml
tags:
- Tesla
- Electric Vehicles
- Automobiles
- IoT
- Smart Vehicles
- Remote Commands
- Telemetry
tools:
- description: List all Tesla vehicles in the owner account
  hints:
    openWorld: true
    readOnly: true
  name: list-vehicles
- description: Get details and status for a specific Tesla vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle
- description: Get complete telemetry snapshot for a Tesla vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-data
- description: Get battery percentage, charging status, and charge limit for a Tesla
  hints:
    openWorld: false
    readOnly: true
  name: get-charge-state
- description: Get interior temperature and climate control settings for a Tesla
  hints:
    openWorld: false
    readOnly: true
  name: get-climate-state
- description: Get GPS location, heading, and speed for a Tesla vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-drive-state
- description: Get physical state of a Tesla (doors, windows, trunk, odometer)
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-state
- description: Wake a sleeping Tesla from sleep mode to enable commands
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: wake-up-vehicle
- description: Lock all doors on a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lock-doors
- description: Unlock all doors on a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unlock-doors
- description: Start climate control (pre-conditioning) on a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-climate
- description: Stop climate control on a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-climate
- description: Start charging a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-charging
- description: Stop charging a Tesla vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: stop-charging
- description: Flash Tesla headlights to visually locate the vehicle
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: flash-lights
- description: Honk the Tesla horn to audibly locate the vehicle
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: honk-horn
- description: Enable or disable Tesla Sentry Mode for security monitoring
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-sentry-mode
---
