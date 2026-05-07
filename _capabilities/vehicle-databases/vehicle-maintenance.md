---
categories: []
consumed_apis: []
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
- check nhtsa safety recalls
- find vehicles with engine options by make, model, and year
- get nhtsa recall information for a vehicle
- check for nhtsa safety recalls affecting a specific vehicle
- get maintenance schedule
- decode a 17-character vin to identify make, model, year, engine, and trim
- look up vehicles by make, model, and year to get vehicle identifiers
- vehicles
- get recalls
- get service items for a maintenance interval
- get technical service bulletins
- list service items
- get oem technical service bulletins for a vehicle
- lookup vehicle
- decode vin
- get oem maintenance schedule
- get service items, fluid specifications, and part numbers for a vehicle at a specific mileage interval
- get tsbs
- fleet management
- get oem technical service bulletins (tsbs) for a vehicle, optionally filtered by category
- automotive
- decode a vin to vehicle details
- get the complete oem maintenance schedule for a vehicle, optionally filtered by current mileage
- maintenance
- recalls
- look up vehicles by make, model, and year
- list service items with fluid specs for a specific mileage
- get complete oem maintenance schedule with service intervals
- decode a 17-character vin to full vehicle specification
slug: vehicle-maintenance
source_filename: vehicle-maintenance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vehicle Maintenance Workflow\n  description: Customer workflow capability for vehicle maintenance management. Combines VIN decoding, OEM maintenance schedule\n    retrieval, service item lookup, NHTSA recall checks, and TSB lookups into a unified interface for fleet operators, repair\n    shops, and consumer maintenance reminder applications.\n  tags:\n  - Automotive\n  - Fleet Management\n  - Maintenance\n  - Recalls\n  - Vehicles\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VEHICLE_DATABASES_API_KEY: VEHICLE_DATABASES_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vehicle-databases\n    baseUri: https://api.vehicledatabases.com/v1\n    description: Vehicle Databases Maintenance API v1\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{env.VEHICLE_DATABASES_API_KEY}}'\n      placement: header\n    resources:\n    - name: vehicle-lookup\n    \
  \  path: /vehicle\n      description: Look up vehicles by make, model, and year\n      operations:\n      - name: lookup-vehicle\n        method: GET\n        description: Find vehicles matching make, model, and year with engine options\n        inputParameters:\n        - name: make\n          in: query\n          type: string\n          required: true\n          description: Vehicle make\n        - name: model\n          in: query\n          type: string\n          required: true\n          description: Vehicle model\n        - name: year\n          in: query\n          type: integer\n          required: true\n          description: 4-digit model year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vin-decode\n      path: /vin/{vin}\n      description: Decode a VIN to vehicle details\n      operations:\n      - name: decode-vin\n        method: GET\n        description: Decode a 17-character VIN\
  \ to make, model, year, engine, and trim\n        inputParameters:\n        - name: vin\n          in: path\n          type: string\n          required: true\n          description: 17-character Vehicle Identification Number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance-schedule\n      path: /maintenance/{vehicleId}\n      description: Get OEM maintenance schedule for a vehicle\n      operations:\n      - name: get-maintenance-schedule\n        method: GET\n        description: Return complete OEM maintenance schedule with all service intervals\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n          description: Vehicle identifier from lookup or VIN decode\n        - name: mileage\n          in: query\n          type: integer\n          required: false\n          description: Current mileage to filter upcoming\
  \ services\n        - name: includeItems\n          in: query\n          type: boolean\n          required: false\n          description: Include service items in response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-items\n      path: /services/{vehicleId}\n      description: Get service items for a vehicle at a specific mileage\n      operations:\n      - name: list-service-items\n        method: GET\n        description: Return service items with fluid specs and parts for a mileage interval\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n          description: Vehicle identifier\n        - name: mileage\n          in: query\n          type: integer\n          required: true\n          description: Service interval mileage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: recalls\n      path: /recalls/{vehicleId}\n      description: Get NHTSA recall data for a vehicle\n      operations:\n      - name: get-recalls\n        method: GET\n        description: Return NHTSA safety recalls with component, risk, and remedy information\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n          description: Vehicle identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tsbs\n      path: /tsb/{vehicleId}\n      description: Get technical service bulletins for a vehicle\n      operations:\n      - name: get-tsbs\n        method: GET\n        description: Return OEM TSBs with symptoms, diagnosis, and remedy procedures\n        inputParameters:\n        - name: vehicleId\n          in: path\n          type: string\n          required: true\n  \
  \        description: Vehicle identifier\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: TSB category filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vehicle-maintenance-api\n    description: Unified REST API for vehicle maintenance management workflows.\n    resources:\n    - path: /v1/vehicles\n      name: vehicles\n      description: Look up vehicles by make, model, and year\n      operations:\n      - method: GET\n        name: lookup-vehicle\n        description: Find vehicles with engine options by make, model, and year\n        call: vehicle-databases.lookup-vehicle\n        with:\n          make: rest.make\n          model: rest.model\n          year: rest.year\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/vin/{vin}\n\
  \      name: vin-decode\n      description: Decode a VIN to vehicle details\n      operations:\n      - method: GET\n        name: decode-vin\n        description: Decode a 17-character VIN to full vehicle specification\n        call: vehicle-databases.decode-vin\n        with:\n          vin: rest.vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/maintenance/{vehicleId}\n      name: maintenance\n      description: Get OEM maintenance schedule\n      operations:\n      - method: GET\n        name: get-maintenance-schedule\n        description: Get complete OEM maintenance schedule with service intervals\n        call: vehicle-databases.get-maintenance-schedule\n        with:\n          vehicleId: rest.vehicleId\n          mileage: rest.mileage\n          includeItems: rest.includeItems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{vehicleId}\n      name: services\n      description: Get\
  \ service items for a maintenance interval\n      operations:\n      - method: GET\n        name: list-service-items\n        description: List service items with fluid specs for a specific mileage\n        call: vehicle-databases.list-service-items\n        with:\n          vehicleId: rest.vehicleId\n          mileage: rest.mileage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recalls/{vehicleId}\n      name: recalls\n      description: Check NHTSA safety recalls\n      operations:\n      - method: GET\n        name: get-recalls\n        description: Get NHTSA recall information for a vehicle\n        call: vehicle-databases.get-recalls\n        with:\n          vehicleId: rest.vehicleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tsb/{vehicleId}\n      name: tsbs\n      description: Get technical service bulletins\n      operations:\n      - method: GET\n        name: get-tsbs\n        description:\
  \ Get OEM technical service bulletins for a vehicle\n        call: vehicle-databases.get-tsbs\n        with:\n          vehicleId: rest.vehicleId\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vehicle-maintenance-mcp\n    transport: http\n    description: MCP server for AI-assisted vehicle maintenance management.\n    tools:\n    - name: lookup-vehicle\n      description: Look up vehicles by make, model, and year to get vehicle identifiers\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-databases.lookup-vehicle\n      with:\n        make: tools.make\n        model: tools.model\n        year: tools.year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: decode-vin\n      description: Decode a 17-character VIN to identify make, model, year, engine, and trim\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: vehicle-databases.decode-vin\n      with:\n        vin: tools.vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-maintenance-schedule\n      description: Get the complete OEM maintenance schedule for a vehicle, optionally filtered by current mileage\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-databases.get-maintenance-schedule\n      with:\n        vehicleId: tools.vehicleId\n        mileage: tools.mileage\n        includeItems: tools.includeItems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-items\n      description: Get service items, fluid specifications, and part numbers for a vehicle at a specific mileage interval\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-databases.list-service-items\n      with:\n        vehicleId: tools.vehicleId\n        mileage: tools.mileage\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: get-recalls\n      description: Check for NHTSA safety recalls affecting a specific vehicle\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-databases.get-recalls\n      with:\n        vehicleId: tools.vehicleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tsbs\n      description: Get OEM technical service bulletins (TSBs) for a vehicle, optionally filtered by category\n      hints:\n        readOnly: true\n        openWorld: false\n      call: vehicle-databases.get-tsbs\n      with:\n        vehicleId: tools.vehicleId\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
