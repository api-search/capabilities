---
api_specs:
- filename: smartcar-vehicles-openapi.yml
  format: yaml
  label: smartcar
  slug: smartcar
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/smartcar/refs/heads/main/openapi/smartcar-vehicles-openapi.yml
categories: []
consumed_apis:
- smartcar
description: Unified workflow capability for managing connected vehicles through Smartcar's platform. Enables fleet operators, mobility apps, and EV management solutions to read vehicle telemetry, monitor charging status, control vehicle access, and send navigation commands across multiple OEM brands through a single integration.
layout: capability
name: Smartcar Connected Vehicle Management
operations:
- description: List all authorized vehicle connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: Get vehicle make, model, year, and VIN
  method: GET
  name: get-vehicle
  path: /v1/vehicles/{id}
- description: Get current battery percentage and estimated range
  method: GET
  name: get-battery-level
  path: /v1/vehicles/{id}/battery
- description: Get current charging state and plug-in status
  method: GET
  name: get-charge-status
  path: /v1/vehicles/{id}/charge
- description: Start or stop EV charging
  method: POST
  name: control-charge
  path: /v1/vehicles/{id}/charge
- description: Get the current maximum charge limit
  method: GET
  name: get-charge-limit
  path: /v1/vehicles/{id}/charge-limit
- description: Set maximum battery charge level
  method: POST
  name: set-charge-limit
  path: /v1/vehicles/{id}/charge-limit
- description: Get current lock status of doors, windows, and storage
  method: GET
  name: get-lock-status
  path: /v1/vehicles/{id}/security
- description: Lock or unlock vehicle doors remotely
  method: POST
  name: control-security
  path: /v1/vehicles/{id}/security
- description: Get current GPS coordinates of the vehicle
  method: GET
  name: get-location
  path: /v1/vehicles/{id}/location
- description: Get the current odometer reading in kilometers
  method: GET
  name: get-odometer
  path: /v1/vehicles/{id}/odometer
- description: Get fuel level, amount remaining, and estimated range
  method: GET
  name: get-fuel-tank
  path: /v1/vehicles/{id}/fuel
- description: Get active OBD-II diagnostic trouble codes
  method: GET
  name: get-diagnostic-codes
  path: /v1/vehicles/{id}/diagnostics
- description: Set a navigation destination in the vehicle
  method: POST
  name: set-destination
  path: /v1/vehicles/{id}/destination
