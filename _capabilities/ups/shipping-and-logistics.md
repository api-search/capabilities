---
api_specs:
- filename: ups-shipping-openapi.yml
  format: yaml
  label: ups-shipping
  slug: ups-shipping
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/ups/refs/heads/main/openapi/ups-shipping-openapi.yml
categories: []
consumed_apis:
- ups-shipping
description: Workflow capability for UPS shipping and logistics operations, combining rate shopping, shipment creation, package tracking, address validation, pickup scheduling, and transit time estimation into a unified workflow. Designed for e-commerce platforms, shipping operations teams, and logistics integrators.
layout: capability
name: UPS Shipping and Logistics
operations:
- description: Compare rates across all UPS services
  method: POST
  name: shop-rates
  path: /v1/rates
- description: Get rate for a specific service
  method: POST
  name: get-rate
  path: /v1/rate
- description: Create shipment and generate label
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Void/cancel a shipment
  method: DELETE
  name: void-shipment
  path: /v1/shipments/{trackingNumber}
- description: Track a package by tracking number
  method: GET
  name: track-shipment
  path: /v1/tracking/{inquiryNumber}
- description: Validate a shipping address
  method: POST
  name: validate-address
  path: /v1/address-validation
- description: Schedule a UPS pickup
  method: POST
  name: schedule-pickup
  path: /v1/pickups
- description: Cancel a scheduled pickup
  method: DELETE
  name: cancel-pickup
  path: /v1/pickups/{prn}
- description: Get transit time estimates by service
  method: POST
  name: get-time-in-transit
  path: /v1/transit-times
