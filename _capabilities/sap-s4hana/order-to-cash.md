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
- delete sales order
- delete a sales order
- sales order management
- list sales order texts
- retrieve partners for a sales order
- procurement
- finance
- human resources
- order-to-cash
- list sales order partners
- list sales order pricing
- business applications
- list sales orders
- plant maintenance
- cloud
- inventory
- create sales order item
- create a sales order
- enterprise resource planning
- logistics
- retrieve a single sales order by key
- manufacturing
- erp
- retrieve text records for a sales order
- retrieve header pricing elements
- sap
- create a new sales order
- create a new sales order item
- update sales order
- retrieve items for a sales order
- get sales order
- list sales order items
- sales
- create sales order
- s/4hana
- update a sales order header
- retrieve a list of sales orders
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
