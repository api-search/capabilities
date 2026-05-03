---
api_specs:
- filename: union-pacific-api.yaml
  format: yaml
  label: union-pacific
  slug: union-pacific
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/union-pacific/refs/heads/main/openapi/union-pacific-api.yaml
categories: []
consumed_apis:
- union-pacific
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
- get case
- order rail car equipment for a shipment from origin to destination
- active rail shipment tracking
- view union pacific network facilities, yards, and terminals with location details
- look up waybill details for shipments
- coordinates equipment ordering, intermodal reservations, and terminal operations
- list intermodal departures
- supply chain
- track active rail shipments showing current location and estimated arrival times
- list equipment
- list cases
- list waybills
- list intermodal lanes
- rail equipment search and management
- get detailed tracking information for a specific rail shipment
- supply chain exception case management
- list shipments
- create an intermodal terminal reservation
- manages rail freight shipments and oversees supply chain exception handling
- track active shipments with real-time location and etas
- get details for a specific supply chain exception case
- list locations
- view scheduled intermodal train departures and available capacity
- reserve space on an intermodal train between up terminals
- available intermodal service lanes
- view exception cases for shipments that are off course or experiencing delays
- search available rail car equipment by type and specifications
- union pacific network locations
- list available service lanes
- union pacific
- release held equipment for a shipment
- get details for a specific exception case
- order equipment
- analyzes freight patterns, plans intermodal routes, and tracks performance
- get tracking details for a specific shipment
- shipping
- list available intermodal service lanes and transit times between terminals
- order rail car equipment
- release held rail car equipment for a shipment
- create intermodal reservation
- logistics
- get shipment
- search available rail equipment
- view up network facility locations
- release shipment
- end-to-end rail freight workflow from equipment ordering through shipment tracking and exception management
- railroads
- trains
- intermodal terminal reservation management
- freight
- view exception cases for off-course shipments
slug: rail-freight-operations
source_filename: rail-freight-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Union Pacific Rail Freight Operations\"\n  description: >-\n    Unified rail freight operations workflow for shipment visibility, supply chain\n    exception management, intermodal planning, and equipment management. Used by\n    logistics managers, supply chain analysts, and operations teams integrating\n    Union Pacific railroad services into their supply chain platforms.\n  tags:\n    - Union Pacific\n    - Freight\n    - Railroads\n    - Supply Chain\n    - Logistics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UP_API_TOKEN: UP_API_TOKEN\n\ncapability:\n  consumes:\n    - import: union-pacific\n      location: ./shared/union-pacific-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: union-pacific-freight-api\n      description: \"Unified REST API for Union Pacific rail freight operations.\"\n      resources:\n        - path: /v1/shipments\n\
  \          name: shipments\n          description: \"Active rail shipment tracking\"\n          operations:\n            - method: GET\n              name: list-shipments\n              description: \"Track active shipments with real-time location and ETAs\"\n              call: \"union-pacific.list-shipments\"\n              with:\n                accountId: \"rest.accountId\"\n                destination: \"rest.destination\"\n                origin: \"rest.origin\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-shipment\n              description: \"Get tracking details for a specific shipment\"\n              call: \"union-pacific.get-shipment\"\n              with:\n                shipmentId: \"rest.shipmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cases\n          name: cases\n          description:\
  \ \"Supply chain exception case management\"\n          operations:\n            - method: GET\n              name: list-cases\n              description: \"View exception cases for off-course shipments\"\n              call: \"union-pacific.list-cases\"\n              with:\n                accountId: \"rest.accountId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-case\n              description: \"Get details for a specific exception case\"\n              call: \"union-pacific.get-case\"\n              with:\n                caseId: \"rest.caseId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/equipment\n          name: equipment\n          description: \"Rail equipment search and management\"\n          operations:\n            - method: GET\n              name:\
  \ list-equipment\n              description: \"Search available rail equipment\"\n              call: \"union-pacific.list-equipment\"\n              with:\n                equipmentType: \"rest.equipmentType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: release-shipment\n              description: \"Release held equipment for a shipment\"\n              call: \"union-pacific.release-shipment\"\n              with:\n                shipmentId: \"rest.shipmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: order-equipment\n              description: \"Order rail car equipment\"\n              call: \"union-pacific.order-equipment\"\n              with:\n                accountId: \"rest.accountId\"\n                equipmentType: \"rest.equipmentType\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/intermodal/reservations\n          name: intermodal-reservations\n          description: \"Intermodal terminal reservation management\"\n          operations:\n            - method: POST\n              name: create-intermodal-reservation\n              description: \"Create an intermodal terminal reservation\"\n              call: \"union-pacific.create-intermodal-reservation\"\n              with:\n                origin: \"rest.origin\"\n                destination: \"rest.destination\"\n                date: \"rest.date\"\n                equipmentType: \"rest.equipmentType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/intermodal/lanes\n          name: intermodal-lanes\n          description: \"Available intermodal service lanes\"\n          operations:\n            - method: GET\n              name: list-intermodal-lanes\n\
  \              description: \"List available service lanes\"\n              call: \"union-pacific.list-intermodal-lanes\"\n              with:\n                origin: \"rest.origin\"\n                destination: \"rest.destination\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/locations\n          name: locations\n          description: \"Union Pacific network locations\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"View UP network facility locations\"\n              call: \"union-pacific.list-locations\"\n              with:\n                state: \"rest.state\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: union-pacific-freight-mcp\n      transport: http\n      description: \"MCP server for\
  \ AI-assisted rail freight operations and supply chain visibility.\"\n      tools:\n        - name: list-shipments\n          description: \"Track active rail shipments showing current location and estimated arrival times\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.list-shipments\"\n          with:\n            accountId: \"tools.accountId\"\n            destination: \"tools.destination\"\n            origin: \"tools.origin\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-shipment\n          description: \"Get detailed tracking information for a specific rail shipment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.get-shipment\"\n          with:\n            shipmentId: \"tools.shipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-cases\n          description: \"View exception cases for shipments that are off course or experiencing delays\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.list-cases\"\n          with:\n            accountId: \"tools.accountId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-case\n          description: \"Get details for a specific supply chain exception case\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.get-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-equipment\n          description: \"Search available rail car equipment by type and specifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n\
  \          call: \"union-pacific.list-equipment\"\n          with:\n            equipmentType: \"tools.equipmentType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: order-equipment\n          description: \"Order rail car equipment for a shipment from origin to destination\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"union-pacific.order-equipment\"\n          with:\n            accountId: \"tools.accountId\"\n            equipmentType: \"tools.equipmentType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: release-shipment\n          description: \"Release held rail car equipment for a shipment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"union-pacific.release-shipment\"\n          with:\n          \
  \  shipmentId: \"tools.shipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-intermodal-reservation\n          description: \"Reserve space on an intermodal train between UP terminals\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"union-pacific.create-intermodal-reservation\"\n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            date: \"tools.date\"\n            equipmentType: \"tools.equipmentType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-intermodal-lanes\n          description: \"List available intermodal service lanes and transit times between terminals\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"union-pacific.list-intermodal-lanes\"\n          with:\n\
  \            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-intermodal-departures\n          description: \"View scheduled intermodal train departures and available capacity\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.list-intermodal-departures\"\n          with:\n            origin: \"tools.origin\"\n            destination: \"tools.destination\"\n            date: \"tools.date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-locations\n          description: \"View Union Pacific network facilities, yards, and terminals with location details\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"union-pacific.list-locations\"\n          with:\n            state: \"tools.state\"\n\
  \            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-waybills\n          description: \"Look up waybill details for shipments\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"union-pacific.list-waybills\"\n          with:\n            waybillNumber: \"tools.waybillNumber\"\n            shipmentId: \"tools.shipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
