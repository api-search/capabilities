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
- consumer segmentation data
- get brand
- report management
- create a data export
- consumer panel data, purchase behavior, and segmentation
- business intelligence
- get detailed brand information including market presence
- list retailers
- retrieve consumer segments
- analytics
- consumer data
- retrieve consumer purchase data
- monitors retailer performance, distribution, and channel dynamics
- product category taxonomy
- retrieve pos data by category and time period
- get report status and details
- retrieve consumer segmentation data based on purchase behavior
- cpg
- point-of-sale data access
- list available analytics reports
- create report
- analyzes consumer behavior, market trends, and competitive dynamics
- list brands in a category
- get consumer purchases
- brand analytics
- get detailed information about a specific product category
- circana
- get pos data
- consumer purchase behavior data
- create export
- data export
- retrieve market share data for brands in a product category
- create a data export job in csv, excel, json, or parquet format
- get report
- retrieve point-of-sale data for a product category and time period
- Category Manager
- list all available product categories in circana taxonomy
- Brand Manager
- point of sale
- categories, brands, and retailers
- list retailers covered in circana measurement universe
- market share analytics
- create a new report
- list reports
- check data export status and get download url
- manages product category performance, assortment, and shopper insights
- get category
- consumer insights
- create a new analytics report for a category and time period
- retrieve market share data
- retail
- pos data, market share, and sales performance analytics
- list brands within a specific product category
- market research
- get market share
- list product categories
- unified market intelligence combining pos, share, consumer, and reporting data
- market intelligence
- list categories
- manages brand performance, market share, and competitive positioning
- report generation, management, and data export
- list brands
- get export
- retrieve aggregated consumer purchase data from panel surveys
- retailer coverage data
- get consumer segments
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
