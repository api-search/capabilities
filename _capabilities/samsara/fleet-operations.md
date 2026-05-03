---
api_specs:
- filename: samsara-openapi.yml
  format: yaml
  label: samsara
  slug: samsara
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/samsara/refs/heads/main/openapi/samsara-openapi.yml
categories: []
consumed_apis:
- samsara
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
- non-powered asset tracking (trailers, equipment)
- list all addresses and geofences
- list drivers
- create webhook
- create driver
- list tags
- organizational tags for fleet grouping
- get details for a specific driver by id
- list all drivers
- create a new dispatch route
- create a new dispatch route with stops for a driver
- create tag
- get details for a specific vehicle by id
- telematics
- list addresses
- create a new driver profile in the organization
- logistics
- samsara
- individual driver details
- connected operations
- asset tracking
- iot
- real-time and historical vehicle gps locations
- list all addresses and geofence locations
- list all tags
- gps tracking
- list all webhook subscriptions
- list all non-powered assets (trailers, equipment)
- get a specific driver by id
- list all vehicles in the fleet
- eld
- asset management
- list all dispatch routes
- get a specific vehicle by id
- get driver
- list all drivers in the organization
- transportation
- list all vehicles in the fleet, optionally filtered by tag
- list vehicles
- create route
- create address
- create a new address with geofence for fleet operations
- dispatch route planning and tracking
- list routes
- location and geofence management
- create a new driver
- list webhooks
- safety
- driver profile management
- get vehicle locations
- subscribe to fleet event webhooks
- routes
- fleet management
- get vehicle
- dispatch
- get vehicle locations feed
- list assets
- list all tracked assets
- gps
- get real-time gps locations for fleet vehicles
- driver management
- create an organizational tag
- vehicle fleet inventory and management
- individual vehicle details
- create an address with geofence
- event webhook subscription management
slug: fleet-operations
source_filename: fleet-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Samsara Fleet Operations\"\n  description: >-\n    Unified fleet operations capability composing Samsara vehicle, driver, route, address,\n    tag, and asset management APIs into a single workflow surface for fleet managers and\n    dispatchers. Supports full fleet lifecycle: vehicle tracking, driver assignment, route\n    dispatch, asset management, and organizational tagging.\n  tags:\n    - Asset Management\n    - Dispatch\n    - Driver Management\n    - Fleet Management\n    - GPS\n    - Routes\n    - Samsara\n    - Telematics\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAMSARA_API_TOKEN: SAMSARA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: samsara\n      location: ./shared/samsara.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: fleet-operations-api\n      description: \"Unified REST API for Samsara fleet operations management.\"\n \
  \     resources:\n        - path: /v1/vehicles\n          name: vehicles\n          description: \"Vehicle fleet inventory and management\"\n          operations:\n            - method: GET\n              name: list-vehicles\n              description: \"List all vehicles in the fleet\"\n              call: \"samsara.list-vehicles\"\n              with:\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                tagIds: \"rest.tagIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vehicles/{id}\n          name: vehicle\n          description: \"Individual vehicle details\"\n          operations:\n            - method: GET\n              name: get-vehicle\n              description: \"Get a specific vehicle by ID\"\n              call: \"samsara.get-vehicle\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/vehicle-locations\n          name: vehicle-locations\n          description: \"Real-time and historical vehicle GPS locations\"\n          operations:\n            - method: GET\n              name: get-vehicle-locations\n              description: \"Get vehicle locations feed\"\n              call: \"samsara.get-vehicle-locations\"\n              with:\n                after: \"rest.after\"\n                vehicleIds: \"rest.vehicleIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/drivers\n          name: drivers\n          description: \"Driver profile management\"\n          operations:\n            - method: GET\n              name: list-drivers\n              description: \"List all drivers\"\n              call: \"samsara.list-drivers\"\n              with:\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-driver\n              description: \"Create a new driver\"\n              call: \"samsara.create-driver\"\n              with:\n                name: \"rest.name\"\n                username: \"rest.username\"\n                licenseNumber: \"rest.licenseNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/drivers/{id}\n          name: driver\n          description: \"Individual driver details\"\n          operations:\n            - method: GET\n              name: get-driver\n              description: \"Get a specific driver by ID\"\n              call: \"samsara.get-driver\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/routes\n          name:\
  \ routes\n          description: \"Dispatch route planning and tracking\"\n          operations:\n            - method: GET\n              name: list-routes\n              description: \"List all dispatch routes\"\n              call: \"samsara.list-routes\"\n              with:\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-route\n              description: \"Create a new dispatch route\"\n              call: \"samsara.create-route\"\n              with:\n                name: \"rest.name\"\n                driverId: \"rest.driverId\"\n                stops: \"rest.stops\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Non-powered asset tracking (trailers, equipment)\"\n \
  \         operations:\n            - method: GET\n              name: list-assets\n              description: \"List all tracked assets\"\n              call: \"samsara.list-assets\"\n              with:\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/addresses\n          name: addresses\n          description: \"Location and geofence management\"\n          operations:\n            - method: GET\n              name: list-addresses\n              description: \"List all addresses and geofences\"\n              call: \"samsara.list-addresses\"\n              with:\n                limit: \"rest.limit\"\n                after: \"rest.after\"\n                tagIds: \"rest.tagIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-address\n\
  \              description: \"Create an address with geofence\"\n              call: \"samsara.create-address\"\n              with:\n                name: \"rest.name\"\n                formattedAddress: \"rest.formattedAddress\"\n                geofence: \"rest.geofence\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tags\n          name: tags\n          description: \"Organizational tags for fleet grouping\"\n          operations:\n            - method: GET\n              name: list-tags\n              description: \"List all tags\"\n              call: \"samsara.list-tags\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-tag\n              description: \"Create an organizational tag\"\n              call: \"samsara.create-tag\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Event webhook subscription management\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List all webhook subscriptions\"\n              call: \"samsara.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Subscribe to fleet event webhooks\"\n              call: \"samsara.create-webhook\"\n              with:\n                name: \"rest.name\"\n                url: \"rest.url\"\n                eventTypes: \"rest.eventTypes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: fleet-operations-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted fleet operations and dispatch management.\"\n      tools:\n        - name: list-vehicles\n          description: \"List all vehicles in the fleet, optionally filtered by tag\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"samsara.list-vehicles\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            tagIds: \"tools.tagIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle\n          description: \"Get details for a specific vehicle by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"samsara.get-vehicle\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-vehicle-locations\n          description: \"Get real-time GPS locations\
  \ for fleet vehicles\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"samsara.get-vehicle-locations\"\n          with:\n            after: \"tools.after\"\n            vehicleIds: \"tools.vehicleIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-drivers\n          description: \"List all drivers in the organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"samsara.list-drivers\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-driver\n          description: \"Get details for a specific driver by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"samsara.get-driver\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-driver\n          description: \"Create a new driver profile in the organization\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"samsara.create-driver\"\n          with:\n            name: \"tools.name\"\n            username: \"tools.username\"\n            licenseNumber: \"tools.licenseNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routes\n          description: \"List all dispatch routes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"samsara.list-routes\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-route\n          description: \"Create a new dispatch\
  \ route with stops for a driver\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"samsara.create-route\"\n          with:\n            name: \"tools.name\"\n            driverId: \"tools.driverId\"\n            stops: \"tools.stops\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List all non-powered assets (trailers, equipment)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"samsara.list-assets\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-addresses\n          description: \"List all addresses and geofence locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  samsara.list-addresses\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n            tagIds: \"tools.tagIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-address\n          description: \"Create a new address with geofence for fleet operations\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"samsara.create-address\"\n          with:\n            name: \"tools.name\"\n            formattedAddress: \"tools.formattedAddress\"\n            geofence: \"tools.geofence\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
