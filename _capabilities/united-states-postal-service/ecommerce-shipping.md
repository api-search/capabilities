---
categories: []
consumed_apis: []
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
- get base postage rates for a shipment.
- logistics
- validate address for shipping.
- schedule carrier pickup
- search base rates
- search total rates
- get pickup details.
- customer-facing delivery inquiry and address validation support
- get carrier pickup
- fulfillment
- validate address
- validate and standardize a us shipping address to usps specifications.
- search base postage rates.
- get city state
- ecommerce developer
- online retail shipping and fulfillment operations
- package tracking and delivery status monitoring for customer service and logistics
- get zip code
- cancel a previously scheduled usps carrier pickup.
- search usps base postage rates for a domestic shipment by weight, dimensions, and mail class.
- package tracking
- look up zip code for a street address.
- operations manager overseeing fulfillment and carrier pickup scheduling
- e-commerce
- schedule carrier pickup.
- get zip code.
- validate shipping address
- look up zip code by address.
- manager monitoring shipment delivery performance and address quality
- cancel carrier pickup
- e-commerce shipping lifecycle from address validation through rate shopping to pickup scheduling
- manage an existing pickup.
- customer service agent
- order fulfillment and shipping label generation operations
- package tracking and delivery status monitoring
- government
- cancel a pickup.
- get total usps postage rates including extra service fees for a complete shipping configuration.
- schedule a free usps carrier pickup at a residential or commercial address.
- postal service
- developer integrating usps shipping into an online store or marketplace
- usps
- get pickup
- validate and standardize a shipping address.
- schedule a usps carrier pickup.
- search total postage rates with fees.
- logistics manager
- agent assisting customers with package status and delivery inquiries
- shipping
- shipping manager
- address validation
- schedule pickup
- cancel pickup
- get total postage rates including all fees.
- get city and state name for a zip code.
- retrieve details of a scheduled usps carrier pickup by confirmation number.
slug: ecommerce-shipping
source_filename: ecommerce-shipping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USPS E-Commerce Shipping\n  description: 'Unified workflow capability for e-commerce shipping operations. Combines the USPS Addresses, Domestic Prices,\n    and Carrier Pickup APIs to support the complete shipping lifecycle: address validation at checkout, rate shopping, and\n    pickup scheduling. Designed for e-commerce developers and shipping software integrators.'\n  tags:\n  - USPS\n  - E-Commerce\n  - Shipping\n  - Fulfillment\n  - Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USPS_BEARER_TOKEN: USPS_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: usps-addresses\n    baseUri: https://apis.usps.com\n    description: USPS address validation and standardization API.\n    authentication:\n      type: bearer\n      token: '{{USPS_BEARER_TOKEN}}'\n    resources:\n    - name: address\n      path: /addresses/v3/address\n      description: Address validation and\
  \ standardization.\n      operations:\n      - name: validate-address\n        method: GET\n        description: Validates and standardizes a US address to USPS specifications.\n        inputParameters:\n        - name: streetAddress\n          in: query\n          type: string\n          required: true\n          description: Primary street address line.\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Two-letter state abbreviation.\n        - name: ZIPCode\n          in: query\n          type: string\n          required: false\n          description: 5-digit ZIP Code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: city-state\n      path: /addresses/v3/city-state\n      description: City and state\
  \ lookup by ZIP Code.\n      operations:\n      - name: get-city-state\n        method: GET\n        description: Returns the city and state for a given ZIP Code.\n        inputParameters:\n        - name: ZIPCode\n          in: query\n          type: string\n          required: true\n          description: 5-digit ZIP Code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zipcode\n      path: /addresses/v3/zipcode\n      description: ZIP Code lookup by address.\n      operations:\n      - name: get-zip-code\n        method: GET\n        description: Returns ZIP Code for a given address.\n        inputParameters:\n        - name: streetAddress\n          in: query\n          type: string\n          required: true\n          description: Primary street address.\n        - name: city\n          in: query\n          type: string\n          required: true\n          description: City name.\n        -\
  \ name: state\n          in: query\n          type: string\n          required: true\n          description: Two-letter state abbreviation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: usps-domestic-prices\n    baseUri: https://apis.usps.com\n    description: USPS domestic postage pricing API.\n    authentication:\n      type: bearer\n      token: '{{USPS_BEARER_TOKEN}}'\n    resources:\n    - name: base-rates\n      path: /prices/v3/base-rates/search\n      description: Base postage rate search.\n      operations:\n      - name: search-base-rates\n        method: POST\n        description: Search for base postage rates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            originZIPCode: '{{tools.originZIPCode}}'\n            destinationZIPCode:\
  \ '{{tools.destinationZIPCode}}'\n            weight: '{{tools.weight}}'\n            mailClass: '{{tools.mailClass}}'\n    - name: extra-service-rates\n      path: /prices/v3/extra-service-rates/search\n      description: Extra service rates search.\n      operations:\n      - name: search-extra-service-rates\n        method: POST\n        description: Search for extra service rates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            extraServiceCode: '{{tools.extraServiceCode}}'\n            mailClass: '{{tools.mailClass}}'\n    - name: total-rates\n      path: /prices/v3/total-rates/search\n      description: Total rate search including all fees.\n      operations:\n      - name: search-total-rates\n        method: POST\n        description: Search for total postage rates including all fees.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            originZIPCode: '{{tools.originZIPCode}}'\n            destinationZIPCode: '{{tools.destinationZIPCode}}'\n            weight: '{{tools.weight}}'\n            mailClass: '{{tools.mailClass}}'\n  - type: http\n    namespace: usps-carrier-pickup\n    baseUri: https://apis.usps.com\n    description: USPS carrier pickup scheduling API.\n    authentication:\n      type: bearer\n      token: '{{USPS_BEARER_TOKEN}}'\n    resources:\n    - name: carrier-pickup\n      path: /pickup/v3/carrier-pickup\n      description: Carrier pickup scheduling and management.\n      operations:\n      - name: schedule-carrier-pickup\n        method: POST\n        description: Schedule a free USPS carrier pickup.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n  \
  \        data:\n            pickupAddress: '{{tools.pickupAddress}}'\n            packages: '{{tools.packages}}'\n            packageLocation: '{{tools.packageLocation}}'\n      - name: get-carrier-pickup\n        method: GET\n        description: Retrieve an existing carrier pickup by confirmation number.\n        inputParameters:\n        - name: confirmationNumber\n          in: query\n          type: string\n          required: true\n          description: Pickup confirmation number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-carrier-pickup\n        method: PUT\n        description: Update an existing carrier pickup request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            confirmationNumber: '{{tools.confirmationNumber}}'\n          \
  \  packages: '{{tools.packages}}'\n      - name: cancel-carrier-pickup\n        method: DELETE\n        description: Cancel a previously scheduled carrier pickup.\n        inputParameters:\n        - name: confirmationNumber\n          in: query\n          type: string\n          required: true\n          description: Pickup confirmation number to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: usps-ecommerce-shipping-api\n    description: Unified REST API for USPS e-commerce shipping workflows.\n    resources:\n    - path: /v1/addresses/validate\n      name: address-validation\n      description: Validate and standardize a shipping address.\n      operations:\n      - method: GET\n        name: validate-address\n        description: Validate address for shipping.\n        call: usps-addresses.validate-address\n        with:\n          streetAddress:\
  \ rest.streetAddress\n          city: rest.city\n          state: rest.state\n          ZIPCode: rest.ZIPCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses/zipcode\n      name: zipcode-lookup\n      description: Look up ZIP Code by address.\n      operations:\n      - method: GET\n        name: get-zip-code\n        description: Get ZIP Code.\n        call: usps-addresses.get-zip-code\n        with:\n          streetAddress: rest.streetAddress\n          city: rest.city\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rates/base\n      name: base-rates\n      description: Search base postage rates.\n      operations:\n      - method: POST\n        name: search-base-rates\n        description: Get base postage rates for a shipment.\n        call: usps-domestic-prices.search-base-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /v1/rates/total\n      name: total-rates\n      description: Search total postage rates with fees.\n      operations:\n      - method: POST\n        name: search-total-rates\n        description: Get total postage rates including all fees.\n        call: usps-domestic-prices.search-total-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pickups\n      name: pickups\n      description: Schedule a USPS carrier pickup.\n      operations:\n      - method: POST\n        name: schedule-pickup\n        description: Schedule carrier pickup.\n        call: usps-carrier-pickup.schedule-carrier-pickup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pickups/{confirmationNumber}\n      name: pickup-management\n      description: Manage an existing pickup.\n      operations:\n      - method: GET\n        name: get-pickup\n        description: Get pickup details.\n        call: usps-carrier-pickup.get-carrier-pickup\n\
  \        with:\n          confirmationNumber: rest.confirmationNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-pickup\n        description: Cancel a pickup.\n        call: usps-carrier-pickup.cancel-carrier-pickup\n        with:\n          confirmationNumber: rest.confirmationNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: usps-ecommerce-shipping-mcp\n    transport: http\n    description: MCP server for AI-assisted USPS e-commerce shipping workflows.\n    tools:\n    - name: validate-shipping-address\n      description: Validate and standardize a US shipping address to USPS specifications.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-addresses.validate-address\n      with:\n        streetAddress: tools.streetAddress\n        city: tools.city\n        state: tools.state\n        ZIPCode: tools.ZIPCode\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-city-state\n      description: Get city and state name for a ZIP Code.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-addresses.get-city-state\n      with:\n        ZIPCode: tools.ZIPCode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-zip-code\n      description: Look up ZIP Code for a street address.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-addresses.get-zip-code\n      with:\n        streetAddress: tools.streetAddress\n        city: tools.city\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-base-rates\n      description: Search USPS base postage rates for a domestic shipment by weight, dimensions, and mail class.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-domestic-prices.search-base-rates\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-total-rates\n      description: Get total USPS postage rates including extra service fees for a complete shipping configuration.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-domestic-prices.search-total-rates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-carrier-pickup\n      description: Schedule a free USPS carrier pickup at a residential or commercial address.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: usps-carrier-pickup.schedule-carrier-pickup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-carrier-pickup\n      description: Retrieve details of a scheduled USPS carrier pickup by confirmation number.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-carrier-pickup.get-carrier-pickup\n  \
  \    with:\n        confirmationNumber: tools.confirmationNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-carrier-pickup\n      description: Cancel a previously scheduled USPS carrier pickup.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: usps-carrier-pickup.cancel-carrier-pickup\n      with:\n        confirmationNumber: tools.confirmationNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