personas: []
provider_name: Smartcar
provider_slug: smartcar
search_terms:
- mobility
- get current battery percentage and estimated range
- check if the ev is plugged in and its current charging state
- stop ev charging session
- automotive
- vehicle attributes and metadata
- get make, model, year, and vin for a connected vehicle
- lock or unlock vehicle doors remotely
- set navigation destination
- get battery level
- connected vehicles
- list connections
- list vehicle connections
- get the current odometer reading in kilometers
- get current gps coordinates of the vehicle
- set charge limit
- control charge
- get charge limit
- get odometer
- get fuel tank
- get active obd-ii diagnostic trouble codes
- start charging
- get fuel tank level, liters remaining, and estimated driving range
- send a gps navigation destination to the vehicle's nav system
- check current lock status of all vehicle doors and windows
- get vehicle location
- set destination
- unlock vehicle
- ice vehicle fuel status
- read the vehicle's current odometer value in kilometers
- get lock status
- get the current maximum battery charge limit setting
- vehicle odometer reading
- vehicle navigation
- get the current maximum charge limit
- get current lock status of doors, windows, and storage
- get current gps latitude and longitude of the vehicle
- get vehicle
- get diagnostic codes
- get fuel level
- get current charging state and plug-in status
- read active obd-ii diagnostic trouble codes for vehicle health assessment
- set the maximum battery charge percentage limit (0.5 to 1.0)
- vehicle diagnostics
- remotely unlock the vehicle's doors
- start or stop ev charging
- get remaining engine oil life percentage to assess maintenance needs
- remotely lock the vehicle's doors
- lock vehicle
- stop charging
- set maximum battery charge level
- ev charge limit management
- list all connected vehicles authorized via smartcar
- ev battery status and range
- get fuel level, amount remaining, and estimated range
- vehicle lock/unlock status and control
- get charge status
- ev management
- get location
- get vehicle info
- telematics
- get vehicle make, model, year, and vin
- smartcar
- vehicle gps location
- start ev charging session
- fleet management
- get current battery charge percentage and estimated range for an ev
- get engine oil life
- iot
- list all authorized vehicle connections
- set a navigation destination in the vehicle
- control security
- manage vehicle connections and authorizations
- ev charging status and control
slug: connected-vehicle-management
source_filename: connected-vehicle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Smartcar Connected Vehicle Management\n  description: >-\n    Unified workflow capability for managing connected vehicles through Smartcar's\n    platform. Enables fleet operators, mobility apps, and EV management solutions\n    to read vehicle telemetry, monitor charging status, control vehicle access,\n    and send navigation commands across multiple OEM brands through a single\n    integration.\n  tags:\n    - Smartcar\n    - Connected Vehicles\n    - Automotive\n    - Fleet Management\n    - EV Management\n    - Telematics\n    - IoT\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMARTCAR_ACCESS_TOKEN: SMARTCAR_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: smartcar\n      location: ./shared/smartcar-vehicles.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: smartcar-vehicle-api\n      description: Unified REST API for connected vehicle telemetry\
  \ and control.\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: Manage vehicle connections and authorizations\n          operations:\n            - method: GET\n              name: list-connections\n              description: List all authorized vehicle connections\n              call: \"smartcar.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}\n          name: vehicle\n          description: Vehicle attributes and metadata\n          operations:\n            - method: GET\n              name: get-vehicle\n              description: Get vehicle make, model, year, and VIN\n              call: \"smartcar.get-vehicle\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/battery\n          name: battery\n\
  \          description: EV battery status and range\n          operations:\n            - method: GET\n              name: get-battery-level\n              description: Get current battery percentage and estimated range\n              call: \"smartcar.get-battery-level\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/charge\n          name: charge\n          description: EV charging status and control\n          operations:\n            - method: GET\n              name: get-charge-status\n              description: Get current charging state and plug-in status\n              call: \"smartcar.get-charge-status\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: control-charge\n              description:\
  \ Start or stop EV charging\n              call: \"smartcar.control-charge\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/charge-limit\n          name: charge-limit\n          description: EV charge limit management\n          operations:\n            - method: GET\n              name: get-charge-limit\n              description: Get the current maximum charge limit\n              call: \"smartcar.get-charge-limit\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: set-charge-limit\n              description: Set maximum battery charge level\n              call: \"smartcar.set-charge-limit\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n               \
  \ - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/security\n          name: security\n          description: Vehicle lock/unlock status and control\n          operations:\n            - method: GET\n              name: get-lock-status\n              description: Get current lock status of doors, windows, and storage\n              call: \"smartcar.get-lock-status\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: control-security\n              description: Lock or unlock vehicle doors remotely\n              call: \"smartcar.control-security\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/location\n          name: location\n          description: Vehicle GPS\
  \ location\n          operations:\n            - method: GET\n              name: get-location\n              description: Get current GPS coordinates of the vehicle\n              call: \"smartcar.get-location\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/odometer\n          name: odometer\n          description: Vehicle odometer reading\n          operations:\n            - method: GET\n              name: get-odometer\n              description: Get the current odometer reading in kilometers\n              call: \"smartcar.get-odometer\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/fuel\n          name: fuel\n          description: ICE vehicle fuel status\n          operations:\n            - method:\
  \ GET\n              name: get-fuel-tank\n              description: Get fuel level, amount remaining, and estimated range\n              call: \"smartcar.get-fuel-tank\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/diagnostics\n          name: diagnostics\n          description: Vehicle diagnostics\n          operations:\n            - method: GET\n              name: get-diagnostic-codes\n              description: Get active OBD-II diagnostic trouble codes\n              call: \"smartcar.get-diagnostic-codes\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}/destination\n          name: navigation\n          description: Vehicle navigation\n          operations:\n            - method: POST\n            \
  \  name: set-destination\n              description: Set a navigation destination in the vehicle\n              call: \"smartcar.set-destination\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: smartcar-vehicle-mcp\n      transport: http\n      description: MCP server for AI-assisted connected vehicle management.\n      tools:\n        - name: list-vehicle-connections\n          description: List all connected vehicles authorized via Smartcar\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-info\n          description: Get make, model, year, and VIN for a connected vehicle\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"smartcar.get-vehicle\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-battery-level\n          description: Get current battery charge percentage and estimated range for an EV\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-battery-level\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-charge-status\n          description: Check if the EV is plugged in and its current charging state\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-charge-status\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-charging\n          description:\
  \ Start EV charging session\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"smartcar.control-charge\"\n          with:\n            id: \"tools.id\"\n            action: \"START\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-charging\n          description: Stop EV charging session\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"smartcar.control-charge\"\n          with:\n            id: \"tools.id\"\n            action: \"STOP\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-charge-limit\n          description: Get the current maximum battery charge limit setting\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-charge-limit\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: set-charge-limit\n          description: Set the maximum battery charge percentage limit (0.5 to 1.0)\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"smartcar.set-charge-limit\"\n          with:\n            id: \"tools.id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-location\n          description: Get current GPS latitude and longitude of the vehicle\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-location\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lock-vehicle\n          description: Remotely lock the vehicle's doors\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"smartcar.control-security\"\n          with:\n            id: \"tools.id\"\n            action: \"LOCK\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unlock-vehicle\n          description: Remotely unlock the vehicle's doors\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"smartcar.control-security\"\n          with:\n            id: \"tools.id\"\n            action: \"UNLOCK\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lock-status\n          description: Check current lock status of all vehicle doors and windows\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-lock-status\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-odometer\n          description: Read the vehicle's current odometer value in kilometers\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-odometer\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-fuel-level\n          description: Get fuel tank level, liters remaining, and estimated driving range\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-fuel-tank\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-engine-oil-life\n          description: Get remaining engine oil life percentage to assess maintenance needs\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"smartcar.get-engine-oil\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-diagnostic-codes\n          description: Read active OBD-II diagnostic trouble codes for vehicle health assessment\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"smartcar.get-diagnostic-codes\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-navigation-destination\n          description: Send a GPS navigation destination to the vehicle's nav system\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"smartcar.set-destination\"\n          with:\n            id: \"tools.id\"\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            address: \"tools.address\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smartcar/refs/heads/main/capabilities/connected-vehicle-management.yaml
