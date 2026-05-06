---
categories: []
consumed_apis: []
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
- logistics
- list fleet invoices with line items and payment status
- invoices
- list all vehicles in the ryder-managed fleet with specifications
- list fleet vehicles
- fleet vehicle catalog
- get maintenance and repair history for a specific fleet vehicle
- service history
- list locations
- list all vehicles in the fleet with specifications
- get detailed information and specifications for a specific fleet vehicle
- vehicle service history
- fleet management
- locations
- get maintenance history for a specific vehicle
- supply chain
- transportation
- fleet invoices
- vehicles
- list ryder service center locations with services and hours
- get service history
- list ryder service center locations with available services and business hours
- list fleet invoices with line items, amounts, and payment status
- ryder service locations
- list invoices
- trucking
- get vehicle
- get detailed vehicle information and specifications
- single vehicle details
slug: fleet-operations
source_filename: fleet-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ryder Fleet Operations\n  description: Unified workflow for fleet operations customers leasing and maintaining commercial vehicles with Ryder. Enables\n    fleet managers to view vehicle specifications, track maintenance history, access service locations, and manage invoices\n    through a single interface.\n  tags:\n  - Fleet Management\n  - Invoices\n  - Locations\n  - Service History\n  - Transportation\n  - Vehicles\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RYDER_FMS_API_KEY: RYDER_FMS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ryder-fms\n    baseUri: https://developer.ryder.com/fms/apis\n    description: Ryder Fleet Management System API\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{RYDER_FMS_API_KEY}}'\n      placement: header\n    resources:\n    - name: fleet\n      path: /fleet\n      description: Fleet vehicle\
  \ information and specifications\n      operations:\n      - name: list-fleet-vehicles\n        method: GET\n        description: Retrieve a list of vehicles in the fleet\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vehicle\n        method: GET\n        description: Retrieve detailed information about a specific vehicle\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n          description: Vehicle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n    - name: locations\n      path: /locations\n      description: Ryder service location information\n      operations:\n      - name: list-locations\n        method: GET\n        description: Retrieve location information including address and services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-history\n      path: /fleet/{vehicleId}/service-history\n      description: Vehicle service history records\n      operations:\n      - name: get-service-history\n        method: GET\n        description: Retrieve historical maintenance records for a specific vehicle\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n          description: Vehicle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: invoices\n      path: /invoices\n      description: Fleet invoice details and payment status\n      operations:\n      - name: list-invoices\n        method: GET\n        description: Retrieve historical invoice details for the fleet\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date for invoice filter (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for invoice filter (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ryder-fleet-ops-api\n    description: Unified REST API for Ryder fleet operations management.\n    resources:\n    - path: /v1/fleet\n      name: fleet\n      description: Fleet vehicle catalog\n      operations:\n\
  \      - method: GET\n        name: list-fleet-vehicles\n        description: List all vehicles in the fleet with specifications\n        call: ryder-fms.list-fleet-vehicles\n        with:\n          page: rest.query.page\n          pageSize: rest.query.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/{vehicleId}\n      name: vehicle\n      description: Single vehicle details\n      operations:\n      - method: GET\n        name: get-vehicle\n        description: Get detailed vehicle information and specifications\n        call: ryder-fms.get-vehicle\n        with:\n          vehicleId: rest.path.vehicleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fleet/{vehicleId}/service-history\n      name: service-history\n      description: Vehicle service history\n      operations:\n      - method: GET\n        name: get-service-history\n        description: Get maintenance history for a specific\
  \ vehicle\n        call: ryder-fms.get-service-history\n        with:\n          vehicleId: rest.path.vehicleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Ryder service locations\n      operations:\n      - method: GET\n        name: list-locations\n        description: List Ryder service center locations with services and hours\n        call: ryder-fms.list-locations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Fleet invoices\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List fleet invoices with line items and payment status\n        call: ryder-fms.list-invoices\n        with:\n          startDate: rest.query.startDate\n          endDate: rest.query.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n\
  \    port: 9080\n    namespace: ryder-fleet-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Ryder fleet operations management.\n    tools:\n    - name: list-fleet-vehicles\n      description: List all vehicles in the Ryder-managed fleet with specifications\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ryder-fms.list-fleet-vehicles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle\n      description: Get detailed information and specifications for a specific fleet vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ryder-fms.get-vehicle\n      with:\n        vehicleId: tools.vehicleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-history\n      description: Get maintenance and repair history for a specific fleet vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ryder-fms.get-service-history\n\
  \      with:\n        vehicleId: tools.vehicleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-locations\n      description: List Ryder service center locations with available services and business hours\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ryder-fms.list-locations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List fleet invoices with line items, amounts, and payment status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ryder-fms.list-invoices\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
