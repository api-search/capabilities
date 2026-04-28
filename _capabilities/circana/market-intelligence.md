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
- retail
- create a data export job in csv, excel, json, or parquet format
- point of sale
- report management
- list categories
- business intelligence
- cpg
- Category Manager
- manages product category performance, assortment, and shopper insights
- retailer coverage data
- get report
- get report status and details
- manages brand performance, market share, and competitive positioning
- circana
- point-of-sale data access
- pos data, market share, and sales performance analytics
- get detailed brand information including market presence
- consumer insights
- list reports
- monitors retailer performance, distribution, and channel dynamics
- data export
- list brands within a specific product category
- list retailers covered in circana measurement universe
- consumer purchase behavior data
- product category taxonomy
- create export
- get detailed information about a specific product category
- retrieve aggregated consumer purchase data from panel surveys
- consumer data
- retrieve pos data by category and time period
- create report
- list brands
- create a new report
- list brands in a category
- get market share
- get consumer segments
- list available analytics reports
- check data export status and get download url
- list all available product categories in circana taxonomy
- consumer segmentation data
- retrieve consumer purchase data
- create a new analytics report for a category and time period
- market share analytics
- create a data export
- unified market intelligence combining pos, share, consumer, and reporting data
- get export
- get pos data
- retrieve market share data for brands in a product category
- retrieve consumer segments
- brand analytics
- list retailers
- analytics
- market intelligence
- retrieve market share data
- retrieve point-of-sale data for a product category and time period
- Brand Manager
- get consumer purchases
- market research
- list product categories
- retrieve consumer segmentation data based on purchase behavior
- get brand
- get category
- report generation, management, and data export
- categories, brands, and retailers
- analyzes consumer behavior, market trends, and competitive dynamics
- consumer panel data, purchase behavior, and segmentation
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
