---
categories: []
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
- get detailed product information by sku
- find best buy stores near a location using postal code or gps coordinates
- recommendations
- retail
- find best buy stores with proximity search
- list stores
- get detailed product information for a specific best buy sku including price, availability, and specs
- developer building retail integrations and shopping applications
- get also viewed
- store location, hours, and services
- get a specific best buy product by sku
- get most viewed products
- get product
- product search, store lookup, and recommendations
- Developer
- e-commerce
- get trending
- products
- best buy
- get products frequently purchased with this sku
- search and filter best buy products with keyword search and attribute filtering
- get also bought products
- search products
- stores
- get a specific best buy store
- get the most viewed best buy products in the last 48 hours
- get also-bought product recommendations
- get hours, services, and contact information for a specific best buy store
- get products frequently purchased together with a specific sku for bundle recommendations
- Partner
- get products frequently viewed alongside this sku
- get top trending products by view velocity
- get also viewed products
- find stores
- list products
- get trending products
- get store details including hours and services
- search the best buy product catalog by keyword, price range, or product attributes
- product search, filtering, and attribute retrieval
- get also-viewed product recommendations
- authorized best buy commerce partner building shopping experiences
- search and browse the best buy product catalog
- behavioral recommendations and trending data
- get the top trending best buy products by category or across the entire catalog
- get also bought
- get products frequently viewed alongside a specific sku for cross-sell discovery
- consumer electronics
- find best buy stores near a location
- get store
slug: retail-discovery
source_filename: retail-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Best Buy Retail Discovery\"\n  description: >-\n    Unified retail discovery workflow combining product search, store locator, and\n    personalized recommendations. Designed for developers and partners building\n    retail integrations, shopping apps, and e-commerce experiences. Combines the\n    Products, Stores, and Recommendations APIs into a cohesive consumer-facing\n    workflow for product discovery, inventory lookup, and personalized suggestions.\n  tags:\n    - Best Buy\n    - Retail\n    - Products\n    - Stores\n    - Recommendations\n    - E-Commerce\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BEST_BUY_API_KEY: BEST_BUY_API_KEY\n\ncapability:\n  consumes:\n    - import: best-buy-products\n      location: ./shared/products-api.yaml\n    - import: best-buy-stores\n      location: ./shared/stores-api.yaml\n    - import: best-buy-recommendations\n      location:\
  \ ./shared/recommendations-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: retail-discovery-api\n      description: \"Unified REST API for Best Buy retail product discovery and store lookup.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Search and browse the Best Buy product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"Search and filter Best Buy products with keyword search and attribute filtering\"\n              call: \"best-buy-products.list-products\"\n              with:\n                search: \"rest.search\"\n                pageSize: \"rest.pageSize\"\n                page: \"rest.page\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{sku}\n          name: product\n          description: \"Get a specific\
  \ Best Buy product by SKU\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get detailed product information by SKU\"\n              call: \"best-buy-products.get-product-by-sku\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores\n          name: stores\n          description: \"Find Best Buy stores near a location\"\n          operations:\n            - method: GET\n              name: list-stores\n              description: \"Find Best Buy stores with proximity search\"\n              call: \"best-buy-stores.list-stores\"\n              with:\n                area: \"rest.area\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores/{storeId}\n          name: store\n     \
  \     description: \"Get a specific Best Buy store\"\n          operations:\n            - method: GET\n              name: get-store\n              description: \"Get store details including hours and services\"\n              call: \"best-buy-stores.get-store-by-id\"\n              with:\n                storeId: \"rest.storeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trending\n          name: trending-products\n          description: \"Get trending Best Buy products\"\n          operations:\n            - method: GET\n              name: get-trending\n              description: \"Get top trending products by view velocity\"\n              call: \"best-buy-recommendations.get-trending-products\"\n              with:\n                categoryId: \"rest.categoryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{sku}/also-viewed\n\
  \          name: also-viewed\n          description: \"Get also-viewed product recommendations\"\n          operations:\n            - method: GET\n              name: get-also-viewed\n              description: \"Get products frequently viewed alongside this SKU\"\n              call: \"best-buy-recommendations.get-also-viewed-products\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{sku}/also-bought\n          name: also-bought\n          description: \"Get also-bought product recommendations\"\n          operations:\n            - method: GET\n              name: get-also-bought\n              description: \"Get products frequently purchased with this SKU\"\n              call: \"best-buy-recommendations.get-also-bought-products\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: retail-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Best Buy product discovery, store lookup, and recommendations.\"\n      tools:\n        - name: search-products\n          description: \"Search the Best Buy product catalog by keyword, price range, or product attributes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"best-buy-products.list-products\"\n          with:\n            search: \"tools.search\"\n            pageSize: \"tools.pageSize\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get detailed product information for a specific Best Buy SKU including price, availability, and specs\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"best-buy-products.get-product-by-sku\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-stores\n          description: \"Find Best Buy stores near a location using postal code or GPS coordinates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"best-buy-stores.list-stores\"\n          with:\n            area: \"tools.area\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-store\n          description: \"Get hours, services, and contact information for a specific Best Buy store\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"best-buy-stores.get-store-by-id\"\n          with:\n            storeId: \"tools.storeId\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: get-trending-products\n          description: \"Get the top trending Best Buy products by category or across the entire catalog\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"best-buy-recommendations.get-trending-products\"\n          with:\n            categoryId: \"tools.categoryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-most-viewed-products\n          description: \"Get the most viewed Best Buy products in the last 48 hours\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"best-buy-recommendations.get-most-viewed-products\"\n          with:\n            categoryId: \"tools.categoryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-also-viewed-products\n          description: \"Get products frequently viewed alongside a\
  \ specific SKU for cross-sell discovery\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"best-buy-recommendations.get-also-viewed-products\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-also-bought-products\n          description: \"Get products frequently purchased together with a specific SKU for bundle recommendations\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"best-buy-recommendations.get-also-bought-products\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/best-buy/refs/heads/main/capabilities/retail-discovery.yaml
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
