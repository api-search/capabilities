---
categories:
- analytics
consumed_apis: []
description: Unified market intelligence workflow combining POS data, market share analytics, consumer panel insights, brand performance, and reporting capabilities for brand managers, category managers, and market researchers.
layout: capability
name: Circana Market Intelligence
operations:
- description: Retrieve POS data by category and time period
  method: GET
  name: get-pos-data
  path: /v1/pos-data
- description: Retrieve market share data
  method: GET
  name: get-market-share
  path: /v1/market-share
- description: Retrieve consumer purchase data
  method: GET
  name: get-consumer-purchases
  path: /v1/consumer-purchases
- description: Retrieve consumer segments
  method: GET
  name: get-consumer-segments
  path: /v1/consumer-segments
- description: List product categories
  method: GET
  name: list-categories
  path: /v1/categories
- description: List brands in a category
  method: GET
  name: list-brands
  path: /v1/brands
- description: List retailers
  method: GET
  name: list-retailers
  path: /v1/retailers
- description: List reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Create a new report
  method: POST
  name: create-report
  path: /v1/reports
- description: Create a data export
  method: POST
  name: create-export
  path: /v1/exports
personas: []
provider_name: Circana
provider_slug: circana
search_terms:
- retrieve pos data by category and time period
- retrieve aggregated consumer purchase data from panel surveys
- create a data export job in csv, excel, json, or parquet format
- list retailers
- retrieve consumer purchase data
- create report
- consumer insights
- manages product category performance, assortment, and shopper insights
- analytics
- get detailed information about a specific product category
- consumer segmentation data
- get report
- list brands in a category
- check data export status and get download url
- create export
- monitors retailer performance, distribution, and channel dynamics
- list all available product categories in circana taxonomy
- market share analytics
- retrieve point-of-sale data for a product category and time period
- report management
- retail
- circana
- list product categories
- create a data export
- create a new analytics report for a category and time period
- manages brand performance, market share, and competitive positioning
- cpg
- list brands within a specific product category
- get brand
- market research
- categories, brands, and retailers
- consumer panel data, purchase behavior, and segmentation
- get consumer segments
- list reports
- retrieve consumer segments
- unified market intelligence combining pos, share, consumer, and reporting data
- Category Manager
- report generation, management, and data export
- list retailers covered in circana measurement universe
- list brands
- point-of-sale data access
- get consumer purchases
- brand analytics
- consumer data
- data export
- list categories
- get export
- point of sale
- get pos data
- retailer coverage data
- retrieve market share data for brands in a product category
- Brand Manager
- business intelligence
- get category
- analyzes consumer behavior, market trends, and competitive dynamics
- market intelligence
- product category taxonomy
- consumer purchase behavior data
- get report status and details
- get detailed brand information including market presence
- create a new report
- get market share
- retrieve market share data
- list available analytics reports
- pos data, market share, and sales performance analytics
- retrieve consumer segmentation data based on purchase behavior
slug: market-intelligence
source_filename: market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Circana Market Intelligence\n  description: Unified market intelligence workflow combining POS data, market share analytics, consumer panel insights, brand\n    performance, and reporting capabilities for brand managers, category managers, and market researchers.\n  tags:\n  - Circana\n  - Market Intelligence\n  - Analytics\n  - Consumer Insights\n  - Retail\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CIRCANA_API_TOKEN: CIRCANA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: liquid-data\n    baseUri: https://api.circana.com/liquid-data/v1\n    description: Circana Liquid Data API for market measurement, consumer panel, and retail analytics.\n    authentication:\n      type: bearer\n      token: '{{CIRCANA_API_TOKEN}}'\n    resources:\n    - name: market-data\n      path: /market-data\n      description: Point-of-sale and market share data\n      operations:\n      - name:\
  \ get-pos-data\n        method: GET\n        path: /pos\n        description: Retrieve point-of-sale data with filters for time period, geography, category, and retailer.\n        inputParameters:\n        - name: category_id\n          in: query\n          type: string\n          required: true\n          description: Product category identifier\n        - name: start_date\n          in: query\n          type: string\n          required: true\n          description: Start date for data range\n        - name: end_date\n          in: query\n          type: string\n          required: true\n          description: End date for data range\n        - name: geography\n          in: query\n          type: string\n          required: false\n          description: Geographic market filter\n        - name: retailer_id\n          in: query\n          type: string\n          required: false\n          description: Retailer filter\n        - name: granularity\n          in: query\n          type: string\n\
  \          required: false\n          description: Time granularity\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-market-share\n        method: GET\n        path: /share\n        description: Retrieve market share data showing brand and category share metrics.\n        inputParameters:\n        - name: category_id\n          in: query\n          type: string\n          required: true\n          description: Product category identifier\n        - name: start_date\n          in: query\n          type: string\n          required: true\n          description: Start date for data range\n        - name: end_date\n   \
  \       in: query\n          type: string\n          required: true\n          description: End date for data range\n        - name: metric\n          in: query\n          type: string\n          required: false\n          description: Share metric type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumer-panel\n      path: /consumer-panel\n      description: Consumer purchase and segmentation data\n      operations:\n      - name: get-consumer-purchases\n        method: GET\n        path: /purchases\n        description: Retrieve aggregated consumer purchase data from panel surveys and receipt scanning.\n        inputParameters:\n        - name: category_id\n          in: query\n          type: string\n          required: true\n          description: Product category identifier\n        - name: start_date\n          in: query\n          type: string\n          required: true\n          description:\
  \ Start date\n        - name: end_date\n          in: query\n          type: string\n          required: true\n          description: End date\n        - name: demographic\n          in: query\n          type: string\n          required: false\n          description: Demographic segment filter\n        - name: channel\n          in: query\n          type: string\n          required: false\n          description: Purchase channel filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-consumer-segments\n        method: GET\n        path: /segments\n        description: Retrieve consumer segmentation data based on purchase behavior.\n        inputParameters:\n        - name: category_id\n          in: query\n          type: string\n          required: true\n          description: Product category identifier\n        - name: segmentation_type\n          in: query\n          type: string\n    \
  \      required: false\n          description: Type of segmentation analysis\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: categories\n      path: /categories\n      description: Product category hierarchy\n      operations:\n      - name: list-categories\n        method: GET\n        description: List available product categories.\n        inputParameters:\n        - name: parent_id\n          in: query\n          type: string\n          required: false\n          description: Parent category ID\n        - name: industry\n          in: query\n          type: string\n          required: false\n          description: Industry vertical filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-category\n        method: GET\n        path: /{category_id}\n        description: Get detailed information about\
  \ a specific product category.\n        inputParameters:\n        - name: category_id\n          in: path\n          type: string\n          required: true\n          description: Category identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: brands\n      path: /brands\n      description: Brand data and analytics\n      operations:\n      - name: list-brands\n        method: GET\n        description: List brands within a specific category.\n        inputParameters:\n        - name: category_id\n          in: query\n          type: string\n          required: true\n          description: Product category\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-brand\n     \
  \   method: GET\n        path: /{brand_id}\n        description: Get detailed brand information.\n        inputParameters:\n        - name: brand_id\n          in: path\n          type: string\n          required: true\n          description: Brand identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retailers\n      path: /retailers\n      description: Retailer data and coverage\n      operations:\n      - name: list-retailers\n        method: GET\n        description: List retailers covered in Circana measurement universe.\n        inputParameters:\n        - name: channel\n          in: query\n          type: string\n          required: false\n          description: Retail channel filter\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: reports\n      path: /reports\n      description: Report generation and management\n      operations:\n      - name: list-reports\n        method: GET\n        description: List available reports.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Report status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-report\n        method: POST\n        description: Create a new report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            report_type: '{{tools.report_type}}'\n            category_id: '{{tools.category_id}}'\n            start_date: '{{tools.start_date}}'\n\
  \            end_date: '{{tools.end_date}}'\n      - name: get-report\n        method: GET\n        path: /{report_id}\n        description: Get report details.\n        inputParameters:\n        - name: report_id\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exports\n      path: /exports\n      description: Data export operations\n      operations:\n      - name: create-export\n        method: POST\n        description: Create a data export job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            source_type: '{{tools.source_type}}'\n            source_id: '{{tools.source_id}}'\n            format: '{{tools.format}}'\n      - name: get-export\n\
  \        method: GET\n        path: /{export_id}\n        description: Check export status and get download URL.\n        inputParameters:\n        - name: export_id\n          in: path\n          type: string\n          required: true\n          description: Export identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: market-intelligence-api\n    description: Unified REST API for Circana market intelligence workflows.\n    resources:\n    - path: /v1/pos-data\n      name: pos-data\n      description: Point-of-sale data access\n      operations:\n      - method: GET\n        name: get-pos-data\n        description: Retrieve POS data by category and time period\n        call: liquid-data.get-pos-data\n        with:\n          category_id: rest.category_id\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/market-share\n      name: market-share\n      description: Market share analytics\n      operations:\n      - method: GET\n        name: get-market-share\n        description: Retrieve market share data\n        call: liquid-data.get-market-share\n        with:\n          category_id: rest.category_id\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumer-purchases\n      name: consumer-purchases\n      description: Consumer purchase behavior data\n      operations:\n      - method: GET\n        name: get-consumer-purchases\n        description: Retrieve consumer purchase data\n        call: liquid-data.get-consumer-purchases\n        with:\n          category_id: rest.category_id\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/consumer-segments\n      name: consumer-segments\n      description: Consumer segmentation data\n      operations:\n      - method: GET\n        name: get-consumer-segments\n        description: Retrieve consumer segments\n        call: liquid-data.get-consumer-segments\n        with:\n          category_id: rest.category_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/categories\n      name: categories\n      description: Product category taxonomy\n      operations:\n      - method: GET\n        name: list-categories\n        description: List product categories\n        call: liquid-data.list-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/brands\n      name: brands\n      description: Brand analytics\n      operations:\n      - method: GET\n        name: list-brands\n        description: List brands in a category\n        call: liquid-data.list-brands\n\
  \        with:\n          category_id: rest.category_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/retailers\n      name: retailers\n      description: Retailer coverage data\n      operations:\n      - method: GET\n        name: list-retailers\n        description: List retailers\n        call: liquid-data.list-retailers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Report management\n      operations:\n      - method: GET\n        name: list-reports\n        description: List reports\n        call: liquid-data.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-report\n        description: Create a new report\n        call: liquid-data.create-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/exports\n      name: exports\n\
  \      description: Data export\n      operations:\n      - method: POST\n        name: create-export\n        description: Create a data export\n        call: liquid-data.create-export\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: market-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted market intelligence and consumer analytics.\n    tools:\n    - name: get-pos-data\n      description: Retrieve point-of-sale data for a product category and time period\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-pos-data\n      with:\n        category_id: tools.category_id\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-market-share\n      description: Retrieve market share data for brands in a product category\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: liquid-data.get-market-share\n      with:\n        category_id: tools.category_id\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-consumer-purchases\n      description: Retrieve aggregated consumer purchase data from panel surveys\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-consumer-purchases\n      with:\n        category_id: tools.category_id\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-consumer-segments\n      description: Retrieve consumer segmentation data based on purchase behavior\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-consumer-segments\n      with:\n        category_id: tools.category_id\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: list-categories\n      description: List all available product categories in Circana taxonomy\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.list-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-category\n      description: Get detailed information about a specific product category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-category\n      with:\n        category_id: tools.category_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-brands\n      description: List brands within a specific product category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.list-brands\n      with:\n        category_id: tools.category_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-brand\n      description:\
  \ Get detailed brand information including market presence\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-brand\n      with:\n        brand_id: tools.brand_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-retailers\n      description: List retailers covered in Circana measurement universe\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.list-retailers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available analytics reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-report\n      description: Create a new analytics report for a category and time period\n      hints:\n        readOnly: false\n      call: liquid-data.create-report\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-report\n      description: Get report status and details\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-report\n      with:\n        report_id: tools.report_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-export\n      description: Create a data export job in CSV, Excel, JSON, or Parquet format\n      hints:\n        readOnly: false\n      call: liquid-data.create-export\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-export\n      description: Check data export status and get download URL\n      hints:\n        readOnly: true\n        openWorld: true\n      call: liquid-data.get-export\n      with:\n        export_id: tools.export_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/circana/refs/heads/main/capabilities/market-intelligence.yaml
