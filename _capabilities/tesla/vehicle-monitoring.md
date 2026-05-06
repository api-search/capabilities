---
categories: []
consumed_apis: []
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
- get battery percentage, charging status, and range estimate
- cars
- stop charging
- full vehicle telemetry
- climate and temperature
- get vehicle state
- nearby charging sites
- start charging
- clean energy
- lock all doors on a tesla vehicle
- set sentry mode
- unlock all doors
- get drive state
- iot
- unlock doors
- wake a sleeping tesla to enable remote commands
- remote commands
- electric vehicles
- fleet management
- lock all doors
- get physical state of the vehicle (doors, windows, trunk, odometer)
- get charge state
- start charging a tesla vehicle
- get vehicle data
- get nearby charging sites
- unlock all doors on a tesla vehicle
- stop climate control on a tesla
- enable or disable tesla sentry mode for security monitoring
- battery and charging status
- start climate pre-conditioning (heating/cooling) on a tesla
- find nearby charging sites
- wake vehicle from sleep
- get drive state and location
- find nearby superchargers and destination chargers with availability
- vehicles
- automobiles
- tesla
- wake up vehicle
- stop climate
- energy
- smart vehicles
- get complete telemetry snapshot for a tesla vehicle
- list all tesla vehicles
- list all tesla vehicles in the owner account
- list vehicles
- stop charging a tesla vehicle
- vehicle fleet listing
- get climate state
- lock doors
- get interior temperature and climate control settings
- get vehicle gps location, heading, and speed
- start climate
- get all vehicle data
- location and driving state
- wake vehicle
slug: vehicle-monitoring
source_filename: vehicle-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tesla Vehicle Monitoring and Control\n  description: Workflow capability for Tesla vehicle monitoring and remote control via the Tesla Owner API. Enables fleet\n    managers, IoT integrations, and personal vehicle owners to monitor battery, climate, location, and physical state, and\n    execute remote commands including wake-up, lock/unlock, climate control, charging management, sentry mode, and charging\n    site discovery.\n  tags:\n  - Tesla\n  - Electric Vehicles\n  - Automobiles\n  - IoT\n  - Smart Vehicles\n  - Remote Commands\n  - Fleet Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TESLA_ACCESS_TOKEN: TESLA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tesla\n    baseUri: https://owner-api.teslamotors.com\n    description: Tesla Owner API for vehicle telemetry and remote commands\n    authentication:\n      type: bearer\n      token: '{{TESLA_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: vehicles\n      path: /api/1/vehicles\n      description: List all vehicles in owner account\n      operations:\n      - name: list-vehicles\n        method: GET\n        description: List all owned Tesla vehicles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle\n      path: /api/1/vehicles/{vehicle_id}\n      description: Get specific vehicle details\n      operations:\n      - name: get-vehicle\n        method: GET\n        description: Retrieve a specific vehicle\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-data\n      path: /api/1/vehicles/{vehicle_id}/vehicle_data\n      description: Get all vehicle\
  \ data\n      operations:\n      - name: get-vehicle-data\n        method: GET\n        description: Get all vehicle data including charge, climate, drive, and state\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/charge_state\n      description: Get battery and charge state\n      operations:\n      - name: get-charge-state\n        method: GET\n        description: Get battery level and charging status\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: climate-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/climate_state\n      description: Get climate and temperature state\n      operations:\n      - name: get-climate-state\n        method: GET\n        description: Get temperature and climate settings\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drive-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/drive_state\n      description: Get drive and position state\n      operations:\n      - name: get-drive-state\n        method: GET\n        description: Get location, speed, and drive state\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-state\n      path: /api/1/vehicles/{vehicle_id}/data_request/vehicle_state\n      description: Get physical vehicle state\n      operations:\n      - name: get-vehicle-state\n        method: GET\n        description: Get physical state (doors, windows, trunk)\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wake-up\n      path: /api/1/vehicles/{vehicle_id}/wake_up\n      description: Wake up vehicle\n      operations:\n      - name: wake-up-vehicle\n        method: POST\n        description: Wake the vehicle from sleep\n        inputParameters:\n        - name: vehicle_id\n        \
  \  in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: door-unlock\n      path: /api/1/vehicles/{vehicle_id}/command/door_unlock\n      description: Unlock vehicle doors\n      operations:\n      - name: unlock-doors\n        method: POST\n        description: Unlock all vehicle doors\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: door-lock\n      path: /api/1/vehicles/{vehicle_id}/command/door_lock\n      description: Lock vehicle doors\n      operations:\n      - name: lock-doors\n        method: POST\n        description: Lock all vehicle doors\n        inputParameters:\n\
  \        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate-start\n      path: /api/1/vehicles/{vehicle_id}/command/auto_conditioning_start\n      description: Start climate control\n      operations:\n      - name: start-climate\n        method: POST\n        description: Start auto conditioning\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate-stop\n      path: /api/1/vehicles/{vehicle_id}/command/auto_conditioning_stop\n      description: Stop climate control\n      operations:\n      - name: stop-climate\n      \
  \  method: POST\n        description: Stop auto conditioning\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-start\n      path: /api/1/vehicles/{vehicle_id}/command/charge_start\n      description: Start charging\n      operations:\n      - name: start-charging\n        method: POST\n        description: Start vehicle charging\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-stop\n      path: /api/1/vehicles/{vehicle_id}/command/charge_stop\n      description: Stop charging\n    \
  \  operations:\n      - name: stop-charging\n        method: POST\n        description: Stop vehicle charging\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sentry-mode\n      path: /api/1/vehicles/{vehicle_id}/command/set_sentry_mode\n      description: Control sentry mode\n      operations:\n      - name: set-sentry-mode\n        method: POST\n        description: Enable or disable Sentry Mode\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        body:\n          type: json\n          data:\n            true: '{{tools.on}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: nearby-charging\n      path: /api/1/vehicles/{vehicle_id}/nearby_charging_sites\n      description: Get nearby charging sites\n      operations:\n      - name: get-nearby-charging-sites\n        method: GET\n        description: Get nearby Superchargers and destination chargers\n        inputParameters:\n        - name: vehicle_id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tesla-vehicle-api\n    description: Unified REST API for Tesla vehicle monitoring and control.\n    resources:\n    - path: /v1/vehicles\n      name: vehicles\n      description: Vehicle fleet listing\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: List all Tesla vehicles\n        call: tesla.list-vehicles\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/data\n      name: vehicle-data\n      description: Full vehicle telemetry\n      operations:\n      - method: GET\n        name: get-vehicle-data\n        description: Get all vehicle data\n        call: tesla.get-vehicle-data\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/charge-state\n      name: charge-state\n      description: Battery and charging status\n      operations:\n      - method: GET\n        name: get-charge-state\n        description: Get charge state\n        call: tesla.get-charge-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/climate-state\n      name: climate-state\n      description: Climate and temperature\n   \
  \   operations:\n      - method: GET\n        name: get-climate-state\n        description: Get climate state\n        call: tesla.get-climate-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/drive-state\n      name: drive-state\n      description: Location and driving state\n      operations:\n      - method: GET\n        name: get-drive-state\n        description: Get drive state and location\n        call: tesla.get-drive-state\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/nearby-charging\n      name: nearby-charging\n      description: Nearby charging sites\n      operations:\n      - method: GET\n        name: get-nearby-charging-sites\n        description: Find nearby charging sites\n        call: tesla.get-nearby-charging-sites\n        with:\n\
  \          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/commands/wake-up\n      name: wake-up\n      description: Wake vehicle from sleep\n      operations:\n      - method: POST\n        name: wake-up-vehicle\n        description: Wake vehicle\n        call: tesla.wake-up-vehicle\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/commands/lock\n      name: lock\n      description: Lock doors\n      operations:\n      - method: POST\n        name: lock-doors\n        description: Lock all doors\n        call: tesla.lock-doors\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vehicle_id}/commands/unlock\n      name: unlock\n      description: Unlock doors\n      operations:\n\
  \      - method: POST\n        name: unlock-doors\n        description: Unlock all doors\n        call: tesla.unlock-doors\n        with:\n          vehicle_id: rest.vehicle_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tesla-vehicle-mcp\n    transport: http\n    description: MCP server for AI-assisted Tesla vehicle monitoring and control.\n    tools:\n    - name: list-vehicles\n      description: List all Tesla vehicles in the owner account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tesla.list-vehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-data\n      description: Get complete telemetry snapshot for a Tesla vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla.get-vehicle-data\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-charge-state\n      description: Get battery percentage, charging status, and range estimate\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla.get-charge-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-climate-state\n      description: Get interior temperature and climate control settings\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla.get-climate-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-drive-state\n      description: Get vehicle GPS location, heading, and speed\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla.get-drive-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-state\n\
  \      description: Get physical state of the vehicle (doors, windows, trunk, odometer)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tesla.get-vehicle-state\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-nearby-charging-sites\n      description: Find nearby Superchargers and destination chargers with availability\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tesla.get-nearby-charging-sites\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wake-up-vehicle\n      description: Wake a sleeping Tesla to enable remote commands\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.wake-up-vehicle\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: lock-doors\n      description: Lock all doors on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.lock-doors\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlock-doors\n      description: Unlock all doors on a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.unlock-doors\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-climate\n      description: Start climate pre-conditioning (heating/cooling) on a Tesla\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.start-climate\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: stop-climate\n      description: Stop climate control on a Tesla\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.stop-climate\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-charging\n      description: Start charging a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.start-charging\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-charging\n      description: Stop charging a Tesla vehicle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.stop-charging\n      with:\n        vehicle_id: tools.vehicle_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-sentry-mode\n\
  \      description: Enable or disable Tesla Sentry Mode for security monitoring\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: tesla.set-sentry-mode\n      with:\n        vehicle_id: tools.vehicle_id\n        true: tools.on\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
