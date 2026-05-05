---
categories:
- analytics
consumed_apis:
- liquid-data
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
- circana
- categories, brands, and retailers
- retrieve pos data by category and time period
- retailer coverage data
- create a new analytics report for a category and time period
- get detailed information about a specific product category
- monitors retailer performance, distribution, and channel dynamics
- create a data export job in csv, excel, json, or parquet format
- get consumer purchases
- list retailers covered in circana measurement universe
- create a data export
- pos data, market share, and sales performance analytics
- business intelligence
- analytics
- list all available product categories in circana taxonomy
- point-of-sale data access
- get report status and details
- analyzes consumer behavior, market trends, and competitive dynamics
- check data export status and get download url
- retrieve market share data for brands in a product category
- get market share
- get export
- retrieve market share data
- manages product category performance, assortment, and shopper insights
- retrieve consumer segmentation data based on purchase behavior
- get category
- get brand
- Brand Manager
- list brands
- product category taxonomy
- consumer segmentation data
- consumer insights
- unified market intelligence combining pos, share, consumer, and reporting data
- list categories
- list product categories
- brand analytics
- report management
- retrieve point-of-sale data for a product category and time period
- Category Manager
- consumer data
- retail
- get pos data
- retrieve aggregated consumer purchase data from panel surveys
- list available analytics reports
- list brands in a category
- consumer purchase behavior data
- retrieve consumer segments
- consumer panel data, purchase behavior, and segmentation
- market share analytics
- create a new report
- get report
- report generation, management, and data export
- get detailed brand information including market presence
- market research
- cpg
- create export
- list brands within a specific product category
- retrieve consumer purchase data
- market intelligence
- list reports
- create report
- manages brand performance, market share, and competitive positioning
- get consumer segments
- point of sale
- data export
- list retailers
slug: market-intelligence
source_filename: market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Circana Market Intelligence\"\n  description: \"Unified market intelligence workflow combining POS data, market share analytics, consumer panel insights, brand performance, and reporting capabilities for brand managers, category managers, and market researchers.\"\n  tags:\n    - Circana\n    - Market Intelligence\n    - Analytics\n    - Consumer Insights\n    - Retail\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CIRCANA_API_TOKEN: CIRCANA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: liquid-data\n      location: ./shared/liquid-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: market-intelligence-api\n      description: \"Unified REST API for Circana market intelligence workflows.\"\n      resources:\n        - path: /v1/pos-data\n          name: pos-data\n          description: \"Point-of-sale data access\"\n          operations:\n  \
  \          - method: GET\n              name: get-pos-data\n              description: \"Retrieve POS data by category and time period\"\n              call: \"liquid-data.get-pos-data\"\n              with:\n                category_id: \"rest.category_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/market-share\n          name: market-share\n          description: \"Market share analytics\"\n          operations:\n            - method: GET\n              name: get-market-share\n              description: \"Retrieve market share data\"\n              call: \"liquid-data.get-market-share\"\n              with:\n                category_id: \"rest.category_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/consumer-purchases\n          name: consumer-purchases\n          description: \"Consumer purchase behavior data\"\n          operations:\n            - method: GET\n              name: get-consumer-purchases\n              description: \"Retrieve consumer purchase data\"\n              call: \"liquid-data.get-consumer-purchases\"\n              with:\n                category_id: \"rest.category_id\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consumer-segments\n          name: consumer-segments\n          description: \"Consumer segmentation data\"\n          operations:\n            - method: GET\n              name: get-consumer-segments\n              description: \"Retrieve consumer segments\"\n              call: \"liquid-data.get-consumer-segments\"\n   \
  \           with:\n                category_id: \"rest.category_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/categories\n          name: categories\n          description: \"Product category taxonomy\"\n          operations:\n            - method: GET\n              name: list-categories\n              description: \"List product categories\"\n              call: \"liquid-data.list-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/brands\n          name: brands\n          description: \"Brand analytics\"\n          operations:\n            - method: GET\n              name: list-brands\n              description: \"List brands in a category\"\n              call: \"liquid-data.list-brands\"\n              with:\n                category_id: \"rest.category_id\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/retailers\n          name: retailers\n          description: \"Retailer coverage data\"\n          operations:\n            - method: GET\n              name: list-retailers\n              description: \"List retailers\"\n              call: \"liquid-data.list-retailers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Report management\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List reports\"\n              call: \"liquid-data.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-report\n              description: \"Create a new report\"\n              call: \"liquid-data.create-report\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/exports\n          name: exports\n          description: \"Data export\"\n          operations:\n            - method: POST\n              name: create-export\n              description: \"Create a data export\"\n              call: \"liquid-data.create-export\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: market-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted market intelligence and consumer analytics.\"\n      tools:\n        - name: get-pos-data\n          description: \"Retrieve point-of-sale data for a product category and time period\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-pos-data\"\n          with:\n            category_id: \"tools.category_id\"\n            start_date: \"\
  tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-market-share\n          description: \"Retrieve market share data for brands in a product category\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-market-share\"\n          with:\n            category_id: \"tools.category_id\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-consumer-purchases\n          description: \"Retrieve aggregated consumer purchase data from panel surveys\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-consumer-purchases\"\n          with:\n            category_id: \"tools.category_id\"\n            start_date: \"tools.start_date\"\
  \n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-consumer-segments\n          description: \"Retrieve consumer segmentation data based on purchase behavior\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-consumer-segments\"\n          with:\n            category_id: \"tools.category_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-categories\n          description: \"List all available product categories in Circana taxonomy\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.list-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-category\n          description: \"Get detailed information about a specific product category\"\n      \
  \    hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-category\"\n          with:\n            category_id: \"tools.category_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-brands\n          description: \"List brands within a specific product category\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.list-brands\"\n          with:\n            category_id: \"tools.category_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-brand\n          description: \"Get detailed brand information including market presence\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-brand\"\n          with:\n            brand_id: \"tools.brand_id\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n        - name: list-retailers\n          description: \"List retailers covered in Circana measurement universe\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.list-retailers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List available analytics reports\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-report\n          description: \"Create a new analytics report for a category and time period\"\n          hints:\n            readOnly: false\n          call: \"liquid-data.create-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report\n          description:\
  \ \"Get report status and details\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-report\"\n          with:\n            report_id: \"tools.report_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-export\n          description: \"Create a data export job in CSV, Excel, JSON, or Parquet format\"\n          hints:\n            readOnly: false\n          call: \"liquid-data.create-export\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-export\n          description: \"Check data export status and get download URL\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"liquid-data.get-export\"\n          with:\n            export_id: \"tools.export_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
