---
categories: []
consumed_apis:
- sinch-numbers
description: Unified number management workflow combining the Sinch Numbers API with brand and registration management for compliant business messaging. Used by operations teams and developers provisioning phone numbers, registering sender IDs, and managing messaging compliance requirements.
layout: capability
name: Sinch Number Management
operations:
- description: Search for available numbers by country and type
  method: GET
  name: search-available-numbers
  path: /v1/numbers/available
- description: List all active phone numbers
  method: GET
  name: list-active-numbers
  path: /v1/numbers/active
- description: Rent a phone number matching specified criteria
  method: POST
  name: rent-phone-number
  path: /v1/numbers/active
personas: []
provider_name: Sinch
provider_slug: sinch
search_terms:
- numbers
- list active numbers
- verification
- voice
- manage active phone numbers
- search for available phone numbers
- search available numbers
- sms
- messaging
- communications
- brands
- compliance
- search phone numbers
- list all active phone numbers
- rent phone number
- provisioning
- search for available phone numbers by country code and type (local, toll-free, mobile)
- registration
- search for available numbers by country and type
- list all phone numbers currently rented in the project
- rent a phone number matching the specified country and type requirements
- cpaas
- phone numbers
- rent a phone number matching specified criteria
slug: number-management
source_filename: number-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sinch Number Management\"\n  description: >-\n    Unified number management workflow combining the Sinch Numbers API with\n    brand and registration management for compliant business messaging.\n    Used by operations teams and developers provisioning phone numbers,\n    registering sender IDs, and managing messaging compliance requirements.\n  tags:\n    - Numbers\n    - Phone Numbers\n    - Provisioning\n    - Compliance\n    - Brands\n    - Registration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SINCH_API_TOKEN: SINCH_API_TOKEN\n      SINCH_PROJECT_ID: SINCH_PROJECT_ID\n\ncapability:\n  consumes:\n    - import: sinch-numbers\n      location: ./shared/numbers.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: number-management-api\n      description: \"Unified REST API for Sinch phone number provisioning and compliance management.\"\n      resources:\n\
  \        - path: /v1/numbers/available\n          name: available-numbers\n          description: Search for available phone numbers\n          operations:\n            - method: GET\n              name: search-available-numbers\n              description: Search for available numbers by country and type\n              call: \"sinch-numbers.list-available-numbers\"\n              with:\n                regionCode: \"rest.regionCode\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/numbers/active\n          name: active-numbers\n          description: Manage active phone numbers\n          operations:\n            - method: GET\n              name: list-active-numbers\n              description: List all active phone numbers\n              call: \"sinch-numbers.list-active-numbers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n            - method: POST\n              name: rent-phone-number\n              description: Rent a phone number matching specified criteria\n              call: \"sinch-numbers.rent-any-number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: number-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted phone number provisioning and management.\"\n      tools:\n        - name: search-phone-numbers\n          description: Search for available phone numbers by country code and type (local, toll-free, mobile)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sinch-numbers.list-available-numbers\"\n          with:\n            regionCode: \"tools.regionCode\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-active-numbers\n\
  \          description: List all phone numbers currently rented in the project\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sinch-numbers.list-active-numbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rent-phone-number\n          description: Rent a phone number matching the specified country and type requirements\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"sinch-numbers.rent-any-number\"\n          with:\n            regionCode: \"tools.regionCode\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sinch/refs/heads/main/capabilities/number-management.yaml
tags:
- Numbers
- Phone Numbers
- Provisioning
- Compliance
- Brands
- Registration
tools:
- description: Search for available phone numbers by country code and type (local, toll-free, mobile)
  hints:
    openWorld: true
    readOnly: true
  name: search-phone-numbers
- description: List all phone numbers currently rented in the project
  hints:
    openWorld: false
    readOnly: true
  name: list-active-numbers
- description: Rent a phone number matching the specified country and type requirements
  hints:
    destructive: false
    readOnly: false
  name: rent-phone-number
---
