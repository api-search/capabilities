---
categories: []
consumed_apis: []
description: Safety and compliance workflow combining Samsara safety events, driver coaching, Hours of Service (HOS/ELD) compliance logs, DVIR inspections, and maintenance tracking. Designed for safety managers and compliance officers to monitor driver behavior, enforce regulatory HOS requirements, and track vehicle inspection status.
layout: capability
name: Samsara Safety and Compliance
operations:
- description: List safety events for a time range
  method: GET
  name: list-safety-events
  path: /v1/safety-events
- description: List all DVIR inspection reports
  method: GET
  name: list-dvirs
  path: /v1/dvirs
- description: Submit a DVIR inspection report
  method: POST
  name: create-dvir
  path: /v1/dvirs
- description: List HOS logs for ELD compliance
  method: GET
  name: list-hos-logs
  path: /v1/hos-logs
personas: []
provider_name: Samsara
provider_slug: samsara
search_terms:
- driver vehicle inspection reports (dvir)
- logistics
- hours of service
- list hos logs for eld compliance
- inspection
- list safety events for a time range
- telematics
- eld
- gps tracking
- maintenance
- dvir
- iot
- list driver safety events including harsh braking, speeding, and camera events for a time range
- submit a driver vehicle inspection report (dvir) with defects
- compliance
- samsara
- fleet management
- asset tracking
- list safety events
- list dvirs
- transportation
- driver safety event monitoring and scoring
- hours of service eld compliance logs
- list hours of service eld logs for regulatory compliance reporting
- safety
- list all dvir vehicle inspection reports
- connected operations
- create dvir
- submit a dvir inspection report
- list all dvir inspection reports
- list hos logs
slug: safety-compliance
source_filename: safety-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Samsara Safety and Compliance\n  description: Safety and compliance workflow combining Samsara safety events, driver coaching, Hours of Service (HOS/ELD)\n    compliance logs, DVIR inspections, and maintenance tracking. Designed for safety managers and compliance officers to monitor\n    driver behavior, enforce regulatory HOS requirements, and track vehicle inspection status.\n  tags:\n  - Compliance\n  - DVIR\n  - ELD\n  - Hours Of Service\n  - Inspection\n  - Maintenance\n  - Safety\n  - Samsara\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAMSARA_API_TOKEN: SAMSARA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: samsara\n    baseUri: https://api.samsara.com\n    description: Samsara connected operations platform REST API\n    authentication:\n      type: bearer\n      token: '{{SAMSARA_API_TOKEN}}'\n    resources:\n    - name: addresses\n      path: /addresses\n    \
  \  description: Manage addresses and geofence locations in the organization\n      operations:\n      - name: list-addresses\n        method: GET\n        description: List All Addresses in the organization\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max objects returned (max 512)\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for next page of results\n        - name: tagIds\n          in: query\n          type: array\n          required: false\n          description: Filter by tag IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-address\n        method: POST\n        description: Create an Address in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            formattedAddress: '{{tools.formattedAddress}}'\n            geofence: '{{tools.geofence}}'\n      - name: get-address\n        method: GET\n        description: Retrieve an Address by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles\n      path: /fleet/vehicles\n      description: Manage and retrieve vehicle data and diagnostics\n      operations:\n      - name: list-vehicles\n        method: GET\n        description: List All Vehicles in the organization\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n\
  \          description: Max results returned\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: tagIds\n          in: query\n          type: array\n          required: false\n          description: Filter by tag IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vehicle\n        method: GET\n        description: Retrieve a Vehicle by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drivers\n      path: /fleet/drivers\n      description: Manage drivers and driver profiles\n      operations:\n      - name: list-drivers\n        method: GET\n       \
  \ description: List All Drivers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: driverActivationStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by activation status (active/deactivated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-driver\n        method: GET\n        description: Retrieve a Driver by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Driver ID or external ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-driver\n        method: POST\n        description: Create a Driver\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            username: '{{tools.username}}'\n            licenseNumber: '{{tools.licenseNumber}}'\n    - name: routes\n      path: /fleet/routes\n      description: Create and manage dispatch routes\n      operations:\n      - name: list-routes\n        method: GET\n        description: List All Routes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a Route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            driverId: '{{tools.driverId}}'\n            stops: '{{tools.stops}}'\n    - name: safety-events\n      path: /fleet/safety/events\n      description: Retrieve driver safety events and scores\n      operations:\n      - name: list-safety-events\n        method: GET\n        description: List Safety Events\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: true\n          description: Start time in RFC 3339 format\n        - name: endTime\n          in: query\n          type: string\n          required: true\n          description: End time in RFC 3339 format\n\
  \        - name: driverIds\n          in: query\n          type: array\n          required: false\n          description: Filter by driver IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dvirs\n      path: /fleet/maintenance/dvirs\n      description: Manage Driver Vehicle Inspection Reports (DVIRs)\n      operations:\n      - name: list-dvirs\n        method: GET\n        description: List All DVIRs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dvir\n        method: POST\n        description: Create a\
  \ DVIR\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            vehicleId: '{{tools.vehicleId}}'\n            inspectionType: '{{tools.inspectionType}}'\n            defects: '{{tools.defects}}'\n    - name: hos-logs\n      path: /fleet/hos/logs\n      description: Retrieve Hours of Service (HOS) ELD logs for compliance\n      operations:\n      - name: list-hos-logs\n        method: GET\n        description: List HOS Logs for ELD Compliance\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: true\n          description: Start time RFC 3339\n        - name: endTime\n          in: query\n          type: string\n          required: true\n          description: End time RFC 3339\n        - name: driverIds\n          in: query\n          type: array\n          required: false\n          description:\
  \ Filter by driver IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-locations\n      path: /fleet/vehicles/locations\n      description: Retrieve real-time and historical vehicle GPS locations\n      operations:\n      - name: get-vehicle-locations\n        method: GET\n        description: Get Vehicle Locations Feed\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: vehicleIds\n          in: query\n          type: array\n          required: false\n          description: Filter by vehicle IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      description: Manage non-powered assets such as trailers and equipment\n      operations:\n    \
  \  - name: list-assets\n        method: GET\n        description: List All Assets\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Manage organizational tags for grouping vehicles, drivers, and assets\n      operations:\n      - name: list-tags\n        method: GET\n        description: List All Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag\n        method: POST\n        description: Create a Tag\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: webhooks\n      path: /webhooks\n      description: Manage webhook subscriptions for real-time event notifications\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List All Webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a Webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n            eventTypes: '{{tools.eventTypes}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: safety-compliance-api\n   \
  \ description: Unified REST API for driver safety monitoring and regulatory compliance.\n    resources:\n    - path: /v1/safety-events\n      name: safety-events\n      description: Driver safety event monitoring and scoring\n      operations:\n      - method: GET\n        name: list-safety-events\n        description: List safety events for a time range\n        call: samsara.list-safety-events\n        with:\n          startTime: rest.startTime\n          endTime: rest.endTime\n          driverIds: rest.driverIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dvirs\n      name: dvirs\n      description: Driver Vehicle Inspection Reports (DVIR)\n      operations:\n      - method: GET\n        name: list-dvirs\n        description: List all DVIR inspection reports\n        call: samsara.list-dvirs\n        with:\n          limit: rest.limit\n          after: rest.after\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: POST\n        name: create-dvir\n        description: Submit a DVIR inspection report\n        call: samsara.create-dvir\n        with:\n          vehicleId: rest.vehicleId\n          inspectionType: rest.inspectionType\n          defects: rest.defects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hos-logs\n      name: hos-logs\n      description: Hours of Service ELD compliance logs\n      operations:\n      - method: GET\n        name: list-hos-logs\n        description: List HOS logs for ELD compliance\n        call: samsara.list-hos-logs\n        with:\n          startTime: rest.startTime\n          endTime: rest.endTime\n          driverIds: rest.driverIds\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: safety-compliance-mcp\n    transport: http\n    description: MCP server for AI-assisted safety analysis and compliance monitoring.\n    tools:\n  \
  \  - name: list-safety-events\n      description: List driver safety events including harsh braking, speeding, and camera events for a time range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: samsara.list-safety-events\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        driverIds: tools.driverIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dvirs\n      description: List all DVIR vehicle inspection reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-dvirs\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dvir\n      description: Submit a Driver Vehicle Inspection Report (DVIR) with defects\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: samsara.create-dvir\n      with:\n\
  \        vehicleId: tools.vehicleId\n        inspectionType: tools.inspectionType\n        defects: tools.defects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hos-logs\n      description: List Hours of Service ELD logs for regulatory compliance reporting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: samsara.list-hos-logs\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        driverIds: tools.driverIds\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/samsara/refs/heads/main/capabilities/safety-compliance.yaml
tags:
- Compliance
- DVIR
- ELD
- Hours Of Service
- Inspection
- Maintenance
- Safety
- Samsara
tools:
- description: List driver safety events including harsh braking, speeding, and camera events for a time range
  hints:
    openWorld: false
    readOnly: true
  name: list-safety-events
- description: List all DVIR vehicle inspection reports
  hints:
    openWorld: true
    readOnly: true
  name: list-dvirs
- description: Submit a Driver Vehicle Inspection Report (DVIR) with defects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dvir
- description: List Hours of Service ELD logs for regulatory compliance reporting
  hints:
    openWorld: false
    readOnly: true
  name: list-hos-logs
---
