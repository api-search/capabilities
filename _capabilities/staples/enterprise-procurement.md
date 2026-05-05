---
categories: []
consumed_apis:
- staples
description: Unified capability for enterprise office supply procurement workflows using Staples Advantage. Enables procurement managers, finance teams, and operations staff to search the product catalog, manage orders with cost center allocation, track deliveries, and handle invoicing through a single integrated API.
layout: capability
name: Staples Enterprise Procurement
operations:
- description: Search office supplies by keyword, category, or brand
  method: GET
  name: search-products
  path: /v1/catalog/search
- description: List all product categories and subcategories
  method: GET
  name: list-categories
  path: /v1/catalog/categories
- description: Get full product specs, pricing, and availability by SKU
  method: GET
  name: get-product
  path: /v1/catalog/products/{sku}
- description: View order history with status and cost center filtering
  method: GET
  name: list-orders
  path: /v1/orders
- description: Place a purchase order with delivery address and cost center allocation
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order details, line items, and tracking numbers
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Get contract terms, credit limits, and account details
  method: GET
  name: get-account
  path: /v1/account
- description: List cost centers with budget and spending data
  method: GET
  name: list-cost-centers
  path: /v1/account/cost-centers
- description: Track shipment status and delivery events
  method: GET
  name: track-delivery
  path: /v1/delivery/tracking/{trackingNumber}
- description: View invoice history with payment status filtering
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Get invoice line items and payment details
  method: GET
  name: get-invoice
  path: /v1/invoices/{invoiceId}
personas: []
provider_name: Staples
provider_slug: staples
search_terms:
- get full staples product specifications, contract pricing, availability, and related skus
- list all product categories and subcategories
- get order details, line items, and tracking numbers
- get staples invoice line items, amounts, and payment status for reconciliation
- enterprise procurement
- get order status
- get staples advantage account information including contract number, credit limit, and payment terms
- track the delivery status and shipment events for a staples order by tracking number
- get contract terms, credit limits, and account details
- invoice and billing management
- get product details
- get account
- cost center budget management
- list cost centers with budget and spending data
- get account details
- search office supplies by keyword, category, or brand
- get invoice details
- place order
- get order
- get invoice line items and payment details
- submit a staples advantage purchase order with product skus, quantities, delivery address, and cost center allocation
- search staples advantage product catalog by keyword, category, or brand with in-stock filtering
- invoicing
- list invoices
- procurement
- get invoice
- account and contract information
- check staples advantage order status, line items, and carrier tracking numbers
- view staples advantage invoice history with filtering by payment status and date range
- list categories
- view all configured cost centers with budget allocations and current spending
- retail
- b2b
- invoice details
- eprocurement
- shipment delivery tracking
- view invoice history with payment status filtering
- search the staples product catalog
- staples
- get product
- get full product specs, pricing, and availability by sku
- place a purchase order with delivery address and cost center allocation
- list orders
- view order history with status and cost center filtering
- track shipment status and delivery events
- track delivery
- create order
- browse product category hierarchy
- order status and details
- browse staples product category hierarchy including office supplies, technology, furniture, and cleaning
- purchase order management
- office supplies
- order management
- search products
- list cost centers
- view staples advantage order history filterable by status, date range, and cost center
slug: enterprise-procurement
source_filename: enterprise-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Staples Enterprise Procurement\"\n  description: >-\n    Unified capability for enterprise office supply procurement workflows using Staples Advantage. Enables procurement managers, finance teams, and operations staff to search the product catalog, manage orders with cost center allocation, track deliveries, and handle invoicing through a single integrated API.\n  tags:\n    - Staples\n    - Enterprise Procurement\n    - Office Supplies\n    - B2B\n    - eProcurement\n    - Order Management\n    - Invoicing\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STAPLES_API_TOKEN: STAPLES_API_TOKEN\n\ncapability:\n  consumes:\n    - import: staples\n      location: ./shared/staples-advantage-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: enterprise-procurement-api\n      description: \"Unified REST API for Staples Advantage enterprise procurement workflows.\"\
  \n      resources:\n        - path: /v1/catalog/search\n          name: catalog-search\n          description: Search the Staples product catalog\n          operations:\n            - method: GET\n              name: search-products\n              description: Search office supplies by keyword, category, or brand\n              call: \"staples.search-products\"\n              with:\n                q: \"rest.q\"\n                category: \"rest.category\"\n                brand: \"rest.brand\"\n                inStock: \"rest.inStock\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/categories\n          name: catalog-categories\n          description: Browse product category hierarchy\n          operations:\n            - method: GET\n              name: list-categories\n              description: List all product categories and subcategories\n              call:\
  \ \"staples.list-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog/products/{sku}\n          name: catalog-product\n          description: Get product details\n          operations:\n            - method: GET\n              name: get-product\n              description: Get full product specs, pricing, and availability by SKU\n              call: \"staples.get-product\"\n              with:\n                sku: \"rest.sku\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: Purchase order management\n          operations:\n            - method: GET\n              name: list-orders\n              description: View order history with status and cost center filtering\n              call: \"staples.list-orders\"\n              with:\n                status: \"rest.status\"\
  \n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                costCenter: \"rest.costCenter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: Place a purchase order with delivery address and cost center allocation\n              call: \"staples.create-order\"\n              with:\n                items: \"rest.items\"\n                deliveryAddress: \"rest.deliveryAddress\"\n                purchaseOrderNumber: \"rest.purchaseOrderNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{orderId}\n          name: order\n          description: Order status and details\n          operations:\n            - method: GET\n              name: get-order\n              description: Get order details, line items, and tracking numbers\n\
  \              call: \"staples.get-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/account\n          name: account\n          description: Account and contract information\n          operations:\n            - method: GET\n              name: get-account\n              description: Get contract terms, credit limits, and account details\n              call: \"staples.get-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/account/cost-centers\n          name: cost-centers\n          description: Cost center budget management\n          operations:\n            - method: GET\n              name: list-cost-centers\n              description: List cost centers with budget and spending data\n              call: \"staples.list-cost-centers\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/delivery/tracking/{trackingNumber}\n          name: delivery-tracking\n          description: Shipment delivery tracking\n          operations:\n            - method: GET\n              name: track-delivery\n              description: Track shipment status and delivery events\n              call: \"staples.track-delivery\"\n              with:\n                trackingNumber: \"rest.trackingNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: Invoice and billing management\n          operations:\n            - method: GET\n              name: list-invoices\n              description: View invoice history with payment status filtering\n              call: \"staples.list-invoices\"\n              with:\n                status: \"rest.status\"\n                startDate:\
  \ \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices/{invoiceId}\n          name: invoice\n          description: Invoice details\n          operations:\n            - method: GET\n              name: get-invoice\n              description: Get invoice line items and payment details\n              call: \"staples.get-invoice\"\n              with:\n                invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: enterprise-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Staples enterprise procurement workflows.\"\n      tools:\n        - name: search-products\n          description: Search Staples Advantage product catalog by keyword, category, or brand with in-stock filtering\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"staples.search-products\"\n          with:\n            q: \"tools.q\"\n            category: \"tools.category\"\n            brand: \"tools.brand\"\n            inStock: \"tools.inStock\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-categories\n          description: Browse Staples product category hierarchy including office supplies, technology, furniture, and cleaning\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"staples.list-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-details\n          description: Get full Staples product specifications, contract pricing, availability, and related SKUs\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"staples.get-product\"\n          with:\n            sku: \"tools.sku\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-orders\n          description: View Staples Advantage order history filterable by status, date range, and cost center\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.list-orders\"\n          with:\n            status: \"tools.status\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            costCenter: \"tools.costCenter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: place-order\n          description: Submit a Staples Advantage purchase order with product SKUs, quantities, delivery address, and cost center allocation\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"staples.create-order\"\
  \n          with:\n            items: \"tools.items\"\n            deliveryAddress: \"tools.deliveryAddress\"\n            purchaseOrderNumber: \"tools.purchaseOrderNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-order-status\n          description: Check Staples Advantage order status, line items, and carrier tracking numbers\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.get-order\"\n          with:\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account-details\n          description: Get Staples Advantage account information including contract number, credit limit, and payment terms\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.get-account\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-cost-centers\n          description: View all configured cost centers with budget allocations and current spending\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.list-cost-centers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-delivery\n          description: Track the delivery status and shipment events for a Staples order by tracking number\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.track-delivery\"\n          with:\n            trackingNumber: \"tools.trackingNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-invoices\n          description: View Staples Advantage invoice history with filtering by payment status and date range\n          hints:\n            readOnly: true\n     \
  \       idempotent: true\n          call: \"staples.list-invoices\"\n          with:\n            status: \"tools.status\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-invoice-details\n          description: Get Staples invoice line items, amounts, and payment status for reconciliation\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"staples.get-invoice\"\n          with:\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/staples/refs/heads/main/capabilities/enterprise-procurement.yaml
