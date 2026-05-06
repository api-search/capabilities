---
categories: []
consumed_apis: []
description: Marko is Aramark's data and AI platform providing fast, frictionless access to Aramark's robust data universe with 70+ services designed to provide realtime insights and streamline business processes.
layout: capability
name: Aramark Marko API
operations:
- description: Aramark Get Organization Data
  method: GET
  name: getorganization
  path: /organization
- description: Aramark Get Service Data
  method: GET
  name: getservice
  path: /service
- description: Aramark Get Product Data
  method: GET
  name: getproduct
  path: /product
- description: Aramark Get Profit Centers
  method: GET
  name: getprofitcenters
  path: /profit-centers
- description: Aramark Get Revenue Snapshot
  method: GET
  name: getrevenuesnapshot
  path: /revenue-snapshot
- description: Aramark Get Point of Sale Data
  method: GET
  name: getpointofsale
  path: /point-of-sale
personas: []
provider_name: Aramark
provider_slug: aramark
search_terms:
- aramark get product data
- tracks service delivery and organizational performance
- facilities management
- uniform services
- aramark get service data
- monitors revenue performance and profit center reporting
- getservice
- aramark
- getorganization
- getrevenuesnapshot
- campus dining, catering, and food service operations
- facilities operations and service tracking
- getpointofsale
- aramark get point of sale data
- getprofitcenters
- aramark get profit centers
- builds dashboards and reports using aramark operational data
- api
- aramark get organization data
- financial performance tracking by profit center and period
- fortune 500
- aramark get revenue snapshot
- getproduct
- data platform
- food services
slug: aramark-capability
source_filename: aramark-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Aramark Marko API\n  description: Marko is Aramark's data and AI platform providing fast, frictionless access to Aramark's robust data universe\n    with 70+ services designed to provide realtime insights and streamline business processes.\n  tags:\n  - Aramark\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aramark\n    baseUri: https://www.marko.aramark.net/v1\n    description: Aramark Marko API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apiKey\n      value: '{{ARAMARK_TOKEN}}'\n    resources:\n    - name: organization\n      path: /organization\n      operations:\n      - name: getorganization\n        method: GET\n        description: Aramark Get Organization Data\n        inputParameters:\n        - name: locationId\n          in: query\n          type: string\n          description: Filter by location identifier\n        -\
  \ name: orgType\n          in: query\n          type: string\n          description: Filter by organization type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service\n      path: /service\n      operations:\n      - name: getservice\n        method: GET\n        description: Aramark Get Service Data\n        inputParameters:\n        - name: serviceType\n          in: query\n          type: string\n          description: Filter by service type\n        - name: locationId\n          in: query\n          type: string\n          description: Filter by location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product\n      path: /product\n      operations:\n      - name: getproduct\n        method: GET\n        description: Aramark Get Product Data\n        inputParameters:\n        - name: category\n    \
  \      in: query\n          type: string\n          description: Filter by product category\n        - name: locationId\n          in: query\n          type: string\n          description: Filter by location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profit-centers\n      path: /profit-centers\n      operations:\n      - name: getprofitcenters\n        method: GET\n        description: Aramark Get Profit Centers\n        inputParameters:\n        - name: parentId\n          in: query\n          type: string\n          description: Filter by parent profit center\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revenue-snapshot\n      path: /revenue-snapshot\n      operations:\n      - name: getrevenuesnapshot\n        method: GET\n        description: Aramark Get Revenue Snapshot\n        inputParameters:\n\
  \        - name: profitCenterId\n          in: query\n          type: string\n          description: Filter by profit center\n        - name: startDate\n          in: query\n          type: string\n          description: Start date for revenue period (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          description: End date for revenue period (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: point-of-sale\n      path: /point-of-sale\n      operations:\n      - name: getpointofsale\n        method: GET\n        description: Aramark Get Point of Sale Data\n        inputParameters:\n        - name: locationId\n          in: query\n          type: string\n          description: Filter by location identifier\n        - name: startDate\n          in: query\n          type: string\n          description: Start date (YYYY-MM-DD)\n        - name: endDate\n\
  \          in: query\n          type: string\n          description: End date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aramark-rest\n    description: REST adapter for Aramark Marko API.\n    resources:\n    - path: /organization\n      name: getorganization\n      operations:\n      - method: GET\n        name: getorganization\n        description: Aramark Get Organization Data\n        call: aramark.getorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Aramark Get Service Data\n        call: aramark.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /product\n      name: getproduct\n      operations:\n      - method:\
  \ GET\n        name: getproduct\n        description: Aramark Get Product Data\n        call: aramark.getproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /profit-centers\n      name: getprofitcenters\n      operations:\n      - method: GET\n        name: getprofitcenters\n        description: Aramark Get Profit Centers\n        call: aramark.getprofitcenters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /revenue-snapshot\n      name: getrevenuesnapshot\n      operations:\n      - method: GET\n        name: getrevenuesnapshot\n        description: Aramark Get Revenue Snapshot\n        call: aramark.getrevenuesnapshot\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /point-of-sale\n      name: getpointofsale\n      operations:\n      - method: GET\n        name: getpointofsale\n        description: Aramark Get Point of Sale Data\n        call: aramark.getpointofsale\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aramark-mcp\n    transport: http\n    description: MCP adapter for Aramark Marko API for AI agent use.\n    tools:\n    - name: getorganization\n      description: Aramark Get Organization Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getorganization\n      with:\n        locationId: tools.locationId\n        orgType: tools.orgType\n      inputParameters:\n      - name: locationId\n        type: string\n        description: Filter by location identifier\n      - name: orgType\n        type: string\n        description: Filter by organization type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Aramark Get Service Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getservice\n\
  \      with:\n        serviceType: tools.serviceType\n        locationId: tools.locationId\n      inputParameters:\n      - name: serviceType\n        type: string\n        description: Filter by service type\n      - name: locationId\n        type: string\n        description: Filter by location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Aramark Get Product Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getproduct\n      with:\n        category: tools.category\n        locationId: tools.locationId\n      inputParameters:\n      - name: category\n        type: string\n        description: Filter by product category\n      - name: locationId\n        type: string\n        description: Filter by location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprofitcenters\n      description: Aramark Get Profit Centers\n \
  \     hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getprofitcenters\n      with:\n        parentId: tools.parentId\n      inputParameters:\n      - name: parentId\n        type: string\n        description: Filter by parent profit center\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrevenuesnapshot\n      description: Aramark Get Revenue Snapshot\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getrevenuesnapshot\n      with:\n        profitCenterId: tools.profitCenterId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: profitCenterId\n        type: string\n        description: Filter by profit center\n      - name: startDate\n        type: string\n        description: Start date for revenue period (YYYY-MM-DD)\n      - name: endDate\n        type: string\n        description:\
  \ End date for revenue period (YYYY-MM-DD)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpointofsale\n      description: Aramark Get Point of Sale Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aramark.getpointofsale\n      with:\n        locationId: tools.locationId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      inputParameters:\n      - name: locationId\n        type: string\n        description: Filter by location identifier\n      - name: startDate\n        type: string\n        description: Start date (YYYY-MM-DD)\n      - name: endDate\n        type: string\n        description: End date (YYYY-MM-DD)\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ARAMARK_TOKEN: ARAMARK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aramark/refs/heads/main/capabilities/aramark-capability.yaml
tags:
- Aramark
- API
tools:
- description: Aramark Get Organization Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
- description: Aramark Get Service Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Aramark Get Product Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Aramark Get Profit Centers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprofitcenters
- description: Aramark Get Revenue Snapshot
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrevenuesnapshot
- description: Aramark Get Point of Sale Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpointofsale
---
