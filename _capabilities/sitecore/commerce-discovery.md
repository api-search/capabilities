---
categories: []
consumed_apis:
- ordercloud
- discover
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
- create product
- get personalized product recommendations from sitecore discover
- list products
- ordercloud list buyers
- commerce
- list ordercloud orders
- manage commerce orders
- sitecore
- ordercloud create product
- manage commerce products and search product catalog
- full-text search products via sitecore discover
- list products in the ordercloud marketplace
- create a new ordercloud product
- track a behavioral event to improve discover personalization
- get personalized product recommendations via discover
- list ordercloud products
- ordercloud list catalogs
- discover track event
- recommendations
- list orders in ordercloud
- create a new order in ordercloud
- manage product catalogs
- track a behavioral event via discover
- list buyers
- b2b
- list product catalogs in ordercloud
- product discovery
- search
- list orders
- list buyer organizations
- ordercloud list products
- create order
- ordercloud create order
- track event
- get recommendations
- ordercloud list orders
- track behavioral events for discovery personalization
- list buyer organizations in ordercloud
- discover search products
- create a new product in ordercloud
- search products using discover
- order management
- create a new order
- search products
- manage buyer organizations
- list product catalogs
- search products using sitecore discover full-text and faceted search
- list catalogs
- b2c
- get product recommendations
- discover get recommendations
slug: commerce-discovery
source_filename: commerce-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sitecore Commerce and Discovery\"\n  description: >-\n    Unified capability combining Sitecore OrderCloud headless commerce with Sitecore\n    Discover search and recommendations. Enables commerce teams and developers to\n    manage products, catalogs, orders, buyers, and deliver personalized search and\n    discovery experiences from a single interface.\n  tags:\n    - Sitecore\n    - Commerce\n    - Order Management\n    - Product Discovery\n    - Search\n    - Recommendations\n    - B2B\n    - B2C\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORDERCLOUD_ACCESS_TOKEN: ORDERCLOUD_ACCESS_TOKEN\n      DISCOVER_SUBDOMAIN: DISCOVER_SUBDOMAIN\n      DISCOVER_API_KEY: DISCOVER_API_KEY\n\ncapability:\n  consumes:\n    - import: ordercloud\n      location: ./shared/ordercloud.yaml\n    - import: discover\n      location: ./shared/discover.yaml\n\n  exposes:\n    - type: rest\n\
  \      port: 8082\n      namespace: commerce-discovery-api\n      description: \"Unified REST API for Sitecore OrderCloud commerce and Discover search.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Manage commerce products and search product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List OrderCloud products\"\n              call: \"ordercloud.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new OrderCloud product\"\n              call: \"ordercloud.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/search\n          name: product-search\n          description: \"Search products using Discover\"\
  \n          operations:\n            - method: POST\n              name: search-products\n              description: \"Full-text search products via Sitecore Discover\"\n              call: \"discover.search-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations\n          name: recommendations\n          description: \"Get product recommendations\"\n          operations:\n            - method: POST\n              name: get-recommendations\n              description: \"Get personalized product recommendations via Discover\"\n              call: \"discover.get-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Manage commerce orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List\
  \ OrderCloud orders\"\n              call: \"ordercloud.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new order\"\n              call: \"ordercloud.create-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buyers\n          name: buyers\n          description: \"Manage buyer organizations\"\n          operations:\n            - method: GET\n              name: list-buyers\n              description: \"List buyer organizations\"\n              call: \"ordercloud.list-buyers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalogs\n          name: catalogs\n          description: \"Manage product catalogs\"\n          operations:\n            - method: GET\n         \
  \     name: list-catalogs\n              description: \"List product catalogs\"\n              call: \"ordercloud.list-catalogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Track behavioral events for discovery personalization\"\n          operations:\n            - method: POST\n              name: track-event\n              description: \"Track a behavioral event via Discover\"\n              call: \"discover.track-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: commerce-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sitecore commerce and product discovery.\"\n      tools:\n        - name: ordercloud-list-products\n          description: \"List products in the OrderCloud marketplace\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"ordercloud.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ordercloud-create-product\n          description: \"Create a new product in OrderCloud\"\n          call: \"ordercloud.create-product\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ordercloud-list-orders\n          description: \"List orders in OrderCloud\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ordercloud.list-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ordercloud-create-order\n          description: \"Create a new order in OrderCloud\"\n          call: \"ordercloud.create-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ordercloud-list-buyers\n\
  \          description: \"List buyer organizations in OrderCloud\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ordercloud.list-buyers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: ordercloud-list-catalogs\n          description: \"List product catalogs in OrderCloud\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ordercloud.list-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-search-products\n          description: \"Search products using Sitecore Discover full-text and faceted search\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"discover.search-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-get-recommendations\n       \
  \   description: \"Get personalized product recommendations from Sitecore Discover\"\n          hints:\n            readOnly: true\n          call: \"discover.get-recommendations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: discover-track-event\n          description: \"Track a behavioral event to improve Discover personalization\"\n          call: \"discover.track-event\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
