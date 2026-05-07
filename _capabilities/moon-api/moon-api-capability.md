---
categories: []
consumed_apis: []
description: API for retrieving detailed moon phase data, sun data, calendars, and astronomical information
layout: capability
name: Moon-API.com
operations:
- description: Get basic moon phase information
  method: GET
  name: get-basic
  path: /basic
- description: Get detailed moon and sun data (MEGA plan)
  method: GET
  name: get-advanced
  path: /advanced
- description: Get astrology data (natal chart and planetary positions)
  method: GET
  name: get-astrology
  path: /astrology
- description: Get moon phase information only
  method: GET
  name: get-phase
  path: /phase
- description: Get current moon phase emoji (plain text)
  method: GET
  name: get-emoji
  path: /emoji
- description: Get moon phase name (plain text)
  method: GET
  name: get-plain-text
  path: /plain-text
- description: Get moon and sun data calendar
  method: GET
  name: get-calendar
  path: /calendar
personas: []
provider_name: Moon-API
provider_slug: moon-api
search_terms:
- get emoji
- space
- get basic
- api
- lunar
- get plain text
- get basic moon phase information
- get calendar
- moon phases
- get advanced
- get detailed moon and sun data (mega plan)
- get moon and sun data calendar
- get moon phase information only
- get moon phase name (plain text)
- get phase
- get astrology
- astronomy
- get astrology data (natal chart and planetary positions)
- moon
- astrology
- get current moon phase emoji (plain text)
slug: moon-api-capability
source_filename: moon-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Moon-API.com\n  description: API for retrieving detailed moon phase data, sun data, calendars, and astronomical information\n  tags:\n  - Moon\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: moon-api\n    baseUri: https://moon-phase.p.rapidapi.com\n    description: Moon-API.com HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-rapidapi-key\n      value: '{{MOON_API_TOKEN}}'\n    resources:\n    - name: basic\n      path: /basic\n      operations:\n      - name: get-basic\n        method: GET\n        description: Get basic moon phase information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: advanced\n      path: /advanced\n      operations:\n      - name: get-advanced\n        method: GET\n        description: Get detailed moon and\
  \ sun data (MEGA plan)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: astrology\n      path: /astrology\n      operations:\n      - name: get-astrology\n        method: GET\n        description: Get astrology data (natal chart and planetary positions)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phase\n      path: /phase\n      operations:\n      - name: get-phase\n        method: GET\n        description: Get moon phase information only\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emoji\n      path: /emoji\n      operations:\n      - name: get-emoji\n        method: GET\n        description: Get current moon phase emoji (plain text)\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: plain-text\n      path: /plain-text\n      operations:\n      - name: get-plain-text\n        method: GET\n        description: Get moon phase name (plain text)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calendar\n      path: /calendar\n      operations:\n      - name: get-calendar\n        method: GET\n        description: Get moon and sun data calendar\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          description: Start date (YYYY-MM-DD)\n        - name: end_date\n          in: query\n          type: string\n          description: End date (YYYY-MM-DD)\n        - name: days\n          in: query\n          type: integer\n          description: 'Number of days from today (if dates not provided, default: 30)'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: moon-api-rest\n    description: REST adapter for Moon-API.com.\n    resources:\n    - path: /basic\n      name: get-basic\n      operations:\n      - method: GET\n        name: get-basic\n        description: Get basic moon phase information\n        call: moon-api.get-basic\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /advanced\n      name: get-advanced\n      operations:\n      - method: GET\n        name: get-advanced\n        description: Get detailed moon and sun data (MEGA plan)\n        call: moon-api.get-advanced\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /astrology\n      name: get-astrology\n      operations:\n      - method: GET\n        name: get-astrology\n        description: Get astrology data (natal chart and planetary positions)\n        call: moon-api.get-astrology\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /phase\n      name: get-phase\n      operations:\n      - method: GET\n        name: get-phase\n        description: Get moon phase information only\n        call: moon-api.get-phase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /emoji\n      name: get-emoji\n      operations:\n      - method: GET\n        name: get-emoji\n        description: Get current moon phase emoji (plain text)\n        call: moon-api.get-emoji\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plain-text\n      name: get-plain-text\n      operations:\n      - method: GET\n        name: get-plain-text\n        description: Get moon phase name (plain text)\n        call: moon-api.get-plain-text\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /calendar\n      name: get-calendar\n      operations:\n      - method:\
  \ GET\n        name: get-calendar\n        description: Get moon and sun data calendar\n        call: moon-api.get-calendar\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: moon-api-mcp\n    transport: http\n    description: MCP adapter for Moon-API.com for AI agent use.\n    tools:\n    - name: get-basic\n      description: Get basic moon phase information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-basic\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-advanced\n      description: Get detailed moon and sun data (MEGA plan)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-advanced\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-astrology\n      description: Get astrology data (natal chart and planetary\
  \ positions)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-astrology\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-phase\n      description: Get moon phase information only\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-phase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-emoji\n      description: Get current moon phase emoji (plain text)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-emoji\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plain-text\n      description: Get moon phase name (plain text)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-plain-text\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-calendar\n      description: Get moon and sun data calendar\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: moon-api.get-calendar\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n        days: tools.days\n      inputParameters:\n      - name: start_date\n        type: string\n        description: Start date (YYYY-MM-DD)\n      - name: end_date\n        type: string\n        description: End date (YYYY-MM-DD)\n      - name: days\n        type: integer\n        description: 'Number of days from today (if dates not provided, default: 30)'\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MOON_API_TOKEN: MOON_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/moon-api/refs/heads/main/capabilities/moon-api-capability.yaml
tags:
- Moon
- Api
- API
tools:
- description: Get basic moon phase information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-basic
- description: Get detailed moon and sun data (MEGA plan)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-advanced
- description: Get astrology data (natal chart and planetary positions)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-astrology
- description: Get moon phase information only
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-phase
- description: Get current moon phase emoji (plain text)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-emoji
- description: Get moon phase name (plain text)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-plain-text
- description: Get moon and sun data calendar
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-calendar
---
