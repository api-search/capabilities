---
consumed_apis:
- acuity-brands
description: Workflow for distributor integration with Acuity Brands covering inventory lookup, order status tracking, product catalog search, and shipment tracking. Used by electrical distributors integrating Acuity Brands data into ERP and e-commerce systems.
layout: capability
name: Acuity Brands Distributor Integration
operations:
- description: List inventory with optional filters
  method: GET
  name: list-inventory
  path: /v1/inventory
- description: List orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Search product catalog
  method: GET
  name: list-catalog
  path: /v1/catalog
personas: []
provider_name: acuity-brands
provider_slug: acuity-brands
search_terms:
- inventory
- developers integrating acuity brands data into erp systems for automated ordering and inventory sync
- acuity brands
- lighting
- distributor
- track shipment
- check inventory
- ERP Integration Developer
- developers building e-commerce sites that display acuity brands product data, pricing, and availability
- list inventory
- get detailed inventory including warehouse locations and estimated ship dates for a specific product
- product catalog search
- inventory lookup, order tracking, product catalog search, and shipment tracking for distributors
- list recent orders filtered by status or date range
- get full order status and details including estimated and actual ship dates
- order management
- E Commerce Developer
- search product catalog
- Electrical Distributor
- b2b distributor ordering, inventory management, and shipment tracking
- list orders
- get product inventory
- search the acuity brands product catalog by keyword, brand, or product category
- check inventory availability for an acuity brands product by product number or brand
- search products
- get shipment records for an order including carrier name and pro number for freight tracking
- commercial, industrial, and residential lighting products and controls
- get full product details including specifications, certifications, list price, and data sheet
- track order
- order status and tracking
- get product
- product inventory availability
- list inventory with optional filters
- electrical distributors who carry acuity brands products and need real-time inventory and order data
- b2b
- list catalog
slug: distributor-integration
tags:
- Acuity Brands
- Lighting
- B2B
- Distributor
- Inventory
- Order Management
tools:
- description: Check inventory availability for an Acuity Brands product by product number or brand
  hints:
    openWorld: true
    readOnly: true
  name: check-inventory
- description: Get detailed inventory including warehouse locations and estimated ship dates for a specific product
  hints:
    openWorld: false
    readOnly: true
  name: get-product-inventory
- description: Get full order status and details including estimated and actual ship dates
  hints:
    openWorld: false
    readOnly: true
  name: track-order
- description: Get shipment records for an order including carrier name and pro number for freight tracking
  hints:
    openWorld: false
    readOnly: true
  name: track-shipment
- description: Search the Acuity Brands product catalog by keyword, brand, or product category
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get full product details including specifications, certifications, list price, and data sheet
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: List recent orders filtered by status or date range
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
---
