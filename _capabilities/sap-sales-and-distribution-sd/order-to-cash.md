---
categories: []
consumed_apis: []
description: Unified capability for end-to-end order-to-cash operations in SAP S/4HANA Sales and Distribution. Combines Sales Order, Outbound Delivery, Billing Document, and Pricing APIs into a single workflow for sales representatives, order management teams, and finance operations. Covers quote-to-order, pick-pack-ship, and invoice generation workflows.
layout: capability
name: SAP SD Order-to-Cash
operations:
- description: List all sales orders
  method: GET
  name: list-sales-orders
  path: /v1/sales-orders
- description: Create a new sales order
  method: POST
  name: create-sales-order
  path: /v1/sales-orders
- description: Get a specific sales order
  method: GET
  name: get-sales-order
  path: /v1/sales-orders/{id}
- description: Update a sales order
  method: PATCH
  name: update-sales-order
  path: /v1/sales-orders/{id}
- description: List outbound deliveries
  method: GET
  name: list-outbound-deliveries
  path: /v1/outbound-deliveries
- description: Create a new outbound delivery
  method: POST
  name: create-outbound-delivery
  path: /v1/outbound-deliveries
- description: Post goods issue for an outbound delivery
  method: POST
  name: post-goods-issue
  path: /v1/outbound-deliveries/{id}/goods-issue
- description: List billing documents
  method: GET
  name: list-billing-documents
  path: /v1/billing-documents
- description: Get a specific billing document
  method: GET
  name: get-billing-document
  path: /v1/billing-documents/{id}
- description: List pricing condition records
  method: GET
  name: list-pricing-conditions
  path: /v1/pricing-conditions
- description: Create a new pricing condition record
  method: POST
  name: create-pricing-condition
  path: /v1/pricing-conditions
