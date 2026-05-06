---
categories: []
consumed_apis: []
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
- create a new sales order item
- sales
- list sales order items
- logistics
- manufacturing
- create a sales order
- finance
- enterprise resource planning
- retrieve a single sales order by key
- cloud
- retrieve items for a sales order
- list sales order texts
- erp
- update a sales order header
- inventory
- s/4hana
- sales order management
- get sales order
- list sales order partners
- delete sales order
- update sales order
- order-to-cash
- sap
- retrieve a list of sales orders
- business applications
- plant maintenance
- create sales order
- human resources
- list sales order pricing
- retrieve text records for a sales order
- retrieve partners for a sales order
- delete a sales order
- create sales order item
- list sales orders
- retrieve header pricing elements
- procurement
- create a new sales order
slug: order-to-cash
source_filename: order-to-cash.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP S/4HANA Order-to-Cash\n  description: Unified order-to-cash capability combining sales order management with items, partners, pricing, schedule lines,\n    and text records. Used by sales operations and order management teams.\n  tags:\n  - SAP\n  - S/4HANA\n  - Sales\n  - Order-to-Cash\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_USERNAME: SAP_USERNAME\n    SAP_PASSWORD: SAP_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: sales-order\n    baseUri: https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_SALES_ORDER_SRV\n    description: SAP S/4HANA Sales Order API for CRUD operations on sales documents.\n    authentication:\n      type: basic\n      username: '{{SAP_USERNAME}}'\n      password: '{{SAP_PASSWORD}}'\n    resources:\n    - name: sales-orders\n      path: /A_SalesOrder\n      description: Sales order header operations\n      operations:\n      -\
  \ name: list-sales-orders\n        method: GET\n        description: Retrieve a list of sales orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order\n        method: POST\n        description: Create a new sales order with optional deep insert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            SalesOrderType: '{{tools.SalesOrderType}}'\n            SalesOrganization: '{{tools.SalesOrganization}}'\n            DistributionChannel: '{{tools.DistributionChannel}}'\n            OrganizationDivision: '{{tools.OrganizationDivision}}'\n      - name: get-sales-order\n        method: GET\n        description: Retrieve a single sales order by key\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n\
  \          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-sales-order\n        method: PATCH\n        description: Update a sales order header\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-sales-order\n        method: DELETE\n        description: Delete a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: list-sales-order-items\n        method: GET\n        description: Retrieve items for a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order-item\n        method: POST\n        description: Create a new sales order item\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-sales-order-partners\n        method: GET\n        description: Retrieve partners for a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n\
  \          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-sales-order-pricing\n        method: GET\n        description: Retrieve header pricing elements\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-sales-order-texts\n        method: GET\n        description: Retrieve text records for a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: order-to-cash-api\n    description: Unified REST API for SAP S/4HANA order-to-cash operations.\n    resources:\n    - path: /v1/sales-orders\n      name: sales-orders\n      description: Sales order management\n      operations:\n      - method: GET\n        name: list-sales-orders\n        description: List sales orders\n        call: sales-order.list-sales-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sales-order\n        description: Create a sales order\n        call: sales-order.create-sales-order\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: order-to-cash-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP S/4HANA order-to-cash operations.\n    tools:\n    - name: list-sales-orders\n      description: Retrieve\
  \ a list of sales orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sales-order.list-sales-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-order\n      description: Retrieve a single sales order by key\n      hints:\n        readOnly: true\n      call: sales-order.get-sales-order\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sales-order\n      description: Create a new sales order\n      call: sales-order.create-sales-order\n      with:\n        SalesOrderType: tools.SalesOrderType\n        SalesOrganization: tools.SalesOrganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-sales-order\n      description: Update a sales order header\n      call: sales-order.update-sales-order\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: delete-sales-order\n      description: Delete a sales order\n      hints:\n        destructive: true\n      call: sales-order.delete-sales-order\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-order-items\n      description: Retrieve items for a sales order\n      hints:\n        readOnly: true\n      call: sales-order.list-sales-order-items\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sales-order-item\n      description: Create a new sales order item\n      call: sales-order.create-sales-order-item\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-order-partners\n      description: Retrieve partners for a sales order\n      hints:\n        readOnly: true\n      call: sales-order.list-sales-order-partners\n\
  \      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-order-pricing\n      description: Retrieve header pricing elements\n      hints:\n        readOnly: true\n      call: sales-order.list-sales-order-pricing\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-order-texts\n      description: Retrieve text records for a sales order\n      hints:\n        readOnly: true\n      call: sales-order.list-sales-order-texts\n      with:\n        SalesOrder: tools.SalesOrder\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
