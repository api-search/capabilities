---
categories: []
consumed_apis: []
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
- get pricing
- list fuel codes
- service documentation search
- get current diesel, gasoline, and def pricing
- search service records, invoices, and maintenance documents
- find travel centers by proximity, brand, or state
- search service documents
- travel centers
- check parking availability
- get real-time truck parking availability
- find travel centers
- check shower facility availability and wait times at travel centers
- list fleet fuel authorization codes for ta/petro locations
- driver services
- travel center location discovery
- fuel prices at travel centers
- truck parking availability
- retail
- list work orders
- get shower availability
- get parking availability
- list locations
- fleet management
- locations
- get fuel pricing
- fuel
- search documents
- truck service work orders
- shower facility availability
- search truck service records, invoices, and maintenance documents
- list fuel codes for the fleet
- get shower availability and wait times
- find ta, petro, or ta express travel centers near a location
- list truck service work orders for fleet vehicles
- truck service
- check real-time truck parking availability at travel centers
- get current diesel, gasoline, and def pricing at travel centers
- fleet fuel code management
- trucking
- list truck service work orders
- check shower availability
slug: fleet-and-driver-services
source_filename: fleet-and-driver-services.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TravelCenters of America Fleet and Driver Services\n  description: Workflow capability for fleet operators and professional truck drivers using TravelCenters of America (TA/Petro)\n    locations. Covers location discovery, parking and shower availability, fuel pricing, truck service work orders, and fleet\n    fuel code management.\n  tags:\n  - Travel Centers\n  - Truck Service\n  - Fleet Management\n  - Fuel\n  - Locations\n  - Trucking\n  - Driver Services\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TA_API_TOKEN: TA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ta\n    baseUri: https://api.accessta.com/v1\n    description: TravelCenters of America REST APIs for truck service and retail operations.\n    authentication:\n      type: bearer\n      token: '{{TA_API_TOKEN}}'\n    resources:\n    - name: locations\n      path: /locations\n      description: Travel center\
  \ location search\n      operations:\n      - name: list-locations\n        method: GET\n        description: List TA/Petro travel center locations with amenity details\n        inputParameters:\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        - name: radius\n          in: query\n          type: number\n          required: false\n          description: Search radius in miles\n        - name: brand\n          in: query\n          type: string\n          required: false\n          description: TA, Petro, or TA Express\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: US state code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: parking\n      path: /parking/availability\n      description: Truck parking availability\n      operations:\n      - name: get-parking-availability\n        method: GET\n        description: Get real-time truck parking availability at travel centers\n        inputParameters:\n        - name: location_id\n          in: query\n          type: string\n          required: false\n          description: Filter by location ID\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        - name: radius\n          in: query\n          type: number\n          required: false\n          description: Search radius in miles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: showers\n      path: /showers/availability\n      description: Shower facility availability\n      operations:\n      - name: get-shower-availability\n        method: GET\n        description: Get shower availability at travel centers\n        inputParameters:\n        - name: location_id\n          in: query\n          type: string\n          required: false\n          description: Filter by location ID\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-orders\n      path: /truck-service/work-orders\n      description: Truck service work order management\n\
  \      operations:\n      - name: list-work-orders\n        method: GET\n        description: List truck service work orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        - name: location_id\n          in: query\n          type: string\n          required: false\n          description: Filter by service location\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /truck-service/documents\n      description: Truck service documentation search\n      operations:\n      - name: search-documents\n\
  \        method: GET\n        description: Search truck service documents including invoices and service records\n        inputParameters:\n        - name: work_order_id\n          in: query\n          type: string\n          required: false\n          description: Filter by work order ID\n        - name: vehicle_id\n          in: query\n          type: string\n          required: false\n          description: Filter by vehicle ID\n        - name: document_type\n          in: query\n          type: string\n          required: false\n          description: Filter by document type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fuel-codes\n      path: /fuel-codes\n      description: Fleet fuel code management\n      operations:\n      - name: list-fuel-codes\n        method: GET\n        description: List fuel codes for the fleet account\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: pricing\n      path: /pricing\n      description: Fuel and service pricing\n      operations:\n      - name: get-pricing\n        method: GET\n        description: Get current fuel pricing at travel center locations\n        inputParameters:\n        - name: location_id\n          in: query\n          type: string\n          required: false\n          description: Filter by location\n        - name: fuel_type\n          in: query\n          type: string\n          required: false\n          description: Filter by fuel type\n        - name: lat\n          in: query\n          type: number\n          required: false\n          description: Latitude for proximity search\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Longitude for proximity search\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fleet-driver-api\n    description: Unified REST API for fleet and driver services at TA/Petro travel centers.\n    resources:\n    - path: /v1/locations\n      name: locations\n      description: Travel center location discovery\n      operations:\n      - method: GET\n        name: list-locations\n        description: Find travel centers by proximity, brand, or state\n        call: ta.list-locations\n        with:\n          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n          brand: rest.brand\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parking\n      name: parking\n      description: Truck parking availability\n      operations:\n      - method: GET\n        name: get-parking-availability\n        description: Get real-time truck parking availability\n        call: ta.get-parking-availability\n\
  \        with:\n          location_id: rest.location_id\n          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/showers\n      name: showers\n      description: Shower facility availability\n      operations:\n      - method: GET\n        name: get-shower-availability\n        description: Get shower availability and wait times\n        call: ta.get-shower-availability\n        with:\n          location_id: rest.location_id\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fuel-pricing\n      name: fuel-pricing\n      description: Fuel prices at travel centers\n      operations:\n      - method: GET\n        name: get-pricing\n        description: Get current diesel, gasoline, and DEF pricing\n        call: ta.get-pricing\n        with:\n          location_id: rest.location_id\n   \
  \       fuel_type: rest.fuel_type\n          lat: rest.lat\n          lon: rest.lon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-orders\n      name: work-orders\n      description: Truck service work orders\n      operations:\n      - method: GET\n        name: list-work-orders\n        description: List truck service work orders\n        call: ta.list-work-orders\n        with:\n          status: rest.status\n          location_id: rest.location_id\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents\n      name: documents\n      description: Service documentation search\n      operations:\n      - method: GET\n        name: search-documents\n        description: Search service records, invoices, and maintenance documents\n        call: ta.search-documents\n        with:\n          work_order_id: rest.work_order_id\n\
  \          vehicle_id: rest.vehicle_id\n          document_type: rest.document_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fuel-codes\n      name: fuel-codes\n      description: Fleet fuel code management\n      operations:\n      - method: GET\n        name: list-fuel-codes\n        description: List fuel codes for the fleet\n        call: ta.list-fuel-codes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fleet-driver-mcp\n    transport: http\n    description: MCP server for AI-assisted fleet management and driver services at TA/Petro.\n    tools:\n    - name: find-travel-centers\n      description: Find TA, Petro, or TA Express travel centers near a location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ta.list-locations\n      with:\n        lat: tools.lat\n        lon: tools.lon\n        radius: tools.radius\n        brand: tools.brand\n\
  \        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-parking-availability\n      description: Check real-time truck parking availability at travel centers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ta.get-parking-availability\n      with:\n        location_id: tools.location_id\n        lat: tools.lat\n        lon: tools.lon\n        radius: tools.radius\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-shower-availability\n      description: Check shower facility availability and wait times at travel centers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ta.get-shower-availability\n      with:\n        location_id: tools.location_id\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-fuel-pricing\n      description: Get current diesel, gasoline, and\
  \ DEF pricing at travel centers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ta.get-pricing\n      with:\n        location_id: tools.location_id\n        fuel_type: tools.fuel_type\n        lat: tools.lat\n        lon: tools.lon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-work-orders\n      description: List truck service work orders for fleet vehicles\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ta.list-work-orders\n      with:\n        status: tools.status\n        location_id: tools.location_id\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-service-documents\n      description: Search truck service records, invoices, and maintenance documents\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ta.search-documents\n      with:\n        work_order_id:\
  \ tools.work_order_id\n        vehicle_id: tools.vehicle_id\n        document_type: tools.document_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fuel-codes\n      description: List fleet fuel authorization codes for TA/Petro locations\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ta.list-fuel-codes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
