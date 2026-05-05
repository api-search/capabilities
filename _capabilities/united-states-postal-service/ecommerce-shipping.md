---
categories: []
consumed_apis:
- usps-addresses
- usps-domestic-prices
- usps-carrier-pickup
description: 'Unified workflow capability for e-commerce shipping operations. Combines the USPS Addresses, Domestic Prices, and Carrier Pickup APIs to support the complete shipping lifecycle: address validation at checkout, rate shopping, and pickup scheduling. Designed for e-commerce developers and shipping software integrators.'
layout: capability
name: USPS E-Commerce Shipping
operations:
- description: Validate address for shipping.
  method: GET
  name: validate-address
  path: /v1/addresses/validate
- description: Get ZIP Code.
  method: GET
  name: get-zip-code
  path: /v1/addresses/zipcode
- description: Get base postage rates for a shipment.
  method: POST
  name: search-base-rates
  path: /v1/rates/base
- description: Get total postage rates including all fees.
  method: POST
  name: search-total-rates
  path: /v1/rates/total
- description: Schedule carrier pickup.
  method: POST
  name: schedule-pickup
  path: /v1/pickups
- description: Get pickup details.
  method: GET
  name: get-pickup
  path: /v1/pickups/{confirmationNumber}
- description: Cancel a pickup.
  method: DELETE
  name: cancel-pickup
  path: /v1/pickups/{confirmationNumber}
