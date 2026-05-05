---
api_specs:
- filename: travelcenters-of-america-openapi.yml
  format: yaml
  label: ta
  slug: ta
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/travelcenters-of-america/refs/heads/main/openapi/travelcenters-of-america-openapi.yml
categories: []
consumed_apis:
- ta
description: Workflow capability for fleet operators and professional truck drivers using TravelCenters of America (TA/Petro) locations. Covers location discovery, parking and shower availability, fuel pricing, truck service work orders, and fleet fuel code management.
layout: capability
name: TravelCenters of America Fleet and Driver Services
operations:
- description: Find travel centers by proximity, brand, or state
  method: GET
  name: list-locations
  path: /v1/locations
- description: Get real-time truck parking availability
  method: GET
  name: get-parking-availability
  path: /v1/parking
- description: Get shower availability and wait times
  method: GET
  name: get-shower-availability
  path: /v1/showers
- description: Get current diesel, gasoline, and DEF pricing
  method: GET
  name: get-pricing
  path: /v1/fuel-pricing
- description: List truck service work orders
  method: GET
  name: list-work-orders
  path: /v1/work-orders
- description: Search service records, invoices, and maintenance documents
  method: GET
  name: search-documents
  path: /v1/documents
- description: List fuel codes for the fleet
  method: GET
  name: list-fuel-codes
  path: /v1/fuel-codes
