---
categories: []
consumed_apis:
- ryder-fms
description: Unified workflow for fleet operations customers leasing and maintaining commercial vehicles with Ryder. Enables fleet managers to view vehicle specifications, track maintenance history, access service locations, and manage invoices through a single interface.
layout: capability
name: Ryder Fleet Operations
operations:
- description: List all vehicles in the fleet with specifications
  method: GET
  name: list-fleet-vehicles
  path: /v1/fleet
- description: Get detailed vehicle information and specifications
  method: GET
  name: get-vehicle
  path: /v1/fleet/{vehicleId}
- description: Get maintenance history for a specific vehicle
  method: GET
  name: get-service-history
  path: /v1/fleet/{vehicleId}/service-history
- description: List Ryder service center locations with services and hours
  method: GET
  name: list-locations
  path: /v1/locations
- description: List fleet invoices with line items and payment status
  method: GET
  name: list-invoices
  path: /v1/invoices
personas: []
provider_name: Ryder System
provider_slug: ryder-system
search_terms:
- get service history
- fleet invoices
- invoices
- get maintenance history for a specific vehicle
- trucking
- list ryder service center locations with services and hours
- service history
- single vehicle details
- list invoices
- locations
- transportation
- list fleet vehicles
- list all vehicles in the fleet with specifications
- list fleet invoices with line items, amounts, and payment status
- get maintenance and repair history for a specific fleet vehicle
- supply chain
- get vehicle
- list all vehicles in the ryder-managed fleet with specifications
- list locations
- logistics
- get detailed information and specifications for a specific fleet vehicle
- get detailed vehicle information and specifications
- vehicle service history
- list ryder service center locations with available services and business hours
- list fleet invoices with line items and payment status
- ryder service locations
- fleet vehicle catalog
- vehicles
- fleet management
slug: fleet-operations
source_filename: fleet-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ryder Fleet Operations\"\n  description: >-\n    Unified workflow for fleet operations customers leasing and maintaining\n    commercial vehicles with Ryder. Enables fleet managers to view vehicle\n    specifications, track maintenance history, access service locations, and\n    manage invoices through a single interface.\n  tags:\n    - Fleet Management\n    - Invoices\n    - Locations\n    - Service History\n    - Transportation\n    - Vehicles\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RYDER_FMS_API_KEY: RYDER_FMS_API_KEY\n\ncapability:\n  consumes:\n    - import: ryder-fms\n      location: ./shared/fleet-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ryder-fleet-ops-api\n      description: \"Unified REST API for Ryder fleet operations management.\"\n      resources:\n        - path: /v1/fleet\n          name: fleet\n          description:\
  \ \"Fleet vehicle catalog\"\n          operations:\n            - method: GET\n              name: list-fleet-vehicles\n              description: \"List all vehicles in the fleet with specifications\"\n              call: \"ryder-fms.list-fleet-vehicles\"\n              with:\n                page: \"rest.query.page\"\n                pageSize: \"rest.query.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fleet/{vehicleId}\n          name: vehicle\n          description: \"Single vehicle details\"\n          operations:\n            - method: GET\n              name: get-vehicle\n              description: \"Get detailed vehicle information and specifications\"\n              call: \"ryder-fms.get-vehicle\"\n              with:\n                vehicleId: \"rest.path.vehicleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/fleet/{vehicleId}/service-history\n\
  \          name: service-history\n          description: \"Vehicle service history\"\n          operations:\n            - method: GET\n              name: get-service-history\n              description: \"Get maintenance history for a specific vehicle\"\n              call: \"ryder-fms.get-service-history\"\n              with:\n                vehicleId: \"rest.path.vehicleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations\n          name: locations\n          description: \"Ryder service locations\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"List Ryder service center locations with services and hours\"\n              call: \"ryder-fms.list-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description:\
  \ \"Fleet invoices\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List fleet invoices with line items and payment status\"\n              call: \"ryder-fms.list-invoices\"\n              with:\n                startDate: \"rest.query.startDate\"\n                endDate: \"rest.query.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: ryder-fleet-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ryder fleet operations management.\"\n      tools:\n        - name: list-fleet-vehicles\n          description: \"List all vehicles in the Ryder-managed fleet with specifications\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ryder-fms.list-fleet-vehicles\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-vehicle\n          description: \"Get detailed information and specifications for a specific fleet vehicle\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ryder-fms.get-vehicle\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-history\n          description: \"Get maintenance and repair history for a specific fleet vehicle\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ryder-fms.get-service-history\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-locations\n          description: \"List Ryder service center locations with available services and business hours\"\n          hints:\n            readOnly: true\n \
  \           openWorld: true\n          call: \"ryder-fms.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List fleet invoices with line items, amounts, and payment status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ryder-fms.list-invoices\"\n          with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ryder-system/refs/heads/main/capabilities/fleet-operations.yaml
tags:
- Fleet Management
- Invoices
- Locations
- Service History
- Transportation
- Vehicles
tools:
- description: List all vehicles in the Ryder-managed fleet with specifications
  hints:
    openWorld: true
    readOnly: true
  name: list-fleet-vehicles
- description: Get detailed information and specifications for a specific fleet vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle
- description: Get maintenance and repair history for a specific fleet vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-service-history
- description: List Ryder service center locations with available services and business hours
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: List fleet invoices with line items, amounts, and payment status
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
---
