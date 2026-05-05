---
categories: []
consumed_apis:
- toyota-connected
description: Workflow capability for Toyota and Lexus vehicle owners and mobility app developers using Toyota Connected Services. Provides real-time vehicle monitoring, remote control, EV charging management, climate pre-conditioning, and trip analytics for personal and commercial connected vehicle applications.
layout: capability
name: Toyota Connected Vehicle
operations:
- description: List connected vehicles
  method: GET
  name: list-connected-vehicles
  path: /v1/vehicles
- description: Get door and ignition status
  method: GET
  name: get-vehicle-status
  path: /v1/vehicles/{vin}/status
- description: Get vehicle health status
  method: GET
  name: get-vehicle-health
  path: /v1/vehicles/{vin}/health
- description: Get parking location
  method: GET
  name: get-vehicle-location
  path: /v1/vehicles/{vin}/location
- description: Get EV battery and charging status
  method: GET
  name: get-electric-status
  path: /v1/vehicles/{vin}/electric
- description: Get climate status
  method: GET
  name: get-climate-status
  path: /v1/vehicles/{vin}/climate
- description: Start or stop climate
  method: POST
  name: send-climate-command
  path: /v1/vehicles/{vin}/climate/command
- description: Get trip history
  method: GET
  name: get-trips
  path: /v1/vehicles/{vin}/trips
- description: Get vehicle alerts
  method: GET
  name: get-vehicle-notifications
  path: /v1/vehicles/{vin}/notifications
- description: Send remote command
  method: POST
  name: send-remote-command
  path: /v1/vehicles/{vin}/remote-command
- description: Get service history
  method: GET
  name: get-service-history
  path: /v1/vehicles/{vin}/service-history
personas: []
provider_name: Toyota
provider_slug: toyota
search_terms:
- get service history
- climate control
- get vehicle alerts
- sound horn
- check vehicle health including warning lights and oil level
- stop climate
- get current climate control settings and whether it is running
- get trip history
- start climate
- vehicle real-time status
- vehicle gps location
- lock doors
- telematics
- send climate command
- service history
- ev
- get trips
- electric vehicles
- connected car
- get recent driving trip history including distance and route
- send remote command
- get vehicle notifications
- get recent trips
- list connected vehicles
- get electric status
- check vehicle health
- get vehicle maintenance alerts, recall notices, and system messages
- remote control
- get vehicle status
- list my vehicles
- check ev battery
- trip history
- sound the vehicle horn to help locate the vehicle
- find vehicle
- get climate status
- check ev battery level, electric range, and whether the vehicle is charging
- automobiles
- check if vehicle doors are locked and ignition status
- remote commands
- get vehicle health
- vehicle notifications
- get dealer service and maintenance history for the vehicle
- remotely start the vehicle's climate system before you get in
- personal mobility
- vehicle health
- automotive
- climate commands
- start or stop climate
- list all toyota/lexus connected vehicles registered to the account
- remotely stop the vehicle's climate system
- get parking location
- find where the vehicle is parked using gps coordinates
- ev/hybrid battery data
- unlock doors
- remotely unlock the vehicle's doors
- remotely lock the vehicle's doors
- connected vehicles
- cars
- get ev battery and charging status
- check vehicle status
- get vehicle health status
- get door and ignition status
- get vehicle location
- vehicles
- fleet management
slug: connected-vehicle
source_filename: connected-vehicle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toyota Connected Vehicle\"\n  description: \"Workflow capability for Toyota and Lexus vehicle owners and mobility app developers using Toyota Connected Services. Provides real-time vehicle monitoring, remote control, EV charging management, climate pre-conditioning, and trip analytics for personal and commercial connected vehicle applications.\"\n  tags:\n    - Automotive\n    - Connected Car\n    - Remote Control\n    - EV\n    - Personal Mobility\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOYOTA_CONNECTED_TOKEN: TOYOTA_CONNECTED_TOKEN\n\ncapability:\n  consumes:\n    - import: toyota-connected\n      location: ./shared/connected-services.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: toyota-vehicle-api\n      description: \"Unified REST API for Toyota connected vehicle owner and mobility developer workflows.\"\n      resources:\n        - path:\
  \ /v1/vehicles\n          name: vehicles\n          description: \"Connected vehicles\"\n          operations:\n            - method: GET\n              name: list-connected-vehicles\n              description: \"List connected vehicles\"\n              call: \"toyota-connected.list-connected-vehicles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/status\n          name: vehicle-status\n          description: \"Vehicle real-time status\"\n          operations:\n            - method: GET\n              name: get-vehicle-status\n              description: \"Get door and ignition status\"\n              call: \"toyota-connected.get-vehicle-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/health\n          name: vehicle-health\n          description:\
  \ \"Vehicle health\"\n          operations:\n            - method: GET\n              name: get-vehicle-health\n              description: \"Get vehicle health status\"\n              call: \"toyota-connected.get-vehicle-health-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/location\n          name: vehicle-location\n          description: \"Vehicle GPS location\"\n          operations:\n            - method: GET\n              name: get-vehicle-location\n              description: \"Get parking location\"\n              call: \"toyota-connected.get-vehicle-position\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/electric\n          name: electric-status\n          description: \"EV/hybrid battery\
  \ data\"\n          operations:\n            - method: GET\n              name: get-electric-status\n              description: \"Get EV battery and charging status\"\n              call: \"toyota-connected.get-electric-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/climate\n          name: climate\n          description: \"Climate control\"\n          operations:\n            - method: GET\n              name: get-climate-status\n              description: \"Get climate status\"\n              call: \"toyota-connected.get-climate-status\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/climate/command\n          name: climate-command\n          description: \"Climate commands\"\n          operations:\n\
  \            - method: POST\n              name: send-climate-command\n              description: \"Start or stop climate\"\n              call: \"toyota-connected.send-climate-command\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/trips\n          name: trips\n          description: \"Trip history\"\n          operations:\n            - method: GET\n              name: get-trips\n              description: \"Get trip history\"\n              call: \"toyota-connected.get-trips\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/notifications\n          name: notifications\n          description: \"Vehicle notifications\"\n          operations:\n            - method: GET\n              name: get-vehicle-notifications\n\
  \              description: \"Get vehicle alerts\"\n              call: \"toyota-connected.get-vehicle-notifications\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/remote-command\n          name: remote-command\n          description: \"Remote commands\"\n          operations:\n            - method: POST\n              name: send-remote-command\n              description: \"Send remote command\"\n              call: \"toyota-connected.send-remote-command\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{vin}/service-history\n          name: service-history\n          description: \"Service history\"\n          operations:\n            - method: GET\n              name: get-service-history\n              description:\
  \ \"Get service history\"\n              call: \"toyota-connected.get-service-history\"\n              with:\n                vin: \"rest.vin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: toyota-vehicle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Toyota connected vehicle owner workflows.\"\n      tools:\n        - name: list-my-vehicles\n          description: \"List all Toyota/Lexus connected vehicles registered to the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-connected.list-connected-vehicles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-vehicle-status\n          description: \"Check if vehicle doors are locked and ignition status\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"toyota-connected.get-vehicle-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-vehicle-health\n          description: \"Check vehicle health including warning lights and oil level\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-vehicle-health-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-vehicle\n          description: \"Find where the vehicle is parked using GPS coordinates\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-vehicle-position\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-ev-battery\n\
  \          description: \"Check EV battery level, electric range, and whether the vehicle is charging\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-electric-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-climate-status\n          description: \"Get current climate control settings and whether it is running\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-climate-status\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-climate\n          description: \"Remotely start the vehicle's climate system before you get in\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"toyota-connected.send-climate-command\"\
  \n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-climate\n          description: \"Remotely stop the vehicle's climate system\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"toyota-connected.send-climate-command\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: lock-doors\n          description: \"Remotely lock the vehicle's doors\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"toyota-connected.send-remote-command\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unlock-doors\n          description: \"Remotely unlock the vehicle's doors\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"toyota-connected.send-remote-command\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sound-horn\n          description: \"Sound the vehicle horn to help locate the vehicle\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"toyota-connected.send-remote-command\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recent-trips\n          description: \"Get recent driving trip history including distance and route\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-connected.get-trips\"\n          with:\n            vin: \"tools.vin\"\n            fromDate:\
  \ \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-alerts\n          description: \"Get vehicle maintenance alerts, recall notices, and system messages\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toyota-connected.get-vehicle-notifications\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-history\n          description: \"Get dealer service and maintenance history for the vehicle\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"toyota-connected.get-service-history\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toyota/refs/heads/main/capabilities/connected-vehicle.yaml