personas: []
provider_name: SAP Sales and Distribution (SD)
provider_slug: sap-sales-and-distribution-sd
search_terms:
- cancel a billing document
- get a specific billing document
- distribution
- sales
- list all sales orders
- list sales orders from sap s/4hana sd
- post goods issue
- billing document management
- pricing condition management
- sales and distribution
- outbound delivery management
- post goods issue for delivery
- get a specific sales order by number
- post goods issue to confirm shipment of outbound delivery
- create pricing condition
- create outbound delivery
- single sales order operations
- list billing documents and invoices from sap s/4hana
- list pricing conditions
- erp
- cancel billing document
- get pricing condition
- s/4hana
- sales order management
- get sales order
- update a sales order
- list outbound deliveries from sap s/4hana
- list outbound deliveries
- update sales order
- order-to-cash
- single billing document operations
- get a specific sales order
- sap
- list pricing condition records
- get a specific billing document or invoice
- create sales order
- list billing documents
- create a new sales order in sap s/4hana
- get billing document
- odata
- create a new pricing condition record
- get a specific pricing condition record
- list sales orders
- create a new outbound delivery
- post goods issue for an outbound delivery
- create a new sales order
slug: order-to-cash
source_filename: order-to-cash.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP SD Order-to-Cash\n  description: Unified capability for end-to-end order-to-cash operations in SAP S/4HANA Sales and Distribution. Combines\n    Sales Order, Outbound Delivery, Billing Document, and Pricing APIs into a single workflow for sales representatives, order\n    management teams, and finance operations. Covers quote-to-order, pick-pack-ship, and invoice generation workflows.\n  tags:\n  - SAP\n  - Sales and Distribution\n  - Order-to-Cash\n  - OData\n  - S/4HANA\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_SD_API_KEY: SAP_SD_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sales-order\n    baseUri: https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_SALES_ORDER_SRV\n    description: SAP S/4HANA Sales Order OData service\n    authentication:\n      type: apikey\n      key: APIKey\n      value: '{{SAP_SD_API_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: sales-orders\n      path: /A_SalesOrder\n      description: Sales order header collection\n      operations:\n      - name: list-sales-orders\n        method: GET\n        description: Retrieve a list of sales orders\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $expand\n          in: query\n          type: string\n          required: false\n          description: Navigation properties to expand\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order\n\
  \        method: POST\n        description: Create a new sales order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            SalesOrderType: '{{tools.SalesOrderType}}'\n            SalesOrganization: '{{tools.SalesOrganization}}'\n            DistributionChannel: '{{tools.DistributionChannel}}'\n            OrganizationDivision: '{{tools.OrganizationDivision}}'\n    - name: sales-order-by-id\n      path: /A_SalesOrder('{SalesOrder}')\n      description: Single sales order by ID\n      operations:\n      - name: get-sales-order\n        method: GET\n        description: Retrieve a single sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: update-sales-order\n        method: PATCH\n        description: Update a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-sales-order\n        method: DELETE\n        description: Delete a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-order-items\n      path: /A_SalesOrder('{SalesOrder}')/to_Item\n      description: Sales order items\n      operations:\n      - name: list-sales-order-items\n\
  \        method: GET\n        description: Retrieve items for a sales order\n        inputParameters:\n        - name: SalesOrder\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: outbound-delivery\n    baseUri: https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_OUTBOUND_DELIVERY_SRV\n    description: SAP S/4HANA Outbound Delivery OData service\n    authentication:\n      type: apikey\n      key: APIKey\n      value: '{{SAP_SD_API_KEY}}'\n      placement: header\n    resources:\n    - name: deliveries\n      path: /A_OutbDeliveryHeader\n      description: Outbound delivery collection\n      operations:\n      - name: list-outbound-deliveries\n        method: GET\n        description: Retrieve a list of outbound deliveries\n        inputParameters:\n       \
  \ - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-outbound-delivery\n        method: POST\n        description: Create a new outbound delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ShipToParty: '{{tools.ShipToParty}}'\n            ShippingPoint: '{{tools.ShippingPoint}}'\n    - name: delivery-by-id\n      path: /A_OutbDeliveryHeader(DeliveryDocument='{DeliveryDocument}')\n      description: Single outbound delivery\n      operations:\n      - name:\
  \ get-outbound-delivery\n        method: GET\n        description: Retrieve a single outbound delivery\n        inputParameters:\n        - name: DeliveryDocument\n          in: path\n          type: string\n          required: true\n          description: Delivery document number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: post-goods-issue\n      path: /PostGoodsIssue\n      description: Post goods issue for delivery\n      operations:\n      - name: post-goods-issue\n        method: POST\n        description: Post goods issue for an outbound delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            DeliveryDocument: '{{tools.DeliveryDocument}}'\n  - type: http\n    namespace: billing-document\n    baseUri: https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_BILLING_DOCUMENT_SRV\n\
  \    description: SAP S/4HANA Billing Document OData service\n    authentication:\n      type: apikey\n      key: APIKey\n      value: '{{SAP_SD_API_KEY}}'\n      placement: header\n    resources:\n    - name: billing-documents\n      path: /A_BillingDocument\n      description: Billing document collection\n      operations:\n      - name: list-billing-documents\n        method: GET\n        description: Retrieve a list of billing documents\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-document-by-id\n      path: /A_BillingDocument('{BillingDocument}')\n      description:\
  \ Single billing document\n      operations:\n      - name: get-billing-document\n        method: GET\n        description: Retrieve a single billing document\n        inputParameters:\n        - name: BillingDocument\n          in: path\n          type: string\n          required: true\n          description: Billing document number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cancel-billing-document\n      path: /A_BillingDocument('{BillingDocument}')/Cancel\n      description: Cancel a billing document\n      operations:\n      - name: cancel-billing-document\n        method: POST\n        description: Cancel a billing document\n        inputParameters:\n        - name: BillingDocument\n          in: path\n          type: string\n          required: true\n          description: Billing document number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n  - type: http\n    namespace: pricing\n    baseUri: https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_SLSPRCGCONDITIONRECORD_SRV\n    description: SAP S/4HANA Pricing Condition Record OData service\n    authentication:\n      type: apikey\n      key: APIKey\n      value: '{{SAP_SD_API_KEY}}'\n      placement: header\n    resources:\n    - name: pricing-conditions\n      path: /A_SlsPricingConditionRecord\n      description: Pricing condition record collection\n      operations:\n      - name: list-pricing-condition-records\n        method: GET\n        description: Retrieve a list of pricing condition records\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pricing-condition-record\n        method: POST\n        description: Create a pricing condition record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ConditionType: '{{tools.ConditionType}}'\n            ConditionRateValue: '{{tools.ConditionRateValue}}'\n            ConditionCurrency: '{{tools.ConditionCurrency}}'\n    - name: pricing-condition-by-id\n      path: /A_SlsPricingConditionRecord('{ConditionRecord}')\n      description: Single pricing condition record\n      operations:\n      - name: get-pricing-condition-record\n        method: GET\n        description: Retrieve a single pricing condition record\n        inputParameters:\n        - name: ConditionRecord\n          in: path\n      \
  \    type: string\n          required: true\n          description: Condition record number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-pricing-condition-record\n        method: PATCH\n        description: Update a pricing condition record\n        inputParameters:\n        - name: ConditionRecord\n          in: path\n          type: string\n          required: true\n          description: Condition record number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-pricing-condition-record\n        method: DELETE\n        description: Delete a pricing condition record\n        inputParameters:\n        - name: ConditionRecord\n          in: path\n          type: string\n          required: true\n          description: Condition record number\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: order-to-cash-api\n    description: Unified REST API for SAP SD order-to-cash workflow management.\n    resources:\n    - path: /v1/sales-orders\n      name: sales-orders\n      description: Sales order management\n      operations:\n      - method: GET\n        name: list-sales-orders\n        description: List all sales orders\n        call: sales-order.list-sales-orders\n        with:\n          $top: rest.$top\n          $filter: rest.$filter\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sales-order\n        description: Create a new sales order\n        call: sales-order.create-sales-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sales-orders/{id}\n      name: sales-order-by-id\n      description: Single sales order operations\n     \
  \ operations:\n      - method: GET\n        name: get-sales-order\n        description: Get a specific sales order\n        call: sales-order.get-sales-order\n        with:\n          SalesOrder: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-sales-order\n        description: Update a sales order\n        call: sales-order.update-sales-order\n        with:\n          SalesOrder: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/outbound-deliveries\n      name: outbound-deliveries\n      description: Outbound delivery management\n      operations:\n      - method: GET\n        name: list-outbound-deliveries\n        description: List outbound deliveries\n        call: outbound-delivery.list-outbound-deliveries\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-outbound-delivery\n        description:\
  \ Create a new outbound delivery\n        call: outbound-delivery.create-outbound-delivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/outbound-deliveries/{id}/goods-issue\n      name: goods-issue\n      description: Post goods issue for delivery\n      operations:\n      - method: POST\n        name: post-goods-issue\n        description: Post goods issue for an outbound delivery\n        call: outbound-delivery.post-goods-issue\n        with:\n          DeliveryDocument: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-documents\n      name: billing-documents\n      description: Billing document management\n      operations:\n      - method: GET\n        name: list-billing-documents\n        description: List billing documents\n        call: billing-document.list-billing-documents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-documents/{id}\n\
  \      name: billing-document-by-id\n      description: Single billing document operations\n      operations:\n      - method: GET\n        name: get-billing-document\n        description: Get a specific billing document\n        call: billing-document.get-billing-document\n        with:\n          BillingDocument: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing-conditions\n      name: pricing-conditions\n      description: Pricing condition management\n      operations:\n      - method: GET\n        name: list-pricing-conditions\n        description: List pricing condition records\n        call: pricing.list-pricing-condition-records\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-pricing-condition\n        description: Create a new pricing condition record\n        call: pricing.create-pricing-condition-record\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: order-to-cash-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP SD order-to-cash workflow management.\n    tools:\n    - name: list-sales-orders\n      description: List sales orders from SAP S/4HANA SD\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sales-order.list-sales-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-order\n      description: Get a specific sales order by number\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sales-order.get-sales-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sales-order\n      description: Create a new sales order in SAP S/4HANA\n      hints:\n        readOnly: false\n        destructive: false\n      call: sales-order.create-sales-order\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: list-outbound-deliveries\n      description: List outbound deliveries from SAP S/4HANA\n      hints:\n        readOnly: true\n        openWorld: true\n      call: outbound-delivery.list-outbound-deliveries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-outbound-delivery\n      description: Create a new outbound delivery\n      hints:\n        readOnly: false\n        destructive: false\n      call: outbound-delivery.create-outbound-delivery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-goods-issue\n      description: Post goods issue to confirm shipment of outbound delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: outbound-delivery.post-goods-issue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-billing-documents\n      description: List billing documents and invoices from SAP S/4HANA\n    \
  \  hints:\n        readOnly: true\n        openWorld: true\n      call: billing-document.list-billing-documents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-billing-document\n      description: Get a specific billing document or invoice\n      hints:\n        readOnly: true\n        openWorld: false\n      call: billing-document.get-billing-document\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-billing-document\n      description: Cancel a billing document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: billing-document.cancel-billing-document\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pricing-conditions\n      description: List pricing condition records\n      hints:\n        readOnly: true\n        openWorld: true\n      call: pricing.list-pricing-condition-records\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-pricing-condition\n      description: Get a specific pricing condition record\n      hints:\n        readOnly: true\n        openWorld: false\n      call: pricing.get-pricing-condition-record\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pricing-condition\n      description: Create a new pricing condition record\n      hints:\n        readOnly: false\n        destructive: false\n      call: pricing.create-pricing-condition-record\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-sales-and-distribution-sd/refs/heads/main/capabilities/order-to-cash.yaml
