---
categories: []
consumed_apis:
- environet
description: Unified DCIM monitoring capability composing Vertiv Environet Alert API resources for data center infrastructure monitoring. Provides data center operators with a unified view of devices, alarms, environmental sensors, power circuits, racks, and IT assets through a single REST and MCP interface. Designed for NOC teams, data center managers, and infrastructure automation workflows.
layout: capability
name: Vertiv DCIM Monitoring
operations:
- description: List All Devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get Device by ID
  method: GET
  name: get-device
  path: /v1/devices/{deviceId}
- description: List Active Alarms
  method: GET
  name: list-alarms
  path: /v1/alarms
- description: List All Sensor Points
  method: GET
  name: list-sensors
  path: /v1/sensors
- description: List All Racks
  method: GET
  name: list-racks
  path: /v1/racks
- description: List All Circuits
  method: GET
  name: list-circuits
  path: /v1/circuits
- description: List All Assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: List All Data Sets
  method: GET
  name: list-datasets
  path: /v1/datasets
personas: []
provider_name: Vertiv
provider_slug: vertiv
search_terms:
- list all data sets
- alarms
- get device by id
- active alarms across all data center infrastructure
- vertiv
- sensors
- list all top-level data set entity categories available in the environet system (group, location, rack, device, circuit, etc.)
- data center rack inventory and status
- list all monitored racks in the data center with status and capacity information.
- list all it assets tracked in the dcim system including servers, network equipment, and other data center hardware.
- environmental sensor data points
- list sensors
- list all circuits
- single monitored device
- asset management
- operations
- list all assets
- list all electrical circuits with current (amps), voltage, and power (watts) readings.
- power management
- list assets
- list active alarms
- list all environmental sensor data points including temperature, humidity, airflow, door position, and leak detection sensors.
- list all sensor points
- list devices
- all monitored dcim devices
- list all devices
- list circuits
- ups
- top-level data set entity catalog
- list alarms
- list all monitored dcim devices. filter by site name, group path, or status (normal, alarm, warning, down, maintenance, disabled).
- critical infrastructure
- list datasets
- list all active alarms across data center infrastructure. filter by severity (alarm, warning, info), alarm source device name, or site name.
- it asset inventory
- data center
- electrical circuit monitoring and power readings
- list racks
- list all racks
- get device
- environmental monitoring
- get detailed information about a specific monitored device by its id.
- infrastructure monitoring
- dcim
slug: dcim-monitoring
source_filename: dcim-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vertiv DCIM Monitoring\"\n  description: >-\n    Unified DCIM monitoring capability composing Vertiv Environet Alert API\n    resources for data center infrastructure monitoring. Provides data center\n    operators with a unified view of devices, alarms, environmental sensors,\n    power circuits, racks, and IT assets through a single REST and MCP\n    interface. Designed for NOC teams, data center managers, and infrastructure\n    automation workflows.\n  tags:\n    - Alarms\n    - Asset Management\n    - DCIM\n    - Environmental Monitoring\n    - Infrastructure Monitoring\n    - Operations\n    - Power Management\n    - Sensors\n    - Vertiv\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERTIV_ENVIRONET_TOKEN: VERTIV_ENVIRONET_TOKEN\n      VERTIV_ENVIRONET_HOST: VERTIV_ENVIRONET_HOST\n\ncapability:\n  consumes:\n    - import: environet\n      location: ./shared/environet-alert.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: dcim-monitoring-api\n      description: \"Unified REST API for data center infrastructure monitoring via Vertiv Environet.\"\n      resources:\n        - path: /v1/devices\n          name: devices\n          description: \"All monitored DCIM devices\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List All Devices\"\n              call: \"environet.list-devices\"\n              with:\n                siteName: \"rest.siteName\"\n                groupPath: \"rest.groupPath\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/devices/{deviceId}\n          name: device\n          description: \"Single monitored device\"\n          operations:\n            - method: GET\n              name: get-device\n              description: \"Get Device by ID\"\
  \n              call: \"environet.get-device\"\n              with:\n                deviceId: \"rest.deviceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alarms\n          name: alarms\n          description: \"Active alarms across all data center infrastructure\"\n          operations:\n            - method: GET\n              name: list-alarms\n              description: \"List Active Alarms\"\n              call: \"environet.list-alarms\"\n              with:\n                severity: \"rest.severity\"\n                alarmSource: \"rest.alarmSource\"\n                siteName: \"rest.siteName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sensors\n          name: sensors\n          description: \"Environmental sensor data points\"\n          operations:\n            - method: GET\n              name: list-sensors\n       \
  \       description: \"List All Sensor Points\"\n              call: \"environet.list-sensors\"\n              with:\n                deviceName: \"rest.deviceName\"\n                siteName: \"rest.siteName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/racks\n          name: racks\n          description: \"Data center rack inventory and status\"\n          operations:\n            - method: GET\n              name: list-racks\n              description: \"List All Racks\"\n              call: \"environet.list-racks\"\n              with:\n                rackName: \"rest.rackName\"\n                siteName: \"rest.siteName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/circuits\n          name: circuits\n          description: \"Electrical circuit monitoring and power readings\"\n          operations:\n            - method: GET\n\
  \              name: list-circuits\n              description: \"List All Circuits\"\n              call: \"environet.list-circuits\"\n              with:\n                circuitName: \"rest.circuitName\"\n                siteName: \"rest.siteName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: \"IT asset inventory\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List All Assets\"\n              call: \"environet.list-assets\"\n              with:\n                assetName: \"rest.assetName\"\n                rackName: \"rest.rackName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/datasets\n          name: datasets\n          description: \"Top-level data set entity catalog\"\n          operations:\n            -\
  \ method: GET\n              name: list-datasets\n              description: \"List All Data Sets\"\n              call: \"environet.list-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: dcim-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data center infrastructure monitoring.\"\n      tools:\n        - name: list-devices\n          description: >-\n            List all monitored DCIM devices. Filter by site name, group path,\n            or status (NORMAL, ALARM, WARNING, DOWN, MAINTENANCE, DISABLED).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-devices\"\n          with:\n            siteName: \"tools.siteName\"\n            groupPath: \"tools.groupPath\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: get-device\n          description: \"Get detailed information about a specific monitored device by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"environet.get-device\"\n          with:\n            deviceId: \"tools.deviceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-alarms\n          description: >-\n            List all active alarms across data center infrastructure. Filter\n            by severity (ALARM, WARNING, INFO), alarm source device name, or\n            site name.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-alarms\"\n          with:\n            severity: \"tools.severity\"\n            alarmSource: \"tools.alarmSource\"\n            siteName: \"tools.siteName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n \
  \       - name: list-sensors\n          description: >-\n            List all environmental sensor data points including temperature,\n            humidity, airflow, door position, and leak detection sensors.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-sensors\"\n          with:\n            deviceName: \"tools.deviceName\"\n            siteName: \"tools.siteName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-racks\n          description: >-\n            List all monitored racks in the data center with status and\n            capacity information.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-racks\"\n          with:\n            rackName: \"tools.rackName\"\n            siteName: \"tools.siteName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n    \
  \    - name: list-circuits\n          description: >-\n            List all electrical circuits with current (amps), voltage, and\n            power (watts) readings.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-circuits\"\n          with:\n            circuitName: \"tools.circuitName\"\n            siteName: \"tools.siteName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assets\n          description: >-\n            List all IT assets tracked in the DCIM system including servers,\n            network equipment, and other data center hardware.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-assets\"\n          with:\n            assetName: \"tools.assetName\"\n            rackName: \"tools.rackName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n     \
  \   - name: list-datasets\n          description: >-\n            List all top-level data set entity categories available in the\n            Environet system (GROUP, LOCATION, RACK, DEVICE, CIRCUIT, etc.)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"environet.list-datasets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vertiv/refs/heads/main/capabilities/dcim-monitoring.yaml