tags:
- Automotive
- Connected Car
- Remote Control
- EV
- Personal Mobility
tools:
- description: List all Toyota/Lexus connected vehicles registered to the account
  hints:
    openWorld: true
    readOnly: true
  name: list-my-vehicles
- description: Check if vehicle doors are locked and ignition status
  hints:
    idempotent: true
    readOnly: true
  name: check-vehicle-status
- description: Check vehicle health including warning lights and oil level
  hints:
    idempotent: true
    readOnly: true
  name: check-vehicle-health
- description: Find where the vehicle is parked using GPS coordinates
  hints:
    idempotent: true
    readOnly: true
  name: find-vehicle
- description: Check EV battery level, electric range, and whether the vehicle is charging
  hints:
    idempotent: true
    readOnly: true
  name: check-ev-battery
- description: Get current climate control settings and whether it is running
  hints:
    idempotent: true
    readOnly: true
  name: get-climate-status
- description: Remotely start the vehicle's climate system before you get in
  hints:
    destructive: false
    readOnly: false
  name: start-climate
- description: Remotely stop the vehicle's climate system
  hints:
    destructive: false
    readOnly: false
  name: stop-climate
- description: Remotely lock the vehicle's doors
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: lock-doors
- description: Remotely unlock the vehicle's doors
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unlock-doors
- description: Sound the vehicle horn to help locate the vehicle
  hints:
    destructive: false
    readOnly: false
  name: sound-horn
- description: Get recent driving trip history including distance and route
  hints:
    openWorld: true
    readOnly: true
  name: get-recent-trips
- description: Get vehicle maintenance alerts, recall notices, and system messages
  hints:
    openWorld: true
    readOnly: true
  name: get-vehicle-alerts
- description: Get dealer service and maintenance history for the vehicle
  hints:
    idempotent: true
    readOnly: true
  name: get-service-history
---
