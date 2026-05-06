---
categories: []
consumed_apis: []
description: The CargoSmart Shipment Tracking API provides real-time container tracking and shipment visibility across ocean carriers and ports. APIs return container movement events, vessel positions, ETA predictions, and port arrival/departure data for supply chain visibility platforms.
layout: capability
name: CargoSmart Shipment Tracking API
operations:
- description: Track container
  method: GET
  name: trackcontainer
  path: /tracking/v1/containers/{containerId}
- description: Track multiple containers
  method: GET
  name: listcontainertracking
  path: /tracking/v1/containers
- description: Get shipment by bill of lading
  method: GET
  name: getshipment
  path: /tracking/v1/shipments/{billOfLadingNumber}
- description: Search vessel schedules
  method: GET
  name: searchvesselschedules
  path: /vessels/v1/schedules
- description: Get vessel position
  method: GET
  name: getvesselposition
  path: /vessels/v1/{vesselIMO}/position
- description: Create container booking
  method: POST
  name: createbooking
  path: /bookings/v1
- description: List bookings
  method: GET
  name: listbookings
  path: /bookings/v1
- description: Get bill of lading
  method: GET
  name: getbilloflading
  path: /documents/v1/bills-of-lading/{blNumber}
personas: []
provider_name: CargoSmart
provider_slug: cargosmart
search_terms:
- logistics
- get bill of lading
- create container booking
- vessel
- container
- searchvesselschedules
- get shipment by bill of lading
- trackcontainer
- maritime
- ocean freight
- visibility
- createbooking
- track multiple containers
- documentation
- iqax
- supply chain
- listbookings
- search vessel schedules
- shipping
- listcontainertracking
- api
- booking
- schedule
- track container
- getshipment
- list bookings
- getbilloflading
- cargosmart
- gsbn
- get vessel position
- tracking
- getvesselposition
slug: cargosmart-capability
source_filename: cargosmart-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CargoSmart Shipment Tracking API\n  description: The CargoSmart Shipment Tracking API provides real-time container tracking and shipment visibility across ocean\n    carriers and ports. APIs return container movement events, vessel positions, ETA predictions, and port arrival/departure\n    data for supply chain visibility platforms.\n  tags:\n  - Cargosmart\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cargosmart\n    baseUri: https://api.cargosmart.com\n    description: CargoSmart Shipment Tracking API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{CARGOSMART_TOKEN}}'\n    resources:\n    - name: tracking-v1-containers-containerid\n      path: /tracking/v1/containers/{containerId}\n      operations:\n      - name: trackcontainer\n        method: GET\n        description: Track container\n        inputParameters:\n\
  \        - name: containerId\n          in: path\n          type: string\n          required: true\n          description: Container number (e.g., MSCU1234567)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracking-v1-containers\n      path: /tracking/v1/containers\n      operations:\n      - name: listcontainertracking\n        method: GET\n        description: Track multiple containers\n        inputParameters:\n        - name: containerIds\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of container numbers\n        - name: billOfLadingNumber\n          in: query\n          type: string\n          description: Filter by bill of lading number\n        - name: bookingNumber\n          in: query\n          type: string\n          description: Filter by booking number\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: tracking-v1-shipments-billofladingnumber\n      path: /tracking/v1/shipments/{billOfLadingNumber}\n      operations:\n      - name: getshipment\n        method: GET\n        description: Get shipment by bill of lading\n        inputParameters:\n        - name: billOfLadingNumber\n          in: path\n          type: string\n          required: true\n          description: Bill of lading number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessels-v1-schedules\n      path: /vessels/v1/schedules\n      operations:\n      - name: searchvesselschedules\n        method: GET\n        description: Search vessel schedules\n        inputParameters:\n        - name: originPort\n          in: query\n          type: string\n          description: Origin port UN/LOCODE (e.g., USNYC)\n        - name: destinationPort\n         \
  \ in: query\n          type: string\n          description: Destination port UN/LOCODE\n        - name: carrierId\n          in: query\n          type: string\n          description: Carrier SCAC code\n        - name: departureFrom\n          in: query\n          type: string\n        - name: departureTo\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessels-v1-vesselimo-position\n      path: /vessels/v1/{vesselIMO}/position\n      operations:\n      - name: getvesselposition\n        method: GET\n        description: Get vessel position\n        inputParameters:\n        - name: vesselIMO\n          in: path\n          type: string\n          required: true\n          description: IMO vessel number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: bookings-v1\n      path: /bookings/v1\n      operations:\n      - name: createbooking\n        method: POST\n        description: Create container booking\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listbookings\n        method: GET\n        description: List bookings\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: carrierId\n          in: query\n          type: string\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-v1-bills-of-lading-blnumber\n      path: /documents/v1/bills-of-lading/{blNumber}\n      operations:\n      - name: getbilloflading\n\
  \        method: GET\n        description: Get bill of lading\n        inputParameters:\n        - name: blNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cargosmart-rest\n    description: REST adapter for CargoSmart Shipment Tracking API.\n    resources:\n    - path: /tracking/v1/containers/{containerId}\n      name: trackcontainer\n      operations:\n      - method: GET\n        name: trackcontainer\n        description: Track container\n        call: cargosmart.trackcontainer\n        with:\n          containerId: rest.containerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/v1/containers\n      name: listcontainertracking\n      operations:\n      - method: GET\n        name: listcontainertracking\n        description:\
  \ Track multiple containers\n        call: cargosmart.listcontainertracking\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tracking/v1/shipments/{billOfLadingNumber}\n      name: getshipment\n      operations:\n      - method: GET\n        name: getshipment\n        description: Get shipment by bill of lading\n        call: cargosmart.getshipment\n        with:\n          billOfLadingNumber: rest.billOfLadingNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessels/v1/schedules\n      name: searchvesselschedules\n      operations:\n      - method: GET\n        name: searchvesselschedules\n        description: Search vessel schedules\n        call: cargosmart.searchvesselschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vessels/v1/{vesselIMO}/position\n      name: getvesselposition\n      operations:\n      - method: GET\n        name: getvesselposition\n\
  \        description: Get vessel position\n        call: cargosmart.getvesselposition\n        with:\n          vesselIMO: rest.vesselIMO\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/v1\n      name: createbooking\n      operations:\n      - method: POST\n        name: createbooking\n        description: Create container booking\n        call: cargosmart.createbooking\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bookings/v1\n      name: listbookings\n      operations:\n      - method: GET\n        name: listbookings\n        description: List bookings\n        call: cargosmart.listbookings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /documents/v1/bills-of-lading/{blNumber}\n      name: getbilloflading\n      operations:\n      - method: GET\n        name: getbilloflading\n        description: Get bill of lading\n        call: cargosmart.getbilloflading\n\
  \        with:\n          blNumber: rest.blNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cargosmart-mcp\n    transport: http\n    description: MCP adapter for CargoSmart Shipment Tracking API for AI agent use.\n    tools:\n    - name: trackcontainer\n      description: Track container\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.trackcontainer\n      with:\n        containerId: tools.containerId\n      inputParameters:\n      - name: containerId\n        type: string\n        description: Container number (e.g., MSCU1234567)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontainertracking\n      description: Track multiple containers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.listcontainertracking\n   \
  \   with:\n        containerIds: tools.containerIds\n        billOfLadingNumber: tools.billOfLadingNumber\n        bookingNumber: tools.bookingNumber\n      inputParameters:\n      - name: containerIds\n        type: string\n        description: Comma-separated list of container numbers\n        required: true\n      - name: billOfLadingNumber\n        type: string\n        description: Filter by bill of lading number\n      - name: bookingNumber\n        type: string\n        description: Filter by booking number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshipment\n      description: Get shipment by bill of lading\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.getshipment\n      with:\n        billOfLadingNumber: tools.billOfLadingNumber\n      inputParameters:\n      - name: billOfLadingNumber\n        type: string\n        description: Bill of lading number\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchvesselschedules\n      description: Search vessel schedules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.searchvesselschedules\n      with:\n        originPort: tools.originPort\n        destinationPort: tools.destinationPort\n        carrierId: tools.carrierId\n        departureFrom: tools.departureFrom\n        departureTo: tools.departureTo\n        limit: tools.limit\n      inputParameters:\n      - name: originPort\n        type: string\n        description: Origin port UN/LOCODE (e.g., USNYC)\n      - name: destinationPort\n        type: string\n        description: Destination port UN/LOCODE\n      - name: carrierId\n        type: string\n        description: Carrier SCAC code\n      - name: departureFrom\n        type: string\n        description: departureFrom\n      - name: departureTo\n        type: string\n    \
  \    description: departureTo\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvesselposition\n      description: Get vessel position\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.getvesselposition\n      with:\n        vesselIMO: tools.vesselIMO\n      inputParameters:\n      - name: vesselIMO\n        type: string\n        description: IMO vessel number\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbooking\n      description: Create container booking\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cargosmart.createbooking\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbookings\n      description: List bookings\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: cargosmart.listbookings\n      with:\n        status: tools.status\n        carrierId: tools.carrierId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: carrierId\n        type: string\n        description: carrierId\n      - name: fromDate\n        type: string\n        description: fromDate\n      - name: toDate\n        type: string\n        description: toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbilloflading\n      description: Get bill of lading\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cargosmart.getbilloflading\n      with:\n        blNumber: tools.blNumber\n      inputParameters:\n      - name: blNumber\n        type: string\n        description: blNumber\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CARGOSMART_TOKEN: CARGOSMART_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cargosmart/refs/heads/main/capabilities/cargosmart-capability.yaml
tags:
- Cargosmart
- API
tools:
- description: Track container
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: trackcontainer
- description: Track multiple containers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontainertracking
- description: Get shipment by bill of lading
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipment
- description: Search vessel schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchvesselschedules
- description: Get vessel position
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvesselposition
- description: Create container booking
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbooking
- description: List bookings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbookings
- description: Get bill of lading
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbilloflading
---
