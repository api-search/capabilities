---
categories: []
consumed_apis: []
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
- agronomics
- get fleet equipment
- get water usage report
- equipment health reporting
- get current irrigation system status
- get equipment health report
- get zone details
- get a fleet equipment health summary report showing maintenance status
- real-time irrigation system status
- get equipment current location
- list all sensors with latest readings
- get detailed health information for a specific piece of equipment
- list all golf course irrigation zones and their current state
- get equipment location
- get the current gps location of a specific piece of equipment
- list all irrigation zones
- get detailed information for a specific irrigation zone
- individual equipment details
- water usage reporting
- start irrigation
- individual irrigation zone
- get a water usage summary report for a date range to track irrigation efficiency
- stop irrigation
- manually start irrigation for a specific zone with optional duration
- stop active irrigation
- get the current status of the golf course irrigation system
- turf management
- fleet management
- equipment gps location
- stop zone irrigation
- golf course fleet equipment
- equipment
- golf
- environmental and soil sensors
- irrigation
- historical sensor data
- get irrigation status
- irrigation zone management
- landscaping
- smart connected products
- list all golf course fleet equipment with health and status data
- start zone irrigation
- list fleet equipment
- list all environmental and soil moisture sensors with latest readings
- list irrigation zones
- list fleet equipment with health data
- get sensor readings
- stop active irrigation for a specific zone
- get irrigation zone
- start irrigation for a zone
- get historical readings for a sensor over a specified time range
- list sensors
- get equipment details and health
- get sensor historical readings
slug: golf-course-management
source_filename: golf-course-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toro Golf Course Management\n  description: Workflow capability for golf course superintendents combining IntelliDash irrigation control with fleet equipment\n    monitoring. Enables real-time irrigation management, equipment health tracking, environmental sensor monitoring, and agronomic\n    reporting to optimize course conditions.\n  tags:\n  - Golf\n  - Irrigation\n  - Fleet Management\n  - Turf Management\n  - Agronomics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INTELLIDASH_API_KEY: INTELLIDASH_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: intellidash\n    baseUri: https://api.intellidash.toro.com/v1\n    description: Toro IntelliDash irrigation and fleet management API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{INTELLIDASH_API_KEY}}'\n      placement: header\n    resources:\n    - name: irrigation-status\n      path: /irrigation/status\n\
  \      description: Irrigation system status\n      operations:\n      - name: get-irrigation-status\n        method: GET\n        description: Get current status of all irrigation systems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: irrigation-zones\n      path: /irrigation/zones\n      description: Irrigation zone management\n      operations:\n      - name: list-irrigation-zones\n        method: GET\n        description: List all irrigation zones\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by zone status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: irrigation-zone\n      path: /irrigation/zones/{zoneId}\n      description: Individual zone operations\n      operations:\n      - name: get-irrigation-zone\n\
  \        method: GET\n        description: Get a specific irrigation zone\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-zone-irrigation\n      path: /irrigation/zones/{zoneId}/start\n      description: Start irrigation for a zone\n      operations:\n      - name: start-irrigation\n        method: POST\n        description: Start manual irrigation for a zone\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            duration: '{{tools.duration}}'\n\
  \    - name: stop-zone-irrigation\n      path: /irrigation/zones/{zoneId}/stop\n      description: Stop irrigation for a zone\n      operations:\n      - name: stop-irrigation\n        method: POST\n        description: Stop active irrigation for a zone\n        inputParameters:\n        - name: zoneId\n          in: path\n          type: string\n          required: true\n          description: Zone identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment\n      path: /equipment\n      description: Fleet equipment tracking\n      operations:\n      - name: list-fleet-equipment\n        method: GET\n        description: List all fleet equipment with health data\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by equipment status\n        - name: type\n          in: query\n         \
  \ type: string\n          required: false\n          description: Filter by equipment type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-item\n      path: /equipment/{equipmentId}\n      description: Individual equipment details\n      operations:\n      - name: get-fleet-equipment\n        method: GET\n        description: Get equipment health and details\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-location\n      path: /equipment/{equipmentId}/location\n      description: Equipment GPS location\n      operations:\n      - name: get-equipment-location\n        method: GET\n        description: Get current GPS location\
  \ of equipment\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sensors\n      path: /sensors\n      description: Environmental and soil sensor monitoring\n      operations:\n      - name: list-sensors\n        method: GET\n        description: List all sensors and latest readings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by sensor type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sensor-readings\n      path: /sensors/{sensorId}/readings\n      description: Historical sensor data\n      operations:\n      - name: get-sensor-readings\n\
  \        method: GET\n        description: Get historical sensor readings\n        inputParameters:\n        - name: sensorId\n          in: path\n          type: string\n          required: true\n          description: Sensor identifier\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start of the time range\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End of the time range\n        - name: interval\n          in: query\n          type: string\n          required: false\n          description: Data interval (15min, 1hour, 1day)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: water-usage-report\n      path: /reports/water-usage\n      description: Water usage reporting\n      operations:\n      - name: get-water-usage-report\n        method: GET\n  \
  \      description: Get water usage summary report\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: true\n          description: Start date\n        - name: endDate\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: groupBy\n          in: query\n          type: string\n          required: false\n          description: Group results by day, week, month, or zone\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-health-report\n      path: /reports/equipment-health\n      description: Equipment health reporting\n      operations:\n      - name: get-equipment-health-report\n        method: GET\n        description: Get fleet equipment health summary\n        inputParameters:\n        - name: asOf\n          in: query\n          type: string\n          required:\
  \ false\n          description: Report date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: toro-golf-api\n    description: Unified REST API for golf course irrigation and fleet management.\n    resources:\n    - path: /v1/irrigation/status\n      name: irrigation-status\n      description: Real-time irrigation system status\n      operations:\n      - method: GET\n        name: get-irrigation-status\n        description: Get current irrigation system status\n        call: intellidash.get-irrigation-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/irrigation/zones\n      name: irrigation-zones\n      description: Irrigation zone management\n      operations:\n      - method: GET\n        name: list-irrigation-zones\n        description: List all irrigation zones\n        call: intellidash.list-irrigation-zones\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/irrigation/zones/{zoneId}\n      name: irrigation-zone\n      description: Individual irrigation zone\n      operations:\n      - method: GET\n        name: get-irrigation-zone\n        description: Get zone details\n        call: intellidash.get-irrigation-zone\n        with:\n          zoneId: rest.zoneId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/irrigation/zones/{zoneId}/start\n      name: start-irrigation\n      description: Start zone irrigation\n      operations:\n      - method: POST\n        name: start-irrigation\n        description: Start irrigation for a zone\n        call: intellidash.start-irrigation\n        with:\n          zoneId: rest.zoneId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/irrigation/zones/{zoneId}/stop\n      name: stop-irrigation\n      description: Stop zone irrigation\n\
  \      operations:\n      - method: POST\n        name: stop-irrigation\n        description: Stop active irrigation\n        call: intellidash.stop-irrigation\n        with:\n          zoneId: rest.zoneId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment\n      name: equipment\n      description: Golf course fleet equipment\n      operations:\n      - method: GET\n        name: list-fleet-equipment\n        description: List fleet equipment with health data\n        call: intellidash.list-fleet-equipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment/{equipmentId}\n      name: equipment-item\n      description: Individual equipment details\n      operations:\n      - method: GET\n        name: get-fleet-equipment\n        description: Get equipment details and health\n        call: intellidash.get-fleet-equipment\n        with:\n          equipmentId: rest.equipmentId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/equipment/{equipmentId}/location\n      name: equipment-location\n      description: Equipment GPS location\n      operations:\n      - method: GET\n        name: get-equipment-location\n        description: Get equipment current location\n        call: intellidash.get-equipment-location\n        with:\n          equipmentId: rest.equipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sensors\n      name: sensors\n      description: Environmental and soil sensors\n      operations:\n      - method: GET\n        name: list-sensors\n        description: List all sensors with latest readings\n        call: intellidash.list-sensors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sensors/{sensorId}/readings\n      name: sensor-readings\n      description: Historical sensor data\n      operations:\n      - method: GET\n        name: get-sensor-readings\n\
  \        description: Get sensor historical readings\n        call: intellidash.get-sensor-readings\n        with:\n          sensorId: rest.sensorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/water-usage\n      name: water-usage-report\n      description: Water usage reporting\n      operations:\n      - method: GET\n        name: get-water-usage-report\n        description: Get water usage report\n        call: intellidash.get-water-usage-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/equipment-health\n      name: equipment-health-report\n      description: Equipment health reporting\n      operations:\n      - method: GET\n        name: get-equipment-health-report\n        description: Get equipment health report\n        call: intellidash.get-equipment-health-report\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n\
  \    namespace: toro-golf-mcp\n    transport: http\n    description: MCP server for AI-assisted golf course irrigation and fleet management.\n    tools:\n    - name: get-irrigation-status\n      description: Get the current status of the golf course irrigation system\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-irrigation-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-irrigation-zones\n      description: List all golf course irrigation zones and their current state\n      hints:\n        readOnly: true\n        openWorld: true\n      call: intellidash.list-irrigation-zones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-irrigation-zone\n      description: Get detailed information for a specific irrigation zone\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-irrigation-zone\n      with:\n        zoneId: tools.zoneId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-zone-irrigation\n      description: Manually start irrigation for a specific zone with optional duration\n      hints:\n        readOnly: false\n        destructive: false\n      call: intellidash.start-irrigation\n      with:\n        zoneId: tools.zoneId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-zone-irrigation\n      description: Stop active irrigation for a specific zone\n      hints:\n        readOnly: false\n        destructive: false\n      call: intellidash.stop-irrigation\n      with:\n        zoneId: tools.zoneId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fleet-equipment\n      description: List all golf course fleet equipment with health and status data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: intellidash.list-fleet-equipment\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-fleet-equipment\n      description: Get detailed health information for a specific piece of equipment\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-fleet-equipment\n      with:\n        equipmentId: tools.equipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-location\n      description: Get the current GPS location of a specific piece of equipment\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-equipment-location\n      with:\n        equipmentId: tools.equipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sensors\n      description: List all environmental and soil moisture sensors with latest readings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: intellidash.list-sensors\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-sensor-readings\n      description: Get historical readings for a sensor over a specified time range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-sensor-readings\n      with:\n        sensorId: tools.sensorId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-water-usage-report\n      description: Get a water usage summary report for a date range to track irrigation efficiency\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-water-usage-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-health-report\n      description: Get a fleet equipment health summary report showing maintenance status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: intellidash.get-equipment-health-report\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