tags:
- SAP
- Sales and Distribution
- Order-to-Cash
- OData
- S/4HANA
tools:
- description: List sales orders from SAP S/4HANA SD
  hints:
    openWorld: true
    readOnly: true
  name: list-sales-orders
- description: Get a specific sales order by number
  hints:
    openWorld: false
    readOnly: true
  name: get-sales-order
- description: Create a new sales order in SAP S/4HANA
  hints:
    destructive: false
    readOnly: false
  name: create-sales-order
- description: List outbound deliveries from SAP S/4HANA
  hints:
    openWorld: true
    readOnly: true
  name: list-outbound-deliveries
- description: Create a new outbound delivery
  hints:
    destructive: false
    readOnly: false
  name: create-outbound-delivery
- description: Post goods issue to confirm shipment of outbound delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-goods-issue
- description: List billing documents and invoices from SAP S/4HANA
  hints:
    openWorld: true
    readOnly: true
  name: list-billing-documents
- description: Get a specific billing document or invoice
  hints:
    openWorld: false
    readOnly: true
  name: get-billing-document
- description: Cancel a billing document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-billing-document
- description: List pricing condition records
  hints:
    openWorld: true
    readOnly: true
  name: list-pricing-conditions
- description: Get a specific pricing condition record
  hints:
    openWorld: false
    readOnly: true
  name: get-pricing-condition
- description: Create a new pricing condition record
  hints:
    destructive: false
    readOnly: false
  name: create-pricing-condition
---
