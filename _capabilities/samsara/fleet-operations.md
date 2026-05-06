---
categories: []
consumed_apis: []
description: 'Unified fleet operations capability composing Samsara vehicle, driver, route, address, tag, and asset management APIs into a single workflow surface for fleet managers and dispatchers. Supports full fleet lifecycle: vehicle tracking, driver assignment, route dispatch, asset management, and organizational tagging.'
layout: capability
name: Samsara Fleet Operations
operations:
- description: List all vehicles in the fleet
  method: GET
  name: list-vehicles
  path: /v1/vehicles
- description: Get a specific vehicle by ID
  method: GET
  name: get-vehicle
  path: /v1/vehicles/{id}
- description: Get vehicle locations feed
  method: GET
  name: get-vehicle-locations
  path: /v1/vehicle-locations
- description: List all drivers
  method: GET
  name: list-drivers
  path: /v1/drivers
- description: Create a new driver
  method: POST
  name: create-driver
  path: /v1/drivers
- description: Get a specific driver by ID
  method: GET
  name: get-driver
  path: /v1/drivers/{id}
- description: List all dispatch routes
  method: GET
  name: list-routes
  path: /v1/routes
- description: Create a new dispatch route
  method: POST
  name: create-route
  path: /v1/routes
- description: List all tracked assets
  method: GET
  name: list-assets
  path: /v1/assets
- description: List all addresses and geofences
  method: GET
  name: list-addresses
  path: /v1/addresses
- description: Create an address with geofence
  method: POST
  name: create-address
  path: /v1/addresses
- description: List all tags
  method: GET
  name: list-tags
  path: /v1/tags
- description: Create an organizational tag
  method: POST
  name: create-tag
  path: /v1/tags
