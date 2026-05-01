---
categories:
- iot
consumed_apis:
- agco-agcommand
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
- agco
- machine fleet management.
- get machine telemetry
- agricultural machine inventory and fleet management.
- list machines
- list all agco agricultural machines connected to the account.
- iot
- machine location history.
- agricultural operation manager monitoring machine fleet location and performance.
- precision ag developer
- get machine locations
- farm manager
- real-time engine, fuel, and operational telemetry monitoring.
- get machine telemetry.
- fleet monitoring and performance tracking for agco agricultural machines.
- machine telematics.
- agriculture
- telematics
- gps-based machine location and field work tracking.
- get machine location history.
- get real-time performance telemetry for an agco machine.
- developer building farm management applications using agco machine telemetry data.
- precision farming
- list all connected agco machines.
- get location history for an agco machine.
slug: precision-farming
source_filename: precision-farming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AGCO Precision Farming\"\n  description: \"Unified workflow capability for AGCO precision farming — monitoring machine location, performance telemetry, and operating conditions across a connected fleet. Used by farm managers and precision agriculture software developers.\"\n  tags:\n    - AGCO\n    - Agriculture\n    - Precision Farming\n    - IoT\n    - Telematics\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AGCO_API_KEY: AGCO_API_KEY\n\ncapability:\n  consumes:\n    - import: agco-agcommand\n      location: ./shared/agcommand-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: agco-precision-api\n      description: \"Unified REST API for AGCO precision farming fleet monitoring.\"\n      resources:\n        - path: /v1/machines\n          name: machines\n          description: \"Machine fleet management.\"\n          operations:\n            - method:\
  \ GET\n              name: list-machines\n              description: \"List all connected AGCO machines.\"\n              call: \"agco-agcommand.list-machines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/machines/{machineId}/telemetry\n          name: machine-telemetry\n          description: \"Machine telematics.\"\n          operations:\n            - method: GET\n              name: get-machine-telemetry\n              description: \"Get machine telemetry.\"\n              call: \"agco-agcommand.get-machine-telemetry\"\n              with:\n                machineId: \"rest.machineId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/machines/{machineId}/locations\n          name: machine-locations\n          description: \"Machine location history.\"\n          operations:\n            - method: GET\n              name: get-machine-locations\n\
  \              description: \"Get machine location history.\"\n              call: \"agco-agcommand.get-machine-locations\"\n              with:\n                machineId: \"rest.machineId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: agco-precision-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AGCO precision farming fleet monitoring.\"\n      tools:\n        - name: list-machines\n          description: \"List all AGCO agricultural machines connected to the account.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"agco-agcommand.list-machines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-machine-telemetry\n          description: \"Get real-time performance telemetry for an AGCO machine.\"\n          hints:\n            readOnly: true\n\
  \            destructive: false\n          call: \"agco-agcommand.get-machine-telemetry\"\n          with:\n            machineId: \"tools.machineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-machine-locations\n          description: \"Get location history for an AGCO machine.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"agco-agcommand.get-machine-locations\"\n          with:\n            machineId: \"tools.machineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
