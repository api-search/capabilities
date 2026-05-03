---
categories: []
consumed_apis:
- tesla
description: Workflow capability for Tesla vehicle monitoring and remote control via the Tesla Owner API. Enables fleet managers, IoT integrations, and personal vehicle owners to monitor battery, climate, location, and physical state, and execute remote commands including wake-up, lock/unlock, climate control, charging management, sentry mode, and charging site discovery.
layout: capability
name: Tesla Vehicle Monitoring and Control
operations:
- description: List all Tesla vehicles
  method: GET
  name: list-vehicles
  path: /v1/vehicles
- description: Get all vehicle data
  method: GET
  name: get-vehicle-data
  path: /v1/vehicles/{vehicle_id}/data
- description: Get charge state
  method: GET
  name: get-charge-state
  path: /v1/vehicles/{vehicle_id}/charge-state
- description: Get climate state
  method: GET
  name: get-climate-state
  path: /v1/vehicles/{vehicle_id}/climate-state
- description: Get drive state and location
  method: GET
  name: get-drive-state
  path: /v1/vehicles/{vehicle_id}/drive-state
- description: Find nearby charging sites
  method: GET
  name: get-nearby-charging-sites
  path: /v1/vehicles/{vehicle_id}/nearby-charging
- description: Wake vehicle
  method: POST
  name: wake-up-vehicle
  path: /v1/vehicles/{vehicle_id}/commands/wake-up
- description: Lock all doors
  method: POST
  name: lock-doors
  path: /v1/vehicles/{vehicle_id}/commands/lock
- description: Unlock all doors
  method: POST
  name: unlock-doors
  path: /v1/vehicles/{vehicle_id}/commands/unlock