- description: List all webhook subscriptions
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Subscribe to fleet event webhooks
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Samsara
provider_slug: samsara
search_terms:
- create a new driver
- list all addresses and geofence locations
- create driver
- logistics
- get a specific vehicle by id
- individual driver details
- create a new driver profile in the organization
- vehicle fleet inventory and management
- real-time and historical vehicle gps locations
- list all webhook subscriptions
- get a specific driver by id
- telematics
- eld
- individual vehicle details
- list all drivers
- gps tracking
- get vehicle locations feed
- create a new dispatch route
- create webhook
- create a new dispatch route with stops for a driver
- list all non-powered assets (trailers, equipment)
- iot
- driver profile management
- samsara
- fleet management
- create route
- get driver
- create an organizational tag
- asset tracking
- create tag
- transportation
- non-powered asset tracking (trailers, equipment)
- get details for a specific driver by id
- dispatch route planning and tracking
- list routes
- create address
- get details for a specific vehicle by id
- get real-time gps locations for fleet vehicles
- create an address with geofence
- list all vehicles in the fleet, optionally filtered by tag
- list tags
- dispatch
- list all tags
- list all addresses and geofences
- list assets
- safety
- list all dispatch routes
- list vehicles
- list all vehicles in the fleet
- organizational tags for fleet grouping
- driver management
- gps
- list addresses
- create a new address with geofence for fleet operations
- location and geofence management
- connected operations
- event webhook subscription management
- list drivers
- list webhooks
- list all tracked assets
- asset management
- get vehicle
- routes
- subscribe to fleet event webhooks
- list all drivers in the organization
- get vehicle locations
slug: fleet-operations
source_filename: fleet-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Samsara Fleet Operations\n  description: 'Unified fleet operations capability composing Samsara vehicle, driver, route, address, tag, and asset management\n    APIs into a single workflow surface for fleet managers and dispatchers. Supports full fleet lifecycle: vehicle tracking,\n    driver assignment, route dispatch, asset management, and organizational tagging.'\n  tags:\n  - Asset Management\n  - Dispatch\n  - Driver Management\n  - Fleet Management\n  - GPS\n  - Routes\n  - Samsara\n  - Telematics\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAMSARA_API_TOKEN: SAMSARA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: samsara\n    baseUri: https://api.samsara.com\n    description: Samsara connected operations platform REST API\n    authentication:\n      type: bearer\n      token: '{{SAMSARA_API_TOKEN}}'\n    resources:\n    - name: addresses\n      path: /addresses\n\
  \      description: Manage addresses and geofence locations in the organization\n      operations:\n      - name: list-addresses\n        method: GET\n        description: List All Addresses in the organization\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max objects returned (max 512)\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor for next page of results\n        - name: tagIds\n          in: query\n          type: array\n          required: false\n          description: Filter by tag IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-address\n        method: POST\n        description: Create an Address in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            formattedAddress: '{{tools.formattedAddress}}'\n            geofence: '{{tools.geofence}}'\n      - name: get-address\n        method: GET\n        description: Retrieve an Address by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles\n      path: /fleet/vehicles\n      description: Manage and retrieve vehicle data and diagnostics\n      operations:\n      - name: list-vehicles\n        method: GET\n        description: List All Vehicles in the organization\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Max results returned\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: tagIds\n          in: query\n          type: array\n          required: false\n          description: Filter by tag IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vehicle\n        method: GET\n        description: Retrieve a Vehicle by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Vehicle ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drivers\n      path: /fleet/drivers\n      description: Manage drivers and driver profiles\n      operations:\n      - name: list-drivers\n        method: GET\n\
  \        description: List All Drivers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: driverActivationStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by activation status (active/deactivated)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-driver\n        method: GET\n        description: Retrieve a Driver by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Driver ID or external ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-driver\n        method: POST\n        description: Create a Driver\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            username: '{{tools.username}}'\n            licenseNumber: '{{tools.licenseNumber}}'\n    - name: routes\n      path: /fleet/routes\n      description: Create and manage dispatch routes\n      operations:\n      - name: list-routes\n        method: GET\n        description: List All Routes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: create-route\n        method: POST\n        description: Create a Route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            driverId: '{{tools.driverId}}'\n            stops: '{{tools.stops}}'\n    - name: safety-events\n      path: /fleet/safety/events\n      description: Retrieve driver safety events and scores\n      operations:\n      - name: list-safety-events\n        method: GET\n        description: List Safety Events\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: true\n          description: Start time in RFC 3339 format\n        - name: endTime\n          in: query\n          type: string\n          required: true\n          description: End time in RFC\
  \ 3339 format\n        - name: driverIds\n          in: query\n          type: array\n          required: false\n          description: Filter by driver IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dvirs\n      path: /fleet/maintenance/dvirs\n      description: Manage Driver Vehicle Inspection Reports (DVIRs)\n      operations:\n      - name: list-dvirs\n        method: GET\n        description: List All DVIRs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dvir\n        method: POST\n        description:\
  \ Create a DVIR\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            vehicleId: '{{tools.vehicleId}}'\n            inspectionType: '{{tools.inspectionType}}'\n            defects: '{{tools.defects}}'\n    - name: hos-logs\n      path: /fleet/hos/logs\n      description: Retrieve Hours of Service (HOS) ELD logs for compliance\n      operations:\n      - name: list-hos-logs\n        method: GET\n        description: List HOS Logs for ELD Compliance\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: true\n          description: Start time RFC 3339\n        - name: endTime\n          in: query\n          type: string\n          required: true\n          description: End time RFC 3339\n        - name: driverIds\n          in: query\n          type: array\n          required: false\n  \
  \        description: Filter by driver IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-locations\n      path: /fleet/vehicles/locations\n      description: Retrieve real-time and historical vehicle GPS locations\n      operations:\n      - name: get-vehicle-locations\n        method: GET\n        description: Get Vehicle Locations Feed\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: vehicleIds\n          in: query\n          type: array\n          required: false\n          description: Filter by vehicle IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      description: Manage non-powered assets such as trailers and equipment\n   \
  \   operations:\n      - name: list-assets\n        method: GET\n        description: List All Assets\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      description: Manage organizational tags for grouping vehicles, drivers, and assets\n      operations:\n      - name: list-tags\n        method: GET\n        description: List All Tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-tag\n        method: POST\n        description: Create a Tag\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: webhooks\n      path: /webhooks\n      description: Manage webhook subscriptions for real-time event notifications\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List All Webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a Webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            url: '{{tools.url}}'\n            eventTypes: '{{tools.eventTypes}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fleet-operations-api\n\
  \    description: Unified REST API for Samsara fleet operations management.\n    resources:\n    - path: /v1/vehicles\n      name: vehicles\n      description: Vehicle fleet inventory and management\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: List all vehicles in the fleet\n        call: samsara.list-vehicles\n        with:\n          limit: rest.limit\n          after: rest.after\n          tagIds: rest.tagIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicles/{id}\n      name: vehicle\n      description: Individual vehicle details\n      operations:\n      - method: GET\n        name: get-vehicle\n        description: Get a specific vehicle by ID\n        call: samsara.get-vehicle\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vehicle-locations\n      name: vehicle-locations\n      description: Real-time and\
  \ historical vehicle GPS locations\n      operations:\n      - method: GET\n        name: get-vehicle-locations\n        description: Get vehicle locations feed\n        call: samsara.get-vehicle-locations\n        with:\n          after: rest.after\n          vehicleIds: rest.vehicleIds\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/drivers\n      name: drivers\n      description: Driver profile management\n      operations:\n      - method: GET\n        name: list-drivers\n        description: List all drivers\n        call: samsara.list-drivers\n        with:\n          limit: rest.limit\n          after: rest.after\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-driver\n        description: Create a new driver\n        call: samsara.create-driver\n        with:\n          name: rest.name\n          username: rest.username\n          licenseNumber: rest.licenseNumber\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/drivers/{id}\n      name: driver\n      description: Individual driver details\n      operations:\n      - method: GET\n        name: get-driver\n        description: Get a specific driver by ID\n        call: samsara.get-driver\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/routes\n      name: routes\n      description: Dispatch route planning and tracking\n      operations:\n      - method: GET\n        name: list-routes\n        description: List all dispatch routes\n        call: samsara.list-routes\n        with:\n          limit: rest.limit\n          after: rest.after\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-route\n        description: Create a new dispatch route\n        call: samsara.create-route\n        with:\n          name: rest.name\n\
  \          driverId: rest.driverId\n          stops: rest.stops\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Non-powered asset tracking (trailers, equipment)\n      operations:\n      - method: GET\n        name: list-assets\n        description: List all tracked assets\n        call: samsara.list-assets\n        with:\n          limit: rest.limit\n          after: rest.after\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses\n      name: addresses\n      description: Location and geofence management\n      operations:\n      - method: GET\n        name: list-addresses\n        description: List all addresses and geofences\n        call: samsara.list-addresses\n        with:\n          limit: rest.limit\n          after: rest.after\n          tagIds: rest.tagIds\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-address\n        description: Create an address with geofence\n        call: samsara.create-address\n        with:\n          name: rest.name\n          formattedAddress: rest.formattedAddress\n          geofence: rest.geofence\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tags\n      description: Organizational tags for fleet grouping\n      operations:\n      - method: GET\n        name: list-tags\n        description: List all tags\n        call: samsara.list-tags\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-tag\n        description: Create an organizational tag\n        call: samsara.create-tag\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Event webhook subscription management\n     \
  \ operations:\n      - method: GET\n        name: list-webhooks\n        description: List all webhook subscriptions\n        call: samsara.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Subscribe to fleet event webhooks\n        call: samsara.create-webhook\n        with:\n          name: rest.name\n          url: rest.url\n          eventTypes: rest.eventTypes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: fleet-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted fleet operations and dispatch management.\n    tools:\n    - name: list-vehicles\n      description: List all vehicles in the fleet, optionally filtered by tag\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-vehicles\n      with:\n        limit: tools.limit\n        after:\
  \ tools.after\n        tagIds: tools.tagIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle\n      description: Get details for a specific vehicle by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: samsara.get-vehicle\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vehicle-locations\n      description: Get real-time GPS locations for fleet vehicles\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.get-vehicle-locations\n      with:\n        after: tools.after\n        vehicleIds: tools.vehicleIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-drivers\n      description: List all drivers in the organization\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-drivers\n      with:\n        limit: tools.limit\n        after: tools.after\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-driver\n      description: Get details for a specific driver by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: samsara.get-driver\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-driver\n      description: Create a new driver profile in the organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: samsara.create-driver\n      with:\n        name: tools.name\n        username: tools.username\n        licenseNumber: tools.licenseNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-routes\n      description: List all dispatch routes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-routes\n      with:\n        limit: tools.limit\n        after: tools.after\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-route\n      description: Create a new dispatch route with stops for a driver\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: samsara.create-route\n      with:\n        name: tools.name\n        driverId: tools.driverId\n        stops: tools.stops\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List all non-powered assets (trailers, equipment)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-assets\n      with:\n        limit: tools.limit\n        after: tools.after\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-addresses\n      description: List all addresses and geofence locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: samsara.list-addresses\n      with:\n        limit:\
  \ tools.limit\n        after: tools.after\n        tagIds: tools.tagIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-address\n      description: Create a new address with geofence for fleet operations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: samsara.create-address\n      with:\n        name: tools.name\n        formattedAddress: tools.formattedAddress\n        geofence: tools.geofence\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/samsara/refs/heads/main/capabilities/fleet-operations.yaml
tags:
- Asset Management
- Dispatch
- Driver Management
- Fleet Management
- GPS
- Routes
- Samsara
- Telematics
tools:
- description: List all vehicles in the fleet, optionally filtered by tag
  hints:
    openWorld: true
    readOnly: true
  name: list-vehicles
- description: Get details for a specific vehicle by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-vehicle
- description: Get real-time GPS locations for fleet vehicles
  hints:
    openWorld: true
    readOnly: true
  name: get-vehicle-locations
- description: List all drivers in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-drivers
- description: Get details for a specific driver by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-driver
- description: Create a new driver profile in the organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-driver
- description: List all dispatch routes
  hints:
    openWorld: true
    readOnly: true
  name: list-routes
- description: Create a new dispatch route with stops for a driver
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-route
- description: List all non-powered assets (trailers, equipment)
  hints:
    openWorld: true
    readOnly: true
  name: list-assets
- description: List all addresses and geofence locations
  hints:
    openWorld: true
    readOnly: true
  name: list-addresses
- description: Create a new address with geofence for fleet operations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-address
---
