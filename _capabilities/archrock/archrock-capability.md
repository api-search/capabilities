---
categories: []
consumed_apis: []
description: API providing access to Archrock investor relations data including financial reports, compression fleet statistics, SEC filings, and operational performance metrics.
layout: capability
name: Archrock Investor Relations API
operations:
- description: Get quarterly financial results
  method: GET
  name: getquarterlyfinancials
  path: /financials/quarterly
- description: Get compression fleet statistics
  method: GET
  name: getfleetstatistics
  path: /fleet/statistics
- description: List compression equipment
  method: GET
  name: listequipment
  path: /fleet/equipment
- description: List SEC filings
  method: GET
  name: listsecfilings
  path: /sec-filings
- description: Get operational performance metrics
  method: GET
  name: getoperationalmetrics
  path: /operations/metrics
personas: []
provider_name: Archrock
provider_slug: archrock
search_terms:
- getquarterlyfinancials
- industrial
- getoperationalmetrics
- compression services
- getfleetstatistics
- get quarterly financial results
- get operational performance metrics
- listequipment
- oil and gas
- list sec filings
- energy
- 'nyse: aroc'
- archrock
- api
- natural gas
- listsecfilings
- get compression fleet statistics
- list compression equipment
slug: archrock-capability
source_filename: archrock-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Archrock Investor Relations API\n  description: API providing access to Archrock investor relations data including financial reports, compression fleet statistics,\n    SEC filings, and operational performance metrics.\n  tags:\n  - Archrock\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: archrock\n    baseUri: https://api.archrock.com/v1\n    description: Archrock Investor Relations API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{ARCHROCK_TOKEN}}'\n    resources:\n    - name: financials-quarterly\n      path: /financials/quarterly\n      operations:\n      - name: getquarterlyfinancials\n        method: GET\n        description: Get quarterly financial results\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n          description: Fiscal year\n        - name:\
  \ quarter\n          in: query\n          type: integer\n          description: Fiscal quarter (1-4)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fleet-statistics\n      path: /fleet/statistics\n      operations:\n      - name: getfleetstatistics\n        method: GET\n        description: Get compression fleet statistics\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n        - name: quarter\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fleet-equipment\n      path: /fleet/equipment\n      operations:\n      - name: listequipment\n        method: GET\n        description: List compression equipment\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: limit\n\
  \          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sec-filings\n      path: /sec-filings\n      operations:\n      - name: listsecfilings\n        method: GET\n        description: List SEC filings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        - name: year\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-metrics\n      path: /operations/metrics\n      operations:\n      - name: getoperationalmetrics\n        method: GET\n        description: Get operational\
  \ performance metrics\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n        - name: quarter\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: archrock-rest\n    description: REST adapter for Archrock Investor Relations API.\n    resources:\n    - path: /financials/quarterly\n      name: getquarterlyfinancials\n      operations:\n      - method: GET\n        name: getquarterlyfinancials\n        description: Get quarterly financial results\n        call: archrock.getquarterlyfinancials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fleet/statistics\n      name: getfleetstatistics\n      operations:\n      - method: GET\n        name: getfleetstatistics\n        description: Get compression fleet statistics\n        call:\
  \ archrock.getfleetstatistics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fleet/equipment\n      name: listequipment\n      operations:\n      - method: GET\n        name: listequipment\n        description: List compression equipment\n        call: archrock.listequipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sec-filings\n      name: listsecfilings\n      operations:\n      - method: GET\n        name: listsecfilings\n        description: List SEC filings\n        call: archrock.listsecfilings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/metrics\n      name: getoperationalmetrics\n      operations:\n      - method: GET\n        name: getoperationalmetrics\n        description: Get operational performance metrics\n        call: archrock.getoperationalmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9090\n    namespace: archrock-mcp\n    transport: http\n    description: MCP adapter for Archrock Investor Relations API for AI agent use.\n    tools:\n    - name: getquarterlyfinancials\n      description: Get quarterly financial results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archrock.getquarterlyfinancials\n      with:\n        year: tools.year\n        quarter: tools.quarter\n      inputParameters:\n      - name: year\n        type: integer\n        description: Fiscal year\n      - name: quarter\n        type: integer\n        description: Fiscal quarter (1-4)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfleetstatistics\n      description: Get compression fleet statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archrock.getfleetstatistics\n      with:\n        year: tools.year\n        quarter: tools.quarter\n\
  \      inputParameters:\n      - name: year\n        type: integer\n        description: year\n      - name: quarter\n        type: integer\n        description: quarter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listequipment\n      description: List compression equipment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archrock.listequipment\n      with:\n        status: tools.status\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsecfilings\n      description: List SEC filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: archrock.listsecfilings\n      with:\n        type: tools.type\n        year: tools.year\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      - name: year\n        type: integer\n        description: year\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperationalmetrics\n      description: Get operational performance metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: archrock.getoperationalmetrics\n      with:\n        year: tools.year\n        quarter: tools.quarter\n      inputParameters:\n      - name: year\n        type: integer\n        description: year\n      - name: quarter\n        type: integer\n        description:\
  \ quarter\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCHROCK_TOKEN: ARCHROCK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/archrock/refs/heads/main/capabilities/archrock-capability.yaml
tags:
- Archrock
- API
tools:
- description: Get quarterly financial results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquarterlyfinancials
- description: Get compression fleet statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfleetstatistics
- description: List compression equipment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listequipment
- description: List SEC filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecfilings
- description: Get operational performance metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperationalmetrics
---
