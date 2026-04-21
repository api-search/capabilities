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
- create a data export
- list reports
- monitors retailer performance, distribution, and channel dynamics
- manages brand performance, market share, and competitive positioning
- get category
- report generation, management, and data export
- Brand Manager
- business intelligence
- get report
- get brand
- list brands within a specific product category
- list product categories
- pos data, market share, and sales performance analytics
- get consumer segments
- create export
- point of sale
- data export
- product category taxonomy
- retrieve market share data
- consumer segmentation data
- list retailers
- list available analytics reports
- Category Manager
- cpg
- retrieve consumer segments
- get consumer purchases
- point-of-sale data access
- list brands
- get report status and details
- list all available product categories in circana taxonomy
- consumer data
- retrieve consumer segmentation data based on purchase behavior
- list categories
- list brands in a category
- create a data export job in csv, excel, json, or parquet format
- get pos data
- categories, brands, and retailers
- get export
- unified market intelligence combining pos, share, consumer, and reporting data
- retail
- retailer coverage data
- report management
- get detailed brand information including market presence
- create a new analytics report for a category and time period
- analytics
- consumer panel data, purchase behavior, and segmentation
- retrieve market share data for brands in a product category
- consumer purchase behavior data
- market share analytics
- analyzes consumer behavior, market trends, and competitive dynamics
- get detailed information about a specific product category
- consumer insights
- list retailers covered in circana measurement universe
- brand analytics
- create report
- market intelligence
- retrieve pos data by category and time period
- get market share
- circana
- create a new report
- market research
- manages product category performance, assortment, and shopper insights
- check data export status and get download url
- retrieve aggregated consumer purchase data from panel surveys
- retrieve consumer purchase data
- retrieve point-of-sale data for a product category and time period
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