personas: []
provider_name: Tesla
provider_slug: tesla
search_terms:
- unlock all doors on a tesla vehicle
- nearby charging sites
- climate and temperature
- list all tesla vehicles
- unlock all doors
- get battery percentage, charging status, and range estimate
- wake a sleeping tesla to enable remote commands
- smart vehicles
- list all tesla vehicles in the owner account
- automobiles
- get interior temperature and climate control settings
- enable or disable tesla sentry mode for security monitoring
- get drive state and location
- get charge state
- find nearby charging sites
- start climate pre-conditioning (heating/cooling) on a tesla
- vehicles
- get physical state of the vehicle (doors, windows, trunk, odometer)
- get all vehicle data
- get nearby charging sites
- lock doors
- get vehicle gps location, heading, and speed
- energy
- full vehicle telemetry
- wake up vehicle
- set sentry mode
- electric vehicles
- remote commands
- get vehicle data
- get drive state
- get vehicle state
- stop climate control on a tesla
- stop charging
- get climate state
- get complete telemetry snapshot for a tesla vehicle
- wake vehicle from sleep
- location and driving state
- vehicle fleet listing
- find nearby superchargers and destination chargers with availability
- cars
- tesla
- fleet management
- battery and charging status
- lock all doors on a tesla vehicle
- list vehicles
- start climate
- start charging a tesla vehicle
- stop charging a tesla vehicle
- wake vehicle
- iot
- lock all doors
- start charging
- stop climate
- clean energy
- unlock doors
slug: vehicle-monitoring
source_filename: vehicle-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tesla Vehicle Monitoring and Control\"\n  description: >-\n    Workflow capability for Tesla vehicle monitoring and remote control via the\n    Tesla Owner API. Enables fleet managers, IoT integrations, and personal vehicle\n    owners to monitor battery, climate, location, and physical state, and execute\n    remote commands including wake-up, lock/unlock, climate control, charging\n    management, sentry mode, and charging site discovery.\n  tags:\n    - Tesla\n    - Electric Vehicles\n    - Automobiles\n    - IoT\n    - Smart Vehicles\n    - Remote Commands\n    - Fleet Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TESLA_ACCESS_TOKEN: TESLA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tesla\n      location: ./shared/tesla.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tesla-vehicle-api\n      description: \"Unified REST API\
  \ for Tesla vehicle monitoring and control.\"\n      resources:\n        - path: /v1/vehicles\n          name: vehicles\n          description: \"Vehicle fleet listing\"\n          operations:\n            - method: GET\n              name: list-vehicles\n              description: \"List all Tesla vehicles\"\n              call: \"tesla.list-vehicles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/data\n          name: vehicle-data\n          description: \"Full vehicle telemetry\"\n          operations:\n            - method: GET\n              name: get-vehicle-data\n              description: \"Get all vehicle data\"\n              call: \"tesla.get-vehicle-data\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/charge-state\n\
  \          name: charge-state\n          description: \"Battery and charging status\"\n          operations:\n            - method: GET\n              name: get-charge-state\n              description: \"Get charge state\"\n              call: \"tesla.get-charge-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/climate-state\n          name: climate-state\n          description: \"Climate and temperature\"\n          operations:\n            - method: GET\n              name: get-climate-state\n              description: \"Get climate state\"\n              call: \"tesla.get-climate-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/drive-state\n    \
  \      name: drive-state\n          description: \"Location and driving state\"\n          operations:\n            - method: GET\n              name: get-drive-state\n              description: \"Get drive state and location\"\n              call: \"tesla.get-drive-state\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/nearby-charging\n          name: nearby-charging\n          description: \"Nearby charging sites\"\n          operations:\n            - method: GET\n              name: get-nearby-charging-sites\n              description: \"Find nearby charging sites\"\n              call: \"tesla.get-nearby-charging-sites\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/commands/wake-up\n\
  \          name: wake-up\n          description: \"Wake vehicle from sleep\"\n          operations:\n            - method: POST\n              name: wake-up-vehicle\n              description: \"Wake vehicle\"\n              call: \"tesla.wake-up-vehicle\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/commands/lock\n          name: lock\n          description: \"Lock doors\"\n          operations:\n            - method: POST\n              name: lock-doors\n              description: \"Lock all doors\"\n              call: \"tesla.lock-doors\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vehicle_id}/commands/unlock\n          name: unlock\n          description: \"Unlock\
  \ doors\"\n          operations:\n            - method: POST\n              name: unlock-doors\n              description: \"Unlock all doors\"\n              call: \"tesla.unlock-doors\"\n              with:\n                vehicle_id: \"rest.vehicle_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tesla-vehicle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tesla vehicle monitoring and control.\"\n      tools:\n        - name: list-vehicles\n          description: \"List all Tesla vehicles in the owner account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tesla.list-vehicles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-data\n          description: \"Get complete telemetry snapshot for a Tesla vehicle\"\n          hints:\n \
  \           readOnly: true\n            openWorld: false\n          call: \"tesla.get-vehicle-data\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-charge-state\n          description: \"Get battery percentage, charging status, and range estimate\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla.get-charge-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-climate-state\n          description: \"Get interior temperature and climate control settings\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla.get-climate-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-drive-state\n          description: \"Get vehicle GPS location, heading, and speed\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla.get-drive-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-state\n          description: \"Get physical state of the vehicle (doors, windows, trunk, odometer)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tesla.get-vehicle-state\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-nearby-charging-sites\n          description: \"Find nearby Superchargers and destination chargers with availability\"\n          hints:\n            readOnly: true\n  \
  \          openWorld: true\n          call: \"tesla.get-nearby-charging-sites\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wake-up-vehicle\n          description: \"Wake a sleeping Tesla to enable remote commands\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.wake-up-vehicle\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lock-doors\n          description: \"Lock all doors on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.lock-doors\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: unlock-doors\n          description: \"Unlock all doors on a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.unlock-doors\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-climate\n          description: \"Start climate pre-conditioning (heating/cooling) on a Tesla\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.start-climate\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-climate\n          description: \"Stop climate control on a Tesla\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: true\n          call: \"tesla.stop-climate\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-charging\n          description: \"Start charging a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.start-charging\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-charging\n          description: \"Stop charging a Tesla vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.stop-charging\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: set-sentry-mode\n          description: \"Enable or disable Tesla Sentry Mode for security monitoring\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"tesla.set-sentry-mode\"\n          with:\n            vehicle_id: \"tools.vehicle_id\"\n            on: \"tools.on\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tesla/refs/heads/main/capabilities/vehicle-monitoring.yaml
tags:
- Tesla
- Electric Vehicles
- Automobiles
- IoT
- Smart Vehicles
- Remote Commands
- Fleet Management
tools:
- description: List all Tesla vehicles in the owner account
  hints:
    openWorld: true
    readOnly: true
  name: list-vehicles
- description: Get complete telemetry snapshot for a Tesla vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-data
- description: Get battery percentage, charging status, and range estimate
  hints:
    openWorld: false
    readOnly: true
  name: get-charge-state
- description: Get interior temperature and climate control settings
  hints:
    openWorld: false
    readOnly: true
  name: get-climate-state
- description: Get vehicle GPS location, heading, and speed
  hints:
    openWorld: false
    readOnly: true
  name: get-drive-state
- description: Get physical state of the vehicle (doors, windows, trunk, odometer)
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-state
- description: Find nearby Superchargers and destination chargers with availability
  hints:
    openWorld: true
    readOnly: true
  name: get-nearby-charging-sites
- description: Wake a sleeping Tesla to enable remote commands
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
- description: Start climate pre-conditioning (heating/cooling) on a Tesla
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-climate
- description: Stop climate control on a Tesla
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
- description: Enable or disable Tesla Sentry Mode for security monitoring
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-sentry-mode
---
