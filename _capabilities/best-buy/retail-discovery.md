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
- get trending best buy products
- search the best buy product catalog by keyword, price range, or product attributes
- get also-bought product recommendations
- get store
- get hours, services, and contact information for a specific best buy store
- get products frequently purchased with this sku
- get detailed product information for a specific best buy sku including price, availability, and specs
- get the most viewed best buy products in the last 48 hours
- get also bought products
- behavioral recommendations and trending data
- get product
- store location, hours, and services
- get also viewed products
- product search, filtering, and attribute retrieval
- get the top trending best buy products by category or across the entire catalog
- get trending products
- developer building retail integrations and shopping applications
- get store details including hours and services
- get products frequently purchased together with a specific sku for bundle recommendations
- products
- consumer electronics
- get a specific best buy product by sku
- get trending
- find best buy stores with proximity search
- e-commerce
- recommendations
- get also viewed
- get products frequently viewed alongside this sku
- find stores
- Partner
- best buy
- stores
- get detailed product information by sku
- get a specific best buy store
- search and browse the best buy product catalog
- find best buy stores near a location using postal code or gps coordinates
- find best buy stores near a location
- product search, store lookup, and recommendations
- list products
- get also bought
- list stores
- search and filter best buy products with keyword search and attribute filtering
- search products
- get most viewed products
- get products frequently viewed alongside a specific sku for cross-sell discovery
- get top trending products by view velocity
- retail
- authorized best buy commerce partner building shopping experiences
- Developer
- get also-viewed product recommendations
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
