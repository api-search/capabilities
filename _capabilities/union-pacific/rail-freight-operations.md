---
categories: []
consumed_apis: []
description: Unified rail freight operations workflow for shipment visibility, supply chain exception management, intermodal planning, and equipment management. Used by logistics managers, supply chain analysts, and operations teams integrating Union Pacific railroad services into their supply chain platforms.
layout: capability
name: Union Pacific Rail Freight Operations
operations:
- description: Track active shipments with real-time location and ETAs
  method: GET
  name: list-shipments
  path: /v1/shipments
- description: Get tracking details for a specific shipment
  method: GET
  name: get-shipment
  path: /v1/shipments
- description: View exception cases for off-course shipments
  method: GET
  name: list-cases
  path: /v1/cases
- description: Get details for a specific exception case
  method: GET
  name: get-case
  path: /v1/cases
- description: Search available rail equipment
  method: GET
  name: list-equipment
  path: /v1/equipment
- description: Release held equipment for a shipment
  method: POST
  name: release-shipment
  path: /v1/equipment
- description: Order rail car equipment
  method: POST
  name: order-equipment
  path: /v1/equipment
- description: Create an intermodal terminal reservation
  method: POST
  name: create-intermodal-reservation
  path: /v1/intermodal/reservations
- description: List available service lanes
  method: GET
  name: list-intermodal-lanes
  path: /v1/intermodal/lanes
- description: View UP network facility locations
  method: GET
  name: list-locations
  path: /v1/locations
