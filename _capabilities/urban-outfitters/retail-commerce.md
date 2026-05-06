---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Retail Commerce
operations: []
personas: []
provider_name: Urban Outfitters
provider_slug: urban-outfitters
search_terms:
- affiliate
- developers integrating urban outfitters affiliate or marketplace apis into applications
- marketplace
- apparel
- independent fashion and lifestyle brands selling through the uo mrkt marketplace
- retail
- ecommerce
- fashion
- content creators, bloggers, and influencers promoting urban outfitters products for commission
- end-to-end retail commerce workflow combining affiliate marketing and marketplace seller management for the urban outfitters ecosystem
slug: retail-commerce
source_filename: retail-commerce.yaml
source_heading: Capability Spec
source_yaml: "name: Urban Outfitters Retail Commerce\ndescription: >-\n  Workflow capability combining Urban Outfitters affiliate and marketplace APIs\n  to enable retail commerce integrations. Supports affiliate marketing for\n  content creators and multi-channel sellers managing inventory through\n  the UO MRKT marketplace platform.\nversion: '1.0.0'\nmcp:\n  port: 9080\nrest:\n  port: 8080\npersonas:\n  - name: Affiliate Partner\n    description: Content creators, bloggers, and influencers earning commissions by promoting Urban Outfitters products\n  - name: Marketplace Seller\n    description: Independent fashion and lifestyle brands selling through the UO MRKT marketplace\n  - name: Developer\n    description: Developers integrating Urban Outfitters affiliate or marketplace APIs into applications\ntools:\n  - name: search_products\n    description: Search the Urban Outfitters product catalog for affiliate promotion\n    operationId: searchProducts\n    api: affiliate-api\n    parameters:\n\
  \      - name: q\n        description: Search query string\n      - name: category\n        description: Product category filter\n      - name: limit\n        description: Number of results to return\n  - name: get_product_details\n    description: Get detailed product information including affiliate deep link\n    operationId: getProduct\n    api: affiliate-api\n    parameters:\n      - name: product_id\n        description: The unique product identifier\n  - name: create_affiliate_link\n    description: Generate an affiliate tracking link for a product or page URL\n    operationId: createAffiliateLink\n    api: affiliate-api\n    parameters:\n      - name: targetUrl\n        description: The Urban Outfitters URL to create an affiliate link for\n      - name: affiliateId\n        description: Your affiliate account identifier\n  - name: get_commission_report\n    description: Retrieve commission earnings and performance metrics for a date range\n    operationId: getCommissionReport\n\
  \    api: affiliate-api\n    parameters:\n      - name: start_date\n        description: Report start date\n      - name: end_date\n        description: Report end date\n      - name: affiliate_id\n        description: Affiliate account identifier\n  - name: list_creative_assets\n    description: Retrieve available banner ads and creative assets for promotion\n    operationId: listCreatives\n    api: affiliate-api\n    parameters:\n      - name: size\n        description: Banner size filter (e.g. 300x250, 728x90)\n  - name: list_seller_products\n    description: List your product catalog on the Urban Outfitters marketplace\n    operationId: listSellerProducts\n    api: marketplace-api\n    parameters:\n      - name: status\n        description: Filter by product status (active, inactive, pending_review)\n      - name: limit\n        description: Number of products to return\n  - name: create_seller_product\n    description: Submit a new product listing to the Urban Outfitters marketplace\n\
  \    operationId: createSellerProduct\n    api: marketplace-api\n    parameters:\n      - name: sku\n        description: Your product SKU\n      - name: name\n        description: Product name\n      - name: price\n        description: Product retail price\n      - name: currency\n        description: Price currency code\n  - name: update_inventory\n    description: Update inventory levels for your marketplace products\n    operationId: updateInventory\n    api: marketplace-api\n    parameters:\n      - name: updates\n        description: Array of SKU and quantity pairs to update\n  - name: list_orders\n    description: Retrieve orders for your marketplace products\n    operationId: listOrders\n    api: marketplace-api\n    parameters:\n      - name: status\n        description: Filter by order status\n      - name: start_date\n        description: Filter orders from this date\n  - name: create_shipment\n    description: Submit shipment tracking information for a fulfilled order\n   \
  \ operationId: createShipment\n    api: marketplace-api\n    parameters:\n      - name: order_id\n        description: The order identifier to create a shipment for\n      - name: carrier\n        description: Shipping carrier name\n      - name: trackingNumber\n        description: Carrier tracking number\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/urban-outfitters/refs/heads/main/capabilities/retail-commerce.yaml
tags: []
tools: []
---
