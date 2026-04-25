---
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
- get market share
- list product categories
- list available analytics reports
- create a new analytics report for a category and time period
- unified market intelligence combining pos, share, consumer, and reporting data
- list brands
- analytics
- list retailers
- data export
- create a data export
- get report
- categories, brands, and retailers
- list brands within a specific product category
- retailer coverage data
- get consumer segments
- list categories
- create report
- list retailers covered in circana measurement universe
- consumer panel data, purchase behavior, and segmentation
- check data export status and get download url
- product category taxonomy
- manages brand performance, market share, and competitive positioning
- consumer purchase behavior data
- cpg
- circana
- brand analytics
- consumer data
- list all available product categories in circana taxonomy
- Brand Manager
- retrieve market share data for brands in a product category
- Category Manager
- retrieve point-of-sale data for a product category and time period
- create a new report
- report generation, management, and data export
- consumer insights
- market research
- list brands in a category
- get detailed brand information including market presence
- market intelligence
- create a data export job in csv, excel, json, or parquet format
- get detailed information about a specific product category
- pos data, market share, and sales performance analytics
- analyzes consumer behavior, market trends, and competitive dynamics
- retail
- retrieve aggregated consumer purchase data from panel surveys
- retrieve consumer purchase data
- market share analytics
- get pos data
- retrieve market share data
- retrieve consumer segments
- report management
- get report status and details
- business intelligence
- point of sale
- get export
- create export
- list reports
- get brand
- consumer segmentation data
- retrieve pos data by category and time period
- point-of-sale data access
- retrieve consumer segmentation data based on purchase behavior
- monitors retailer performance, distribution, and channel dynamics
- get category
- get consumer purchases
- manages product category performance, assortment, and shopper insights
slug: market-intelligence
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
