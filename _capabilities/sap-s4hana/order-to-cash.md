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
- retrieve a single sales order by key
- plant maintenance
- retrieve a list of sales orders
- list sales order texts
- enterprise resource planning
- create a new sales order
- create a sales order
- create sales order item
- list sales order partners
- cloud
- finance
- business applications
- order-to-cash
- list sales orders
- sales
- retrieve partners for a sales order
- retrieve text records for a sales order
- s/4hana
- delete sales order
- sap
- get sales order
- create a new sales order item
- update a sales order header
- list sales order items
- sales order management
- update sales order
- delete a sales order
- erp
- retrieve items for a sales order
- logistics
- list sales order pricing
- manufacturing
- human resources
- create sales order
- inventory
- retrieve header pricing elements
- procurement
slug: order-to-cash
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP S/4HANA Order-to-Cash\"\n  description: \"Unified order-to-cash capability combining sales order management with items, partners, pricing, schedule lines, and text records. Used by sales operations and order management teams.\"\n  tags:\n    - SAP\n    - S/4HANA\n    - Sales\n    - Order-to-Cash\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_USERNAME: SAP_USERNAME\n      SAP_PASSWORD: SAP_PASSWORD\n\ncapability:\n  consumes:\n    - import: sales-order\n      location: ./shared/sales-order.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: order-to-cash-api\n      description: \"Unified REST API for SAP S/4HANA order-to-cash operations.\"\n      resources:\n        - path: /v1/sales-orders\n          name: sales-orders\n          description: \"Sales order management\"\n          operations:\n            - method: GET\n              name: list-sales-orders\n\
  \              description: \"List sales orders\"\n              call: \"sales-order.list-sales-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-sales-order\n              description: \"Create a sales order\"\n              call: \"sales-order.create-sales-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: order-to-cash-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP S/4HANA order-to-cash operations.\"\n      tools:\n        - name: list-sales-orders\n          description: \"Retrieve a list of sales orders\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sales-order.list-sales-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: get-sales-order\n          description: \"Retrieve a single sales order by key\"\n          hints:\n            readOnly: true\n          call: \"sales-order.get-sales-order\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-sales-order\n          description: \"Create a new sales order\"\n          call: \"sales-order.create-sales-order\"\n          with:\n            SalesOrderType: \"tools.SalesOrderType\"\n            SalesOrganization: \"tools.SalesOrganization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-sales-order\n          description: \"Update a sales order header\"\n          call: \"sales-order.update-sales-order\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: delete-sales-order\n          description: \"Delete a sales order\"\n          hints:\n            destructive: true\n          call: \"sales-order.delete-sales-order\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sales-order-items\n          description: \"Retrieve items for a sales order\"\n          hints:\n            readOnly: true\n          call: \"sales-order.list-sales-order-items\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-sales-order-item\n          description: \"Create a new sales order item\"\n          call: \"sales-order.create-sales-order-item\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: list-sales-order-partners\n          description: \"Retrieve partners for a sales order\"\n          hints:\n            readOnly: true\n          call: \"sales-order.list-sales-order-partners\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sales-order-pricing\n          description: \"Retrieve header pricing elements\"\n          hints:\n            readOnly: true\n          call: \"sales-order.list-sales-order-pricing\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sales-order-texts\n          description: \"Retrieve text records for a sales order\"\n          hints:\n            readOnly: true\n          call: \"sales-order.list-sales-order-texts\"\n          with:\n            SalesOrder: \"tools.SalesOrder\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-s4hana/refs/heads/main/capabilities/order-to-cash.yaml
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
