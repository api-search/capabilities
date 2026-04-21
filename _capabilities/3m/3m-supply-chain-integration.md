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
- Procurement Manager
- manufacturing
- track deliveries
- get the partner-negotiated price for a specific 3m product.
- submit a new purchase order.
- delivery tracking and logistics.
- retrieves invoices and reconciles billing with purchase orders
- 3m product catalog and partner pricing.
- Accounts Payable
- delivery tracking and shipment status
- 3m product discovery and pricing
- list 3m products available to the authenticated partner.
- tracks order status, monitors deliveries, and analyzes supply chain data
- track delivery status and estimated arrival for 3m orders.
- list deliveries
- retrieve invoices for billing reconciliation.
- list 3m products available to the authenticated partner with pricing.
- supply chain
- procurement
- list products
- list purchase orders placed with 3m with status and tracking.
- list purchase orders with status information.
- create order
- Supply Chain Analyst
- retrieve 3m invoices for accounts payable reconciliation.
- submit a new purchase order for 3m products.
- end-to-end supply chain workflow for procurement and billing
- get negotiated price for a specific 3m product.
- track delivery status for partner orders.
- searches products, compares pricing, and submits purchase orders
- purchase order submission and tracking
- list invoices
- get product price
- logistics
- list orders
- invoice retrieval for billing reconciliation.
- invoice retrieval and accounts payable reconciliation
- industrial
- purchase order management.
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
