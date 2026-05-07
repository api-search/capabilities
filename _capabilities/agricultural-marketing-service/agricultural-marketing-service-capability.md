---
categories: []
consumed_apis: []
description: The Market Analysis Reporting System (MARS) API provides programmatic access to USDA Agricultural Marketing Service agricultural market news data. The API allows users to automatically pull raw market news data including commodity prices, volume, and trade reports across livestock, dairy, fruits, vegetables, grains, and other agricultural commodities. Authentication via Basic auth with an API key is supported for registered users; no key is required for public access. All responses are in JSON format.
layout: capability
name: USDA AMS MARS API (MyMarketNews)
operations:
- description: USDA AMS List Reports
  method: GET
  name: listreports
  path: /reports
- description: USDA AMS Get Report
  method: GET
  name: getreport
  path: /reports/{slug_id}
- description: USDA AMS List Offices
  method: GET
  name: listoffices
  path: /offices
personas: []
provider_name: Agricultural Marketing Service
provider_slug: agricultural-marketing-service
search_terms:
- getreport
- agricultural commodity price reporting and market news
- api
- usda ams list offices
- fruits and vegetables
- dairy
- service
- agriculture
- usda office and administrative data
- tobacco
- usda ams get report
- livestock
- farmers markets, food hubs, csas, and local food directories
- researchers and analysts monitoring commodity prices and market trends
- cotton
- listreports
- market news
- marketing
- listoffices
- usda ams list reports
- government and academic researchers studying agricultural markets
- federal government
- agricultural
- traders using market news data for pricing and procurement decisions
slug: agricultural-marketing-service-capability
source_filename: agricultural-marketing-service-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USDA AMS MARS API (MyMarketNews)\n  description: The Market Analysis Reporting System (MARS) API provides programmatic access to USDA Agricultural Marketing\n    Service agricultural market news data. The API allows users to automatically pull raw market news data including commodity\n    prices, volume, and trade reports across livestock, dairy, fruits, vegetables, grains, and other agricultural commodities.\n    Authentication via Basic auth with an API key is supported for registered users; no key is required for public access.\n    All responses are in JSON format.\n  tags:\n  - Agricultural\n  - Marketing\n  - Service\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: agricultural-marketing-service\n    baseUri: https://marsapi.ams.usda.gov/services/v1.2\n    description: USDA AMS MARS API (MyMarketNews) HTTP API.\n    authentication:\n      type: basic\n      username:\
  \ '{{AGRICULTURAL_MARKETING_SERVICE_USERNAME}}'\n      password: '{{AGRICULTURAL_MARKETING_SERVICE_PASSWORD}}'\n    resources:\n    - name: reports\n      path: /reports\n      operations:\n      - name: listreports\n        method: GET\n        description: USDA AMS List Reports\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Search query to filter reports by name or description.\n        - name: allSections\n          in: query\n          type: boolean\n          description: Return all report sections (true/false).\n        - name: dateType\n          in: query\n          type: string\n          description: Date type to filter by (published, report).\n        - name: startDate\n          in: query\n          type: string\n          description: Start date for filtering reports (YYYY-MM-DD).\n        - name: endDate\n          in: query\n          type: string\n          description: End date for filtering reports (YYYY-MM-DD).\
  \ Maximum 180 days from startDate.\n        - name: slug_id\n          in: query\n          type: string\n          description: Filter by specific report slug ID.\n        - name: class\n          in: query\n          type: string\n          description: Filter by commodity class (e.g., Livestock, Dairy, Fruit/Veg).\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of records to return (max 100000).\n        - name: offset\n          in: query\n          type: integer\n          description: Number of records to skip for pagination.\n        - name: sort_by\n          in: query\n          type: string\n          description: Field to sort results by.\n        - name: sort_order\n          in: query\n          type: string\n          description: Sort order (asc or desc).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports-slug-id\n \
  \     path: /reports/{slug_id}\n      operations:\n      - name: getreport\n        method: GET\n        description: USDA AMS Get Report\n        inputParameters:\n        - name: slug_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier (Slug_ID) for the market news report.\n        - name: startDate\n          in: query\n          type: string\n          description: Start date for filtering data within the report (YYYY-MM-DD).\n        - name: endDate\n          in: query\n          type: string\n          description: End date for filtering data (YYYY-MM-DD). Maximum 180 days from startDate.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum records to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of records to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: offices\n      path: /offices\n      operations:\n      - name: listoffices\n        method: GET\n        description: USDA AMS List Offices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agricultural-marketing-service-rest\n    description: REST adapter for USDA AMS MARS API (MyMarketNews).\n    resources:\n    - path: /reports\n      name: listreports\n      operations:\n      - method: GET\n        name: listreports\n        description: USDA AMS List Reports\n        call: agricultural-marketing-service.listreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reports/{slug_id}\n      name: getreport\n      operations:\n      - method: GET\n        name: getreport\n        description: USDA AMS Get Report\n        call: agricultural-marketing-service.getreport\n\
  \        with:\n          slug_id: rest.slug_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offices\n      name: listoffices\n      operations:\n      - method: GET\n        name: listoffices\n        description: USDA AMS List Offices\n        call: agricultural-marketing-service.listoffices\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agricultural-marketing-service-mcp\n    transport: http\n    description: MCP adapter for USDA AMS MARS API (MyMarketNews) for AI agent use.\n    tools:\n    - name: listreports\n      description: USDA AMS List Reports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: agricultural-marketing-service.listreports\n      with:\n        q: tools.q\n        allSections: tools.allSections\n        dateType: tools.dateType\n        startDate: tools.startDate\n        endDate: tools.endDate\n\
  \        slug_id: tools.slug_id\n        class: tools.class\n        limit: tools.limit\n        offset: tools.offset\n        sort_by: tools.sort_by\n        sort_order: tools.sort_order\n      inputParameters:\n      - name: q\n        type: string\n        description: Search query to filter reports by name or description.\n      - name: allSections\n        type: boolean\n        description: Return all report sections (true/false).\n      - name: dateType\n        type: string\n        description: Date type to filter by (published, report).\n      - name: startDate\n        type: string\n        description: Start date for filtering reports (YYYY-MM-DD).\n      - name: endDate\n        type: string\n        description: End date for filtering reports (YYYY-MM-DD). Maximum 180 days from startDate.\n      - name: slug_id\n        type: string\n        description: Filter by specific report slug ID.\n      - name: class\n        type: string\n        description: Filter by commodity\
  \ class (e.g., Livestock, Dairy, Fruit/Veg).\n      - name: limit\n        type: integer\n        description: Maximum number of records to return (max 100000).\n      - name: offset\n        type: integer\n        description: Number of records to skip for pagination.\n      - name: sort_by\n        type: string\n        description: Field to sort results by.\n      - name: sort_order\n        type: string\n        description: Sort order (asc or desc).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreport\n      description: USDA AMS Get Report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: agricultural-marketing-service.getreport\n      with:\n        slug_id: tools.slug_id\n        startDate: tools.startDate\n        endDate: tools.endDate\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: slug_id\n        type: string\n        description: Unique\
  \ identifier (Slug_ID) for the market news report.\n        required: true\n      - name: startDate\n        type: string\n        description: Start date for filtering data within the report (YYYY-MM-DD).\n      - name: endDate\n        type: string\n        description: End date for filtering data (YYYY-MM-DD). Maximum 180 days from startDate.\n      - name: limit\n        type: integer\n        description: Maximum records to return.\n      - name: offset\n        type: integer\n        description: Number of records to skip.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoffices\n      description: USDA AMS List Offices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: agricultural-marketing-service.listoffices\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AGRICULTURAL_MARKETING_SERVICE_USERNAME: AGRICULTURAL_MARKETING_SERVICE_USERNAME\n\
  \    AGRICULTURAL_MARKETING_SERVICE_PASSWORD: AGRICULTURAL_MARKETING_SERVICE_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agricultural-marketing-service/refs/heads/main/capabilities/agricultural-marketing-service-capability.yaml
tags:
- Agricultural
- Marketing
- Service
- API
tools:
- description: USDA AMS List Reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreports
- description: USDA AMS Get Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreport
- description: USDA AMS List Offices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoffices
---
