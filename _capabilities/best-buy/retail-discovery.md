---
consumed_apis:
- best-buy-products
- best-buy-stores
- best-buy-recommendations
description: Unified retail discovery workflow combining product search, store locator, and personalized recommendations. Designed for developers and partners building retail integrations, shopping apps, and e-commerce experiences. Combines the Products, Stores, and Recommendations APIs into a cohesive consumer-facing workflow for product discovery, inventory lookup, and personalized suggestions.
layout: capability
name: Best Buy Retail Discovery
operations:
- description: Search and filter Best Buy products with keyword search and attribute filtering
  method: GET
  name: list-products
  path: /v1/products
- description: Get detailed product information by SKU
  method: GET
  name: get-product
  path: /v1/products/{sku}
- description: Find Best Buy stores with proximity search
  method: GET
  name: list-stores
  path: /v1/stores
- description: Get store details including hours and services
  method: GET
  name: get-store
  path: /v1/stores/{storeId}
- description: Get top trending products by view velocity
  method: GET
  name: get-trending
  path: /v1/trending
- description: Get products frequently viewed alongside this SKU
  method: GET
  name: get-also-viewed
  path: /v1/products/{sku}/also-viewed
- description: Get products frequently purchased with this SKU
  method: GET
  name: get-also-bought
  path: /v1/products/{sku}/also-bought
personas: []
provider_name: Best Buy
provider_slug: best-buy
search_terms:
- get also viewed products
- get detailed product information for a specific best buy sku including price, availability, and specs
- product search, store lookup, and recommendations
- list stores
- get store
- find best buy stores near a location
- get hours, services, and contact information for a specific best buy store
- behavioral recommendations and trending data
- find best buy stores with proximity search
- find best buy stores near a location using postal code or gps coordinates
- product search, filtering, and attribute retrieval
- authorized best buy commerce partner building shopping experiences
- get products frequently viewed alongside a specific sku for cross-sell discovery
- get the top trending best buy products by category or across the entire catalog
- products
- get detailed product information by sku
- search products
- search the best buy product catalog by keyword, price range, or product attributes
- get products frequently viewed alongside this sku
- get products frequently purchased together with a specific sku for bundle recommendations
- get also bought products
- get a specific best buy product by sku
- e-commerce
- get top trending products by view velocity
- retail
- best buy
- get also-viewed product recommendations
- get the most viewed best buy products in the last 48 hours
- get a specific best buy store
- list products
- search and filter best buy products with keyword search and attribute filtering
- get trending
- get store details including hours and services
- search and browse the best buy product catalog
- get also bought
- get trending products
- recommendations
- get products frequently purchased with this sku
- find stores
- developer building retail integrations and shopping applications
- consumer electronics
- store location, hours, and services
- get also viewed
- get also-bought product recommendations
- get trending best buy products
- stores
- Developer
- get product
- Partner
- get most viewed products
slug: retail-discovery
tags:
- Best Buy
- Retail
- Products
- Stores
- Recommendations
- E-Commerce
tools:
- description: Search the Best Buy product catalog by keyword, price range, or product attributes
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get detailed product information for a specific Best Buy SKU including price, availability, and specs
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Find Best Buy stores near a location using postal code or GPS coordinates
  hints:
    openWorld: true
    readOnly: true
  name: find-stores
- description: Get hours, services, and contact information for a specific Best Buy store
  hints:
    openWorld: false
    readOnly: true
  name: get-store
- description: Get the top trending Best Buy products by category or across the entire catalog
  hints:
    openWorld: true
    readOnly: true
  name: get-trending-products
- description: Get the most viewed Best Buy products in the last 48 hours
  hints:
    openWorld: true
    readOnly: true
  name: get-most-viewed-products
- description: Get products frequently viewed alongside a specific SKU for cross-sell discovery
  hints:
    openWorld: false
    readOnly: true
  name: get-also-viewed-products
- description: Get products frequently purchased together with a specific SKU for bundle recommendations
  hints:
    openWorld: false
    readOnly: true
  name: get-also-bought-products
---
