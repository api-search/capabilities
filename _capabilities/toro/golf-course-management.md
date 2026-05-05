---
categories: []
consumed_apis:
- intellidash
description: Workflow capability for golf course superintendents combining IntelliDash irrigation control with fleet equipment monitoring. Enables real-time irrigation management, equipment health tracking, environmental sensor monitoring, and agronomic reporting to optimize course conditions.
layout: capability
name: Toro Golf Course Management
operations:
- description: Get current irrigation system status
  method: GET
  name: get-irrigation-status
  path: /v1/irrigation/status
- description: List all irrigation zones
  method: GET
  name: list-irrigation-zones
  path: /v1/irrigation/zones
- description: Get zone details
  method: GET
  name: get-irrigation-zone
  path: /v1/irrigation/zones/{zoneId}
- description: Start irrigation for a zone
  method: POST
  name: start-irrigation
  path: /v1/irrigation/zones/{zoneId}/start
- description: Stop active irrigation
  method: POST
  name: stop-irrigation
  path: /v1/irrigation/zones/{zoneId}/stop
- description: List fleet equipment with health data
  method: GET
  name: list-fleet-equipment
  path: /v1/equipment
- description: Get equipment details and health
  method: GET
  name: get-fleet-equipment
  path: /v1/equipment/{equipmentId}
- description: Get equipment current location
  method: GET
  name: get-equipment-location
  path: /v1/equipment/{equipmentId}/location
- description: List all sensors with latest readings
  method: GET
  name: list-sensors
  path: /v1/sensors
- description: Get sensor historical readings
  method: GET
  name: get-sensor-readings
  path: /v1/sensors/{sensorId}/readings
- description: Get water usage report
  method: GET
  name: get-water-usage-report
  path: /v1/reports/water-usage
- description: Get equipment health report
  method: GET
  name: get-equipment-health-report
  path: /v1/reports/equipment-health
