---
categories: []
consumed_apis: []
description: Workflow capability for package tracking and delivery status monitoring. Combines the USPS Tracking API with address validation to support customer service teams and logistics operations tracking USPS shipments.
layout: capability
name: USPS Package Tracking
operations:
- description: Track a USPS package.
  method: GET
  name: get-tracking
  path: /v1/tracking/{trackingNumber}
- description: Track multiple USPS packages.
  method: POST
  name: get-multiple-tracking
  path: /v1/tracking
- description: Validate address.
  method: GET
  name: validate-address
  path: /v1/addresses/validate
personas: []
provider_name: United States Postal Service
provider_slug: united-states-postal-service
search_terms:
- logistics
- get tracking status for a package.
- validate a delivery address.
- customer-facing delivery inquiry and address validation support
- validate address
- get tracking status and scan event history for a usps package by tracking number.
- ecommerce developer
- online retail shipping and fulfillment operations
- track a usps package.
- package tracking and delivery status monitoring for customer service and logistics
- get multiple tracking
- package tracking
- validate address.
- track multiple usps packages.
- operations manager overseeing fulfillment and carrier pickup scheduling
- validate delivery address
- manager monitoring shipment delivery performance and address quality
- get tracking
- e-commerce shipping lifecycle from address validation through rate shopping to pickup scheduling
- customer service agent
- package tracking and delivery status monitoring
- order fulfillment and shipping label generation operations
- government
- postal service
- developer integrating usps shipping into an online store or marketplace
- usps
- validate and standardize a delivery address to ensure usps deliverability.
- agent assisting customers with package status and delivery inquiries
- track package
- logistics manager
- address validation
- customer service
- get tracking status for multiple usps packages in a single request.
- shipping manager
- shipping
- track multiple packages.
- track multiple packages
slug: package-tracking
source_filename: package-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USPS Package Tracking\n  description: Workflow capability for package tracking and delivery status monitoring. Combines the USPS Tracking API with\n    address validation to support customer service teams and logistics operations tracking USPS shipments.\n  tags:\n  - USPS\n  - Package Tracking\n  - Logistics\n  - Customer Service\n  - Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    USPS_BEARER_TOKEN: USPS_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: usps-tracking\n    baseUri: https://apis.usps.com\n    description: USPS package tracking API.\n    authentication:\n      type: bearer\n      token: '{{USPS_BEARER_TOKEN}}'\n    resources:\n    - name: tracking\n      path: /tracking/v3/tracking\n      description: Package tracking status and event history.\n      operations:\n      - name: get-tracking\n        method: GET\n        description: Get tracking status\
  \ for a package.\n        inputParameters:\n        - name: trackingNumber\n          in: path\n          type: string\n          required: true\n          description: USPS tracking number.\n        - name: expand\n          in: query\n          type: string\n          required: false\n          description: Optional expansion (SUMMARY or DETAIL).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-multiple-tracking\n        method: POST\n        description: Get tracking status for multiple packages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            trackingNumbers: '{{tools.trackingNumbers}}'\n  - type: http\n    namespace: usps-addresses\n    baseUri: https://apis.usps.com\n    description: USPS address validation and standardization API.\n    authentication:\n\
  \      type: bearer\n      token: '{{USPS_BEARER_TOKEN}}'\n    resources:\n    - name: address\n      path: /addresses/v3/address\n      description: Address validation and standardization.\n      operations:\n      - name: validate-address\n        method: GET\n        description: Validates and standardizes a US address to USPS specifications.\n        inputParameters:\n        - name: streetAddress\n          in: query\n          type: string\n          required: true\n          description: Primary street address line.\n        - name: city\n          in: query\n          type: string\n          required: false\n          description: City name.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: Two-letter state abbreviation.\n        - name: ZIPCode\n          in: query\n          type: string\n          required: false\n          description: 5-digit ZIP Code.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: city-state\n      path: /addresses/v3/city-state\n      description: City and state lookup by ZIP Code.\n      operations:\n      - name: get-city-state\n        method: GET\n        description: Returns the city and state for a given ZIP Code.\n        inputParameters:\n        - name: ZIPCode\n          in: query\n          type: string\n          required: true\n          description: 5-digit ZIP Code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zipcode\n      path: /addresses/v3/zipcode\n      description: ZIP Code lookup by address.\n      operations:\n      - name: get-zip-code\n        method: GET\n        description: Returns ZIP Code for a given address.\n        inputParameters:\n        - name: streetAddress\n          in: query\n          type: string\n          required: true\n          description:\
  \ Primary street address.\n        - name: city\n          in: query\n          type: string\n          required: true\n          description: City name.\n        - name: state\n          in: query\n          type: string\n          required: true\n          description: Two-letter state abbreviation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: usps-package-tracking-api\n    description: Unified REST API for USPS package tracking and delivery monitoring.\n    resources:\n    - path: /v1/tracking/{trackingNumber}\n      name: package-tracking\n      description: Get tracking status for a package.\n      operations:\n      - method: GET\n        name: get-tracking\n        description: Track a USPS package.\n        call: usps-tracking.get-tracking\n        with:\n          trackingNumber: rest.trackingNumber\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/tracking\n      name: bulk-tracking\n      description: Track multiple packages.\n      operations:\n      - method: POST\n        name: get-multiple-tracking\n        description: Track multiple USPS packages.\n        call: usps-tracking.get-multiple-tracking\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses/validate\n      name: address-validation\n      description: Validate a delivery address.\n      operations:\n      - method: GET\n        name: validate-address\n        description: Validate address.\n        call: usps-addresses.validate-address\n        with:\n          streetAddress: rest.streetAddress\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: usps-package-tracking-mcp\n    transport: http\n    description: MCP server for AI-assisted USPS package tracking and delivery status.\n    tools:\n   \
  \ - name: track-package\n      description: Get tracking status and scan event history for a USPS package by tracking number.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-tracking.get-tracking\n      with:\n        trackingNumber: tools.trackingNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-multiple-packages\n      description: Get tracking status for multiple USPS packages in a single request.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-tracking.get-multiple-tracking\n      with:\n        trackingNumbers: tools.trackingNumbers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-delivery-address\n      description: Validate and standardize a delivery address to ensure USPS deliverability.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: usps-addresses.validate-address\n      with:\n        streetAddress:\
  \ tools.streetAddress\n        city: tools.city\n        state: tools.state\n        ZIPCode: tools.ZIPCode\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-postal-service/refs/heads/main/capabilities/package-tracking.yaml
tags:
- USPS
- Package Tracking
- Logistics
- Customer Service
- Government
tools:
- description: Get tracking status and scan event history for a USPS package by tracking number.
  hints:
    openWorld: true
    readOnly: true
  name: track-package
- description: Get tracking status for multiple USPS packages in a single request.
  hints:
    openWorld: true
    readOnly: true
  name: track-multiple-packages
- description: Validate and standardize a delivery address to ensure USPS deliverability.
  hints:
    openWorld: true
    readOnly: true
  name: validate-delivery-address
---
