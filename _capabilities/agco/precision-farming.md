---
categories:
- iot
consumed_apis: []
description: Unified workflow capability for AGCO precision farming — monitoring machine location, performance telemetry, and operating conditions across a connected fleet. Used by farm managers and precision agriculture software developers.
layout: capability
name: AGCO Precision Farming
operations:
- description: List all connected AGCO machines.
  method: GET
  name: list-machines
  path: /v1/machines
- description: Get machine telemetry.
  method: GET
  name: get-machine-telemetry
  path: /v1/machines/{machineId}/telemetry
- description: Get machine location history.
  method: GET
  name: get-machine-locations
  path: /v1/machines/{machineId}/locations
personas:
- description: Agricultural operation manager monitoring machine fleet location and performance.
  id: farm-manager
  name: Farm Manager
- description: Developer building farm management applications using AGCO machine telemetry data.
  id: precision-ag-developer
  name: Precision Ag Developer
provider_name: agco
provider_slug: agco
search_terms:
- gps-based machine location and field work tracking.
- fleet monitoring and performance tracking for agco agricultural machines.
- farm manager
- list all connected agco machines.
- get real-time performance telemetry for an agco machine.
- agricultural operation manager monitoring machine fleet location and performance.
- precision ag developer
- list all agco agricultural machines connected to the account.
- telematics
- get machine location history.
- iot
- developer building farm management applications using agco machine telemetry data.
- get location history for an agco machine.
- precision farming
- list machines
- get machine telemetry
- machine telematics.
- get machine locations
- machine location history.
- get machine telemetry.
- real-time engine, fuel, and operational telemetry monitoring.
- machine fleet management.
- agco
- agriculture
- agricultural machine inventory and fleet management.
slug: precision-farming
source_filename: precision-farming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AGCO Precision Farming\n  description: Unified workflow capability for AGCO precision farming — monitoring machine location, performance telemetry,\n    and operating conditions across a connected fleet. Used by farm managers and precision agriculture software developers.\n  tags:\n  - AGCO\n  - Agriculture\n  - Precision Farming\n  - IoT\n  - Telematics\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AGCO_API_KEY: AGCO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: agco-agcommand\n    baseUri: https://api.agcocorp.com/v1\n    description: AGCO AgCommand API for machine telematics and location data.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{AGCO_API_KEY}}\n      placement: header\n    resources:\n    - name: machines\n      path: /machines\n      description: Agricultural machine listing.\n      operations:\n      - name: list-machines\n\
  \        method: GET\n        description: List all machines associated with the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machine-telemetry\n      path: /machines/{machineId}/telemetry\n      description: Machine telematics data.\n      operations:\n      - name: get-machine-telemetry\n        method: GET\n        description: Retrieve real-time telemetry data for a machine.\n        inputParameters:\n        - name: machineId\n          in: path\n          type: string\n          required: true\n          description: Machine identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: machine-locations\n      path: /machines/{machineId}/locations\n      description: Machine location history.\n      operations:\n      - name: get-machine-locations\n        method: GET\n        description:\
  \ Retrieve location history for a machine.\n        inputParameters:\n        - name: machineId\n          in: path\n          type: string\n          required: true\n          description: Machine identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agco-precision-api\n    description: Unified REST API for AGCO precision farming fleet monitoring.\n    resources:\n    - path: /v1/machines\n      name: machines\n      description: Machine fleet management.\n      operations:\n      - method: GET\n        name: list-machines\n        description: List all connected AGCO machines.\n        call: agco-agcommand.list-machines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/machines/{machineId}/telemetry\n      name: machine-telemetry\n      description: Machine telematics.\n      operations:\n      - method:\
  \ GET\n        name: get-machine-telemetry\n        description: Get machine telemetry.\n        call: agco-agcommand.get-machine-telemetry\n        with:\n          machineId: rest.machineId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/machines/{machineId}/locations\n      name: machine-locations\n      description: Machine location history.\n      operations:\n      - method: GET\n        name: get-machine-locations\n        description: Get machine location history.\n        call: agco-agcommand.get-machine-locations\n        with:\n          machineId: rest.machineId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agco-precision-mcp\n    transport: http\n    description: MCP server for AI-assisted AGCO precision farming fleet monitoring.\n    tools:\n    - name: list-machines\n      description: List all AGCO agricultural machines connected to the account.\n      hints:\n\
  \        readOnly: true\n        destructive: false\n      call: agco-agcommand.list-machines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-machine-telemetry\n      description: Get real-time performance telemetry for an AGCO machine.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agco-agcommand.get-machine-telemetry\n      with:\n        machineId: tools.machineId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-machine-locations\n      description: Get location history for an AGCO machine.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agco-agcommand.get-machine-locations\n      with:\n        machineId: tools.machineId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agco/refs/heads/main/capabilities/precision-farming.yaml
tags:
- AGCO
- Agriculture
- Precision Farming
- IoT
- Telematics
tools:
- description: List all AGCO agricultural machines connected to the account.
  hints:
    destructive: false
    readOnly: true
  name: list-machines
- description: Get real-time performance telemetry for an AGCO machine.
  hints:
    destructive: false
    readOnly: true
  name: get-machine-telemetry
- description: Get location history for an AGCO machine.
  hints:
    destructive: false
    readOnly: true
  name: get-machine-locations
---
