---
categories: []
consumed_apis: []
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
- create shipment
- logistics
- track shipment
- pickup cancellation
- cancel pickup
- compare shipping rates across all available ups services for a shipment
- validate a shipping address
- shipping rate comparison
- fulfillment
- get rate
- supply chain
- validate address
- validate a shipping address and classify as residential or commercial
- create a ups shipment and generate a shipping label
- create shipment and generate label
- track a package by tracking number
- ups
- track a ups package by tracking number for real-time status
- cancel a previously scheduled ups pickup
- package tracking
- single service rate
- get transit time estimates by service
- cancel a scheduled pickup
- e-commerce
- get time in transit
- pickup scheduling
- get estimated transit days for ups services between two locations
- void/cancel a shipment
- shop rates
- compare rates across all ups services
- tracking
- get the rate for a specific ups service level
- shipment creation
- void shipment
- address validation
- schedule a ups pickup
- void/cancel a ups shipment before it is tendered
- shipping
- schedule a ups pickup for one or more packages
- schedule pickup
- shipment void
- get rate for a specific service
- fortune 500
- transit time estimates
slug: shipping-and-logistics
source_filename: shipping-and-logistics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UPS Shipping and Logistics\n  description: Workflow capability for UPS shipping and logistics operations, combining rate shopping, shipment creation,\n    package tracking, address validation, pickup scheduling, and transit time estimation into a unified workflow. Designed\n    for e-commerce platforms, shipping operations teams, and logistics integrators.\n  tags:\n  - UPS\n  - Shipping\n  - Logistics\n  - E-Commerce\n  - Fulfillment\n  - Tracking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPS_CLIENT_ID: UPS_CLIENT_ID\n    UPS_CLIENT_SECRET: UPS_CLIENT_SECRET\n    UPS_ACCOUNT_NUMBER: UPS_ACCOUNT_NUMBER\ncapability:\n  consumes:\n  - type: http\n    namespace: ups-shipping\n    baseUri: https://onlinetools.ups.com/api\n    description: UPS REST API for shipping, tracking, and logistics\n    authentication:\n      type: bearer\n      token: '{{UPS_ACCESS_TOKEN}}'\n    resources:\n    - name:\
  \ rates\n      path: /rating/v1/Shop\n      description: Rate shopping across all UPS services\n      operations:\n      - name: shop-rates\n        method: POST\n        description: Get rates for all UPS services for a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            RateRequest:\n              Shipment:\n                Shipper:\n                  ShipperNumber: '{{tools.accountNumber}}'\n                  Address:\n                    AddressLine:\n                    - '{{tools.originAddress}}'\n                    City: '{{tools.originCity}}'\n                    StateProvinceCode: '{{tools.originState}}'\n                    PostalCode: '{{tools.originPostalCode}}'\n                    CountryCode: '{{tools.originCountryCode}}'\n                ShipTo:\n                  Address:\n                    AddressLine:\n            \
  \        - '{{tools.destAddress}}'\n                    City: '{{tools.destCity}}'\n                    StateProvinceCode: '{{tools.destState}}'\n                    PostalCode: '{{tools.destPostalCode}}'\n                    CountryCode: '{{tools.destCountryCode}}'\n                Package:\n                  PackageWeight:\n                    UnitOfMeasurement:\n                      Code: LBS\n                    Weight: '{{tools.weightLbs}}'\n    - name: rate\n      path: /rating/v1/Rate\n      description: Get rate for a specific UPS service\n      operations:\n      - name: get-rate\n        method: POST\n        description: Get rate for a specific service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            RateRequest:\n              Shipment:\n                Service:\n                  Code: '{{tools.serviceCode}}'\n    - name: shipments\n\
  \      path: /shipments/v1/ship\n      description: Shipment creation and label generation\n      operations:\n      - name: create-shipment\n        method: POST\n        description: Create shipment and generate label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ShipmentRequest:\n              Shipment:\n                Shipper:\n                  ShipperNumber: '{{tools.accountNumber}}'\n                Service:\n                  Code: '{{tools.serviceCode}}'\n    - name: void-shipment\n      path: /shipments/v1/void/cancel/{shipmentIdentificationNumber}\n      description: Void a shipment\n      operations:\n      - name: void-shipment\n        method: DELETE\n        description: Cancel/void a shipment by tracking number\n        inputParameters:\n        - name: shipmentIdentificationNumber\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tracking\n      path: /track/v1/details/{inquiryNumber}\n      description: Package tracking\n      operations:\n      - name: track-shipment\n        method: GET\n        description: Track a package by tracking number\n        inputParameters:\n        - name: inquiryNumber\n          in: path\n          type: string\n          required: true\n          description: UPS tracking number\n        - name: locale\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: address-validation\n      path: /addressvalidation/v1/1\n      description: Address validation and classification\n      operations:\n      - name: validate-address\n        method: POST\n        description:\
  \ Validate and classify a shipping address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            AddressValidationRequest:\n              AddressKeyFormat:\n                AddressLine:\n                - '{{tools.addressLine}}'\n                PoliticalDivision2: '{{tools.city}}'\n                PoliticalDivision1: '{{tools.state}}'\n                PostcodePrimaryLow: '{{tools.postalCode}}'\n                CountryCode: '{{tools.countryCode}}'\n    - name: pickups\n      path: /pickup/v1/pickups\n      description: Pickup scheduling\n      operations:\n      - name: schedule-pickup\n        method: POST\n        description: Schedule a UPS pickup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            PickupCreationRequest:\n\
  \              PickupDateInfo:\n                PickupDate: '{{tools.pickupDate}}'\n                ReadyTime: '{{tools.readyTime}}'\n                CloseTime: '{{tools.closeTime}}'\n    - name: time-in-transit\n      path: /timeintransit/v1/transittimes\n      description: Transit time estimates\n      operations:\n      - name: get-time-in-transit\n        method: POST\n        description: Get transit time estimates by service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            originCountryCode: '{{tools.originCountryCode}}'\n            originPostalCode: '{{tools.originPostalCode}}'\n            destinationCountryCode: '{{tools.destCountryCode}}'\n            destinationPostalCode: '{{tools.destPostalCode}}'\n            weight: '{{tools.weightLbs}}'\n            weightUnitOfMeasure: LBS\n            shipDate: '{{tools.shipDate}}'\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: ups-logistics-api\n    description: Unified REST API for UPS shipping and logistics workflows.\n    resources:\n    - path: /v1/rates\n      name: rates\n      description: Shipping rate comparison\n      operations:\n      - method: POST\n        name: shop-rates\n        description: Compare rates across all UPS services\n        call: ups-shipping.shop-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rate\n      name: rate\n      description: Single service rate\n      operations:\n      - method: POST\n        name: get-rate\n        description: Get rate for a specific service\n        call: ups-shipping.get-rate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Shipment creation\n      operations:\n      - method: POST\n        name: create-shipment\n        description: Create shipment and generate\
  \ label\n        call: ups-shipping.create-shipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments/{trackingNumber}\n      name: shipment\n      description: Shipment void\n      operations:\n      - method: DELETE\n        name: void-shipment\n        description: Void/cancel a shipment\n        call: ups-shipping.void-shipment\n        with:\n          shipmentIdentificationNumber: rest.trackingNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracking/{inquiryNumber}\n      name: tracking\n      description: Package tracking\n      operations:\n      - method: GET\n        name: track-shipment\n        description: Track a package by tracking number\n        call: ups-shipping.track-shipment\n        with:\n          inquiryNumber: rest.inquiryNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/address-validation\n      name: address-validation\n\
  \      description: Address validation\n      operations:\n      - method: POST\n        name: validate-address\n        description: Validate a shipping address\n        call: ups-shipping.validate-address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pickups\n      name: pickups\n      description: Pickup scheduling\n      operations:\n      - method: POST\n        name: schedule-pickup\n        description: Schedule a UPS pickup\n        call: ups-shipping.schedule-pickup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pickups/{prn}\n      name: pickup\n      description: Pickup cancellation\n      operations:\n      - method: DELETE\n        name: cancel-pickup\n        description: Cancel a scheduled pickup\n        call: ups-shipping.cancel-pickup\n        with:\n          prn: rest.prn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transit-times\n \
  \     name: transit-times\n      description: Transit time estimates\n      operations:\n      - method: POST\n        name: get-time-in-transit\n        description: Get transit time estimates by service\n        call: ups-shipping.get-time-in-transit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ups-logistics-mcp\n    transport: http\n    description: MCP server for AI-assisted UPS shipping and logistics workflows.\n    tools:\n    - name: shop-rates\n      description: Compare shipping rates across all available UPS services for a shipment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ups-shipping.shop-rates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rate\n      description: Get the rate for a specific UPS service level\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ups-shipping.get-rate\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Create a UPS shipment and generate a shipping label\n      hints:\n        readOnly: false\n        openWorld: false\n      call: ups-shipping.create-shipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-shipment\n      description: Void/cancel a UPS shipment before it is tendered\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ups-shipping.void-shipment\n      with:\n        shipmentIdentificationNumber: tools.trackingNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-shipment\n      description: Track a UPS package by tracking number for real-time status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ups-shipping.track-shipment\n      with:\n        inquiryNumber: tools.inquiryNumber\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: validate-address\n      description: Validate a shipping address and classify as residential or commercial\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ups-shipping.validate-address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-pickup\n      description: Schedule a UPS pickup for one or more packages\n      hints:\n        readOnly: false\n        openWorld: false\n      call: ups-shipping.schedule-pickup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-pickup\n      description: Cancel a previously scheduled UPS pickup\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ups-shipping.cancel-pickup\n      with:\n        prn: tools.prn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-time-in-transit\n      description: Get estimated transit days for UPS services\
  \ between two locations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ups-shipping.get-time-in-transit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