personas: []
provider_name: TravelCenters of America
provider_slug: travelcenters-of-america
search_terms:
- driver services
- get pricing
- check parking availability
- list fuel codes
- truck parking availability
- find ta, petro, or ta express travel centers near a location
- travel centers
- trucking
- search service records, invoices, and maintenance documents
- fuel prices at travel centers
- list truck service work orders
- get shower availability
- search documents
- search service documents
- locations
- check shower availability
- list fleet fuel authorization codes for ta/petro locations
- check shower facility availability and wait times at travel centers
- get real-time truck parking availability
- get current diesel, gasoline, and def pricing
- fuel
- list locations
- get parking availability
- get current diesel, gasoline, and def pricing at travel centers
- retail
- travel center location discovery
- get shower availability and wait times
- get fuel pricing
- shower facility availability
- find travel centers
- list truck service work orders for fleet vehicles
- fleet fuel code management
- check real-time truck parking availability at travel centers
- service documentation search
- list fuel codes for the fleet
- search truck service records, invoices, and maintenance documents
- truck service
- find travel centers by proximity, brand, or state
- truck service work orders
- list work orders
- fleet management
slug: fleet-and-driver-services
source_filename: fleet-and-driver-services.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TravelCenters of America Fleet and Driver Services\"\n  description: >-\n    Workflow capability for fleet operators and professional truck drivers\n    using TravelCenters of America (TA/Petro) locations. Covers location\n    discovery, parking and shower availability, fuel pricing, truck service\n    work orders, and fleet fuel code management.\n  tags:\n    - Travel Centers\n    - Truck Service\n    - Fleet Management\n    - Fuel\n    - Locations\n    - Trucking\n    - Driver Services\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TA_API_TOKEN: TA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: ta\n      location: ./shared/travelcenters-of-america.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: fleet-driver-api\n      description: \"Unified REST API for fleet and driver services at TA/Petro travel centers.\"\n      resources:\n        - path:\
  \ /v1/locations\n          name: locations\n          description: \"Travel center location discovery\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"Find travel centers by proximity, brand, or state\"\n              call: \"ta.list-locations\"\n              with:\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                radius: \"rest.radius\"\n                brand: \"rest.brand\"\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/parking\n          name: parking\n          description: \"Truck parking availability\"\n          operations:\n            - method: GET\n              name: get-parking-availability\n              description: \"Get real-time truck parking availability\"\n              call: \"ta.get-parking-availability\"\n              with:\n                location_id:\
  \ \"rest.location_id\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n                radius: \"rest.radius\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/showers\n          name: showers\n          description: \"Shower facility availability\"\n          operations:\n            - method: GET\n              name: get-shower-availability\n              description: \"Get shower availability and wait times\"\n              call: \"ta.get-shower-availability\"\n              with:\n                location_id: \"rest.location_id\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fuel-pricing\n          name: fuel-pricing\n          description: \"Fuel prices at travel centers\"\n          operations:\n            - method: GET\n              name:\
  \ get-pricing\n              description: \"Get current diesel, gasoline, and DEF pricing\"\n              call: \"ta.get-pricing\"\n              with:\n                location_id: \"rest.location_id\"\n                fuel_type: \"rest.fuel_type\"\n                lat: \"rest.lat\"\n                lon: \"rest.lon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/work-orders\n          name: work-orders\n          description: \"Truck service work orders\"\n          operations:\n            - method: GET\n              name: list-work-orders\n              description: \"List truck service work orders\"\n              call: \"ta.list-work-orders\"\n              with:\n                status: \"rest.status\"\n                location_id: \"rest.location_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/documents\n          name: documents\n          description: \"Service documentation search\"\n          operations:\n            - method: GET\n              name: search-documents\n              description: \"Search service records, invoices, and maintenance documents\"\n              call: \"ta.search-documents\"\n              with:\n                work_order_id: \"rest.work_order_id\"\n                vehicle_id: \"rest.vehicle_id\"\n                document_type: \"rest.document_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fuel-codes\n          name: fuel-codes\n          description: \"Fleet fuel code management\"\n          operations:\n            - method: GET\n              name: list-fuel-codes\n              description: \"List fuel codes for the fleet\"\n              call: \"ta.list-fuel-codes\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: fleet-driver-mcp\n      transport: http\n      description: \"MCP server for AI-assisted fleet management and driver services at TA/Petro.\"\n      tools:\n        - name: find-travel-centers\n          description: \"Find TA, Petro, or TA Express travel centers near a location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ta.list-locations\"\n          with:\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            radius: \"tools.radius\"\n            brand: \"tools.brand\"\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-parking-availability\n          description: \"Check real-time truck parking availability at travel centers\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"ta.get-parking-availability\"\n          with:\n            location_id: \"tools.location_id\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n            radius: \"tools.radius\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-shower-availability\n          description: \"Check shower facility availability and wait times at travel centers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ta.get-shower-availability\"\n          with:\n            location_id: \"tools.location_id\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-fuel-pricing\n          description: \"Get current diesel, gasoline, and DEF pricing at travel centers\"\n          hints:\n            readOnly: true\n            openWorld: true\n   \
  \       call: \"ta.get-pricing\"\n          with:\n            location_id: \"tools.location_id\"\n            fuel_type: \"tools.fuel_type\"\n            lat: \"tools.lat\"\n            lon: \"tools.lon\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-work-orders\n          description: \"List truck service work orders for fleet vehicles\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ta.list-work-orders\"\n          with:\n            status: \"tools.status\"\n            location_id: \"tools.location_id\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-service-documents\n          description: \"Search truck service records, invoices, and maintenance documents\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: false\n          call: \"ta.search-documents\"\n          with:\n            work_order_id: \"tools.work_order_id\"\n            vehicle_id: \"tools.vehicle_id\"\n            document_type: \"tools.document_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-fuel-codes\n          description: \"List fleet fuel authorization codes for TA/Petro locations\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ta.list-fuel-codes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/travelcenters-of-america/refs/heads/main/capabilities/fleet-and-driver-services.yaml
tags:
- Travel Centers
- Truck Service
- Fleet Management
- Fuel
- Locations
- Trucking
- Driver Services
tools:
- description: Find TA, Petro, or TA Express travel centers near a location
  hints:
    openWorld: true
    readOnly: true
  name: find-travel-centers
- description: Check real-time truck parking availability at travel centers
  hints:
    openWorld: true
    readOnly: true
  name: check-parking-availability
- description: Check shower facility availability and wait times at travel centers
  hints:
    openWorld: true
    readOnly: true
  name: check-shower-availability
- description: Get current diesel, gasoline, and DEF pricing at travel centers
  hints:
    openWorld: true
    readOnly: true
  name: get-fuel-pricing
- description: List truck service work orders for fleet vehicles
  hints:
    openWorld: false
    readOnly: true
  name: list-work-orders
- description: Search truck service records, invoices, and maintenance documents
  hints:
    openWorld: false
    readOnly: true
  name: search-service-documents
- description: List fleet fuel authorization codes for TA/Petro locations
  hints:
    openWorld: false
    readOnly: true
  name: list-fuel-codes
---