personas: []
provider_name: United States Postal Service
provider_slug: united-states-postal-service
search_terms:
- usps
- agent assisting customers with package status and delivery inquiries
- address validation
- search base postage rates.
- get total usps postage rates including extra service fees for a complete shipping configuration.
- e-commerce
- validate shipping address
- get zip code
- cancel a pickup.
- search total postage rates with fees.
- government
- validate and standardize a shipping address.
- logistics manager
- get pickup
- schedule carrier pickup.
- schedule carrier pickup
- validate address
- validate address for shipping.
- cancel pickup
- customer-facing delivery inquiry and address validation support
- online retail shipping and fulfillment operations
- search base rates
- postal service
- e-commerce shipping lifecycle from address validation through rate shopping to pickup scheduling
- order fulfillment and shipping label generation operations
- package tracking
- get pickup details.
- look up zip code by address.
- schedule a usps carrier pickup.
- get base postage rates for a shipment.
- look up zip code for a street address.
- search usps base postage rates for a domestic shipment by weight, dimensions, and mail class.
- shipping manager
- logistics
- schedule pickup
- manager monitoring shipment delivery performance and address quality
- package tracking and delivery status monitoring
- get city and state name for a zip code.
- get carrier pickup
- ecommerce developer
- customer service agent
- get city state
- retrieve details of a scheduled usps carrier pickup by confirmation number.
- cancel carrier pickup
- developer integrating usps shipping into an online store or marketplace
- operations manager overseeing fulfillment and carrier pickup scheduling
- get zip code.
- validate and standardize a us shipping address to usps specifications.
- schedule a free usps carrier pickup at a residential or commercial address.
- shipping
- fulfillment
- get total postage rates including all fees.
- cancel a previously scheduled usps carrier pickup.
- search total rates
- package tracking and delivery status monitoring for customer service and logistics
- manage an existing pickup.
slug: ecommerce-shipping
source_filename: ecommerce-shipping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USPS E-Commerce Shipping\"\n  description: >-\n    Unified workflow capability for e-commerce shipping operations. Combines the\n    USPS Addresses, Domestic Prices, and Carrier Pickup APIs to support the complete\n    shipping lifecycle: address validation at checkout, rate shopping, and pickup\n    scheduling. Designed for e-commerce developers and shipping software integrators.\n  tags:\n    - USPS\n    - E-Commerce\n    - Shipping\n    - Fulfillment\n    - Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USPS_BEARER_TOKEN: USPS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: usps-addresses\n      location: ./shared/addresses.yaml\n    - import: usps-domestic-prices\n      location: ./shared/domestic-prices.yaml\n    - import: usps-carrier-pickup\n      location: ./shared/carrier-pickup.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ usps-ecommerce-shipping-api\n      description: \"Unified REST API for USPS e-commerce shipping workflows.\"\n      resources:\n        - path: /v1/addresses/validate\n          name: address-validation\n          description: \"Validate and standardize a shipping address.\"\n          operations:\n            - method: GET\n              name: validate-address\n              description: \"Validate address for shipping.\"\n              call: \"usps-addresses.validate-address\"\n              with:\n                streetAddress: \"rest.streetAddress\"\n                city: \"rest.city\"\n                state: \"rest.state\"\n                ZIPCode: \"rest.ZIPCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/addresses/zipcode\n          name: zipcode-lookup\n          description: \"Look up ZIP Code by address.\"\n          operations:\n            - method: GET\n              name: get-zip-code\n     \
  \         description: \"Get ZIP Code.\"\n              call: \"usps-addresses.get-zip-code\"\n              with:\n                streetAddress: \"rest.streetAddress\"\n                city: \"rest.city\"\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rates/base\n          name: base-rates\n          description: \"Search base postage rates.\"\n          operations:\n            - method: POST\n              name: search-base-rates\n              description: \"Get base postage rates for a shipment.\"\n              call: \"usps-domestic-prices.search-base-rates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/rates/total\n          name: total-rates\n          description: \"Search total postage rates with fees.\"\n          operations:\n            - method: POST\n              name: search-total-rates\n\
  \              description: \"Get total postage rates including all fees.\"\n              call: \"usps-domestic-prices.search-total-rates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pickups\n          name: pickups\n          description: \"Schedule a USPS carrier pickup.\"\n          operations:\n            - method: POST\n              name: schedule-pickup\n              description: \"Schedule carrier pickup.\"\n              call: \"usps-carrier-pickup.schedule-carrier-pickup\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pickups/{confirmationNumber}\n          name: pickup-management\n          description: \"Manage an existing pickup.\"\n          operations:\n            - method: GET\n              name: get-pickup\n              description: \"Get pickup details.\"\n              call: \"usps-carrier-pickup.get-carrier-pickup\"\
  \n              with:\n                confirmationNumber: \"rest.confirmationNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-pickup\n              description: \"Cancel a pickup.\"\n              call: \"usps-carrier-pickup.cancel-carrier-pickup\"\n              with:\n                confirmationNumber: \"rest.confirmationNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: usps-ecommerce-shipping-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USPS e-commerce shipping workflows.\"\n      tools:\n        - name: validate-shipping-address\n          description: \"Validate and standardize a US shipping address to USPS specifications.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-addresses.validate-address\"\
  \n          with:\n            streetAddress: \"tools.streetAddress\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n            ZIPCode: \"tools.ZIPCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-city-state\n          description: \"Get city and state name for a ZIP Code.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-addresses.get-city-state\"\n          with:\n            ZIPCode: \"tools.ZIPCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-zip-code\n          description: \"Look up ZIP Code for a street address.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-addresses.get-zip-code\"\n          with:\n            streetAddress: \"tools.streetAddress\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-base-rates\n          description: \"Search USPS base postage rates for a domestic shipment by weight, dimensions, and mail class.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-domestic-prices.search-base-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-total-rates\n          description: \"Get total USPS postage rates including extra service fees for a complete shipping configuration.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-domestic-prices.search-total-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-carrier-pickup\n          description: \"Schedule a free USPS carrier pickup at a residential or commercial address.\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"usps-carrier-pickup.schedule-carrier-pickup\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-carrier-pickup\n          description: \"Retrieve details of a scheduled USPS carrier pickup by confirmation number.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-carrier-pickup.get-carrier-pickup\"\n          with:\n            confirmationNumber: \"tools.confirmationNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-carrier-pickup\n          description: \"Cancel a previously scheduled USPS carrier pickup.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"usps-carrier-pickup.cancel-carrier-pickup\"\n    \
  \      with:\n            confirmationNumber: \"tools.confirmationNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-postal-service/refs/heads/main/capabilities/ecommerce-shipping.yaml
tags:
- USPS
- E-Commerce
- Shipping
- Fulfillment
- Government
tools:
- description: Validate and standardize a US shipping address to USPS specifications.
  hints:
    openWorld: true
    readOnly: true
  name: validate-shipping-address
- description: Get city and state name for a ZIP Code.
  hints:
    openWorld: true
    readOnly: true
  name: get-city-state
- description: Look up ZIP Code for a street address.
  hints:
    openWorld: true
    readOnly: true
  name: get-zip-code
- description: Search USPS base postage rates for a domestic shipment by weight, dimensions, and mail class.
  hints:
    openWorld: true
    readOnly: true
  name: search-base-rates
- description: Get total USPS postage rates including extra service fees for a complete shipping configuration.
  hints:
    openWorld: true
    readOnly: true
  name: search-total-rates
- description: Schedule a free USPS carrier pickup at a residential or commercial address.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-carrier-pickup
- description: Retrieve details of a scheduled USPS carrier pickup by confirmation number.
  hints:
    openWorld: true
    readOnly: true
  name: get-carrier-pickup
- description: Cancel a previously scheduled USPS carrier pickup.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-carrier-pickup
---
