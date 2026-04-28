---
categories: []
consumed_apis:
- sales-order
description: Unified order-to-cash capability combining sales order management with items, partners, pricing, schedule lines, and text records. Used by sales operations and order management teams.
layout: capability
name: SAP S/4HANA Order-to-Cash
operations:
- description: List sales orders
  method: GET
  name: list-sales-orders
  path: /v1/sales-orders
- description: Create a sales order
  method: POST
  name: create-sales-order
  path: /v1/sales-orders
personas: []
provider_name: SAP S/4HANA
provider_slug: sap-s4hana
search_terms:
- create a new sales order
- inventory
- retrieve partners for a sales order
- procurement
- order-to-cash
- create sales order
- retrieve a list of sales orders
- erp
- list sales order texts
- list sales order pricing
- logistics
- business applications
- delete sales order
- retrieve header pricing elements
- sap
- s/4hana
- finance
- create a sales order
- list sales orders
- plant maintenance
- human resources
- retrieve items for a sales order
- sales order management
- retrieve a single sales order by key
- list sales order partners
- sales
- create a new sales order item
- retrieve text records for a sales order
- enterprise resource planning
- delete a sales order
- list sales order items
- cloud
- get sales order
- create sales order item
- update sales order
- update a sales order header
- manufacturing
slug: order-to-cash
tags:
- SAP
- S/4HANA
- Sales
- Order-to-Cash
tools:
- description: Retrieve a list of sales orders
  hints:
    openWorld: true
    readOnly: true
  name: list-sales-orders
- description: Retrieve a single sales order by key
  hints:
    readOnly: true
  name: get-sales-order
- description: Create a new sales order
  hints: {}
  name: create-sales-order
- description: Update a sales order header
  hints: {}
  name: update-sales-order
- description: Delete a sales order
  hints:
    destructive: true
  name: delete-sales-order
- description: Retrieve items for a sales order
  hints:
    readOnly: true
  name: list-sales-order-items
- description: Create a new sales order item
  hints: {}
  name: create-sales-order-item
- description: Retrieve partners for a sales order
  hints:
    readOnly: true
  name: list-sales-order-partners
- description: Retrieve header pricing elements
  hints:
    readOnly: true
  name: list-sales-order-pricing
- description: Retrieve text records for a sales order
  hints:
    readOnly: true
  name: list-sales-order-texts
---
