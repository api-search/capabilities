---
api_specs:
- filename: telefono-validation-openapi.yml
  format: yaml
  label: telefono
  slug: telefono
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/telefono/refs/heads/main/openapi/telefono-validation-openapi.yml
categories: []
consumed_apis:
- telefono
description: Unified phone number intelligence capability combining validation, carrier lookup, and number formatting APIs. Designed for developers building fraud prevention, user verification, data enrichment, and SMS campaign optimization workflows.
layout: capability
name: Telefono Phone Intelligence
operations:
- description: Validate a phone number and get type, carrier, country, and format
  method: GET
  name: validate-number
  path: /v1/validate
- description: Validate up to 100 phone numbers in one request
  method: POST
  name: validate-batch
  path: /v1/validate/batch
- description: Look up carrier information for a phone number
  method: GET
  name: lookup-carrier
  path: /v1/carrier
- description: Format a phone number into multiple standard formats
  method: GET
  name: format-number
  path: /v1/format
personas: []
provider_name: Telefono
provider_slug: telefono
search_terms:
- validate batch
- format number
- carrier and network information lookup
- number intelligence
- batch phone number validation
- phone number format conversion
- phone validation
- look up the mobile carrier, network type (gsm/lte/5g), mcc, mnc, and portability status for a phone number
- validate phone number
- carrier lookup
- validate number
- format a phone number into multiple standard formats
- validate a phone number and get type, carrier, country, and format
- validate a list of up to 100 phone numbers in a single batch request
- lookup carrier
- validate up to 100 phone numbers in one request
- validate a phone number and check if it is valid, reachable, mobile/landline/voip, and get the carrier and country
- data enrichment
- parse and reformat a phone number into e.164, national, international, and rfc3966 formats
- batch validate numbers
- look up carrier information for a phone number
- phone lookup
- telecommunications
- fraud prevention
- real-time phone number validation
- number verification
slug: phone-intelligence
source_filename: phone-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Telefono Phone Intelligence\"\n  description: >-\n    Unified phone number intelligence capability combining validation, carrier lookup,\n    and number formatting APIs. Designed for developers building fraud prevention,\n    user verification, data enrichment, and SMS campaign optimization workflows.\n  tags:\n    - Carrier Lookup\n    - Data Enrichment\n    - Fraud Prevention\n    - Number Intelligence\n    - Phone Validation\n    - Telecommunications\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TELEFONO_API_KEY: TELEFONO_API_KEY\n\ncapability:\n  consumes:\n    - import: telefono\n      location: ./shared/telefono-validation.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: phone-intelligence-api\n      description: \"Unified REST API for phone number intelligence — validation, carrier lookup, and formatting.\"\n      resources:\n        - path:\
  \ /v1/validate\n          name: validate\n          description: \"Real-time phone number validation\"\n          operations:\n            - method: GET\n              name: validate-number\n              description: \"Validate a phone number and get type, carrier, country, and format\"\n              call: \"telefono.validate-phone-number\"\n              with:\n                number: \"rest.number\"\n                country_code: \"rest.country_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/validate/batch\n          name: validate-batch\n          description: \"Batch phone number validation\"\n          operations:\n            - method: POST\n              name: validate-batch\n              description: \"Validate up to 100 phone numbers in one request\"\n              call: \"telefono.validate-phone-number-batch\"\n              with:\n                numbers: \"rest.numbers\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/carrier\n          name: carrier\n          description: \"Carrier and network information lookup\"\n          operations:\n            - method: GET\n              name: lookup-carrier\n              description: \"Look up carrier information for a phone number\"\n              call: \"telefono.lookup-carrier\"\n              with:\n                number: \"rest.number\"\n                hlr: \"rest.hlr\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/format\n          name: format\n          description: \"Phone number format conversion\"\n          operations:\n            - method: GET\n              name: format-number\n              description: \"Format a phone number into multiple standard formats\"\n              call: \"telefono.format-phone-number\"\n              with:\n                number: \"rest.number\"\n\
  \                country_code: \"rest.country_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: phone-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted phone number intelligence, validation, and data enrichment.\"\n      tools:\n        - name: validate-phone-number\n          description: \"Validate a phone number and check if it is valid, reachable, mobile/landline/VoIP, and get the carrier and country\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"telefono.validate-phone-number\"\n          with:\n            number: \"tools.number\"\n            country_code: \"tools.country_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-validate-numbers\n          description: \"Validate a list of up to 100 phone numbers in a single\
  \ batch request\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"telefono.validate-phone-number-batch\"\n          with:\n            numbers: \"tools.numbers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lookup-carrier\n          description: \"Look up the mobile carrier, network type (GSM/LTE/5G), MCC, MNC, and portability status for a phone number\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"telefono.lookup-carrier\"\n          with:\n            number: \"tools.number\"\n            hlr: \"tools.hlr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: format-number\n          description: \"Parse and reformat a phone number into E.164, national, international, and RFC3966 formats\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"telefono.format-phone-number\"\n          with:\n            number: \"tools.number\"\n            country_code: \"tools.country_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/telefono/refs/heads/main/capabilities/phone-intelligence.yaml
tags:
- Carrier Lookup
- Data Enrichment
- Fraud Prevention
- Number Intelligence
- Phone Validation
- Telecommunications
tools:
- description: Validate a phone number and check if it is valid, reachable, mobile/landline/VoIP, and get the carrier and country
  hints:
    openWorld: true
    readOnly: true
  name: validate-phone-number
- description: Validate a list of up to 100 phone numbers in a single batch request
  hints:
    openWorld: true
    readOnly: true
  name: batch-validate-numbers
- description: Look up the mobile carrier, network type (GSM/LTE/5G), MCC, MNC, and portability status for a phone number
  hints:
    openWorld: true
    readOnly: true
  name: lookup-carrier
- description: Parse and reformat a phone number into E.164, national, international, and RFC3966 formats
  hints:
    openWorld: false
    readOnly: true
  name: format-number
---
