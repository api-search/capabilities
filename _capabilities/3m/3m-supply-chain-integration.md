---
consumed_apis:
- 3m-partner-supplier
description: End-to-end supply chain integration workflow for 3M partners and suppliers. Combines product discovery, order management, delivery tracking, and invoice reconciliation into a unified workflow for procurement managers, supply chain analysts, and accounts payable teams.
layout: capability
name: 3M Supply Chain Integration
operations:
- description: List 3M products available to the authenticated partner.
  method: GET
  name: list-products
  path: /v1/products
- description: Get negotiated price for a specific 3M product.
  method: GET
  name: get-product-price
  path: /v1/products
- description: List purchase orders with status information.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Submit a new purchase order.
  method: POST
  name: create-order
  path: /v1/orders
- description: Track delivery status for partner orders.
  method: GET
  name: list-deliveries
  path: /v1/deliveries
- description: Retrieve invoices for billing reconciliation.
  method: GET
  name: list-invoices
  path: /v1/invoices
personas: []
provider_name: 3M
provider_slug: 3m
search_terms:
- track delivery status for partner orders.
- purchase order management.
- list orders
- 3m product discovery and pricing
- submit a new purchase order.
- Supply Chain Analyst
- 3m product catalog and partner pricing.
- get the partner-negotiated price for a specific 3m product.
- list 3m products available to the authenticated partner with pricing.
- end-to-end supply chain workflow for procurement and billing
- supply chain
- get product price
- searches products, compares pricing, and submits purchase orders
- retrieve 3m invoices for accounts payable reconciliation.
- list purchase orders placed with 3m with status and tracking.
- purchase order submission and tracking
- list 3m products available to the authenticated partner.
- invoice retrieval and accounts payable reconciliation
- track deliveries
- tracks order status, monitors deliveries, and analyzes supply chain data
- manufacturing
- delivery tracking and shipment status
- list deliveries
- retrieve invoices for billing reconciliation.
- list invoices
- industrial
- list products
- list purchase orders with status information.
- submit a new purchase order for 3m products.
- procurement
- Accounts Payable
- invoice retrieval for billing reconciliation.
- get negotiated price for a specific 3m product.
- logistics
- retrieves invoices and reconciles billing with purchase orders
- create order
- Procurement Manager
- delivery tracking and logistics.
- track delivery status and estimated arrival for 3m orders.
slug: 3m-supply-chain-integration
tags:
- Manufacturing
- Supply Chain
- Procurement
- Logistics
tools:
- description: List 3M products available to the authenticated partner with pricing.
  hints:
    openWorld: false
    readOnly: true
  name: list-products
- description: Get the partner-negotiated price for a specific 3M product.
  hints:
    openWorld: false
    readOnly: true
  name: get-product-price
- description: List purchase orders placed with 3M with status and tracking.
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Submit a new purchase order for 3M products.
  hints:
    destructive: false
    readOnly: false
  name: create-order
- description: Track delivery status and estimated arrival for 3M orders.
  hints:
    openWorld: false
    readOnly: true
  name: track-deliveries
- description: Retrieve 3M invoices for accounts payable reconciliation.
  hints:
    openWorld: false
    readOnly: true
  name: list-invoices
---
