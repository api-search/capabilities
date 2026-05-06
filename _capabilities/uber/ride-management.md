---
categories: []
consumed_apis: []
description: Workflow capability for managing the complete Uber ride lifecycle. Combines the Riders API (ride requests, estimates, products) and Drivers API (driver profile, trips, payments) to support ride-booking applications, fleet management dashboards, and driver analytics tools.
layout: capability
name: Uber Ride Management
operations:
- description: List Uber products available at a given location.
  method: GET
  name: list-products
  path: /v1/products
- description: Get price estimates for available products between two points.
  method: GET
  name: get-price-estimates
  path: /v1/estimates/price
- description: Get arrival time estimates for available products.
  method: GET
  name: get-time-estimates
  path: /v1/estimates/time
- description: Request a ride for an authenticated Uber user.
  method: POST
  name: create-ride-request
  path: /v1/ride-requests
- description: Get real-time status of a ride request.
  method: GET
  name: get-ride-request
  path: /v1/ride-requests/{request_id}
- description: Cancel an active ride request.
  method: DELETE
  name: cancel-ride-request
  path: /v1/ride-requests/{request_id}
- description: Get the authenticated rider's Uber profile.
  method: GET
  name: get-rider-profile
  path: /v1/riders/profile
- description: Get the rider's trip history.
  method: GET
  name: get-ride-history
  path: /v1/riders/history
- description: Get the authenticated driver partner's profile.
  method: GET
  name: get-driver-profile
  path: /v1/drivers/profile
- description: Get payment history for the driver partner.
  method: GET
  name: get-driver-payments
  path: /v1/drivers/payments
- description: Get trip history for the driver partner.
  method: GET
  name: get-driver-trips
  path: /v1/drivers/trips