personas: []
provider_name: Union Pacific
provider_slug: union-pacific
search_terms:
- trains
- logistics
- list equipment
- search available rail car equipment by type and specifications
- analyzes freight patterns, plans intermodal routes, and tracks performance
- track active shipments with real-time location and etas
- order rail car equipment
- release held rail car equipment for a shipment
- active rail shipment tracking
- union pacific network locations
- view exception cases for off-course shipments
- intermodal terminal reservation management
- supply chain
- view up network facility locations
- freight
- end-to-end rail freight workflow from equipment ordering through shipment tracking and exception management
- get detailed tracking information for a specific rail shipment
- view union pacific network facilities, yards, and terminals with location details
- manages rail freight shipments and oversees supply chain exception handling
- get details for a specific supply chain exception case
- union pacific
- list intermodal lanes
- list available intermodal service lanes and transit times between terminals
- release held equipment for a shipment
- list intermodal departures
- list available service lanes
- search available rail equipment
- get shipment
- rail equipment search and management
- order rail car equipment for a shipment from origin to destination
- view scheduled intermodal train departures and available capacity
- list cases
- reserve space on an intermodal train between up terminals
- get case
- railroads
- create intermodal reservation
- list shipments
- create an intermodal terminal reservation
- look up waybill details for shipments
- get details for a specific exception case
- view exception cases for shipments that are off course or experiencing delays
- coordinates equipment ordering, intermodal reservations, and terminal operations
- get tracking details for a specific shipment
- release shipment
- list locations
- shipping
- track active rail shipments showing current location and estimated arrival times
- order equipment
- available intermodal service lanes
- list waybills
- supply chain exception case management
slug: rail-freight-operations
source_filename: rail-freight-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Union Pacific Rail Freight Operations\n  description: Unified rail freight operations workflow for shipment visibility, supply chain exception management, intermodal\n    planning, and equipment management. Used by logistics managers, supply chain analysts, and operations teams integrating\n    Union Pacific railroad services into their supply chain platforms.\n  tags:\n  - Union Pacific\n  - Freight\n  - Railroads\n  - Supply Chain\n  - Logistics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UP_API_TOKEN: UP_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: union-pacific\n    baseUri: https://api.up.com\n    description: Union Pacific railroad supply chain API.\n    authentication:\n      type: bearer\n      token: '{{UP_API_TOKEN}}'\n    resources:\n    - name: shipments\n      path: /shipment\n      description: Shipment tracking and management\n      operations:\n     \
  \ - name: list-shipments\n        method: GET\n        description: Search active shipments for location and ETA data\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Account identifier\n        - name: shipmentId\n          in: query\n          type: string\n          required: false\n          description: Filter by shipment ID\n        - name: destination\n          in: query\n          type: string\n          required: false\n          description: Filter by destination\n        - name: origin\n          in: query\n          type: string\n          required: false\n          description: Filter by origin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-shipment\n        method: GET\n        description: Get details for a specific shipment\n        inputParameters:\n        - name: shipmentId\n\
  \          in: path\n          type: string\n          required: true\n          description: Shipment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cases\n      path: /case\n      description: Exception case management for off-course shipments\n      operations:\n      - name: list-cases\n        method: GET\n        description: Find exception cases for shipments requiring attention\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Account identifier\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Case status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-case\n        method: GET\n        description: Get details for\
  \ a specific exception case\n        inputParameters:\n        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Case ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment\n      path: /equipment\n      description: Rail equipment search and management\n      operations:\n      - name: list-equipment\n        method: GET\n        description: Search and identify rail equipment\n        inputParameters:\n        - name: equipmentType\n          in: query\n          type: string\n          required: false\n          description: Equipment type filter\n        - name: equipmentNumber\n          in: query\n          type: string\n          required: false\n          description: Specific equipment number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: equipment-actions\n      path: /releaseShipment\n      description: Shipment action management\n      operations:\n      - name: release-shipment\n        method: POST\n        description: Release held equipment for a shipment\n        inputParameters:\n        - name: shipmentId\n          in: body\n          type: string\n          required: true\n          description: Shipment ID to release equipment for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: order-equipment\n        method: POST\n        description: Order rail car equipment for a shipment\n        inputParameters:\n        - name: accountId\n          in: body\n          type: string\n          required: true\n          description: Account identifier\n        - name: equipmentType\n          in: body\n          type: string\n          required: true\n          description: Type of equipment to order\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intermodal\n      path: /intermodal\n      description: Intermodal planning and reservations\n      operations:\n      - name: create-intermodal-reservation\n        method: POST\n        description: Create an intermodal terminal reservation\n        inputParameters:\n        - name: origin\n          in: body\n          type: string\n          required: true\n          description: Origin terminal code\n        - name: destination\n          in: body\n          type: string\n          required: true\n          description: Destination terminal code\n        - name: date\n          in: body\n          type: string\n          required: true\n          description: Departure date\n        - name: equipmentType\n          in: body\n          type: string\n          required: true\n          description: Container type\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: list-intermodal-lanes\n        method: GET\n        description: List available intermodal service lanes\n        inputParameters:\n        - name: origin\n          in: query\n          type: string\n          required: false\n          description: Origin terminal\n        - name: destination\n          in: query\n          type: string\n          required: false\n          description: Destination terminal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-intermodal-departures\n        method: GET\n        description: List scheduled intermodal train departures\n        inputParameters:\n        - name: origin\n          in: query\n          type: string\n          required: false\n          description: Origin terminal\n        - name: destination\n          in: query\n          type: string\n          required:\
  \ false\n          description: Destination terminal\n        - name: date\n          in: query\n          type: string\n          required: false\n          description: Departure date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /location\n      description: Union Pacific network location data\n      operations:\n      - name: list-locations\n        method: GET\n        description: View Union Pacific network facility details\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: US state code\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Location type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: waybills\n      path:\
  \ /waybill\n      description: Waybill data access\n      operations:\n      - name: list-waybills\n        method: GET\n        description: Look up waybill details\n        inputParameters:\n        - name: waybillNumber\n          in: query\n          type: string\n          required: false\n          description: Waybill number\n        - name: shipmentId\n          in: query\n          type: string\n          required: false\n          description: Associated shipment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: union-pacific-freight-api\n    description: Unified REST API for Union Pacific rail freight operations.\n    resources:\n    - path: /v1/shipments\n      name: shipments\n      description: Active rail shipment tracking\n      operations:\n      - method: GET\n        name: list-shipments\n        description: Track active shipments\
  \ with real-time location and ETAs\n        call: union-pacific.list-shipments\n        with:\n          accountId: rest.accountId\n          destination: rest.destination\n          origin: rest.origin\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-shipment\n        description: Get tracking details for a specific shipment\n        call: union-pacific.get-shipment\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cases\n      name: cases\n      description: Supply chain exception case management\n      operations:\n      - method: GET\n        name: list-cases\n        description: View exception cases for off-course shipments\n        call: union-pacific.list-cases\n        with:\n          accountId: rest.accountId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \   - method: GET\n        name: get-case\n        description: Get details for a specific exception case\n        call: union-pacific.get-case\n        with:\n          caseId: rest.caseId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment\n      name: equipment\n      description: Rail equipment search and management\n      operations:\n      - method: GET\n        name: list-equipment\n        description: Search available rail equipment\n        call: union-pacific.list-equipment\n        with:\n          equipmentType: rest.equipmentType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: release-shipment\n        description: Release held equipment for a shipment\n        call: union-pacific.release-shipment\n        with:\n          shipmentId: rest.shipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: order-equipment\n\
  \        description: Order rail car equipment\n        call: union-pacific.order-equipment\n        with:\n          accountId: rest.accountId\n          equipmentType: rest.equipmentType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intermodal/reservations\n      name: intermodal-reservations\n      description: Intermodal terminal reservation management\n      operations:\n      - method: POST\n        name: create-intermodal-reservation\n        description: Create an intermodal terminal reservation\n        call: union-pacific.create-intermodal-reservation\n        with:\n          origin: rest.origin\n          destination: rest.destination\n          date: rest.date\n          equipmentType: rest.equipmentType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intermodal/lanes\n      name: intermodal-lanes\n      description: Available intermodal service lanes\n      operations:\n      - method:\
  \ GET\n        name: list-intermodal-lanes\n        description: List available service lanes\n        call: union-pacific.list-intermodal-lanes\n        with:\n          origin: rest.origin\n          destination: rest.destination\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/locations\n      name: locations\n      description: Union Pacific network locations\n      operations:\n      - method: GET\n        name: list-locations\n        description: View UP network facility locations\n        call: union-pacific.list-locations\n        with:\n          state: rest.state\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: union-pacific-freight-mcp\n    transport: http\n    description: MCP server for AI-assisted rail freight operations and supply chain visibility.\n    tools:\n    - name: list-shipments\n      description: Track active rail shipments\
  \ showing current location and estimated arrival times\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.list-shipments\n      with:\n        accountId: tools.accountId\n        destination: tools.destination\n        origin: tools.origin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment\n      description: Get detailed tracking information for a specific rail shipment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.get-shipment\n      with:\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cases\n      description: View exception cases for shipments that are off course or experiencing delays\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.list-cases\n      with:\n        accountId: tools.accountId\n        status: tools.status\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-case\n      description: Get details for a specific supply chain exception case\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.get-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-equipment\n      description: Search available rail car equipment by type and specifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.list-equipment\n      with:\n        equipmentType: tools.equipmentType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: order-equipment\n      description: Order rail car equipment for a shipment from origin to destination\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: union-pacific.order-equipment\n      with:\n        accountId: tools.accountId\n   \
  \     equipmentType: tools.equipmentType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: release-shipment\n      description: Release held rail car equipment for a shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: union-pacific.release-shipment\n      with:\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-intermodal-reservation\n      description: Reserve space on an intermodal train between UP terminals\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: union-pacific.create-intermodal-reservation\n      with:\n        origin: tools.origin\n        destination: tools.destination\n        date: tools.date\n        equipmentType: tools.equipmentType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-intermodal-lanes\n      description:\
  \ List available intermodal service lanes and transit times between terminals\n      hints:\n        readOnly: true\n        openWorld: true\n      call: union-pacific.list-intermodal-lanes\n      with:\n        origin: tools.origin\n        destination: tools.destination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-intermodal-departures\n      description: View scheduled intermodal train departures and available capacity\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.list-intermodal-departures\n      with:\n        origin: tools.origin\n        destination: tools.destination\n        date: tools.date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-locations\n      description: View Union Pacific network facilities, yards, and terminals with location details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: union-pacific.list-locations\n \
  \     with:\n        state: tools.state\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-waybills\n      description: Look up waybill details for shipments\n      hints:\n        readOnly: true\n        openWorld: false\n      call: union-pacific.list-waybills\n      with:\n        waybillNumber: tools.waybillNumber\n        shipmentId: tools.shipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/union-pacific/refs/heads/main/capabilities/rail-freight-operations.yaml
