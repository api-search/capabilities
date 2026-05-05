---
categories: []
consumed_apis:
- siemens-building
description: Unified workflow capability for smart building operations using the Siemens Building X platform. Enables facility managers and building operations teams to monitor and control building automation systems including HVAC, lighting, energy management, and equipment. Covers data point monitoring, historical trend analysis, alarm management, and schedule management for commercial and industrial buildings.
layout: capability
name: Siemens Smart Building Operations
operations:
- description: List all building data points
  method: GET
  name: list-points
  path: /v1/points
- description: Get a building data point
  method: GET
  name: get-point
  path: /v1/points/{pointId}
- description: Get current real-time value of a data point
  method: GET
  name: get-point-value
  path: /v1/points/{pointId}/value
- description: Set value of a writable data point (setpoint or command)
  method: PUT
  name: set-point-value
  path: /v1/points/{pointId}/value
- description: Get historical trend data for a building data point
  method: GET
  name: get-trend
  path: /v1/points/{pointId}/trends
- description: List building alarms filtered by status and severity
  method: GET
  name: list-alarms
  path: /v1/alarms
- description: Acknowledge a building alarm
  method: POST
  name: acknowledge-alarm
  path: /v1/alarms/{alarmId}/acknowledge
- description: List building equipment including HVAC, chillers, and AHUs
  method: GET
  name: list-equipment
  path: /v1/equipment
- description: List building automation schedules
  method: GET
  name: list-schedules
  path: /v1/schedules
