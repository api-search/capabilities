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
- get consumer segments
- report generation, management, and data export
- create a data export
- get detailed brand information including market presence
- create a data export job in csv, excel, json, or parquet format
- check data export status and get download url
- retrieve point-of-sale data for a product category and time period
- create a new analytics report for a category and time period
- consumer insights
- retrieve consumer purchase data
- brand analytics
- list brands in a category
- create report
- data export
- market research
- market share analytics
- create a new report
- consumer purchase behavior data
- list available analytics reports
- retrieve pos data by category and time period
- retailer coverage data
- point-of-sale data access
- retrieve market share data
- manages product category performance, assortment, and shopper insights
- categories, brands, and retailers
- Brand Manager
- Category Manager
- get market share
- point of sale
- manages brand performance, market share, and competitive positioning
- get consumer purchases
- cpg
- business intelligence
- monitors retailer performance, distribution, and channel dynamics
- get brand
- market intelligence
- retrieve market share data for brands in a product category
- consumer segmentation data
- get category
- circana
- product category taxonomy
- report management
- get pos data
- get report status and details
- analyzes consumer behavior, market trends, and competitive dynamics
- list reports
- list all available product categories in circana taxonomy
- consumer panel data, purchase behavior, and segmentation
- unified market intelligence combining pos, share, consumer, and reporting data
- list brands
- consumer data
- list brands within a specific product category
- list retailers covered in circana measurement universe
- list categories
- list product categories
- analytics
- retrieve aggregated consumer purchase data from panel surveys
- retrieve consumer segments
- retrieve consumer segmentation data based on purchase behavior
- list retailers
- retail
- get detailed information about a specific product category
- pos data, market share, and sales performance analytics
- get report
- get export
- create export
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
