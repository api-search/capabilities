---
categories: []
consumed_apis: []
description: The Horoscope API provides daily, weekly, and monthly horoscope predictions for each zodiac sign, delivering personalized astrological insights in JSON format.
layout: capability
name: Horoscope API
operations:
- description: Get Daily Horoscope
  method: GET
  name: getdailyhoroscope
  path: /api/v1/get-horoscope/daily
- description: Get Weekly Horoscope
  method: GET
  name: getweeklyhoroscope
  path: /api/v1/get-horoscope/weekly
- description: Get Monthly Horoscope
  method: GET
  name: getmonthlyhoroscope
  path: /api/v1/get-horoscope/monthly
personas: []
provider_name: Horoscope API
provider_slug: horoscope-api
search_terms:
- getweeklyhoroscope
- zodiac
- get daily horoscope
- get monthly horoscope
- horoscope
- getdailyhoroscope
- get weekly horoscope
- getmonthlyhoroscope
- api
- astrology
- content
slug: horoscope-api-capability
source_filename: horoscope-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Horoscope API\n  description: The Horoscope API provides daily, weekly, and monthly horoscope predictions for each zodiac sign, delivering\n    personalized astrological insights in JSON format.\n  tags:\n  - Horoscope\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: horoscope-api\n    baseUri: https://freehoroscopeapi.com\n    description: Horoscope API HTTP API.\n    resources:\n    - name: api-v1-get-horoscope-daily\n      path: /api/v1/get-horoscope/daily\n      operations:\n      - name: getdailyhoroscope\n        method: GET\n        description: Get Daily Horoscope\n        inputParameters:\n        - name: sign\n          in: query\n          type: string\n          required: true\n          description: Zodiac sign (case-insensitive).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: api-v1-get-horoscope-weekly\n      path: /api/v1/get-horoscope/weekly\n      operations:\n      - name: getweeklyhoroscope\n        method: GET\n        description: Get Weekly Horoscope\n        inputParameters:\n        - name: sign\n          in: query\n          type: string\n          required: true\n          description: Zodiac sign (case-insensitive).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-get-horoscope-monthly\n      path: /api/v1/get-horoscope/monthly\n      operations:\n      - name: getmonthlyhoroscope\n        method: GET\n        description: Get Monthly Horoscope\n        inputParameters:\n        - name: sign\n          in: query\n          type: string\n          required: true\n          description: Zodiac sign (case-insensitive).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: horoscope-api-rest\n    description: REST adapter for Horoscope API.\n    resources:\n    - path: /api/v1/get-horoscope/daily\n      name: getdailyhoroscope\n      operations:\n      - method: GET\n        name: getdailyhoroscope\n        description: Get Daily Horoscope\n        call: horoscope-api.getdailyhoroscope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/get-horoscope/weekly\n      name: getweeklyhoroscope\n      operations:\n      - method: GET\n        name: getweeklyhoroscope\n        description: Get Weekly Horoscope\n        call: horoscope-api.getweeklyhoroscope\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/get-horoscope/monthly\n      name: getmonthlyhoroscope\n      operations:\n      - method: GET\n        name: getmonthlyhoroscope\n        description: Get Monthly Horoscope\n        call: horoscope-api.getmonthlyhoroscope\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: horoscope-api-mcp\n    transport: http\n    description: MCP adapter for Horoscope API for AI agent use.\n    tools:\n    - name: getdailyhoroscope\n      description: Get Daily Horoscope\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: horoscope-api.getdailyhoroscope\n      with:\n        sign: tools.sign\n      inputParameters:\n      - name: sign\n        type: string\n        description: Zodiac sign (case-insensitive).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getweeklyhoroscope\n      description: Get Weekly Horoscope\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: horoscope-api.getweeklyhoroscope\n      with:\n        sign: tools.sign\n      inputParameters:\n      - name: sign\n       \
  \ type: string\n        description: Zodiac sign (case-insensitive).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmonthlyhoroscope\n      description: Get Monthly Horoscope\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: horoscope-api.getmonthlyhoroscope\n      with:\n        sign: tools.sign\n      inputParameters:\n      - name: sign\n        type: string\n        description: Zodiac sign (case-insensitive).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/horoscope-api/refs/heads/main/capabilities/horoscope-api-capability.yaml
tags:
- Horoscope
- Api
- API
tools:
- description: Get Daily Horoscope
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdailyhoroscope
- description: Get Weekly Horoscope
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getweeklyhoroscope
- description: Get Monthly Horoscope
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonthlyhoroscope
---