tags:
- Staples
- Enterprise Procurement
- Office Supplies
- B2B
- eProcurement
- Order Management
- Invoicing
tools:
- description: Search Staples Advantage product catalog by keyword, category, or brand with in-stock filtering
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Browse Staples product category hierarchy including office supplies, technology, furniture, and cleaning
  hints:
    openWorld: true
    readOnly: true
  name: list-categories
- description: Get full Staples product specifications, contract pricing, availability, and related SKUs
  hints:
    idempotent: true
    readOnly: true
  name: get-product-details
- description: View Staples Advantage order history filterable by status, date range, and cost center
  hints:
    idempotent: true
    readOnly: true
  name: list-orders
- description: Submit a Staples Advantage purchase order with product SKUs, quantities, delivery address, and cost center allocation
  hints:
    destructive: false
    readOnly: false
  name: place-order
- description: Check Staples Advantage order status, line items, and carrier tracking numbers
  hints:
    idempotent: true
    readOnly: true
  name: get-order-status
- description: Get Staples Advantage account information including contract number, credit limit, and payment terms
  hints:
    idempotent: true
    readOnly: true
  name: get-account-details
- description: View all configured cost centers with budget allocations and current spending
  hints:
    idempotent: true
    readOnly: true
  name: list-cost-centers
- description: Track the delivery status and shipment events for a Staples order by tracking number
  hints:
    idempotent: true
    readOnly: true
  name: track-delivery
- description: View Staples Advantage invoice history with filtering by payment status and date range
  hints:
    idempotent: true
    readOnly: true
  name: list-invoices
- description: Get Staples invoice line items, amounts, and payment status for reconciliation
  hints:
    idempotent: true
    readOnly: true
  name: get-invoice-details
---
