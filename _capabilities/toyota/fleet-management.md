---
categories: []
consumed_apis:
- toyota-telematics
- toyota-connected
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
- ev battery and charging
- get service history
- get current vehicle status
- vehicle trip history
- list all vehicles enrolled in the toyota telematics fleet program
- get vehicle alerts
- vehicle location
- enroll fleet vehicle
- vehicle telemetry
- get trip history
- get vehicle gps location
- telematics
- get subscription details
- get vehicle telemetry
- individual vehicle
- vehicle health status
- get ev battery percentage, electric range, and charging status for hybrid/ev vehicles
- get ev battery status
- connected car
- get dealer service history records for a vehicle
- electric vehicles
- get the current gps coordinates of a fleet vehicle
- get vehicle status
- list vehicles
- list fleet vehicles
- get vehicle health status including warning lights and oil level for a fleet vehicle
- automobiles
- get real-time door lock and window status for a connected vehicle
- get vehicle
- fleet vehicle management
- get vehicle health
- get telematics enrollment details for a specific fleet vehicle by vin
- enroll a new vehicle in the toyota telematics fleet program
- get vehicle door status
- connected service subscriptions
- get vehicle telematics
- get odometer, fuel level, and estimated range for a fleet vehicle
- vehicle health
- automotive
- get connected services and satellite radio subscription status for a vehicle
- get ev status
- get trip history for a fleet vehicle over a specified date range
- get maintenance alerts and vehicle notifications for a connected vehicle
- get vehicle subscriptions
- get ev battery and charging status
- cars
- real-time vehicle status
- get vehicle trips
- get vehicle location
- vehicles
- fleet management
slug: fleet-management
source_filename: fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toyota Fleet Management\"\n  description: \"Workflow capability for fleet managers and rental car operators combining Toyota Telematics and Connected Services APIs. Enables vehicle enrollment, health monitoring, location tracking, telemetry analysis, and trip reporting for Toyota fleet operations.\"\n  tags:\n    - Automotive\n    - Fleet Management\n    - Telematics\n    - Vehicle Health\n    - Connected Car\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOYOTA_TELEMATICS_TOKEN: TOYOTA_TELEMATICS_TOKEN\n      TOYOTA_CONNECTED_TOKEN: TOYOTA_CONNECTED_TOKEN\n\ncapability:\n  consumes:\n    - import: toyota-telematics\n      location: ./shared/telematics.yaml\n    - import: toyota-connected\n      location: ./shared/connected-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: toyota-fleet-api\n      description: \"Unified REST API for Toyota fleet\
  \ management and vehicle monitoring.\"\n      resources:\n        - path: /v1/vehicles\n          name: vehicles\n          description: \"Fleet vehicle management\"\n          operations:\n            - method: GET\n              name: list-vehicles\n              description: \"List fleet vehicles\"\n              call: \"toyota-telematics.list-vehicles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}\n          name: vehicle\n          description: \"Individual vehicle\"\n          operations:\n            - method: GET\n              name: get-vehicle\n              description: \"Get vehicle telematics\"\n              call: \"toyota-telematics.get-vehicle\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/health\n          name: vehicle-health\n      \
  \    description: \"Vehicle health status\"\n          operations:\n            - method: GET\n              name: get-vehicle-health\n              description: \"Get vehicle health\"\n              call: \"toyota-telematics.get-vehicle-health\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/telemetry\n          name: vehicle-telemetry\n          description: \"Vehicle telemetry\"\n          operations:\n            - method: GET\n              name: get-vehicle-telemetry\n              description: \"Get vehicle telemetry\"\n              call: \"toyota-telematics.get-vehicle-telemetry\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/location\n          name: vehicle-location\n          description:\
  \ \"Vehicle location\"\n          operations:\n            - method: GET\n              name: get-vehicle-location\n              description: \"Get vehicle GPS location\"\n              call: \"toyota-telematics.get-vehicle-location\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/trips\n          name: vehicle-trips\n          description: \"Vehicle trip history\"\n          operations:\n            - method: GET\n              name: get-vehicle-trips\n              description: \"Get trip history\"\n              call: \"toyota-telematics.get-vehicle-trips\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/subscriptions\n          name: subscriptions\n          description: \"Connected service subscriptions\"\
  \n          operations:\n            - method: GET\n              name: get-vehicle-subscriptions\n              description: \"Get subscription details\"\n              call: \"toyota-telematics.get-vehicle-subscriptions\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/status\n          name: vehicle-status\n          description: \"Real-time vehicle status\"\n          operations:\n            - method: GET\n              name: get-vehicle-status\n              description: \"Get current vehicle status\"\n              call: \"toyota-connected.get-vehicle-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/ev-status\n          name: ev-status\n          description: \"EV battery and charging\"\n\
  \          operations:\n            - method: GET\n              name: get-ev-status\n              description: \"Get EV battery and charging status\"\n              call: \"toyota-connected.get-electric-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: toyota-fleet-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Toyota fleet management and vehicle monitoring.\"\n      tools:\n        - name: list-fleet-vehicles\n          description: \"List all vehicles enrolled in the Toyota telematics fleet program\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-telematics.list-vehicles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle\n          description: \"Get telematics enrollment\
  \ details for a specific fleet vehicle by VIN\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-telematics.get-vehicle\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-health\n          description: \"Get vehicle health status including warning lights and oil level for a fleet vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-telematics.get-vehicle-health\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-telemetry\n          description: \"Get odometer, fuel level, and estimated range for a fleet vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-telematics.get-vehicle-telemetry\"\
  \n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-location\n          description: \"Get the current GPS coordinates of a fleet vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-telematics.get-vehicle-location\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-trip-history\n          description: \"Get trip history for a fleet vehicle over a specified date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-telematics.get-vehicle-trips\"\n          with:\n            vin: \"tools.vin\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: get-vehicle-subscriptions\n          description: \"Get connected services and satellite radio subscription status for a vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-telematics.get-vehicle-subscriptions\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enroll-fleet-vehicle\n          description: \"Enroll a new vehicle in the Toyota telematics fleet program\"\n          hints:\n            readOnly: false\n          call: \"toyota-telematics.enroll-vehicle\"\n          with:\n            fleetId: \"tools.fleetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-door-status\n          description: \"Get real-time door lock and window status for a connected vehicle\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"toyota-connected.get-vehicle-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ev-battery-status\n          description: \"Get EV battery percentage, electric range, and charging status for hybrid/EV vehicles\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-electric-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-alerts\n          description: \"Get maintenance alerts and vehicle notifications for a connected vehicle\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-connected.get-vehicle-notifications\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-service-history\n          description: \"Get dealer service history records for a vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-service-history\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
