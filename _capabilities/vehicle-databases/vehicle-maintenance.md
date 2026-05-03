---
api_specs:
- filename: vehicle-databases-openapi.yml
  format: yaml
  label: vehicle-databases
  slug: vehicle-databases
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/vehicle-databases/refs/heads/main/openapi/vehicle-databases-openapi.yml
categories: []
consumed_apis:
- vehicle-databases
description: Customer workflow capability for vehicle maintenance management. Combines VIN decoding, OEM maintenance schedule retrieval, service item lookup, NHTSA recall checks, and TSB lookups into a unified interface for fleet operators, repair shops, and consumer maintenance reminder applications.
layout: capability
name: Vehicle Maintenance Workflow
operations:
- description: Find vehicles with engine options by make, model, and year
  method: GET
  name: lookup-vehicle
  path: /v1/vehicles
- description: Decode a 17-character VIN to full vehicle specification
  method: GET
  name: decode-vin
  path: /v1/vehicles/vin/{vin}
- description: Get complete OEM maintenance schedule with service intervals
  method: GET
  name: get-maintenance-schedule
  path: /v1/maintenance/{vehicleId}
- description: List service items with fluid specs for a specific mileage
  method: GET
  name: list-service-items
  path: /v1/services/{vehicleId}
- description: Get NHTSA recall information for a vehicle
  method: GET
  name: get-recalls
  path: /v1/recalls/{vehicleId}
- description: Get OEM technical service bulletins for a vehicle
  method: GET
  name: get-tsbs
  path: /v1/tsb/{vehicleId}
