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
- retrieve market share data for brands in a product category
- get category
- get brand
- product category taxonomy
- report generation, management, and data export
- circana
- point-of-sale data access
- list available analytics reports
- retrieve consumer segments
- get report status and details
- manages product category performance, assortment, and shopper insights
- create a new analytics report for a category and time period
- retrieve point-of-sale data for a product category and time period
- market share analytics
- get market share
- retrieve consumer purchase data
- market research
- create a data export job in csv, excel, json, or parquet format
- retrieve consumer segmentation data based on purchase behavior
- retailer coverage data
- analyzes consumer behavior, market trends, and competitive dynamics
- list reports
- manages brand performance, market share, and competitive positioning
- categories, brands, and retailers
- analytics
- get report
- data export
- get pos data
- get consumer segments
- list brands in a category
- create report
- consumer panel data, purchase behavior, and segmentation
- create export
- consumer data
- list brands
- create a new report
- get export
- create a data export
- list brands within a specific product category
- retail
- consumer purchase behavior data
- report management
- get detailed information about a specific product category
- unified market intelligence combining pos, share, consumer, and reporting data
- get detailed brand information including market presence
- pos data, market share, and sales performance analytics
- get consumer purchases
- consumer insights
- point of sale
- consumer segmentation data
- business intelligence
- Category Manager
- Brand Manager
- retrieve pos data by category and time period
- list categories
- market intelligence
- check data export status and get download url
- monitors retailer performance, distribution, and channel dynamics
- retrieve aggregated consumer purchase data from panel surveys
- list all available product categories in circana taxonomy
- cpg
- brand analytics
- list retailers covered in circana measurement universe
- retrieve market share data
- list product categories
- list retailers
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