tags:
- Union Pacific
- Freight
- Railroads
- Supply Chain
- Logistics
tools:
- description: Track active rail shipments showing current location and estimated arrival times
  hints:
    openWorld: false
    readOnly: true
  name: list-shipments
- description: Get detailed tracking information for a specific rail shipment
  hints:
    openWorld: false
    readOnly: true
  name: get-shipment
- description: View exception cases for shipments that are off course or experiencing delays
  hints:
    openWorld: false
    readOnly: true
  name: list-cases
- description: Get details for a specific supply chain exception case
  hints:
    openWorld: false
    readOnly: true
  name: get-case
- description: Search available rail car equipment by type and specifications
  hints:
    openWorld: false
    readOnly: true
  name: list-equipment
- description: Order rail car equipment for a shipment from origin to destination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: order-equipment
- description: Release held rail car equipment for a shipment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: release-shipment
- description: Reserve space on an intermodal train between UP terminals
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-intermodal-reservation
- description: List available intermodal service lanes and transit times between terminals
  hints:
    openWorld: true
    readOnly: true
  name: list-intermodal-lanes
- description: View scheduled intermodal train departures and available capacity
  hints:
    openWorld: false
    readOnly: true
  name: list-intermodal-departures
- description: View Union Pacific network facilities, yards, and terminals with location details
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: Look up waybill details for shipments
  hints:
    openWorld: false
    readOnly: true
  name: list-waybills
---
