---
categories: []
consumed_apis: []
description: Workflow capability for fleet managers and rental car operators combining Toyota Telematics and Connected Services APIs. Enables vehicle enrollment, health monitoring, location tracking, telemetry analysis, and trip reporting for Toyota fleet operations.
layout: capability
name: Toyota Fleet Management
operations:
- description: List fleet vehicles
  method: GET
  name: list-vehicles
  path: /v1/vehicles
- description: Get vehicle telematics
  method: GET
  name: get-vehicle
  path: /v1/vehicles/{vin}
- description: Get vehicle health
  method: GET
  name: get-vehicle-health
  path: /v1/vehicles/{vin}/health
- description: Get vehicle telemetry
  method: GET
  name: get-vehicle-telemetry
  path: /v1/vehicles/{vin}/telemetry
- description: Get vehicle GPS location
  method: GET
  name: get-vehicle-location
  path: /v1/vehicles/{vin}/location
- description: Get trip history
  method: GET
  name: get-vehicle-trips
  path: /v1/vehicles/{vin}/trips
- description: Get subscription details
  method: GET
  name: get-vehicle-subscriptions
  path: /v1/vehicles/{vin}/subscriptions
- description: Get current vehicle status
  method: GET
  name: get-vehicle-status
  path: /v1/vehicles/{vin}/status
- description: Get EV battery and charging status
  method: GET
  name: get-ev-status
  path: /v1/vehicles/{vin}/ev-status