personas: []
provider_name: UPS
provider_slug: ups
search_terms:
- address validation
- e-commerce
- compare rates across all ups services
- pickup scheduling
- schedule a ups pickup
- validate a shipping address
- transit time estimates
- get estimated transit days for ups services between two locations
- get rate for a specific service
- ups
- shop rates
- validate address
- cancel pickup
- create shipment and generate label
- package tracking
- void shipment
- fortune 500
- get rate
- track a package by tracking number
- validate a shipping address and classify as residential or commercial
- supply chain
- logistics
- get the rate for a specific ups service level
- schedule pickup
- shipment creation
- shipping rate comparison
- shipment void
- get time in transit
- create a ups shipment and generate a shipping label
- single service rate
- compare shipping rates across all available ups services for a shipment
- get transit time estimates by service
- schedule a ups pickup for one or more packages
- cancel a previously scheduled ups pickup
- pickup cancellation
- shipping
- fulfillment
- tracking
- track a ups package by tracking number for real-time status
- cancel a scheduled pickup
- track shipment
- create shipment
- void/cancel a shipment
- void/cancel a ups shipment before it is tendered
slug: shipping-and-logistics
source_filename: shipping-and-logistics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UPS Shipping and Logistics\"\n  description: >-\n    Workflow capability for UPS shipping and logistics operations, combining\n    rate shopping, shipment creation, package tracking, address validation,\n    pickup scheduling, and transit time estimation into a unified workflow.\n    Designed for e-commerce platforms, shipping operations teams, and\n    logistics integrators.\n  tags:\n    - UPS\n    - Shipping\n    - Logistics\n    - E-Commerce\n    - Fulfillment\n    - Tracking\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UPS_CLIENT_ID: UPS_CLIENT_ID\n      UPS_CLIENT_SECRET: UPS_CLIENT_SECRET\n      UPS_ACCOUNT_NUMBER: UPS_ACCOUNT_NUMBER\n\ncapability:\n  consumes:\n    - import: ups-shipping\n      location: ./shared/ups-shipping.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ups-logistics-api\n      description: \"Unified REST API for UPS shipping\
  \ and logistics workflows.\"\n      resources:\n        - path: /v1/rates\n          name: rates\n          description: \"Shipping rate comparison\"\n          operations:\n            - method: POST\n              name: shop-rates\n              description: \"Compare rates across all UPS services\"\n              call: \"ups-shipping.shop-rates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/rate\n          name: rate\n          description: \"Single service rate\"\n          operations:\n            - method: POST\n              name: get-rate\n              description: \"Get rate for a specific service\"\n              call: \"ups-shipping.get-rate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/shipments\n          name: shipments\n          description: \"Shipment creation\"\n          operations:\n            - method: POST\n\
  \              name: create-shipment\n              description: \"Create shipment and generate label\"\n              call: \"ups-shipping.create-shipment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/shipments/{trackingNumber}\n          name: shipment\n          description: \"Shipment void\"\n          operations:\n            - method: DELETE\n              name: void-shipment\n              description: \"Void/cancel a shipment\"\n              call: \"ups-shipping.void-shipment\"\n              with:\n                shipmentIdentificationNumber: \"rest.trackingNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tracking/{inquiryNumber}\n          name: tracking\n          description: \"Package tracking\"\n          operations:\n            - method: GET\n              name: track-shipment\n              description: \"Track\
  \ a package by tracking number\"\n              call: \"ups-shipping.track-shipment\"\n              with:\n                inquiryNumber: \"rest.inquiryNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/address-validation\n          name: address-validation\n          description: \"Address validation\"\n          operations:\n            - method: POST\n              name: validate-address\n              description: \"Validate a shipping address\"\n              call: \"ups-shipping.validate-address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pickups\n          name: pickups\n          description: \"Pickup scheduling\"\n          operations:\n            - method: POST\n              name: schedule-pickup\n              description: \"Schedule a UPS pickup\"\n              call: \"ups-shipping.schedule-pickup\"\n         \
  \     outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pickups/{prn}\n          name: pickup\n          description: \"Pickup cancellation\"\n          operations:\n            - method: DELETE\n              name: cancel-pickup\n              description: \"Cancel a scheduled pickup\"\n              call: \"ups-shipping.cancel-pickup\"\n              with:\n                prn: \"rest.prn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transit-times\n          name: transit-times\n          description: \"Transit time estimates\"\n          operations:\n            - method: POST\n              name: get-time-in-transit\n              description: \"Get transit time estimates by service\"\n              call: \"ups-shipping.get-time-in-transit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n   \
  \ - type: mcp\n      port: 9090\n      namespace: ups-logistics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted UPS shipping and logistics workflows.\"\n      tools:\n        - name: shop-rates\n          description: \"Compare shipping rates across all available UPS services for a shipment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ups-shipping.shop-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rate\n          description: \"Get the rate for a specific UPS service level\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ups-shipping.get-rate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-shipment\n          description: \"Create a UPS shipment and generate a shipping label\"\n          hints:\n            readOnly: false\n  \
  \          openWorld: false\n          call: \"ups-shipping.create-shipment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: void-shipment\n          description: \"Void/cancel a UPS shipment before it is tendered\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ups-shipping.void-shipment\"\n          with:\n            shipmentIdentificationNumber: \"tools.trackingNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-shipment\n          description: \"Track a UPS package by tracking number for real-time status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ups-shipping.track-shipment\"\n          with:\n            inquiryNumber: \"tools.inquiryNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: validate-address\n          description: \"Validate a shipping address and classify as residential or commercial\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ups-shipping.validate-address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-pickup\n          description: \"Schedule a UPS pickup for one or more packages\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"ups-shipping.schedule-pickup\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-pickup\n          description: \"Cancel a previously scheduled UPS pickup\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ups-shipping.cancel-pickup\"\n          with:\n            prn: \"tools.prn\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-time-in-transit\n          description: \"Get estimated transit days for UPS services between two locations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ups-shipping.get-time-in-transit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ups/refs/heads/main/capabilities/shipping-and-logistics.yaml
tags:
- UPS
- Shipping
- Logistics
- E-Commerce
- Fulfillment
- Tracking
tools:
- description: Compare shipping rates across all available UPS services for a shipment
  hints:
    openWorld: true
    readOnly: true
  name: shop-rates
- description: Get the rate for a specific UPS service level
  hints:
    openWorld: true
    readOnly: true
  name: get-rate
- description: Create a UPS shipment and generate a shipping label
  hints:
    openWorld: false
    readOnly: false
  name: create-shipment
- description: Void/cancel a UPS shipment before it is tendered
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: void-shipment
- description: Track a UPS package by tracking number for real-time status
  hints:
    openWorld: true
    readOnly: true
  name: track-shipment
- description: Validate a shipping address and classify as residential or commercial
  hints:
    openWorld: true
    readOnly: true
  name: validate-address
- description: Schedule a UPS pickup for one or more packages
  hints:
    openWorld: false
    readOnly: false
  name: schedule-pickup
- description: Cancel a previously scheduled UPS pickup
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-pickup
- description: Get estimated transit days for UPS services between two locations
  hints:
    openWorld: true
    readOnly: true
  name: get-time-in-transit
---
