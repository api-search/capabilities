---
categories: []
consumed_apis: []
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
- set maximum battery charge level
- read active obd-ii diagnostic trouble codes for vehicle health assessment
- get make, model, year, and vin for a connected vehicle
- stop charging
- ev charging status and control
- ev battery status and range
- start charging
- manage vehicle connections and authorizations
- unlock vehicle
- get remaining engine oil life percentage to assess maintenance needs
- get charge status
- lock or unlock vehicle doors remotely
- telematics
- stop ev charging session
- get the current maximum battery charge limit setting
- get current battery percentage and estimated range
- get the current odometer reading in kilometers
- get battery level
- get lock status
- set a navigation destination in the vehicle
- get current gps latitude and longitude of the vehicle
- ev charge limit management
- get fuel level
- check current lock status of all vehicle doors and windows
- set the maximum battery charge percentage limit (0.5 to 1.0)
- get engine oil life
- get active obd-ii diagnostic trouble codes
- connected vehicles
- iot
- get charge limit
- vehicle lock/unlock status and control
- check if the ev is plugged in and its current charging state
- control charge
- list all connected vehicles authorized via smartcar
- mobility
- fleet management
- ice vehicle fuel status
- vehicle gps location
- set navigation destination
- vehicle attributes and metadata
- get current battery charge percentage and estimated range for an ev
- vehicle navigation
- automotive
- ev management
- get current charging state and plug-in status
- smartcar
- get diagnostic codes
- set charge limit
- vehicle odometer reading
- remotely lock the vehicle's doors
- get fuel tank level, liters remaining, and estimated driving range
- read the vehicle's current odometer value in kilometers
- list vehicle connections
- get current gps coordinates of the vehicle
- lock vehicle
- get vehicle make, model, year, and vin
- list connections
- get location
- send a gps navigation destination to the vehicle's nav system
- get vehicle location
- get fuel level, amount remaining, and estimated range
- remotely unlock the vehicle's doors
- get the current maximum charge limit
- start ev charging session
- list all authorized vehicle connections
- get odometer
- vehicle diagnostics
- get fuel tank
- start or stop ev charging
- control security
- get vehicle info
- get vehicle
- get current lock status of doors, windows, and storage
- set destination
slug: connected-vehicle-management
source_filename: connected-vehicle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Smartcar Connected Vehicle Management\n  description: Unified workflow capability for managing connected vehicles through Smartcar's platform. Enables fleet operators,\n    mobility apps, and EV management solutions to read vehicle telemetry, monitor charging status, control vehicle access,\n    and send navigation commands across multiple OEM brands through a single integration.\n  tags:\n  - Smartcar\n  - Connected Vehicles\n  - Automotive\n  - Fleet Management\n  - EV Management\n  - Telematics\n  - IoT\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SMARTCAR_ACCESS_TOKEN: SMARTCAR_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: smartcar\n    baseUri: https://vehicle.api.smartcar.com/v2.0\n    description: Smartcar Vehicle API for connected vehicle data and commands\n    authentication:\n      type: bearer\n      token: '{{SMARTCAR_ACCESS_TOKEN}}'\n    resources:\n  \
  \  - name: connections\n      path: /connections\n      description: Manage vehicle connections\n      operations:\n      - name: list-connections\n        method: GET\n        description: List all vehicle connections for the authorized user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connection\n        method: GET\n        description: Get a specific vehicle connection\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-connection\n        method: DELETE\n        description: Remove a vehicle connection\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle\n      path: /vehicles/{id}\n      description: Access vehicle data and attributes\n      operations:\n      - name: get-vehicle\n        method: GET\n        description: Get vehicle attributes and metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-signals\n        method: GET\n        description: Read all available telemetry signals for the vehicle\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: battery\n \
  \     path: /vehicles/{id}/battery\n      description: EV battery status\n      operations:\n      - name: get-battery-level\n        method: GET\n        description: Get battery charge level and estimated range\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge\n      path: /vehicles/{id}/charge\n      description: EV charging management\n      operations:\n      - name: get-charge-status\n        method: GET\n        description: Get current charging state and plug-in status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: control-charge\n        method: POST\n        description:\
  \ Start or stop vehicle charging\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charge-limit\n      path: /vehicles/{id}/charge/limit\n      description: EV charge limit management\n      operations:\n      - name: get-charge-limit\n        method: GET\n        description: Get the current charge limit setting\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-charge-limit\n        method: POST\n        description: Set the maximum battery charge level\n        inputParameters:\n \
  \       - name: id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            limit: '{{tools.limit}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security\n      path: /vehicles/{id}/security\n      description: Vehicle lock/unlock controls\n      operations:\n      - name: get-lock-status\n        method: GET\n        description: Get current lock status of doors and windows\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: control-security\n        method: POST\n        description: Lock or unlock vehicle doors\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n      \
  \    required: true\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location\n      path: /vehicles/{id}/location\n      description: Vehicle location\n      operations:\n      - name: get-location\n        method: GET\n        description: Get current GPS coordinates of the vehicle\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: odometer\n      path: /vehicles/{id}/odometer\n      description: Vehicle odometer reading\n      operations:\n      - name: get-odometer\n        method: GET\n        description: Get the vehicle's current odometer reading\n        inputParameters:\n        - name: id\n  \
  \        in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fuel\n      path: /vehicles/{id}/fuel\n      description: Vehicle fuel status\n      operations:\n      - name: get-fuel-tank\n        method: GET\n        description: Get fuel tank level, amount, and estimated range\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: engine-oil\n      path: /vehicles/{id}/engine/oil\n      description: Engine oil life\n      operations:\n      - name: get-engine-oil\n        method: GET\n        description: Get remaining engine oil life percentage\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n       \
  \   required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: diagnostics\n      path: /vehicles/{id}/diagnostics/dtcs\n      description: Vehicle diagnostic trouble codes\n      operations:\n      - name: get-diagnostic-codes\n        method: GET\n        description: Get active OBD-II diagnostic trouble codes\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: navigation\n      path: /vehicles/{id}/commands/set-destination\n      description: Vehicle navigation\n      operations:\n      - name: set-destination\n        method: POST\n        description: Set a navigation destination in the vehicle\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n \
  \         required: true\n        body:\n          type: json\n          data:\n            latitude: '{{tools.latitude}}'\n            longitude: '{{tools.longitude}}'\n            address: '{{tools.address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: smartcar-vehicle-api\n    description: Unified REST API for connected vehicle telemetry and control.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Manage vehicle connections and authorizations\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all authorized vehicle connections\n        call: smartcar.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}\n      name: vehicle\n      description: Vehicle attributes and metadata\n      operations:\n\
  \      - method: GET\n        name: get-vehicle\n        description: Get vehicle make, model, year, and VIN\n        call: smartcar.get-vehicle\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/battery\n      name: battery\n      description: EV battery status and range\n      operations:\n      - method: GET\n        name: get-battery-level\n        description: Get current battery percentage and estimated range\n        call: smartcar.get-battery-level\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/charge\n      name: charge\n      description: EV charging status and control\n      operations:\n      - method: GET\n        name: get-charge-status\n        description: Get current charging state and plug-in status\n        call: smartcar.get-charge-status\n        with:\n          id: rest.id\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: control-charge\n        description: Start or stop EV charging\n        call: smartcar.control-charge\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/charge-limit\n      name: charge-limit\n      description: EV charge limit management\n      operations:\n      - method: GET\n        name: get-charge-limit\n        description: Get the current maximum charge limit\n        call: smartcar.get-charge-limit\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-charge-limit\n        description: Set maximum battery charge level\n        call: smartcar.set-charge-limit\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/security\n\
  \      name: security\n      description: Vehicle lock/unlock status and control\n      operations:\n      - method: GET\n        name: get-lock-status\n        description: Get current lock status of doors, windows, and storage\n        call: smartcar.get-lock-status\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: control-security\n        description: Lock or unlock vehicle doors remotely\n        call: smartcar.control-security\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/location\n      name: location\n      description: Vehicle GPS location\n      operations:\n      - method: GET\n        name: get-location\n        description: Get current GPS coordinates of the vehicle\n        call: smartcar.get-location\n        with:\n          id: rest.id\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/vehicles/{id}/odometer\n      name: odometer\n      description: Vehicle odometer reading\n      operations:\n      - method: GET\n        name: get-odometer\n        description: Get the current odometer reading in kilometers\n        call: smartcar.get-odometer\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/fuel\n      name: fuel\n      description: ICE vehicle fuel status\n      operations:\n      - method: GET\n        name: get-fuel-tank\n        description: Get fuel level, amount remaining, and estimated range\n        call: smartcar.get-fuel-tank\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/diagnostics\n      name: diagnostics\n      description: Vehicle diagnostics\n      operations:\n      - method: GET\n        name: get-diagnostic-codes\n\
  \        description: Get active OBD-II diagnostic trouble codes\n        call: smartcar.get-diagnostic-codes\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}/destination\n      name: navigation\n      description: Vehicle navigation\n      operations:\n      - method: POST\n        name: set-destination\n        description: Set a navigation destination in the vehicle\n        call: smartcar.set-destination\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: smartcar-vehicle-mcp\n    transport: http\n    description: MCP server for AI-assisted connected vehicle management.\n    tools:\n    - name: list-vehicle-connections\n      description: List all connected vehicles authorized via Smartcar\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.list-connections\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-info\n      description: Get make, model, year, and VIN for a connected vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-vehicle\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-battery-level\n      description: Get current battery charge percentage and estimated range for an EV\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-battery-level\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charge-status\n      description: Check if the EV is plugged in and its current charging state\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-charge-status\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: start-charging\n      description: Start EV charging session\n      hints:\n        readOnly: false\n        idempotent: false\n      call: smartcar.control-charge\n      with:\n        id: tools.id\n        action: START\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-charging\n      description: Stop EV charging session\n      hints:\n        readOnly: false\n        idempotent: false\n      call: smartcar.control-charge\n      with:\n        id: tools.id\n        action: STOP\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-charge-limit\n      description: Get the current maximum battery charge limit setting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-charge-limit\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-charge-limit\n      description: Set the maximum battery\
  \ charge percentage limit (0.5 to 1.0)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: smartcar.set-charge-limit\n      with:\n        id: tools.id\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-location\n      description: Get current GPS latitude and longitude of the vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-location\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lock-vehicle\n      description: Remotely lock the vehicle's doors\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: smartcar.control-security\n      with:\n        id: tools.id\n        action: LOCK\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unlock-vehicle\n      description: Remotely unlock the vehicle's\
  \ doors\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: smartcar.control-security\n      with:\n        id: tools.id\n        action: UNLOCK\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-lock-status\n      description: Check current lock status of all vehicle doors and windows\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-lock-status\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-odometer\n      description: Read the vehicle's current odometer value in kilometers\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-odometer\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fuel-level\n      description: Get fuel tank level, liters remaining, and estimated driving range\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-fuel-tank\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-engine-oil-life\n      description: Get remaining engine oil life percentage to assess maintenance needs\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-engine-oil\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-diagnostic-codes\n      description: Read active OBD-II diagnostic trouble codes for vehicle health assessment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: smartcar.get-diagnostic-codes\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-navigation-destination\n      description: Send a GPS navigation destination to the vehicle's nav system\n      hints:\n\
  \        readOnly: false\n        idempotent: false\n      call: smartcar.set-destination\n      with:\n        id: tools.id\n        latitude: tools.latitude\n        longitude: tools.longitude\n        address: tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