personas: []
provider_name: Vehicle Databases
provider_slug: vehicle-databases
search_terms:
- automotive
- get nhtsa recall information for a vehicle
- get oem maintenance schedule
- find vehicles with engine options by make, model, and year
- get technical service bulletins
- get service items, fluid specifications, and part numbers for a vehicle at a specific mileage interval
- decode a vin to vehicle details
- get oem technical service bulletins (tsbs) for a vehicle, optionally filtered by category
- decode a 17-character vin to full vehicle specification
- look up vehicles by make, model, and year to get vehicle identifiers
- vehicles
- list service items
- decode a 17-character vin to identify make, model, year, engine, and trim
- get maintenance schedule
- decode vin
- lookup vehicle
- maintenance
- get recalls
- recalls
- get complete oem maintenance schedule with service intervals
- list service items with fluid specs for a specific mileage
- check nhtsa safety recalls
- look up vehicles by make, model, and year
- check for nhtsa safety recalls affecting a specific vehicle
- fleet management
- get tsbs
- get service items for a maintenance interval
- get the complete oem maintenance schedule for a vehicle, optionally filtered by current mileage
- get oem technical service bulletins for a vehicle
slug: vehicle-maintenance
source_filename: vehicle-maintenance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vehicle Maintenance Workflow\"\n  description: >-\n    Customer workflow capability for vehicle maintenance management. Combines\n    VIN decoding, OEM maintenance schedule retrieval, service item lookup,\n    NHTSA recall checks, and TSB lookups into a unified interface for fleet\n    operators, repair shops, and consumer maintenance reminder applications.\n  tags:\n    - Automotive\n    - Fleet Management\n    - Maintenance\n    - Recalls\n    - Vehicles\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VEHICLE_DATABASES_API_KEY: VEHICLE_DATABASES_API_KEY\n\ncapability:\n  consumes:\n    - import: vehicle-databases\n      location: ./shared/vehicle-databases.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vehicle-maintenance-api\n      description: \"Unified REST API for vehicle maintenance management workflows.\"\n      resources:\n        - path:\
  \ /v1/vehicles\n          name: vehicles\n          description: \"Look up vehicles by make, model, and year\"\n          operations:\n            - method: GET\n              name: lookup-vehicle\n              description: \"Find vehicles with engine options by make, model, and year\"\n              call: \"vehicle-databases.lookup-vehicle\"\n              with:\n                make: \"rest.make\"\n                model: \"rest.model\"\n                year: \"rest.year\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vehicles/vin/{vin}\n          name: vin-decode\n          description: \"Decode a VIN to vehicle details\"\n          operations:\n            - method: GET\n              name: decode-vin\n              description: \"Decode a 17-character VIN to full vehicle specification\"\n              call: \"vehicle-databases.decode-vin\"\n              with:\n                vin: \"rest.vin\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/maintenance/{vehicleId}\n          name: maintenance\n          description: \"Get OEM maintenance schedule\"\n          operations:\n            - method: GET\n              name: get-maintenance-schedule\n              description: \"Get complete OEM maintenance schedule with service intervals\"\n              call: \"vehicle-databases.get-maintenance-schedule\"\n              with:\n                vehicleId: \"rest.vehicleId\"\n                mileage: \"rest.mileage\"\n                includeItems: \"rest.includeItems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{vehicleId}\n          name: services\n          description: \"Get service items for a maintenance interval\"\n          operations:\n            - method: GET\n              name: list-service-items\n              description:\
  \ \"List service items with fluid specs for a specific mileage\"\n              call: \"vehicle-databases.list-service-items\"\n              with:\n                vehicleId: \"rest.vehicleId\"\n                mileage: \"rest.mileage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recalls/{vehicleId}\n          name: recalls\n          description: \"Check NHTSA safety recalls\"\n          operations:\n            - method: GET\n              name: get-recalls\n              description: \"Get NHTSA recall information for a vehicle\"\n              call: \"vehicle-databases.get-recalls\"\n              with:\n                vehicleId: \"rest.vehicleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tsb/{vehicleId}\n          name: tsbs\n          description: \"Get technical service bulletins\"\n          operations:\n            -\
  \ method: GET\n              name: get-tsbs\n              description: \"Get OEM technical service bulletins for a vehicle\"\n              call: \"vehicle-databases.get-tsbs\"\n              with:\n                vehicleId: \"rest.vehicleId\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vehicle-maintenance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted vehicle maintenance management.\"\n      tools:\n        - name: lookup-vehicle\n          description: \"Look up vehicles by make, model, and year to get vehicle identifiers\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.lookup-vehicle\"\n          with:\n            make: \"tools.make\"\n            model: \"tools.model\"\n            year: \"tools.year\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: decode-vin\n          description: \"Decode a 17-character VIN to identify make, model, year, engine, and trim\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.decode-vin\"\n          with:\n            vin: \"tools.vin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-maintenance-schedule\n          description: \"Get the complete OEM maintenance schedule for a vehicle, optionally filtered by current mileage\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.get-maintenance-schedule\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n            mileage: \"tools.mileage\"\n            includeItems: \"tools.includeItems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: list-service-items\n          description: \"Get service items, fluid specifications, and part numbers for a vehicle at a specific mileage interval\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.list-service-items\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n            mileage: \"tools.mileage\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recalls\n          description: \"Check for NHTSA safety recalls affecting a specific vehicle\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.get-recalls\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-tsbs\n          description: \"Get OEM technical service bulletins (TSBs) for a vehicle,\
  \ optionally filtered by category\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"vehicle-databases.get-tsbs\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vehicle-databases/refs/heads/main/capabilities/vehicle-maintenance.yaml
tags:
- Automotive
- Fleet Management
- Maintenance
- Recalls
- Vehicles
tools:
- description: Look up vehicles by make, model, and year to get vehicle identifiers
  hints:
    openWorld: false
    readOnly: true
  name: lookup-vehicle
- description: Decode a 17-character VIN to identify make, model, year, engine, and trim
  hints:
    openWorld: false
    readOnly: true
  name: decode-vin
- description: Get the complete OEM maintenance schedule for a vehicle, optionally filtered by current mileage
  hints:
    openWorld: false
    readOnly: true
  name: get-maintenance-schedule
- description: Get service items, fluid specifications, and part numbers for a vehicle at a specific mileage interval
  hints:
    openWorld: false
    readOnly: true
  name: list-service-items
- description: Check for NHTSA safety recalls affecting a specific vehicle
  hints:
    openWorld: false
    readOnly: true
  name: get-recalls
- description: Get OEM technical service bulletins (TSBs) for a vehicle, optionally filtered by category
  hints:
    openWorld: false
    readOnly: true
  name: get-tsbs
---
