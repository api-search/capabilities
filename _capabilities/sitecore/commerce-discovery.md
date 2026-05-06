---
categories: []
consumed_apis: []
description: Unified capability combining Sitecore OrderCloud headless commerce with Sitecore Discover search and recommendations. Enables commerce teams and developers to manage products, catalogs, orders, buyers, and deliver personalized search and discovery experiences from a single interface.
layout: capability
name: Sitecore Commerce and Discovery
operations:
- description: List OrderCloud products
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new OrderCloud product
  method: POST
  name: create-product
  path: /v1/products
- description: Full-text search products via Sitecore Discover
  method: POST
  name: search-products
  path: /v1/products/search
- description: Get personalized product recommendations via Discover
  method: POST
  name: get-recommendations
  path: /v1/recommendations
- description: List OrderCloud orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order
  method: POST
  name: create-order
  path: /v1/orders
- description: List buyer organizations
  method: GET
  name: list-buyers
  path: /v1/buyers
- description: List product catalogs
  method: GET
  name: list-catalogs
  path: /v1/catalogs
- description: Track a behavioral event via Discover
  method: POST
  name: track-event
  path: /v1/events
personas: []
provider_name: sitecore
provider_slug: sitecore
search_terms:
- list buyers
- list products in the ordercloud marketplace
- ordercloud create product
- ordercloud list buyers
- manage commerce products and search product catalog
- search products using sitecore discover full-text and faceted search
- create a new product in ordercloud
- list orders in ordercloud
- full-text search products via sitecore discover
- list ordercloud orders
- discover get recommendations
- list catalogs
- track a behavioral event via discover
- b2b
- product discovery
- get personalized product recommendations via discover
- manage product catalogs
- discover search products
- commerce
- manage commerce orders
- get product recommendations
- list buyer organizations
- track behavioral events for discovery personalization
- get recommendations
- list product catalogs in ordercloud
- track a behavioral event to improve discover personalization
- list ordercloud products
- create a new ordercloud product
- create a new order
- sitecore
- list product catalogs
- b2c
- ordercloud list products
- discover track event
- search
- manage buyer organizations
- create a new order in ordercloud
- list buyer organizations in ordercloud
- create order
- ordercloud list catalogs
- list orders
- list products
- get personalized product recommendations from sitecore discover
- create product
- search products using discover
- track event
- ordercloud create order
- order management
- ordercloud list orders
- search products
- recommendations
slug: commerce-discovery
source_filename: commerce-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sitecore Commerce and Discovery\n  description: Unified capability combining Sitecore OrderCloud headless commerce with Sitecore Discover search and recommendations.\n    Enables commerce teams and developers to manage products, catalogs, orders, buyers, and deliver personalized search and\n    discovery experiences from a single interface.\n  tags:\n  - Sitecore\n  - Commerce\n  - Order Management\n  - Product Discovery\n  - Search\n  - Recommendations\n  - B2B\n  - B2C\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORDERCLOUD_ACCESS_TOKEN: ORDERCLOUD_ACCESS_TOKEN\n    DISCOVER_SUBDOMAIN: DISCOVER_SUBDOMAIN\n    DISCOVER_API_KEY: DISCOVER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ordercloud\n    baseUri: https://api.ordercloud.io/v1\n    description: Sitecore OrderCloud headless commerce API\n    authentication:\n      type: bearer\n      token: '{{ORDERCLOUD_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: products\n      path: /products\n      description: Manage commerce products and catalog items\n      operations:\n      - name: list-products\n        method: GET\n        description: List products in the marketplace\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search term\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.Name}}'\n            Description: '{{tools.Description}}'\n            Active: '{{tools.Active}}'\n    - name: orders\n      path: /orders\n      description: Manage orders across buyer/seller contexts\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders with filtering and pagination\n        inputParameters:\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: Incoming or outgoing orders\n        - name: buyerID\n          in: query\n          type: string\n          required: false\n          description: Filter by buyer\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Order status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            FromUserID: '{{tools.FromUserID}}'\n            BillingAddressID: '{{tools.BillingAddressID}}'\n    - name: buyers\n      path: /buyers\n      description: Manage buyer organizations\n      operations:\n      - name: list-buyers\n        method: GET\n        description: List buyer organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-buyer\n        method: POST\n        description: Create a new buyer organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n  \
  \        data:\n            Name: '{{tools.Name}}'\n            Active: '{{tools.Active}}'\n    - name: catalogs\n      path: /catalogs\n      description: Manage product catalogs\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List product catalogs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: discover\n    baseUri: https://{{DISCOVER_SUBDOMAIN}}.rfksrv.com\n    description: Sitecore Discover search and recommendations API\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{DISCOVER_API_KEY}}'\n      placement: header\n    resources:\n    - name: search\n      path: /search/v3/{entity}\n      description: Full-text search and faceted filtering for products\n      operations:\n      - name: search-products\n        method: POST\n        description: Search products with full-text and faceted filtering\n \
  \       inputParameters:\n        - name: entity\n          in: path\n          type: string\n          required: true\n          description: Entity type (e.g., content, product)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            facets: '{{tools.facets}}'\n    - name: recommendations\n      path: /rfk/v3/recommend\n      description: Product recommendation endpoints\n      operations:\n      - name: get-recommendations\n        method: POST\n        description: Get personalized product recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            rfkid: '{{tools.rfkid}}'\n            n_item: '{{tools.n_item}}'\n    - name: events\n      path: /v3/event\n     \
  \ description: Behavioral event tracking for discovery algorithms\n      operations:\n      - name: track-event\n        method: POST\n        description: Track a behavioral event to feed discovery algorithms\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            entity_type: '{{tools.entity_type}}'\n            entity_id: '{{tools.entity_id}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: commerce-discovery-api\n    description: Unified REST API for Sitecore OrderCloud commerce and Discover search.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Manage commerce products and search product catalog\n      operations:\n      - method: GET\n        name: list-products\n        description: List OrderCloud products\n        call: ordercloud.list-products\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Create a new OrderCloud product\n        call: ordercloud.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/search\n      name: product-search\n      description: Search products using Discover\n      operations:\n      - method: POST\n        name: search-products\n        description: Full-text search products via Sitecore Discover\n        call: discover.search-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recommendations\n      name: recommendations\n      description: Get product recommendations\n      operations:\n      - method: POST\n        name: get-recommendations\n        description: Get personalized product recommendations via Discover\n        call: discover.get-recommendations\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Manage commerce orders\n      operations:\n      - method: GET\n        name: list-orders\n        description: List OrderCloud orders\n        call: ordercloud.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new order\n        call: ordercloud.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buyers\n      name: buyers\n      description: Manage buyer organizations\n      operations:\n      - method: GET\n        name: list-buyers\n        description: List buyer organizations\n        call: ordercloud.list-buyers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalogs\n      name: catalogs\n      description: Manage product catalogs\n      operations:\n      - method: GET\n        name: list-catalogs\n\
  \        description: List product catalogs\n        call: ordercloud.list-catalogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Track behavioral events for discovery personalization\n      operations:\n      - method: POST\n        name: track-event\n        description: Track a behavioral event via Discover\n        call: discover.track-event\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: commerce-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Sitecore commerce and product discovery.\n    tools:\n    - name: ordercloud-list-products\n      description: List products in the OrderCloud marketplace\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ordercloud.list-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ordercloud-create-product\n\
  \      description: Create a new product in OrderCloud\n      call: ordercloud.create-product\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ordercloud-list-orders\n      description: List orders in OrderCloud\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ordercloud.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ordercloud-create-order\n      description: Create a new order in OrderCloud\n      call: ordercloud.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ordercloud-list-buyers\n      description: List buyer organizations in OrderCloud\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ordercloud.list-buyers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ordercloud-list-catalogs\n      description: List product catalogs in OrderCloud\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: ordercloud.list-catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-search-products\n      description: Search products using Sitecore Discover full-text and faceted search\n      hints:\n        readOnly: true\n        openWorld: true\n      call: discover.search-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-get-recommendations\n      description: Get personalized product recommendations from Sitecore Discover\n      hints:\n        readOnly: true\n      call: discover.get-recommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-track-event\n      description: Track a behavioral event to improve Discover personalization\n      call: discover.track-event\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sitecore/refs/heads/main/capabilities/commerce-discovery.yaml
tags:
- Sitecore
- Commerce
- Order Management
- Product Discovery
- Search
- Recommendations
- B2B
- B2C
tools:
- description: List products in the OrderCloud marketplace
  hints:
    idempotent: true
    readOnly: true
  name: ordercloud-list-products
- description: Create a new product in OrderCloud
  hints: {}
  name: ordercloud-create-product
- description: List orders in OrderCloud
  hints:
    idempotent: true
    readOnly: true
  name: ordercloud-list-orders
- description: Create a new order in OrderCloud
  hints: {}
  name: ordercloud-create-order
- description: List buyer organizations in OrderCloud
  hints:
    idempotent: true
    readOnly: true
  name: ordercloud-list-buyers
- description: List product catalogs in OrderCloud
  hints:
    idempotent: true
    readOnly: true
  name: ordercloud-list-catalogs
- description: Search products using Sitecore Discover full-text and faceted search
  hints:
    openWorld: true
    readOnly: true
  name: discover-search-products
- description: Get personalized product recommendations from Sitecore Discover
  hints:
    readOnly: true
  name: discover-get-recommendations
- description: Track a behavioral event to improve Discover personalization
  hints: {}
  name: discover-track-event
---
