---
categories: []
consumed_apis: []
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
- data enrichment
- validate up to 100 phone numbers in one request
- parse and reformat a phone number into e.164, national, international, and rfc3966 formats
- fraud prevention
- look up carrier information for a phone number
- format number
- validate phone number
- phone validation
- number verification
- phone number format conversion
- look up the mobile carrier, network type (gsm/lte/5g), mcc, mnc, and portability status for a phone number
- number intelligence
- carrier lookup
- real-time phone number validation
- telecommunications
- batch phone number validation
- validate batch
- format a phone number into multiple standard formats
- lookup carrier
- validate a phone number and get type, carrier, country, and format
- validate a list of up to 100 phone numbers in a single batch request
- validate a phone number and check if it is valid, reachable, mobile/landline/voip, and get the carrier and country
- validate number
- batch validate numbers
- carrier and network information lookup
- phone lookup
slug: phone-intelligence
source_filename: phone-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Telefono Phone Intelligence\n  description: Unified phone number intelligence capability combining validation, carrier lookup, and number formatting APIs.\n    Designed for developers building fraud prevention, user verification, data enrichment, and SMS campaign optimization workflows.\n  tags:\n  - Carrier Lookup\n  - Data Enrichment\n  - Fraud Prevention\n  - Number Intelligence\n  - Phone Validation\n  - Telecommunications\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TELEFONO_API_KEY: TELEFONO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: telefono\n    baseUri: https://api.telefono.com/v1\n    description: Telefono phone number intelligence and validation API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{TELEFONO_API_KEY}}'\n      placement: header\n    resources:\n    - name: validate\n      path: /validate\n      description: Phone\
  \ number validation\n      operations:\n      - name: validate-phone-number\n        method: GET\n        description: Validate a phone number and get type, carrier, and format data\n        inputParameters:\n        - name: number\n          in: query\n          type: string\n          required: true\n          description: Phone number to validate\n        - name: country_code\n          in: query\n          type: string\n          required: false\n          description: ISO country code hint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: validate-phone-number-batch\n        method: POST\n        description: Batch validate up to 100 phone numbers\n        inputParameters:\n        - name: numbers\n          in: body\n          type: array\n          required: true\n          description: Array of numbers to validate\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: carrier\n      path: /carrier\n      description: Carrier and network lookup\n      operations:\n      - name: lookup-carrier\n        method: GET\n        description: Look up carrier and network info for a phone number\n        inputParameters:\n        - name: number\n          in: query\n          type: string\n          required: true\n          description: Phone number in E.164 format\n        - name: hlr\n          in: query\n          type: boolean\n          required: false\n          description: Perform real-time HLR lookup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: format\n      path: /format\n      description: Phone number formatting\n      operations:\n      - name: format-phone-number\n        method: GET\n        description: Format a phone number into E.164, national, international, and RFC3966 formats\n \
  \       inputParameters:\n        - name: number\n          in: query\n          type: string\n          required: true\n          description: Phone number to format\n        - name: country_code\n          in: query\n          type: string\n          required: false\n          description: Country code hint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: phone-intelligence-api\n    description: Unified REST API for phone number intelligence — validation, carrier lookup, and formatting.\n    resources:\n    - path: /v1/validate\n      name: validate\n      description: Real-time phone number validation\n      operations:\n      - method: GET\n        name: validate-number\n        description: Validate a phone number and get type, carrier, country, and format\n        call: telefono.validate-phone-number\n        with:\n          number: rest.number\n\
  \          country_code: rest.country_code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/validate/batch\n      name: validate-batch\n      description: Batch phone number validation\n      operations:\n      - method: POST\n        name: validate-batch\n        description: Validate up to 100 phone numbers in one request\n        call: telefono.validate-phone-number-batch\n        with:\n          numbers: rest.numbers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carrier\n      name: carrier\n      description: Carrier and network information lookup\n      operations:\n      - method: GET\n        name: lookup-carrier\n        description: Look up carrier information for a phone number\n        call: telefono.lookup-carrier\n        with:\n          number: rest.number\n          hlr: rest.hlr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/format\n    \
  \  name: format\n      description: Phone number format conversion\n      operations:\n      - method: GET\n        name: format-number\n        description: Format a phone number into multiple standard formats\n        call: telefono.format-phone-number\n        with:\n          number: rest.number\n          country_code: rest.country_code\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: phone-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted phone number intelligence, validation, and data enrichment.\n    tools:\n    - name: validate-phone-number\n      description: Validate a phone number and check if it is valid, reachable, mobile/landline/VoIP, and get the carrier\n        and country\n      hints:\n        readOnly: true\n        openWorld: true\n      call: telefono.validate-phone-number\n      with:\n        number: tools.number\n        country_code: tools.country_code\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-validate-numbers\n      description: Validate a list of up to 100 phone numbers in a single batch request\n      hints:\n        readOnly: true\n        openWorld: true\n      call: telefono.validate-phone-number-batch\n      with:\n        numbers: tools.numbers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-carrier\n      description: Look up the mobile carrier, network type (GSM/LTE/5G), MCC, MNC, and portability status for a phone number\n      hints:\n        readOnly: true\n        openWorld: true\n      call: telefono.lookup-carrier\n      with:\n        number: tools.number\n        hlr: tools.hlr\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: format-number\n      description: Parse and reformat a phone number into E.164, national, international, and RFC3966 formats\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: telefono.format-phone-number\n      with:\n        number: tools.number\n        country_code: tools.country_code\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