personas: []
provider_name: Toro
provider_slug: toro
search_terms:
- start irrigation for a zone
- environmental and soil sensors
- get sensor readings
- irrigation
- list all environmental and soil moisture sensors with latest readings
- get a water usage summary report for a date range to track irrigation efficiency
- get zone details
- historical sensor data
- list all irrigation zones
- manually start irrigation for a specific zone with optional duration
- start zone irrigation
- get the current gps location of a specific piece of equipment
- list irrigation zones
- list fleet equipment
- get detailed information for a specific irrigation zone
- get irrigation status
- water usage reporting
- list fleet equipment with health data
- stop active irrigation
- golf
- turf management
- landscaping
- equipment
- agronomics
- get irrigation zone
- equipment gps location
- irrigation zone management
- stop zone irrigation
- smart connected products
- real-time irrigation system status
- golf course fleet equipment
- get equipment current location
- start irrigation
- list all sensors with latest readings
- get equipment details and health
- get the current status of the golf course irrigation system
- list all golf course irrigation zones and their current state
- stop irrigation
- stop active irrigation for a specific zone
- get current irrigation system status
- individual irrigation zone
- list sensors
- get equipment health report
- get detailed health information for a specific piece of equipment
- get equipment location
- get fleet equipment
- equipment health reporting
- get a fleet equipment health summary report showing maintenance status
- individual equipment details
- get sensor historical readings
- list all golf course fleet equipment with health and status data
- get water usage report
- get historical readings for a sensor over a specified time range
- fleet management
slug: golf-course-management
source_filename: golf-course-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toro Golf Course Management\"\n  description: \"Workflow capability for golf course superintendents combining IntelliDash irrigation control with fleet equipment monitoring. Enables real-time irrigation management, equipment health tracking, environmental sensor monitoring, and agronomic reporting to optimize course conditions.\"\n  tags:\n    - Golf\n    - Irrigation\n    - Fleet Management\n    - Turf Management\n    - Agronomics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      INTELLIDASH_API_KEY: INTELLIDASH_API_KEY\n\ncapability:\n  consumes:\n    - import: intellidash\n      location: ./shared/intellidash.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: toro-golf-api\n      description: \"Unified REST API for golf course irrigation and fleet management.\"\n      resources:\n        - path: /v1/irrigation/status\n          name: irrigation-status\n\
  \          description: \"Real-time irrigation system status\"\n          operations:\n            - method: GET\n              name: get-irrigation-status\n              description: \"Get current irrigation system status\"\n              call: \"intellidash.get-irrigation-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irrigation/zones\n          name: irrigation-zones\n          description: \"Irrigation zone management\"\n          operations:\n            - method: GET\n              name: list-irrigation-zones\n              description: \"List all irrigation zones\"\n              call: \"intellidash.list-irrigation-zones\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irrigation/zones/{zoneId}\n          name: irrigation-zone\n          description: \"Individual irrigation zone\"\n          operations:\n            - method:\
  \ GET\n              name: get-irrigation-zone\n              description: \"Get zone details\"\n              call: \"intellidash.get-irrigation-zone\"\n              with:\n                zoneId: \"rest.zoneId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irrigation/zones/{zoneId}/start\n          name: start-irrigation\n          description: \"Start zone irrigation\"\n          operations:\n            - method: POST\n              name: start-irrigation\n              description: \"Start irrigation for a zone\"\n              call: \"intellidash.start-irrigation\"\n              with:\n                zoneId: \"rest.zoneId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/irrigation/zones/{zoneId}/stop\n          name: stop-irrigation\n          description: \"Stop zone irrigation\"\n          operations:\n            - method: POST\n\
  \              name: stop-irrigation\n              description: \"Stop active irrigation\"\n              call: \"intellidash.stop-irrigation\"\n              with:\n                zoneId: \"rest.zoneId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/equipment\n          name: equipment\n          description: \"Golf course fleet equipment\"\n          operations:\n            - method: GET\n              name: list-fleet-equipment\n              description: \"List fleet equipment with health data\"\n              call: \"intellidash.list-fleet-equipment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/equipment/{equipmentId}\n          name: equipment-item\n          description: \"Individual equipment details\"\n          operations:\n            - method: GET\n              name: get-fleet-equipment\n              description: \"Get\
  \ equipment details and health\"\n              call: \"intellidash.get-fleet-equipment\"\n              with:\n                equipmentId: \"rest.equipmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/equipment/{equipmentId}/location\n          name: equipment-location\n          description: \"Equipment GPS location\"\n          operations:\n            - method: GET\n              name: get-equipment-location\n              description: \"Get equipment current location\"\n              call: \"intellidash.get-equipment-location\"\n              with:\n                equipmentId: \"rest.equipmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sensors\n          name: sensors\n          description: \"Environmental and soil sensors\"\n          operations:\n            - method: GET\n              name: list-sensors\n         \
  \     description: \"List all sensors with latest readings\"\n              call: \"intellidash.list-sensors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sensors/{sensorId}/readings\n          name: sensor-readings\n          description: \"Historical sensor data\"\n          operations:\n            - method: GET\n              name: get-sensor-readings\n              description: \"Get sensor historical readings\"\n              call: \"intellidash.get-sensor-readings\"\n              with:\n                sensorId: \"rest.sensorId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/water-usage\n          name: water-usage-report\n          description: \"Water usage reporting\"\n          operations:\n            - method: GET\n              name: get-water-usage-report\n              description: \"Get water usage report\"\n \
  \             call: \"intellidash.get-water-usage-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/equipment-health\n          name: equipment-health-report\n          description: \"Equipment health reporting\"\n          operations:\n            - method: GET\n              name: get-equipment-health-report\n              description: \"Get equipment health report\"\n              call: \"intellidash.get-equipment-health-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: toro-golf-mcp\n      transport: http\n      description: \"MCP server for AI-assisted golf course irrigation and fleet management.\"\n      tools:\n        - name: get-irrigation-status\n          description: \"Get the current status of the golf course irrigation system\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"intellidash.get-irrigation-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-irrigation-zones\n          description: \"List all golf course irrigation zones and their current state\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"intellidash.list-irrigation-zones\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-irrigation-zone\n          description: \"Get detailed information for a specific irrigation zone\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-irrigation-zone\"\n          with:\n            zoneId: \"tools.zoneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-zone-irrigation\n          description: \"Manually start irrigation\
  \ for a specific zone with optional duration\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"intellidash.start-irrigation\"\n          with:\n            zoneId: \"tools.zoneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-zone-irrigation\n          description: \"Stop active irrigation for a specific zone\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"intellidash.stop-irrigation\"\n          with:\n            zoneId: \"tools.zoneId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-fleet-equipment\n          description: \"List all golf course fleet equipment with health and status data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"intellidash.list-fleet-equipment\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n        - name: get-fleet-equipment\n          description: \"Get detailed health information for a specific piece of equipment\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-fleet-equipment\"\n          with:\n            equipmentId: \"tools.equipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-equipment-location\n          description: \"Get the current GPS location of a specific piece of equipment\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-equipment-location\"\n          with:\n            equipmentId: \"tools.equipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sensors\n          description: \"List all environmental and soil moisture sensors with latest readings\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"intellidash.list-sensors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sensor-readings\n          description: \"Get historical readings for a sensor over a specified time range\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-sensor-readings\"\n          with:\n            sensorId: \"tools.sensorId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-water-usage-report\n          description: \"Get a water usage summary report for a date range to track irrigation efficiency\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-water-usage-report\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-equipment-health-report\n          description: \"Get a fleet equipment health summary report showing maintenance status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"intellidash.get-equipment-health-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toro/refs/heads/main/capabilities/golf-course-management.yaml
tags:
- Golf
- Irrigation
- Fleet Management
- Turf Management
- Agronomics
tools:
- description: Get the current status of the golf course irrigation system
  hints:
    idempotent: true
    readOnly: true
  name: get-irrigation-status
- description: List all golf course irrigation zones and their current state
  hints:
    openWorld: true
    readOnly: true
  name: list-irrigation-zones
- description: Get detailed information for a specific irrigation zone
  hints:
    idempotent: true
    readOnly: true
  name: get-irrigation-zone
- description: Manually start irrigation for a specific zone with optional duration
  hints:
    destructive: false
    readOnly: false
  name: start-zone-irrigation
- description: Stop active irrigation for a specific zone
  hints:
    destructive: false
    readOnly: false
  name: stop-zone-irrigation
- description: List all golf course fleet equipment with health and status data
  hints:
    openWorld: true
    readOnly: true
  name: list-fleet-equipment
- description: Get detailed health information for a specific piece of equipment
  hints:
    idempotent: true
    readOnly: true
  name: get-fleet-equipment
- description: Get the current GPS location of a specific piece of equipment
  hints:
    idempotent: true
    readOnly: true
  name: get-equipment-location
- description: List all environmental and soil moisture sensors with latest readings
  hints:
    openWorld: true
    readOnly: true
  name: list-sensors
- description: Get historical readings for a sensor over a specified time range
  hints:
    idempotent: true
    readOnly: true
  name: get-sensor-readings
- description: Get a water usage summary report for a date range to track irrigation efficiency
  hints:
    idempotent: true
    readOnly: true
  name: get-water-usage-report
- description: Get a fleet equipment health summary report showing maintenance status
  hints:
    idempotent: true
    readOnly: true
  name: get-equipment-health-report
---