personas: []
provider_name: Siemens
provider_slug: siemens
search_terms:
- building alarm monitoring
- acknowledge alarm
- energy management
- list building equipment including hvac, chillers, and ahus
- get details of a specific building data point
- smart buildings
- get building point
- facilities management
- bacnet
- get point
- acknowledge a building alarm to indicate it has been noted
- set point value
- list schedules
- get current real-time value of a data point
- set value of a writable data point (setpoint or command)
- control a building system by setting a setpoint or actuator command
- industry
- list points
- get historical trend data for a building data point
- list equipment
- acknowledge a building alarm
- list all building data points
- real-time point value read/write
- get a building data point
- building data points monitoring
- get point current value
- hvac
- get point value
- list building alarms filtered by status and severity
- get trend
- individual data point operations
- list all building automation data points (sensors, setpoints, actuators)
- get historical trend
- historical trend data queries
- industrial iot
- get historical trend data for a building sensor or setpoint over a time range
- electrification
- digital twin
- alarm acknowledgment
- list building automation schedules controlling system operation times and setpoints
- list building automation schedules
- manufacturing
- building automation schedules
- list building alarms including hvac faults and equipment alerts
- get the current real-time value of a building sensor or setpoint
- list alarms
- building equipment listing
- iot
- list building equipment including hvac units, chillers, air handling units, and boilers
- automation
- building automation
- list building points
slug: building-operations
source_filename: building-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Siemens Smart Building Operations\"\n  description: >-\n    Unified workflow capability for smart building operations using the Siemens\n    Building X platform. Enables facility managers and building operations teams\n    to monitor and control building automation systems including HVAC, lighting,\n    energy management, and equipment. Covers data point monitoring, historical\n    trend analysis, alarm management, and schedule management for commercial and\n    industrial buildings.\n  tags:\n    - Building Automation\n    - Smart Buildings\n    - HVAC\n    - Energy Management\n    - Facilities Management\n    - IoT\n    - BACnet\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIEMENS_BEARER_TOKEN: SIEMENS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: siemens-building\n      location: ./shared/building-operations.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: siemens-building-ops-api\n      description: \"Unified REST API for Siemens smart building operations and automation.\"\n      resources:\n        - path: /v1/points\n          name: points\n          description: \"Building data points monitoring\"\n          operations:\n            - method: GET\n              name: list-points\n              description: \"List all building data points\"\n              call: \"siemens-building.list-points\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/points/{pointId}\n          name: point\n          description: \"Individual data point operations\"\n          operations:\n            - method: GET\n              name: get-point\n              description: \"Get a building data point\"\n              call: \"siemens-building.get-point\"\n              with:\n                pointId: \"rest.pointId\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/points/{pointId}/value\n          name: point-value\n          description: \"Real-time point value read/write\"\n          operations:\n            - method: GET\n              name: get-point-value\n              description: \"Get current real-time value of a data point\"\n              call: \"siemens-building.get-point-value\"\n              with:\n                pointId: \"rest.pointId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: set-point-value\n              description: \"Set value of a writable data point (setpoint or command)\"\n              call: \"siemens-building.set-point-value\"\n              with:\n                pointId: \"rest.pointId\"\n                value: \"rest.value\"\n                priority: \"rest.priority\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/points/{pointId}/trends\n          name: trends\n          description: \"Historical trend data queries\"\n          operations:\n            - method: GET\n              name: get-trend\n              description: \"Get historical trend data for a building data point\"\n              call: \"siemens-building.get-point-trend\"\n              with:\n                pointId: \"rest.pointId\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                resolution: \"rest.resolution\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alarms\n          name: alarms\n          description: \"Building alarm monitoring\"\n          operations:\n            - method: GET\n              name: list-alarms\n              description: \"List building alarms filtered by status and severity\"\n              call: \"siemens-building.list-alarms\"\n\
  \              with:\n                status: \"rest.status\"\n                severity: \"rest.severity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alarms/{alarmId}/acknowledge\n          name: alarm-acknowledge\n          description: \"Alarm acknowledgment\"\n          operations:\n            - method: POST\n              name: acknowledge-alarm\n              description: \"Acknowledge a building alarm\"\n              call: \"siemens-building.acknowledge-alarm\"\n              with:\n                alarmId: \"rest.alarmId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/equipment\n          name: equipment\n          description: \"Building equipment listing\"\n          operations:\n            - method: GET\n              name: list-equipment\n              description: \"List building equipment including HVAC, chillers, and\
  \ AHUs\"\n              call: \"siemens-building.list-equipment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schedules\n          name: schedules\n          description: \"Building automation schedules\"\n          operations:\n            - method: GET\n              name: list-schedules\n              description: \"List building automation schedules\"\n              call: \"siemens-building.list-schedules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: siemens-building-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted smart building operations and facility management using Siemens Building X.\"\n      tools:\n        - name: list-building-points\n          description: \"List all building automation data points (sensors, setpoints, actuators)\"\n          hints:\n   \
  \         readOnly: true\n            openWorld: false\n          call: \"siemens-building.list-points\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-building-point\n          description: \"Get details of a specific building data point\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.get-point\"\n          with:\n            pointId: \"tools.pointId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-point-current-value\n          description: \"Get the current real-time value of a building sensor or setpoint\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.get-point-value\"\n          with:\n            pointId: \"tools.pointId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ set-point-value\n          description: \"Control a building system by setting a setpoint or actuator command\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"siemens-building.set-point-value\"\n          with:\n            pointId: \"tools.pointId\"\n            value: \"tools.value\"\n            priority: \"tools.priority\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-historical-trend\n          description: \"Get historical trend data for a building sensor or setpoint over a time range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.get-point-trend\"\n          with:\n            pointId: \"tools.pointId\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            resolution: \"tools.resolution\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-alarms\n          description: \"List building alarms including HVAC faults and equipment alerts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.list-alarms\"\n          with:\n            status: \"tools.status\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: acknowledge-alarm\n          description: \"Acknowledge a building alarm to indicate it has been noted\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"siemens-building.acknowledge-alarm\"\n          with:\n            alarmId: \"tools.alarmId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-equipment\n          description: \"List building equipment including HVAC units,\
  \ chillers, air handling units, and boilers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.list-equipment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-schedules\n          description: \"List building automation schedules controlling system operation times and setpoints\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"siemens-building.list-schedules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/siemens/refs/heads/main/capabilities/building-operations.yaml
tags:
- Building Automation
- Smart Buildings
- HVAC
- Energy Management
- Facilities Management
- IoT
- BACnet
tools:
- description: List all building automation data points (sensors, setpoints, actuators)
  hints:
    openWorld: false
    readOnly: true
  name: list-building-points
- description: Get details of a specific building data point
  hints:
    openWorld: false
    readOnly: true
  name: get-building-point
- description: Get the current real-time value of a building sensor or setpoint
  hints:
    openWorld: false
    readOnly: true
  name: get-point-current-value
- description: Control a building system by setting a setpoint or actuator command
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-point-value
- description: Get historical trend data for a building sensor or setpoint over a time range
  hints:
    openWorld: false
    readOnly: true
  name: get-historical-trend
- description: List building alarms including HVAC faults and equipment alerts
  hints:
    openWorld: false
    readOnly: true
  name: list-alarms
- description: Acknowledge a building alarm to indicate it has been noted
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-alarm
- description: List building equipment including HVAC units, chillers, air handling units, and boilers
  hints:
    openWorld: false
    readOnly: true
  name: list-equipment
- description: List building automation schedules controlling system operation times and setpoints
  hints:
    openWorld: false
    readOnly: true
  name: list-schedules
---
