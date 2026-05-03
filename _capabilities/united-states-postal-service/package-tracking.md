---
categories: []
consumed_apis:
- usps-tracking
- usps-addresses
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
- validate address
- validate delivery address
- customer-facing delivery inquiry and address validation support
- ecommerce developer
- postal service
- track multiple packages
- get multiple tracking
- agent assisting customers with package status and delivery inquiries
- government
- customer service agent
- get tracking
- package tracking and delivery status monitoring for customer service and logistics
- developer integrating usps shipping into an online store or marketplace
- track multiple usps packages.
- validate a delivery address.
- package tracking
- track a usps package.
- validate address.
- get tracking status and scan event history for a usps package by tracking number.
- package tracking and delivery status monitoring
- e-commerce shipping lifecycle from address validation through rate shopping to pickup scheduling
- logistics manager
- address validation
- manager monitoring shipment delivery performance and address quality
- customer service
- order fulfillment and shipping label generation operations
- track multiple packages.
- operations manager overseeing fulfillment and carrier pickup scheduling
- shipping
- get tracking status for a package.
- logistics
- track package
- get tracking status for multiple usps packages in a single request.
- validate and standardize a delivery address to ensure usps deliverability.
- online retail shipping and fulfillment operations
- shipping manager
- usps
slug: package-tracking
source_filename: package-tracking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USPS Package Tracking\"\n  description: >-\n    Workflow capability for package tracking and delivery status monitoring.\n    Combines the USPS Tracking API with address validation to support customer\n    service teams and logistics operations tracking USPS shipments.\n  tags:\n    - USPS\n    - Package Tracking\n    - Logistics\n    - Customer Service\n    - Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      USPS_BEARER_TOKEN: USPS_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: usps-tracking\n      location: ./shared/tracking.yaml\n    - import: usps-addresses\n      location: ./shared/addresses.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: usps-package-tracking-api\n      description: \"Unified REST API for USPS package tracking and delivery monitoring.\"\n      resources:\n        - path: /v1/tracking/{trackingNumber}\n      \
  \    name: package-tracking\n          description: \"Get tracking status for a package.\"\n          operations:\n            - method: GET\n              name: get-tracking\n              description: \"Track a USPS package.\"\n              call: \"usps-tracking.get-tracking\"\n              with:\n                trackingNumber: \"rest.trackingNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tracking\n          name: bulk-tracking\n          description: \"Track multiple packages.\"\n          operations:\n            - method: POST\n              name: get-multiple-tracking\n              description: \"Track multiple USPS packages.\"\n              call: \"usps-tracking.get-multiple-tracking\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/addresses/validate\n          name: address-validation\n          description: \"Validate\
  \ a delivery address.\"\n          operations:\n            - method: GET\n              name: validate-address\n              description: \"Validate address.\"\n              call: \"usps-addresses.validate-address\"\n              with:\n                streetAddress: \"rest.streetAddress\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: usps-package-tracking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted USPS package tracking and delivery status.\"\n      tools:\n        - name: track-package\n          description: \"Get tracking status and scan event history for a USPS package by tracking number.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-tracking.get-tracking\"\n          with:\n            trackingNumber: \"tools.trackingNumber\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: track-multiple-packages\n          description: \"Get tracking status for multiple USPS packages in a single request.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-tracking.get-multiple-tracking\"\n          with:\n            trackingNumbers: \"tools.trackingNumbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-delivery-address\n          description: \"Validate and standardize a delivery address to ensure USPS deliverability.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"usps-addresses.validate-address\"\n          with:\n            streetAddress: \"tools.streetAddress\"\n            city: \"tools.city\"\n            state: \"tools.state\"\n            ZIPCode: \"tools.ZIPCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n"
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