personas: []
provider_name: Uber
provider_slug: uber
search_terms:
- list uber products
- driver trip history.
- logistics
- get rider history
- create ride request
- get price estimates for uber rides between two locations.
- get driver profile
- get rider profile
- get ride history
- get the authenticated driver partner's profile.
- get ride request
- get trip history for the driver partner.
- delivery
- cancel an active uber ride request.
- rides
- get price estimates for available products between two points.
- list available uber ride products at a specific location.
- rider trip history.
- get ride status
- get real-time status of a ride request.
- driver payment history.
- request an uber ride for a user.
- transportation
- available uber ride products at a location.
- get the authenticated uber rider's profile information.
- cancel ride request
- get time estimates
- authenticated driver partner profile.
- get the trip history for an uber rider.
- get payment history for an uber driver partner.
- get trip history for an uber driver partner.
- ride request creation and management.
- food delivery
- drivers
- uber
- get the authenticated rider's uber profile.
- cancel ride
- get payment history for the driver partner.
- get the profile for an uber driver partner.
- taxis
- list products
- authenticated rider profile.
- price estimates for rides between two locations.
- riders
- get driver trips
- get arrival time estimates for available products.
- eta estimates for ride products at a pickup location.
- list uber products available at a given location.
- request a ride for an authenticated uber user.
- cancel an active ride request.
- get the real-time status of an active ride request.
- individual ride request status and cancellation.
- get the rider's trip history.
- get estimated arrival times for uber products at a pickup location.
- get price estimates
- get driver payments
- ride-sharing
slug: ride-management
source_filename: ride-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Uber Ride Management\n  description: Workflow capability for managing the complete Uber ride lifecycle. Combines the Riders API (ride requests,\n    estimates, products) and Drivers API (driver profile, trips, payments) to support ride-booking applications, fleet management\n    dashboards, and driver analytics tools.\n  tags:\n  - Uber\n  - Ride-Sharing\n  - Transportation\n  - Riders\n  - Drivers\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UBER_RIDERS_ACCESS_TOKEN: UBER_RIDERS_ACCESS_TOKEN\n    UBER_DRIVERS_ACCESS_TOKEN: UBER_DRIVERS_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uber-riders\n    baseUri: https://api.uber.com/v1.2\n    description: Uber Riders API for ride requests, products, and estimates.\n    authentication:\n      type: bearer\n      token: '{{UBER_RIDERS_ACCESS_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description:\
  \ Uber product types available at a location.\n      operations:\n      - name: list-products\n        method: GET\n        description: Returns information about the Uber products offered at a given location.\n        inputParameters:\n        - name: latitude\n          in: query\n          type: number\n          required: true\n          description: Latitude component of location.\n        - name: longitude\n          in: query\n          type: number\n          required: true\n          description: Longitude component of location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product\n      path: /products/{product_id}\n      description: Specific Uber product details.\n      operations:\n      - name: get-product\n        method: GET\n        description: Returns information about a specific Uber product.\n        inputParameters:\n        - name: product_id\n          in: path\n     \
  \     type: string\n          required: true\n          description: Unique identifier for the product.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: price-estimates\n      path: /estimates/price\n      description: Price estimates for ride products.\n      operations:\n      - name: get-price-estimates\n        method: GET\n        description: Returns an estimated price range for each product between two locations.\n        inputParameters:\n        - name: start_latitude\n          in: query\n          type: number\n          required: true\n          description: Start location latitude.\n        - name: start_longitude\n          in: query\n          type: number\n          required: true\n          description: Start location longitude.\n        - name: end_latitude\n          in: query\n          type: number\n          required: true\n          description: End location latitude.\n   \
  \     - name: end_longitude\n          in: query\n          type: number\n          required: true\n          description: End location longitude.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-estimates\n      path: /estimates/time\n      description: ETA estimates for ride products.\n      operations:\n      - name: get-time-estimates\n        method: GET\n        description: Returns ETAs for all products offered at a given location.\n        inputParameters:\n        - name: start_latitude\n          in: query\n          type: number\n          required: true\n          description: Start location latitude.\n        - name: start_longitude\n          in: query\n          type: number\n          required: true\n          description: Start location longitude.\n        - name: product_id\n          in: query\n          type: string\n          required: false\n          description: Filter\
  \ by product ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rider-profile\n      path: /me\n      description: Authenticated rider profile.\n      operations:\n      - name: get-rider-profile\n        method: GET\n        description: Returns the authenticated rider's Uber profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ride-history\n      path: /history\n      description: Rider's trip history.\n      operations:\n      - name: get-ride-history\n        method: GET\n        description: Returns the rider's lifetime activity with Uber.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of items to return.\n        - name: offset\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ride-requests\n      path: /requests\n      description: Ride request management.\n      operations:\n      - name: create-ride-estimate\n        method: POST\n        description: Get an upfront fare estimate before booking a ride.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product_id: '{{tools.product_id}}'\n            start_latitude: '{{tools.start_latitude}}'\n            start_longitude: '{{tools.start_longitude}}'\n            end_latitude: '{{tools.end_latitude}}'\n            end_longitude: '{{tools.end_longitude}}'\n      - name: create-ride-request\n        method: POST\n        description: Request a ride on behalf of an Uber user.\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product_id: '{{tools.product_id}}'\n            start_latitude: '{{tools.start_latitude}}'\n            start_longitude: '{{tools.start_longitude}}'\n            end_latitude: '{{tools.end_latitude}}'\n            end_longitude: '{{tools.end_longitude}}'\n            fare_id: '{{tools.fare_id}}'\n    - name: ride-request\n      path: /requests/{request_id}\n      description: Individual ride request operations.\n      operations:\n      - name: get-ride-request\n        method: GET\n        description: Get real-time status of an ongoing trip.\n        inputParameters:\n        - name: request_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the ride request.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: cancel-ride-request\n        method: DELETE\n        description: Cancel an ongoing ride request.\n        inputParameters:\n        - name: request_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the ride request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: uber-drivers\n    baseUri: https://api.uber.com/v1\n    description: Uber Drivers API for partner profile, payments, and trip data.\n    authentication:\n      type: bearer\n      token: '{{UBER_DRIVERS_ACCESS_TOKEN}}'\n    resources:\n    - name: driver-profile\n      path: /partners/me\n      description: Driver partner profile.\n      operations:\n      - name: get-driver-profile\n        method: GET\n        description: Returns information about the authenticated driver partner.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: driver-payments\n      path: /partners/payments\n      description: Driver payment history.\n      operations:\n      - name: get-driver-payments\n        method: GET\n        description: Returns a list of payments made to the driver.\n        inputParameters:\n        - name: from_time\n          in: query\n          type: integer\n          required: false\n          description: Start of query time range (Unix timestamp).\n        - name: to_time\n          in: query\n          type: integer\n          required: false\n          description: End of query time range (Unix timestamp).\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of items to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: driver-trips\n      path: /partners/trips\n      description: Driver trip history.\n      operations:\n      - name: get-driver-trips\n        method: GET\n        description: Returns trip history for the authenticated driver partner.\n        inputParameters:\n        - name: from_time\n          in: query\n          type: integer\n          required: false\n          description: Start of query time range (Unix timestamp).\n        - name: to_time\n          in: query\n          type: integer\n          required: false\n          description: End of query time range (Unix timestamp).\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of items to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n\
  \          description: Pagination offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uber-ride-management-api\n    description: Unified REST API for managing Uber ride requests, estimates, and driver data.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Available Uber ride products at a location.\n      operations:\n      - method: GET\n        name: list-products\n        description: List Uber products available at a given location.\n        call: uber-riders.list-products\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/estimates/price\n      name: price-estimates\n      description: Price estimates for rides between two locations.\n      operations:\n      - method: GET\n     \
  \   name: get-price-estimates\n        description: Get price estimates for available products between two points.\n        call: uber-riders.get-price-estimates\n        with:\n          start_latitude: rest.start_latitude\n          start_longitude: rest.start_longitude\n          end_latitude: rest.end_latitude\n          end_longitude: rest.end_longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/estimates/time\n      name: time-estimates\n      description: ETA estimates for ride products at a pickup location.\n      operations:\n      - method: GET\n        name: get-time-estimates\n        description: Get arrival time estimates for available products.\n        call: uber-riders.get-time-estimates\n        with:\n          start_latitude: rest.start_latitude\n          start_longitude: rest.start_longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ride-requests\n      name: ride-requests\n\
  \      description: Ride request creation and management.\n      operations:\n      - method: POST\n        name: create-ride-request\n        description: Request a ride for an authenticated Uber user.\n        call: uber-riders.create-ride-request\n        with:\n          product_id: rest.product_id\n          start_latitude: rest.start_latitude\n          start_longitude: rest.start_longitude\n          end_latitude: rest.end_latitude\n          end_longitude: rest.end_longitude\n          fare_id: rest.fare_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ride-requests/{request_id}\n      name: ride-request\n      description: Individual ride request status and cancellation.\n      operations:\n      - method: GET\n        name: get-ride-request\n        description: Get real-time status of a ride request.\n        call: uber-riders.get-ride-request\n        with:\n          request_id: rest.request_id\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-ride-request\n        description: Cancel an active ride request.\n        call: uber-riders.cancel-ride-request\n        with:\n          request_id: rest.request_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/riders/profile\n      name: rider-profile\n      description: Authenticated rider profile.\n      operations:\n      - method: GET\n        name: get-rider-profile\n        description: Get the authenticated rider's Uber profile.\n        call: uber-riders.get-rider-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/riders/history\n      name: ride-history\n      description: Rider trip history.\n      operations:\n      - method: GET\n        name: get-ride-history\n        description: Get the rider's trip history.\n        call: uber-riders.get-ride-history\n        with:\n          limit: rest.limit\n\
  \          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/drivers/profile\n      name: driver-profile\n      description: Authenticated driver partner profile.\n      operations:\n      - method: GET\n        name: get-driver-profile\n        description: Get the authenticated driver partner's profile.\n        call: uber-drivers.get-driver-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/drivers/payments\n      name: driver-payments\n      description: Driver payment history.\n      operations:\n      - method: GET\n        name: get-driver-payments\n        description: Get payment history for the driver partner.\n        call: uber-drivers.get-driver-payments\n        with:\n          from_time: rest.from_time\n          to_time: rest.to_time\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/drivers/trips\n      name: driver-trips\n      description: Driver trip history.\n      operations:\n      - method: GET\n        name: get-driver-trips\n        description: Get trip history for the driver partner.\n        call: uber-drivers.get-driver-trips\n        with:\n          from_time: rest.from_time\n          to_time: rest.to_time\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: uber-ride-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Uber ride booking and driver analytics.\n    tools:\n    - name: list-uber-products\n      description: List available Uber ride products at a specific location.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uber-riders.list-products\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-price-estimates\n      description: Get price estimates for Uber rides between two locations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uber-riders.get-price-estimates\n      with:\n        start_latitude: tools.start_latitude\n        start_longitude: tools.start_longitude\n        end_latitude: tools.end_latitude\n        end_longitude: tools.end_longitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-time-estimates\n      description: Get estimated arrival times for Uber products at a pickup location.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uber-riders.get-time-estimates\n      with:\n        start_latitude: tools.start_latitude\n        start_longitude: tools.start_longitude\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ride-request\n      description: Request an Uber ride for\
  \ a user.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: uber-riders.create-ride-request\n      with:\n        product_id: tools.product_id\n        start_latitude: tools.start_latitude\n        start_longitude: tools.start_longitude\n        end_latitude: tools.end_latitude\n        end_longitude: tools.end_longitude\n        fare_id: tools.fare_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ride-status\n      description: Get the real-time status of an active ride request.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-riders.get-ride-request\n      with:\n        request_id: tools.request_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-ride\n      description: Cancel an active Uber ride request.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: uber-riders.cancel-ride-request\n\
  \      with:\n        request_id: tools.request_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rider-profile\n      description: Get the authenticated Uber rider's profile information.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-riders.get-rider-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rider-history\n      description: Get the trip history for an Uber rider.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-riders.get-ride-history\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-driver-profile\n      description: Get the profile for an Uber driver partner.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-drivers.get-driver-profile\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-driver-payments\n      description: Get payment history for an Uber driver partner.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-drivers.get-driver-payments\n      with:\n        from_time: tools.from_time\n        to_time: tools.to_time\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-driver-trips\n      description: Get trip history for an Uber driver partner.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uber-drivers.get-driver-trips\n      with:\n        from_time: tools.from_time\n        to_time: tools.to_time\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uber/refs/heads/main/capabilities/ride-management.yaml
