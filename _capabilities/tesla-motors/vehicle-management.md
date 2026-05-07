---
categories: []
consumed_apis: []
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
- get vehicle
- start charging a tesla vehicle
- stop climate
- start auto conditioning
- wake the vehicle from sleep mode
- wake vehicle from sleep
- unlock all doors on a tesla vehicle
- vehicle fleet listing
- lock vehicle doors
- lock doors
- start climate
- wake a sleeping tesla from sleep mode to enable commands
- automobiles
- unlock all vehicle doors
- list all tesla vehicles in the owner account
- unlock doors
- telemetry
- get vehicle state
- get battery percentage, charging status, and charge limit for a tesla
- get all vehicle telemetry data
- battery and charging status
- start charging
- electric vehicles
- get specific vehicle details
- flash tesla headlights to visually locate the vehicle
- flash lights
- climate and temperature status
- smart vehicles
- honk horn
- get gps location and driving state
- list vehicles
- enable or disable tesla sentry mode for security monitoring
- tesla
- single vehicle details
- get physical state of a tesla (doors, windows, trunk, odometer)
- start climate control
- get complete telemetry snapshot for a tesla vehicle
- iot
- get climate state
- get interior temperature and climate control settings for a tesla
- get details and status for a specific tesla vehicle
- cars
- list all tesla vehicles in the account
- location and driving state
- wake up vehicle
- get climate settings and temperatures
- get vehicle data
- unlock vehicle doors
- start vehicle charging
- honk the tesla horn to audibly locate the vehicle
- get gps location, heading, and speed for a tesla vehicle
- stop charging a tesla vehicle
- get battery level and charging status
- lock all vehicle doors
- remote commands
- full vehicle telemetry
- lock all doors on a tesla vehicle
- set sentry mode
- stop vehicle charging
- get drive state
- get charge state
- stop charging
- stop climate control on a tesla vehicle
- start climate control (pre-conditioning) on a tesla vehicle
slug: vehicle-management
source_filename: vehicle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tesla Motors Vehicle Management\n  description: Unified workflow capability for Tesla electric vehicle management and monitoring. Enables fleet operators,\n    vehicle owners, and IoT integrations to monitor vehicle telemetry (charge, climate, location, physical state), execute\n    remote commands (wake, lock/unlock, climate control, charging), and manage vehicle settings.\n  tags:\n  - Tesla\n  - Electric Vehicles\n  - Automobiles\n  - IoT\n  - Smart Vehicles\n  - Remote Commands\n  - Telemetry\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TESLA_ACCESS_TOKEN: TESLA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tesla-motors\n    baseUri: https://owner-api.teslamotors.com\n    description: Tesla Motors Owner API for vehicle telemetry and remote commands\n    authentication:\n      type: bearer\n      token: '{{TESLA_ACCESS_TOKEN}}'\n    resources:\n    - name: vehicles\n\
  \      path: /api/1/vehicles\n      description: List all vehicles associated with the owner account\n      operations:\n      - name: list-vehicles\n        method: GET\n        description: List all owned Tesla vehicles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle\n      path: /api/1/vehicles/{vehicle_id}\n      description: Get details for a specific vehicle\n      operations:\n      - name: get-vehicle\n        method: GET\n        description: Retrieve details for a specific vehicle\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-data\n      path: /api/1/vehicles/{vehicle_id}/vehicle_data\n      description: Get all vehicle data\
  \ in one call\n      operations:\n      - name: get-vehicle-data\n        method: GET\n        description: Get all vehicle data (charge, climate, drive, state, config)\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/charge_state\n      description: Get vehicle battery and charge state\n      operations:\n      - name: get-charge-state\n        method: GET\n        description: Get battery level, charging status, and charge settings\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: climate-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/climate_state\n      description: Get vehicle climate and temperature state\n      operations:\n      - name: get-climate-state\n        method: GET\n        description: Get current temperature and climate control settings\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drive-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/drive_state\n      description: Get vehicle driving and GPS position state\n      operations:\n      - name: get-drive-state\n        method: GET\n        description: Get location, speed, and driving state\n        inputParameters:\n        - name: vehicle_id\n          in: path\n \
  \         type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/vehicle_state\n      description: Get physical vehicle state (doors, windows, trunk)\n      operations:\n      - name: get-vehicle-state\n        method: GET\n        description: Get physical state including doors, windows, and trunk\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wake-up\n      path: /api/1/vehicles/{vehicle_id}/wake_up\n      description: Wake up a sleeping vehicle\n      operations:\n      - name: wake-up-vehicle\n        method: POST\n\
  \        description: Wake the vehicle from sleep mode\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: door-unlock\n      path: /api/1/vehicles/{vehicle_id}/command/door_unlock\n      description: Unlock vehicle doors\n      operations:\n      - name: unlock-doors\n        method: POST\n        description: Unlock all vehicle doors\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: door-lock\n      path: /api/1/vehicles/{vehicle_id}/command/door_lock\n      description: Lock vehicle doors\n     \
  \ operations:\n      - name: lock-doors\n        method: POST\n        description: Lock all vehicle doors\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate-start\n      path: /api/1/vehicles/{vehicle_id}/command/auto_conditioning_start\n      description: Start climate control\n      operations:\n      - name: start-climate\n        method: POST\n        description: Start auto conditioning (climate control)\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate-stop\n      path: /api/1/vehicles/{vehicle_id}/command/auto_conditioning_stop\n\
  \      description: Stop climate control\n      operations:\n      - name: stop-climate\n        method: POST\n        description: Stop auto conditioning (climate control)\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-start\n      path: /api/1/vehicles/{vehicle_id}/command/charge_start\n      description: Start charging\n      operations:\n      - name: start-charging\n        method: POST\n        description: Start vehicle charging\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-stop\n\
  \      path: /api/1/vehicles/{vehicle_id}/command/charge_stop\n      description: Stop charging\n      operations:\n      - name: stop-charging\n        method: POST\n        description: Stop vehicle charging\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flash-lights\n      path: /api/1/vehicles/{vehicle_id}/command/flash_lights\n      description: Flash vehicle lights\n      operations:\n      - name: flash-lights\n        method: POST\n        description: Flash the vehicle's headlights\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: honk-horn\n      path: /api/1/vehicles/{vehicle_id}/command/honk_horn\n      description: Honk vehicle horn\n      operations:\n      - name: honk-horn\n        method: POST\n        description: Honk the vehicle's horn\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sentry-mode\n      path: /api/1/vehicles/{vehicle_id}/command/set_sentry_mode\n      description: Control sentry mode\n      operations:\n      - name: set-sentry-mode\n        method: POST\n        description: Enable or disable Sentry Mode\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        body:\n          type:\
  \ json\n          data:\n            true: '{{tools.on}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tesla-vehicle-management-api\n    description: Unified REST API for Tesla vehicle telemetry and remote management.\n    resources:\n    - path: /v1/vehicles\n      name: vehicles\n      description: Vehicle fleet listing\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: List all Tesla vehicles in the account\n        call: tesla-motors.list-vehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}\n      name: vehicle\n      description: Single vehicle details\n      operations:\n      - method: GET\n        name: get-vehicle\n        description: Get specific vehicle details\n        call: tesla-motors.get-vehicle\n        with:\n          vehicle_id:\
  \ rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/data\n      name: vehicle-data\n      description: Full vehicle telemetry\n      operations:\n      - method: GET\n        name: get-vehicle-data\n        description: Get all vehicle telemetry data\n        call: tesla-motors.get-vehicle-data\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/charge-state\n      name: charge-state\n      description: Battery and charging status\n      operations:\n      - method: GET\n        name: get-charge-state\n        description: Get battery level and charging status\n        call: tesla-motors.get-charge-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/climate-state\n      name:\
  \ climate-state\n      description: Climate and temperature status\n      operations:\n      - method: GET\n        name: get-climate-state\n        description: Get climate settings and temperatures\n        call: tesla-motors.get-climate-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/drive-state\n      name: drive-state\n      description: Location and driving state\n      operations:\n      - method: GET\n        name: get-drive-state\n        description: Get GPS location and driving state\n        call: tesla-motors.get-drive-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/wake-up\n      name: wake-up\n      description: Wake vehicle from sleep\n      operations:\n      - method: POST\n        name: wake-up-vehicle\n        description:\
  \ Wake the vehicle from sleep mode\n        call: tesla-motors.wake-up-vehicle\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/doors/lock\n      name: doors-lock\n      description: Lock vehicle doors\n      operations:\n      - method: POST\n        name: lock-doors\n        description: Lock all vehicle doors\n        call: tesla-motors.lock-doors\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/doors/unlock\n      name: doors-unlock\n      description: Unlock vehicle doors\n      operations:\n      - method: POST\n        name: unlock-doors\n        description: Unlock all vehicle doors\n        call: tesla-motors.unlock-doors\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/vehicles/{vehicle_id}/climate/start\n      name: climate-start\n      description: Start climate control\n      operations:\n      - method: POST\n        name: start-climate\n        description: Start auto conditioning\n        call: tesla-motors.start-climate\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/charging/start\n      name: charging-start\n      description: Start charging\n      operations:\n      - method: POST\n        name: start-charging\n        description: Start vehicle charging\n        call: tesla-motors.start-charging\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/charging/stop\n      name: charging-stop\n      description: Stop charging\n      operations:\n      - method: POST\n        name: stop-charging\n\
  \        description: Stop vehicle charging\n        call: tesla-motors.stop-charging\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tesla-vehicle-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Tesla vehicle management and monitoring.\n    tools:\n    - name: list-vehicles\n      description: List all Tesla vehicles in the owner account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tesla-motors.list-vehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle\n      description: Get details and status for a specific Tesla vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-vehicle\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-vehicle-data\n      description: Get complete telemetry snapshot for a Tesla vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-vehicle-data\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charge-state\n      description: Get battery percentage, charging status, and charge limit for a Tesla\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-charge-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-climate-state\n      description: Get interior temperature and climate control settings for a Tesla\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-climate-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-drive-state\n      description: Get GPS location, heading, and speed for a Tesla vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-drive-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-state\n      description: Get physical state of a Tesla (doors, windows, trunk, odometer)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla-motors.get-vehicle-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wake-up-vehicle\n      description: Wake a sleeping Tesla from sleep mode to enable commands\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.wake-up-vehicle\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: lock-doors\n      description: Lock all doors on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.lock-doors\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlock-doors\n      description: Unlock all doors on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.unlock-doors\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-climate\n      description: Start climate control (pre-conditioning) on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.start-climate\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: stop-climate\n      description: Stop climate control on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.stop-climate\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-charging\n      description: Start charging a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.start-charging\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-charging\n      description: Stop charging a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.stop-charging\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: flash-lights\n      description: Flash Tesla headlights to visually locate the vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tesla-motors.flash-lights\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: honk-horn\n      description: Honk the Tesla horn to audibly locate the vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tesla-motors.honk-horn\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-sentry-mode\n      description: Enable or disable Tesla Sentry Mode for security monitoring\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla-motors.set-sentry-mode\n      with:\n    \
  \    vehicle_id: tools.vehicle_id\n        true: tools.on\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