personas: []
provider_name: Toyota
provider_slug: toyota
search_terms:
- get vehicle
- get vehicle telemetry
- telematics
- vehicle telemetry
- real-time vehicle status
- get the current gps coordinates of a fleet vehicle
- ev battery and charging
- automobiles
- connected car
- get odometer, fuel level, and estimated range for a fleet vehicle
- get connected services and satellite radio subscription status for a vehicle
- electric vehicles
- get real-time door lock and window status for a connected vehicle
- get vehicle trips
- vehicles
- get trip history for a fleet vehicle over a specified date range
- connected service subscriptions
- get ev status
- get service history
- fleet vehicle management
- list vehicles
- get dealer service history records for a vehicle
- enroll a new vehicle in the toyota telematics fleet program
- get ev battery status
- vehicle health status
- enroll fleet vehicle
- list all vehicles enrolled in the toyota telematics fleet program
- get ev battery percentage, electric range, and charging status for hybrid/ev vehicles
- vehicle health
- get vehicle telematics
- vehicle location
- vehicle trip history
- get vehicle subscriptions
- get vehicle location
- cars
- list fleet vehicles
- get vehicle status
- get vehicle alerts
- get current vehicle status
- individual vehicle
- fleet management
- automotive
- get telematics enrollment details for a specific fleet vehicle by vin
- get vehicle gps location
- get maintenance alerts and vehicle notifications for a connected vehicle
- get trip history
- get vehicle door status
- get vehicle health
- get ev battery and charging status
- get vehicle health status including warning lights and oil level for a fleet vehicle
- get subscription details
slug: fleet-management
source_filename: fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toyota Fleet Management\n  description: Workflow capability for fleet managers and rental car operators combining Toyota Telematics and Connected Services\n    APIs. Enables vehicle enrollment, health monitoring, location tracking, telemetry analysis, and trip reporting for Toyota\n    fleet operations.\n  tags:\n  - Automotive\n  - Fleet Management\n  - Telematics\n  - Vehicle Health\n  - Connected Car\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOYOTA_TELEMATICS_TOKEN: TOYOTA_TELEMATICS_TOKEN\n    TOYOTA_CONNECTED_TOKEN: TOYOTA_CONNECTED_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: toyota-telematics\n    baseUri: https://api.eig.toyota.com/telematics/v1\n    description: Toyota Telematics API for vehicle fleet data access\n    authentication:\n      type: bearer\n      token: '{{TOYOTA_TELEMATICS_TOKEN}}'\n    resources:\n    - name: vehicles\n      path: /vehicles\n \
  \     description: Fleet vehicle listing\n      operations:\n      - name: list-vehicles\n        method: GET\n        description: List vehicles enrolled in telematics program\n        inputParameters:\n        - name: fleetId\n          in: query\n          type: string\n          required: false\n          description: Fleet identifier filter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Enrollment status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle\n      path: /vehicles/{vin}\n      description: Individual vehicle telematics\n      operations:\n      - name: get-vehicle\n        method: GET\n        description: Get telematics details for a vehicle by VIN\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: 17-character\
  \ VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /vehicles/{vin}/subscriptions\n      description: Vehicle connected service subscriptions\n      operations:\n      - name: get-vehicle-subscriptions\n        method: GET\n        description: Get connected service and satellite radio subscription details\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /vehicles/{vin}/health\n      description: Vehicle health data\n      operations:\n      - name: get-vehicle-health\n        method: GET\n        description: Get vehicle health status and warning lights\n        inputParameters:\n        - name: vin\n          in:\
  \ path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: telemetry\n      path: /vehicles/{vin}/telemetry\n      description: Vehicle telemetry data\n      operations:\n      - name: get-vehicle-telemetry\n        method: GET\n        description: Get odometer, fuel level, and distance data\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location\n      path: /vehicles/{vin}/location\n      description: Vehicle GPS location\n      operations:\n      - name: get-vehicle-location\n        method: GET\n        description: Get current GPS location of vehicle\n        inputParameters:\n     \
  \   - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trips\n      path: /vehicles/{vin}/trips\n      description: Vehicle trip history\n      operations:\n      - name: get-vehicle-trips\n        method: GET\n        description: Get trip history for a date range\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: toDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max trips\
  \ (max 50)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enroll\n      path: /fleet/{fleetId}/vehicles/enroll\n      description: Vehicle fleet enrollment\n      operations:\n      - name: enroll-vehicle\n        method: POST\n        description: Enroll a vehicle in the telematics fleet\n        inputParameters:\n        - name: fleetId\n          in: path\n          type: string\n          required: true\n          description: Fleet identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            vin: '{{tools.vin}}'\n            services: '{{tools.services}}'\n  - type: http\n    namespace: toyota-connected\n    baseUri: https://api.toyota.com/connected/v1\n    description: Toyota Connected Services API for real-time vehicle data and remote commands\n\
  \    authentication:\n      type: bearer\n      token: '{{TOYOTA_CONNECTED_TOKEN}}'\n    resources:\n    - name: vehicles\n      path: /vehicles\n      description: Connected vehicle list\n      operations:\n      - name: list-connected-vehicles\n        method: GET\n        description: List all connected vehicles registered to the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-status\n      path: /vehicles/{vin}/status\n      description: Vehicle real-time status\n      operations:\n      - name: get-vehicle-status\n        method: GET\n        description: Get current vehicle status (doors, ignition, windows)\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: status-refresh\n      path: /vehicles/{vin}/status/refresh\n      description: Refresh vehicle status\n      operations:\n      - name: refresh-vehicle-status\n        method: POST\n        description: Wake vehicle and refresh status data\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            deviceId: '{{tools.deviceId}}'\n            deviceType: '{{tools.deviceType}}'\n            guid: '{{tools.guid}}'\n            vin: '{{tools.vin}}'\n    - name: vehicle-health\n      path: /vehicles/{vin}/health\n      description: Vehicle health diagnostics\n      operations:\n      - name: get-vehicle-health-status\n        method: GET\n        description: Get oil level and warning lights\n        inputParameters:\n\
  \        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-location\n      path: /vehicles/{vin}/location\n      description: Vehicle location\n      operations:\n      - name: get-vehicle-position\n        method: GET\n        description: Get last known GPS location when parked\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: electric-status\n      path: /vehicles/{vin}/electric\n      description: EV battery and charging status\n      operations:\n      - name: get-electric-status\n        method: GET\n        description: Get EV battery level, range,\
  \ and charging status\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: electric-refresh\n      path: /vehicles/{vin}/electric/refresh\n      description: Refresh EV status\n      operations:\n      - name: refresh-electric-status\n        method: POST\n        description: Request updated state-of-charge from vehicle\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate\n      path: /vehicles/{vin}/climate\n      description: Climate control status and settings\n      operations:\n      - name: get-climate-status\n    \
  \    method: GET\n        description: Get current climate control settings\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: climate-command\n      path: /vehicles/{vin}/climate/command\n      description: Remote climate control\n      operations:\n      - name: send-climate-command\n        method: POST\n        description: Send climate start/stop command to vehicle\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            command: '{{tools.command}}'\n            temperature:\
  \ '{{tools.temperature}}'\n    - name: trips\n      path: /vehicles/{vin}/trips\n      description: Trip history\n      operations:\n      - name: get-trips\n        method: GET\n        description: Get trip history for a date range\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: toDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notifications\n      path: /vehicles/{vin}/notifications\n      description: Vehicle notifications\n      operations:\n      - name: get-vehicle-notifications\n        method: GET\n        description: Get vehicle alerts\
  \ and notifications\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: remote-command\n      path: /vehicles/{vin}/remote-command\n      description: Remote vehicle commands\n      operations:\n      - name: send-remote-command\n        method: POST\n        description: Send remote command (lock, unlock, horn, etc.)\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            command: '{{tools.command}}'\n            beeps: '{{tools.beeps}}'\n    - name: service-history\n      path:\
  \ /vehicles/{vin}/service-history\n      description: Vehicle service history\n      operations:\n      - name: get-service-history\n        method: GET\n        description: Get service history records\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: toyota-fleet-api\n    description: Unified REST API for Toyota fleet management and vehicle monitoring.\n    resources:\n    - path: /v1/vehicles\n      name: vehicles\n      description: Fleet vehicle management\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: List fleet vehicles\n        call: toyota-telematics.list-vehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}\n\
  \      name: vehicle\n      description: Individual vehicle\n      operations:\n      - method: GET\n        name: get-vehicle\n        description: Get vehicle telematics\n        call: toyota-telematics.get-vehicle\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/health\n      name: vehicle-health\n      description: Vehicle health status\n      operations:\n      - method: GET\n        name: get-vehicle-health\n        description: Get vehicle health\n        call: toyota-telematics.get-vehicle-health\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/telemetry\n      name: vehicle-telemetry\n      description: Vehicle telemetry\n      operations:\n      - method: GET\n        name: get-vehicle-telemetry\n        description: Get vehicle telemetry\n        call: toyota-telematics.get-vehicle-telemetry\n\
  \        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/location\n      name: vehicle-location\n      description: Vehicle location\n      operations:\n      - method: GET\n        name: get-vehicle-location\n        description: Get vehicle GPS location\n        call: toyota-telematics.get-vehicle-location\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/trips\n      name: vehicle-trips\n      description: Vehicle trip history\n      operations:\n      - method: GET\n        name: get-vehicle-trips\n        description: Get trip history\n        call: toyota-telematics.get-vehicle-trips\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/subscriptions\n      name: subscriptions\n      description: Connected service\
  \ subscriptions\n      operations:\n      - method: GET\n        name: get-vehicle-subscriptions\n        description: Get subscription details\n        call: toyota-telematics.get-vehicle-subscriptions\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/status\n      name: vehicle-status\n      description: Real-time vehicle status\n      operations:\n      - method: GET\n        name: get-vehicle-status\n        description: Get current vehicle status\n        call: toyota-connected.get-vehicle-status\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{vin}/ev-status\n      name: ev-status\n      description: EV battery and charging\n      operations:\n      - method: GET\n        name: get-ev-status\n        description: Get EV battery and charging status\n        call: toyota-connected.get-electric-status\n\
  \        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: toyota-fleet-mcp\n    transport: http\n    description: MCP server for AI-assisted Toyota fleet management and vehicle monitoring.\n    tools:\n    - name: list-fleet-vehicles\n      description: List all vehicles enrolled in the Toyota telematics fleet program\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toyota-telematics.list-vehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle\n      description: Get telematics enrollment details for a specific fleet vehicle by VIN\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-telematics.get-vehicle\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-health\n      description: Get vehicle health status\
  \ including warning lights and oil level for a fleet vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-telematics.get-vehicle-health\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-telemetry\n      description: Get odometer, fuel level, and estimated range for a fleet vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-telematics.get-vehicle-telemetry\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-location\n      description: Get the current GPS coordinates of a fleet vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-telematics.get-vehicle-location\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trip-history\n      description: Get\
  \ trip history for a fleet vehicle over a specified date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toyota-telematics.get-vehicle-trips\n      with:\n        vin: tools.vin\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-subscriptions\n      description: Get connected services and satellite radio subscription status for a vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-telematics.get-vehicle-subscriptions\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-fleet-vehicle\n      description: Enroll a new vehicle in the Toyota telematics fleet program\n      hints:\n        readOnly: false\n      call: toyota-telematics.enroll-vehicle\n      with:\n        fleetId: tools.fleetId\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: get-vehicle-door-status\n      description: Get real-time door lock and window status for a connected vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-connected.get-vehicle-status\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ev-battery-status\n      description: Get EV battery percentage, electric range, and charging status for hybrid/EV vehicles\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-connected.get-electric-status\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-alerts\n      description: Get maintenance alerts and vehicle notifications for a connected vehicle\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toyota-connected.get-vehicle-notifications\n      with:\n        vin: tools.vin\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-history\n      description: Get dealer service history records for a vehicle\n      hints:\n        readOnly: true\n        idempotent: true\n      call: toyota-connected.get-service-history\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toyota/refs/heads/main/capabilities/fleet-management.yaml