tags:
- Alarms
- Asset Management
- DCIM
- Environmental Monitoring
- Infrastructure Monitoring
- Operations
- Power Management
- Sensors
- Vertiv
tools:
- description: List all monitored DCIM devices. Filter by site name, group path, or status (NORMAL, ALARM, WARNING, DOWN, MAINTENANCE, DISABLED).
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get detailed information about a specific monitored device by its ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-device
- description: List all active alarms across data center infrastructure. Filter by severity (ALARM, WARNING, INFO), alarm source device name, or site name.
  hints:
    openWorld: true
    readOnly: true
  name: list-alarms
- description: List all environmental sensor data points including temperature, humidity, airflow, door position, and leak detection sensors.
  hints:
    openWorld: true
    readOnly: true
  name: list-sensors
- description: List all monitored racks in the data center with status and capacity information.
  hints:
    openWorld: true
    readOnly: true
  name: list-racks
- description: List all electrical circuits with current (amps), voltage, and power (watts) readings.
  hints:
    openWorld: true
    readOnly: true
  name: list-circuits
- description: List all IT assets tracked in the DCIM system including servers, network equipment, and other data center hardware.
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: List all top-level data set entity categories available in the Environet system (GROUP, LOCATION, RACK, DEVICE, CIRCUIT, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
---
