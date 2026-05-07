---
categories: []
consumed_apis: []
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
- get also-bought product recommendations
- get trending products
- get product
- find best buy stores with proximity search
- retail
- get also bought products
- list products
- Partner
- store location, hours, and services
- get also bought
- behavioral recommendations and trending data
- get store
- get detailed product information by sku
- get also viewed
- get a specific best buy product by sku
- get the most viewed best buy products in the last 48 hours
- products
- get products frequently viewed alongside this sku
- stores
- get products frequently purchased together with a specific sku for bundle recommendations
- authorized best buy commerce partner building shopping experiences
- developer building retail integrations and shopping applications
- product search, store lookup, and recommendations
- product search, filtering, and attribute retrieval
- e-commerce
- list stores
- get a specific best buy store
- search and browse the best buy product catalog
- consumer electronics
- search and filter best buy products with keyword search and attribute filtering
- find best buy stores near a location
- get most viewed products
- recommendations
- get detailed product information for a specific best buy sku including price, availability, and specs
- Developer
- find stores
- get trending best buy products
- get trending
- get hours, services, and contact information for a specific best buy store
- get the top trending best buy products by category or across the entire catalog
- get top trending products by view velocity
- search the best buy product catalog by keyword, price range, or product attributes
- get products frequently viewed alongside a specific sku for cross-sell discovery
- get also viewed products
- get also-viewed product recommendations
- find best buy stores near a location using postal code or gps coordinates
- get products frequently purchased with this sku
- best buy
- search products
- get store details including hours and services
slug: retail-discovery
source_filename: retail-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Best Buy Retail Discovery\n  description: Unified retail discovery workflow combining product search, store locator, and personalized recommendations.\n    Designed for developers and partners building retail integrations, shopping apps, and e-commerce experiences. Combines\n    the Products, Stores, and Recommendations APIs into a cohesive consumer-facing workflow for product discovery, inventory\n    lookup, and personalized suggestions.\n  tags:\n  - Best Buy\n  - Retail\n  - Products\n  - Stores\n  - Recommendations\n  - E-Commerce\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BEST_BUY_API_KEY: BEST_BUY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: best-buy-products\n    baseUri: https://api.bestbuy.com/v1\n    description: Best Buy Products API for querying the product catalog.\n    authentication:\n      type: apikey\n      key: apiKey\n      value: '{{BEST_BUY_API_KEY}}'\n\
  \      placement: query\n    resources:\n    - name: products\n      path: /products\n      description: Product catalog queries\n      operations:\n      - name: list-products\n        method: GET\n        description: Query the Best Buy product catalog with filtering and search\n        inputParameters:\n        - name: show\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of attributes to return\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page (max 100)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort attribute and direction\n        - name: search\n          in: query\n          type: string\n      \
  \    required: false\n          description: Keyword search across product attributes\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json or xml)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product-by-sku\n        method: GET\n        description: Retrieve a single product by SKU number\n        inputParameters:\n        - name: sku\n          in: path\n          type: integer\n          required: true\n          description: The Best Buy product SKU number\n        - name: show\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of attributes to return\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json or xml)\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: best-buy-stores\n    baseUri: https://api.bestbuy.com/v1\n    description: Best Buy Stores API for location and operational data.\n    authentication:\n      type: apikey\n      key: apiKey\n      value: '{{BEST_BUY_API_KEY}}'\n      placement: query\n    resources:\n    - name: stores\n      path: /stores\n      description: Store location queries\n      operations:\n      - name: list-stores\n        method: GET\n        description: Query Best Buy store locations with proximity search\n        inputParameters:\n        - name: area\n          in: query\n          type: string\n          required: false\n          description: Proximity search - area(postalCode,radius) or area(lat,lng,radius)\n        - name: show\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of attributes to return\n   \
  \     - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort attribute and direction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-store-by-id\n        method: GET\n        description: Get detailed information for a specific Best Buy store\n        inputParameters:\n        - name: storeId\n          in: path\n          type: integer\n          required: true\n          description: The unique Best Buy store identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: best-buy-recommendations\n    baseUri: https://api.bestbuy.com/v1\n    description: Best Buy Recommendations\
  \ API for behavior-based product suggestions.\n    authentication:\n      type: apikey\n      key: apiKey\n      value: '{{BEST_BUY_API_KEY}}'\n      placement: query\n    resources:\n    - name: recommendations\n      path: /products\n      description: Product recommendation endpoints\n      operations:\n      - name: get-trending-products\n        method: GET\n        description: Top 10 products with highest view velocity (rolling 3-hour window)\n        inputParameters:\n        - name: categoryId\n          in: query\n          type: string\n          required: false\n          description: Filter to a specific category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-most-viewed-products\n        method: GET\n        description: Top 10 most frequently viewed products (48-hour window)\n        inputParameters:\n        - name: categoryId\n          in: query\n          type: string\n\
  \          required: false\n          description: Filter to a specific category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-also-viewed-products\n        method: GET\n        description: Products browsed alongside a specific SKU (30-day window)\n        inputParameters:\n        - name: sku\n          in: path\n          type: integer\n          required: true\n          description: SKU to get also-viewed recommendations for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-also-bought-products\n        method: GET\n        description: Products purchased together with a specific SKU (30-day window)\n        inputParameters:\n        - name: sku\n          in: path\n          type: integer\n          required: true\n          description: SKU to get also-bought recommendations for\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: retail-discovery-api\n    description: Unified REST API for Best Buy retail product discovery and store lookup.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Search and browse the Best Buy product catalog\n      operations:\n      - method: GET\n        name: list-products\n        description: Search and filter Best Buy products with keyword search and attribute filtering\n        call: best-buy-products.list-products\n        with:\n          search: rest.search\n          pageSize: rest.pageSize\n          page: rest.page\n          sort: rest.sort\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}\n      name: product\n      description: Get a specific Best Buy product by SKU\n      operations:\n      - method:\
  \ GET\n        name: get-product\n        description: Get detailed product information by SKU\n        call: best-buy-products.get-product-by-sku\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores\n      name: stores\n      description: Find Best Buy stores near a location\n      operations:\n      - method: GET\n        name: list-stores\n        description: Find Best Buy stores with proximity search\n        call: best-buy-stores.list-stores\n        with:\n          area: rest.area\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores/{storeId}\n      name: store\n      description: Get a specific Best Buy store\n      operations:\n      - method: GET\n        name: get-store\n        description: Get store details including hours and services\n        call: best-buy-stores.get-store-by-id\n        with:\n          storeId:\
  \ rest.storeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trending\n      name: trending-products\n      description: Get trending Best Buy products\n      operations:\n      - method: GET\n        name: get-trending\n        description: Get top trending products by view velocity\n        call: best-buy-recommendations.get-trending-products\n        with:\n          categoryId: rest.categoryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}/also-viewed\n      name: also-viewed\n      description: Get also-viewed product recommendations\n      operations:\n      - method: GET\n        name: get-also-viewed\n        description: Get products frequently viewed alongside this SKU\n        call: best-buy-recommendations.get-also-viewed-products\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{sku}/also-bought\n\
  \      name: also-bought\n      description: Get also-bought product recommendations\n      operations:\n      - method: GET\n        name: get-also-bought\n        description: Get products frequently purchased with this SKU\n        call: best-buy-recommendations.get-also-bought-products\n        with:\n          sku: rest.sku\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: retail-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Best Buy product discovery, store lookup, and recommendations.\n    tools:\n    - name: search-products\n      description: Search the Best Buy product catalog by keyword, price range, or product attributes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: best-buy-products.list-products\n      with:\n        search: tools.search\n        pageSize: tools.pageSize\n        page: tools.page\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-product\n      description: Get detailed product information for a specific Best Buy SKU including price, availability, and specs\n      hints:\n        readOnly: true\n        openWorld: false\n      call: best-buy-products.get-product-by-sku\n      with:\n        sku: tools.sku\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-stores\n      description: Find Best Buy stores near a location using postal code or GPS coordinates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: best-buy-stores.list-stores\n      with:\n        area: tools.area\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-store\n      description: Get hours, services, and contact information for a specific Best Buy store\n      hints:\n        readOnly: true\n        openWorld: false\n      call: best-buy-stores.get-store-by-id\n      with:\n       \
  \ storeId: tools.storeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trending-products\n      description: Get the top trending Best Buy products by category or across the entire catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: best-buy-recommendations.get-trending-products\n      with:\n        categoryId: tools.categoryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-most-viewed-products\n      description: Get the most viewed Best Buy products in the last 48 hours\n      hints:\n        readOnly: true\n        openWorld: true\n      call: best-buy-recommendations.get-most-viewed-products\n      with:\n        categoryId: tools.categoryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-also-viewed-products\n      description: Get products frequently viewed alongside a specific SKU for cross-sell discovery\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: best-buy-recommendations.get-also-viewed-products\n      with:\n        sku: tools.sku\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-also-bought-products\n      description: Get products frequently purchased together with a specific SKU for bundle recommendations\n      hints:\n        readOnly: true\n        openWorld: false\n      call: best-buy-recommendations.get-also-bought-products\n      with:\n        sku: tools.sku\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