tags:
- Circana
- Market Intelligence
- Analytics
- Consumer Insights
- Retail
tools:
- description: Retrieve point-of-sale data for a product category and time period
  hints:
    openWorld: true
    readOnly: true
  name: get-pos-data
- description: Retrieve market share data for brands in a product category
  hints:
    openWorld: true
    readOnly: true
  name: get-market-share
- description: Retrieve aggregated consumer purchase data from panel surveys
  hints:
    openWorld: true
    readOnly: true
  name: get-consumer-purchases
- description: Retrieve consumer segmentation data based on purchase behavior
  hints:
    openWorld: true
    readOnly: true
  name: get-consumer-segments
- description: List all available product categories in Circana taxonomy
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: Get detailed information about a specific product category
  hints:
    openWorld: true
    readOnly: true
  name: get-category
- description: List brands within a specific product category
  hints:
    openWorld: true
    readOnly: true
  name: list-brands
- description: Get detailed brand information including market presence
  hints:
    openWorld: true
    readOnly: true
  name: get-brand
- description: List retailers covered in Circana measurement universe
  hints:
    openWorld: true
    readOnly: true
  name: list-retailers
- description: List available analytics reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Create a new analytics report for a category and time period
  hints:
    readOnly: false
  name: create-report
- description: Get report status and details
  hints:
    openWorld: true
    readOnly: true
  name: get-report
- description: Create a data export job in CSV, Excel, JSON, or Parquet format
  hints:
    readOnly: false
  name: create-export
- description: Check data export status and get download URL
  hints:
    openWorld: true
    readOnly: true
  name: get-export
---