tags:
- Smartcar
- Connected Vehicles
- Automotive
- Fleet Management
- EV Management
- Telematics
- IoT
tools:
- description: List all connected vehicles authorized via Smartcar
  hints:
    openWorld: false
    readOnly: true
  name: list-vehicle-connections
- description: Get make, model, year, and VIN for a connected vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-info
- description: Get current battery charge percentage and estimated range for an EV
  hints:
    openWorld: false
    readOnly: true
  name: get-battery-level
- description: Check if the EV is plugged in and its current charging state
  hints:
    openWorld: false
    readOnly: true
  name: get-charge-status
- description: Start EV charging session
  hints:
    idempotent: false
    readOnly: false
  name: start-charging
- description: Stop EV charging session
  hints:
    idempotent: false
    readOnly: false
  name: stop-charging
- description: Get the current maximum battery charge limit setting
  hints:
    openWorld: false
    readOnly: true
  name: get-charge-limit
- description: Set the maximum battery charge percentage limit (0.5 to 1.0)
  hints:
    idempotent: true
    readOnly: false
  name: set-charge-limit
- description: Get current GPS latitude and longitude of the vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle-location
- description: Remotely lock the vehicle's doors
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lock-vehicle
- description: Remotely unlock the vehicle's doors
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unlock-vehicle
- description: Check current lock status of all vehicle doors and windows
  hints:
    openWorld: false
    readOnly: true
  name: get-lock-status
- description: Read the vehicle's current odometer value in kilometers
  hints:
    openWorld: false
    readOnly: true
  name: get-odometer
- description: Get fuel tank level, liters remaining, and estimated driving range
  hints:
    openWorld: false
    readOnly: true
  name: get-fuel-level
- description: Get remaining engine oil life percentage to assess maintenance needs
  hints:
    openWorld: false
    readOnly: true
  name: get-engine-oil-life
- description: Read active OBD-II diagnostic trouble codes for vehicle health assessment
  hints:
    openWorld: false
    readOnly: true
  name: get-diagnostic-codes
- description: Send a GPS navigation destination to the vehicle's nav system
  hints:
    idempotent: false
    readOnly: false
  name: set-navigation-destination
---
