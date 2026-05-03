---
categories: []
consumed_apis:
- target-api
description: Unified retail integration capability for Target partner integrations. Combines product catalog, inventory availability, store locator, and order management APIs into customer-facing workflows for e-commerce platforms, affiliate marketers, and retail technology partners.
layout: capability
name: Target Retail Integration
operations:
- description: List products by TCINs, category, or brand
  method: GET
  name: list-products
  path: /v1/products
- description: Search products by keyword with filters
  method: GET
  name: search-products
  path: /v1/products
- description: Get full product details by TCIN
  method: GET
  name: get-product
  path: /v1/products/{tcin}
- description: Get fulfillment availability across all channels
  method: GET
  name: get-product-fulfillment
  path: /v1/products/{tcin}/fulfillment
- description: List nearby Target stores
  method: GET
  name: list-stores
  path: /v1/stores
- description: Get store hours, features, and contact info
  method: GET
  name: get-store
  path: /v1/stores/{store_id}
- description: List orders with status and date filters
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get full order details including line items
  method: GET
  name: get-order
  path: /v1/orders/{order_id}
personas: []
provider_name: target
provider_slug: target
search_terms:
- find stores
- list products by tcins, category, or brand
- get full order details including line items
- list stores
- orders
- get full product details including price, images, and ratings by tcin
- e-commerce
- get target store details
- inventory
- search products
- find target stores near a zip code or geographic coordinates
- stores
- browse and search target product catalog
- get full product details by tcin
- manage partner orders
- get store details
- products
- check product availability for ship-to-home, in-store pickup, and drive-up
- get target store hours, features, and contact information
- fortune 100
- get fulfillment availability across all channels
- list partner orders filtered by status and date range
- list target products by tcins or category filters
- get order
- search target's product catalog by keyword, category, price range, or brand
- find target stores by location
- search products by keyword with filters
- check product availability
- get full details of a target partner order including line items
- target
- check product fulfillment options
- get order details
- get product fulfillment
- list nearby target stores
- retail
- list products
- get product
- list orders with status and date filters
- get store hours, features, and contact info
- list orders
- get detailed product information
- get store
slug: retail-integration
source_filename: retail-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Target Retail Integration\"\n  description: >-\n    Unified retail integration capability for Target partner integrations. Combines\n    product catalog, inventory availability, store locator, and order management APIs\n    into customer-facing workflows for e-commerce platforms, affiliate marketers,\n    and retail technology partners.\n  tags:\n    - E-Commerce\n    - Retail\n    - Products\n    - Inventory\n    - Stores\n    - Orders\n    - Target\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TARGET_API_TOKEN: TARGET_API_TOKEN\n\ncapability:\n  consumes:\n    - import: target-api\n      location: ./shared/target-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: target-retail-api\n      description: \"Unified REST API for Target retail integration workflows.\"\n      resources:\n        - path: /v1/products\n          name: products\n        \
  \  description: \"Browse and search Target product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"List products by TCINs, category, or brand\"\n              call: \"target-api.list-products\"\n              with:\n                tcins: \"rest.tcins\"\n                category: \"rest.category\"\n                brand: \"rest.brand\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: search-products\n              description: \"Search products by keyword with filters\"\n              call: \"target-api.search-products\"\n              with:\n                q: \"rest.q\"\n                category: \"rest.category\"\n                brand: \"rest.brand\"\n                price_min: \"rest.price_min\"\n                price_max: \"rest.price_max\"\
  \n                sort_by: \"rest.sort_by\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{tcin}\n          name: product-detail\n          description: \"Get detailed product information\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get full product details by TCIN\"\n              call: \"target-api.get-product\"\n              with:\n                tcin: \"rest.tcin\"\n                store_id: \"rest.store_id\"\n                zip: \"rest.zip\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{tcin}/fulfillment\n          name: product-fulfillment\n          description: \"Check product fulfillment options\"\n          operations:\n            - method: GET\n            \
  \  name: get-product-fulfillment\n              description: \"Get fulfillment availability across all channels\"\n              call: \"target-api.get-product-fulfillment\"\n              with:\n                tcin: \"rest.tcin\"\n                store_id: \"rest.store_id\"\n                zip: \"rest.zip\"\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores\n          name: stores\n          description: \"Find Target stores by location\"\n          operations:\n            - method: GET\n              name: list-stores\n              description: \"List nearby Target stores\"\n              call: \"target-api.list-stores\"\n              with:\n                zip: \"rest.zip\"\n                latitude: \"rest.latitude\"\n                longitude: \"rest.longitude\"\n                radius: \"rest.radius\"\n     \
  \           limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stores/{store_id}\n          name: store-detail\n          description: \"Get Target store details\"\n          operations:\n            - method: GET\n              name: get-store\n              description: \"Get store hours, features, and contact info\"\n              call: \"target-api.get-store\"\n              with:\n                store_id: \"rest.store_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Manage partner orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders with status and date filters\"\n              call: \"target-api.list-orders\"\n              with:\n                status: \"rest.status\"\n     \
  \           from_date: \"rest.from_date\"\n                to_date: \"rest.to_date\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{order_id}\n          name: order-detail\n          description: \"Get order details\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get full order details including line items\"\n              call: \"target-api.get-order\"\n              with:\n                order_id: \"rest.order_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: target-retail-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Target retail integration.\"\n      tools:\n        - name: search-products\n          description: \"Search\
  \ Target's product catalog by keyword, category, price range, or brand\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.search-products\"\n          with:\n            q: \"tools.q\"\n            category: \"tools.category\"\n            brand: \"tools.brand\"\n            price_min: \"tools.price_min\"\n            price_max: \"tools.price_max\"\n            sort_by: \"tools.sort_by\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: \"List Target products by TCINs or category filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.list-products\"\n          with:\n            tcins: \"tools.tcins\"\n            category: \"tools.category\"\n            brand: \"tools.brand\"\n            limit: \"tools.limit\"\
  \n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get full product details including price, images, and ratings by TCIN\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.get-product\"\n          with:\n            tcin: \"tools.tcin\"\n            store_id: \"tools.store_id\"\n            zip: \"tools.zip\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-product-availability\n          description: \"Check product availability for ship-to-home, in-store pickup, and drive-up\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.get-product-fulfillment\"\n          with:\n            tcin: \"tools.tcin\"\n            store_id: \"tools.store_id\"\n            zip: \"tools.zip\"\n         \
  \   latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-stores\n          description: \"Find Target stores near a ZIP code or geographic coordinates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.list-stores\"\n          with:\n            zip: \"tools.zip\"\n            latitude: \"tools.latitude\"\n            longitude: \"tools.longitude\"\n            radius: \"tools.radius\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-store-details\n          description: \"Get Target store hours, features, and contact information\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"target-api.get-store\"\n          with:\n            store_id: \"tools.store_id\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-orders\n          description: \"List partner orders filtered by status and date range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"target-api.list-orders\"\n          with:\n            status: \"tools.status\"\n            from_date: \"tools.from_date\"\n            to_date: \"tools.to_date\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Get full details of a Target partner order including line items\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"target-api.get-order\"\n          with:\n            order_id: \"tools.order_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/target/refs/heads/main/capabilities/retail-integration.yaml
tags:
- E-Commerce
- Retail
- Products
- Inventory
- Stores
- Orders
- Target
tools:
- description: Search Target's product catalog by keyword, category, price range, or brand
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: List Target products by TCINs or category filters
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get full product details including price, images, and ratings by TCIN
  hints:
    openWorld: true
    readOnly: true
  name: get-product
- description: Check product availability for ship-to-home, in-store pickup, and drive-up
  hints:
    openWorld: true
    readOnly: true
  name: check-product-availability
- description: Find Target stores near a ZIP code or geographic coordinates
  hints:
    openWorld: true
    readOnly: true
  name: find-stores
- description: Get Target store hours, features, and contact information
  hints:
    openWorld: true
    readOnly: true
  name: get-store-details
- description: List partner orders filtered by status and date range
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Get full details of a Target partner order including line items
  hints:
    openWorld: false
    readOnly: true
  name: get-order
---