tags:
- Uber
- Ride-Sharing
- Transportation
- Riders
- Drivers
tools:
- description: List available Uber ride products at a specific location.
  hints:
    openWorld: true
    readOnly: true
  name: list-uber-products
- description: Get price estimates for Uber rides between two locations.
  hints:
    openWorld: true
    readOnly: true
  name: get-price-estimates
- description: Get estimated arrival times for Uber products at a pickup location.
  hints:
    openWorld: true
    readOnly: true
  name: get-time-estimates
- description: Request an Uber ride for a user.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ride-request
- description: Get the real-time status of an active ride request.
  hints:
    openWorld: false
    readOnly: true
  name: get-ride-status
- description: Cancel an active Uber ride request.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-ride
- description: Get the authenticated Uber rider's profile information.
  hints:
    openWorld: false
    readOnly: true
  name: get-rider-profile
- description: Get the trip history for an Uber rider.
  hints:
    openWorld: false
    readOnly: true
  name: get-rider-history
- description: Get the profile for an Uber driver partner.
  hints:
    openWorld: false
    readOnly: true
  name: get-driver-profile
- description: Get payment history for an Uber driver partner.
  hints:
    openWorld: false
    readOnly: true
  name: get-driver-payments
- description: Get trip history for an Uber driver partner.
  hints:
    openWorld: false
    readOnly: true
  name: get-driver-trips
---
