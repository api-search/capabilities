---
categories: []
consumed_apis: []
description: The Arch Coal Investor Relations API provides access to financial data, SEC filings, coal production reports, and market information for Arch Coal (Arch Resources). This API reflects public financial data available through investor relations portals.
layout: capability
name: Arch Coal Investor Relations API
operations:
- description: Arch Coal Get Quarterly Production
  method: GET
  name: getquarterlyproduction
  path: /production/quarterly
- description: Arch Coal Get Earnings Data
  method: GET
  name: getearnings
  path: /financial/earnings
- description: Arch Coal List SEC Filings
  method: GET
  name: listfilings
  path: /filings
personas: []
provider_name: Arch Coal
provider_slug: arch-coal
search_terms:
- getquarterlyproduction
- shareholders and analysts monitoring arch coal financial performance
- api
- earnings and revenue reporting for investors
- mining
- coal production and sales volume metrics
- listfilings
- arch coal list sec filings
- arch
- arch coal get quarterly production
- arch coal get earnings data
- energy
- getearnings
- coal
- environmental, social, and governance data researchers
- metallurgical coal
- thermal coal
- analysts tracking coal production and pricing data
- fortune 500
- sec filings and regulatory disclosure
slug: arch-coal-capability
source_filename: arch-coal-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Arch Coal Investor Relations API\n  description: The Arch Coal Investor Relations API provides access to financial data, SEC filings, coal production reports,\n    and market information for Arch Coal (Arch Resources). This API reflects public financial data available through investor\n    relations portals.\n  tags:\n  - Arch\n  - Coal\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: arch-coal\n    baseUri: https://api.archresources.com/v1\n    description: Arch Coal Investor Relations API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{ARCH_COAL_TOKEN}}'\n    resources:\n    - name: production-quarterly\n      path: /production/quarterly\n      operations:\n      - name: getquarterlyproduction\n        method: GET\n        description: Arch Coal Get Quarterly Production\n        inputParameters:\n        -\
  \ name: year\n          in: query\n          type: integer\n          description: Fiscal year\n        - name: quarter\n          in: query\n          type: integer\n          description: Quarter (1-4)\n        - name: coalType\n          in: query\n          type: string\n          description: Filter by coal type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-earnings\n      path: /financial/earnings\n      operations:\n      - name: getearnings\n        method: GET\n        description: Arch Coal Get Earnings Data\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n          description: Fiscal year\n        - name: quarter\n          in: query\n          type: integer\n          description: Quarter (1-4), omit for annual\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: filings\n      path: /filings\n      operations:\n      - name: listfilings\n        method: GET\n        description: Arch Coal List SEC Filings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: Filing type\n        - name: year\n          in: query\n          type: integer\n          description: Filing year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: arch-coal-rest\n    description: REST adapter for Arch Coal Investor Relations API.\n    resources:\n    - path: /production/quarterly\n      name: getquarterlyproduction\n      operations:\n      - method: GET\n        name: getquarterlyproduction\n        description: Arch Coal Get Quarterly Production\n        call: arch-coal.getquarterlyproduction\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /financial/earnings\n      name: getearnings\n      operations:\n      - method: GET\n        name: getearnings\n        description: Arch Coal Get Earnings Data\n        call: arch-coal.getearnings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filings\n      name: listfilings\n      operations:\n      - method: GET\n        name: listfilings\n        description: Arch Coal List SEC Filings\n        call: arch-coal.listfilings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: arch-coal-mcp\n    transport: http\n    description: MCP adapter for Arch Coal Investor Relations API for AI agent use.\n    tools:\n    - name: getquarterlyproduction\n      description: Arch Coal Get Quarterly Production\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arch-coal.getquarterlyproduction\n      with:\n\
  \        year: tools.year\n        quarter: tools.quarter\n        coalType: tools.coalType\n      inputParameters:\n      - name: year\n        type: integer\n        description: Fiscal year\n      - name: quarter\n        type: integer\n        description: Quarter (1-4)\n      - name: coalType\n        type: string\n        description: Filter by coal type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getearnings\n      description: Arch Coal Get Earnings Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arch-coal.getearnings\n      with:\n        year: tools.year\n        quarter: tools.quarter\n      inputParameters:\n      - name: year\n        type: integer\n        description: Fiscal year\n      - name: quarter\n        type: integer\n        description: Quarter (1-4), omit for annual\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfilings\n   \
  \   description: Arch Coal List SEC Filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: arch-coal.listfilings\n      with:\n        type: tools.type\n        year: tools.year\n      inputParameters:\n      - name: type\n        type: string\n        description: Filing type\n      - name: year\n        type: integer\n        description: Filing year\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARCH_COAL_TOKEN: ARCH_COAL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/arch-coal/refs/heads/main/capabilities/arch-coal-capability.yaml
tags:
- Arch
- Coal
- API
tools:
- description: Arch Coal Get Quarterly Production
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getquarterlyproduction
- description: Arch Coal Get Earnings Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getearnings
- description: Arch Coal List SEC Filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilings
---