tags:
- Automotive
- Fleet Management
- Telematics
- Vehicle Health
- Connected Car
tools:
- description: List all vehicles enrolled in the Toyota telematics fleet program
  hints:
    openWorld: true
    readOnly: true
  name: list-fleet-vehicles
- description: Get telematics enrollment details for a specific fleet vehicle by VIN
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle
- description: Get vehicle health status including warning lights and oil level for a fleet vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-health
- description: Get odometer, fuel level, and estimated range for a fleet vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-telemetry
- description: Get the current GPS coordinates of a fleet vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-location
- description: Get trip history for a fleet vehicle over a specified date range
  hints:
    openWorld: true
    readOnly: true
  name: get-trip-history
- description: Get connected services and satellite radio subscription status for a vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-subscriptions
- description: Enroll a new vehicle in the Toyota telematics fleet program
  hints:
    readOnly: false
  name: enroll-fleet-vehicle
- description: Get real-time door lock and window status for a connected vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-door-status
- description: Get EV battery percentage, electric range, and charging status for hybrid/EV vehicles
  hints:
    idempotent: true
    readOnly: true
  name: get-ev-battery-status
- description: Get maintenance alerts and vehicle notifications for a connected vehicle
  hints:
    openWorld: true
    readOnly: true
  name: get-vehicle-alerts
- description: Get dealer service history records for a vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-service-history
---
