---
categories: []
consumed_apis: []
description: Unified capability for ScanSource technology distribution partners. Combines product catalog, pricing, availability, order management, tracking, and invoicing into a single partner commerce workflow. Used by partner ERP systems, sales tools, and customer self-service portals to automate the full purchase-to-payment cycle.
layout: capability
name: ScanSource Partner Commerce
operations:
- description: Search for products in the ScanSource catalog
  method: GET
  name: search-products
  path: /v1/products
- description: Get detailed product information
  method: GET
  name: get-product-detail
  path: /v1/products/{itemNumber}
- description: Get real-time pricing for products
  method: POST
  name: get-product-pricing
  path: /v1/pricing
- description: Check real-time inventory availability
  method: POST
  name: get-product-availability
  path: /v1/availability
- description: Create a new sales order
  method: POST
  name: create-sales-order
  path: /v1/orders
- description: Get sales order summary
  method: GET
  name: get-sales-order-summary
  path: /v1/orders
- description: Get comprehensive order details
  method: GET
  name: get-sales-order-detail
  path: /v1/orders/{salesOrderNumber}
- description: Cancel a pending order
  method: DELETE
  name: cancel-sales-order
  path: /v1/orders/{salesOrderNumber}
- description: Get carrier tracking for an order
  method: GET
  name: get-order-tracking
  path: /v1/tracking
- description: Generate shipping quote before ordering
  method: POST
  name: get-shipping-quote
  path: /v1/shipping-quotes
- description: Get invoice summary for a customer
  method: GET
  name: get-invoice-summary
  path: /v1/invoices
- description: Get comprehensive invoice details
  method: GET
  name: get-invoice-detail
  path: /v1/invoices/{invoiceNumber}
- description: Download invoice as PDF
  method: GET
  name: get-invoice-pdf
  path: /v1/invoices/{invoiceNumber}/pdf
personas: []
provider_name: ScanSource
provider_slug: scansource
search_terms:
- product detail
- check real-time inventory availability for up to 40 products
- real-time product availability
- check real-time inventory availability
- get detailed specifications and information for a specific product
- generate shipping quote options and costs before placing an order
- get comprehensive invoice details including line items and serial numbers
- create sales order
- point of sale
- invoice pdf download
- generate shipping quote before ordering
- search for products in the scansource catalog by text, manufacturer, or category
- invoice summary and management
- scansource
- search for products in the scansource catalog
- create a new sales order
- sales order detail and management
- order management
- get comprehensive order details
- cancel a pending order
- get real-time pricing for up to 40 products for a customer
- inventory
- get sales order summary
- shipping quote generation
- get product availability
- barcode
- real-time product pricing
- get product pricing
- create a new sales order with line items and ship-to address
- order tracking
- get product detail
- e-commerce
- get invoice pdf
- get invoice detail
- get a summary of sales orders for a customer with optional date range filtering
- aidc
- get order tracking
- distribution
- partner integration
- download invoice as pdf
- get carrier tracking for an order
- product search and catalog
- get a summary of invoices for a customer with optional date range filtering
- get invoice summary
- get invoice summary for a customer
- get comprehensive details for a specific sales order including all line items and pricing
- get comprehensive invoice details
- get real-time pricing for products
- cancel a pending sales order that has not yet shipped
- get carrier tracking and delivery status for an order
- cancel sales order
- get detailed product information
- get sales order detail
- sales order creation and summary
- invoice detail
- search products
- get shipping quote
slug: partner-commerce
source_filename: partner-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ScanSource Partner Commerce\n  description: Unified capability for ScanSource technology distribution partners. Combines product catalog, pricing, availability,\n    order management, tracking, and invoicing into a single partner commerce workflow. Used by partner ERP systems, sales\n    tools, and customer self-service portals to automate the full purchase-to-payment cycle.\n  tags:\n  - ScanSource\n  - Distribution\n  - E-Commerce\n  - Order Management\n  - Partner Integration\n  - Barcode\n  - Point Of Sale\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCANSOURCE_API_KEY: SCANSOURCE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scansource-product\n    baseUri: https://services.scansource.com/api\n    description: ScanSource Product API for real-time inventory, pricing, and product data.\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n  \
  \    value: '{{SCANSOURCE_API_KEY}}'\n      placement: header\n    resources:\n    - name: products\n      path: /product\n      description: Product catalog search and detail operations\n      operations:\n      - name: search-products\n        method: GET\n        description: Search for products in the ScanSource catalog\n        inputParameters:\n        - name: customerNumber\n          in: query\n          type: string\n          required: true\n          description: Customer account number\n        - name: searchText\n          in: query\n          type: string\n          required: false\n          description: Free-text search string\n        - name: manufacturer\n          in: query\n          type: string\n          required: false\n          description: Filter by manufacturer\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n\
  \          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product-detail\n        method: GET\n        description: Retrieve detailed product information\n        inputParameters:\n        - name: customerNumber\n          in: query\n          type: string\n          required: true\n          description: Customer account number\n        - name: itemNumber\n          in: query\n          type: string\n          required: true\n          description: Item number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricing\n      path: /product/pricing\n      description: Real-time product pricing\n      operations:\n      - name: get-product-pricing\n        method: POST\n        description: Get real-time pricing for up to 40 products\n        inputParameters:\n\
  \        - name: customerNumber\n          in: query\n          type: string\n          required: true\n          description: Customer account number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n    - name: availability\n      path: /product/availability\n      description: Real-time inventory availability\n      operations:\n      - name: get-product-availability\n        method: POST\n        description: Check real-time availability for up to 40 products\n        inputParameters:\n        - name: customerNumber\n          in: query\n          type: string\n          required: false\n          description: Customer account number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n \
  \           items: '{{tools.items}}'\n  - type: http\n    namespace: scansource-sales-order\n    baseUri: https://services.scansource.com/api\n    description: ScanSource Sales Order API for order lifecycle management.\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{SCANSOURCE_API_KEY}}'\n      placement: header\n    resources:\n    - name: orders\n      path: /salesorder\n      description: Sales order creation and management\n      operations:\n      - name: create-sales-order\n        method: POST\n        description: Create a synchronous sales order\n        inputParameters:\n        - name: customerNumber\n          in: query\n          type: string\n          required: true\n          description: Customer account number\n        - name: requestor\n          in: query\n          type: string\n          required: false\n          description: Requestor identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            poNumber: '{{tools.poNumber}}'\n            lineItems: '{{tools.lineItems}}'\n            shipToAddress: '{{tools.shipToAddress}}'\n      - name: create-sales-order-async\n        method: POST\n        description: Create an asynchronous sales order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            poNumber: '{{tools.poNumber}}'\n            lineItems: '{{tools.lineItems}}'\n      - name: get-sales-order-summary\n        method: GET\n        description: Get paginated order summary for a customer\n        inputParameters:\n        - name: customerNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number\n        - name: fromDate\n          in: query\n        \
  \  type: string\n          required: false\n          description: Start date filter\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sales-order-detail\n        method: GET\n        description: Get comprehensive order details\n        inputParameters:\n        - name: customerNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number\n        - name: salesOrderNumber\n          in: path\n          type: string\n          required: true\n          description: Sales order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: cancel-sales-order\n        method: DELETE\n        description: Cancel a pending sales order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            salesOrderNumber: '{{tools.salesOrderNumber}}'\n            customerNumber: '{{tools.customerNumber}}'\n    - name: tracking\n      path: /salesorder/tracking\n      description: Order tracking and delivery status\n      operations:\n      - name: get-order-tracking\n        method: GET\n        description: Get carrier tracking information for an order\n        inputParameters:\n        - name: orderNumber\n          in: query\n          type: string\n          required: false\n          description: Order number\n        - name: poNumber\n          in: query\n          type: string\n          required: false\n          description: Purchase order\
  \ number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-serial-numbers\n        method: GET\n        description: Get serial number tracking for order items\n        inputParameters:\n        - name: orderNumber\n          in: query\n          type: string\n          required: false\n          description: Order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipping\n      path: /salesorder/shipquote\n      description: Shipping quotes\n      operations:\n      - name: get-shipping-quote\n        method: POST\n        description: Generate a shipping quote before order submission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerNumber: '{{tools.customerNumber}}'\n\
  \            shipToAddress: '{{tools.shipToAddress}}'\n            items: '{{tools.items}}'\n  - type: http\n    namespace: scansource-invoice\n    baseUri: https://services.scansource.com/api\n    description: ScanSource Invoice API for billing and financial record access.\n    authentication:\n      type: apikey\n      key: Ocp-Apim-Subscription-Key\n      value: '{{SCANSOURCE_API_KEY}}'\n      placement: header\n    resources:\n    - name: invoices\n      path: /invoice\n      description: Invoice retrieval and management\n      operations:\n      - name: get-invoice-summary\n        method: GET\n        description: Get paginated invoice summary for a customer\n        inputParameters:\n        - name: customerNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        -\
  \ name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-invoices\n        method: GET\n        description: Get detailed invoice list for a customer\n        inputParameters:\n        - name: customerNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-invoice-detail\n        method: GET\n        description: Get comprehensive details for a specific invoice\n        inputParameters:\n        - name: customerNumber\n          in:\
  \ path\n          type: string\n          required: true\n          description: Customer account number\n        - name: invoiceNumber\n          in: path\n          type: string\n          required: true\n          description: Invoice number\n        - name: excludeSerialTracking\n          in: query\n          type: boolean\n          required: false\n          description: Exclude serial tracking data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-invoice-pdf\n        method: GET\n        description: Download a PDF copy of an invoice\n        inputParameters:\n        - name: customerNumber\n          in: path\n          type: string\n          required: true\n          description: Customer account number\n        - name: invoiceNumber\n          in: path\n          type: string\n          required: true\n          description: Invoice number\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: scansource-partner-commerce-api\n    description: Unified REST API for ScanSource partner commerce workflows.\n    resources:\n    - path: /v1/products\n      name: products\n      description: Product search and catalog\n      operations:\n      - method: GET\n        name: search-products\n        description: Search for products in the ScanSource catalog\n        call: scansource-product.search-products\n        with:\n          customerNumber: rest.customerNumber\n          searchText: rest.searchText\n          manufacturer: rest.manufacturer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{itemNumber}\n      name: product-detail\n      description: Product detail\n      operations:\n      - method: GET\n        name: get-product-detail\n        description: Get detailed product information\n\
  \        call: scansource-product.get-product-detail\n        with:\n          customerNumber: rest.customerNumber\n          itemNumber: rest.itemNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing\n      name: pricing\n      description: Real-time product pricing\n      operations:\n      - method: POST\n        name: get-product-pricing\n        description: Get real-time pricing for products\n        call: scansource-product.get-product-pricing\n        with:\n          items: rest.items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/availability\n      name: availability\n      description: Real-time product availability\n      operations:\n      - method: POST\n        name: get-product-availability\n        description: Check real-time inventory availability\n        call: scansource-product.get-product-availability\n        with:\n          items: rest.items\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Sales order creation and summary\n      operations:\n      - method: POST\n        name: create-sales-order\n        description: Create a new sales order\n        call: scansource-sales-order.create-sales-order\n        with:\n          customerNumber: rest.customerNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-sales-order-summary\n        description: Get sales order summary\n        call: scansource-sales-order.get-sales-order-summary\n        with:\n          customerNumber: rest.customerNumber\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{salesOrderNumber}\n      name: order-detail\n      description: Sales order detail and management\n      operations:\n      - method: GET\n      \
  \  name: get-sales-order-detail\n        description: Get comprehensive order details\n        call: scansource-sales-order.get-sales-order-detail\n        with:\n          customerNumber: rest.customerNumber\n          salesOrderNumber: rest.salesOrderNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-sales-order\n        description: Cancel a pending order\n        call: scansource-sales-order.cancel-sales-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tracking\n      name: tracking\n      description: Order tracking\n      operations:\n      - method: GET\n        name: get-order-tracking\n        description: Get carrier tracking for an order\n        call: scansource-sales-order.get-order-tracking\n        with:\n          orderNumber: rest.orderNumber\n          poNumber: rest.poNumber\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/shipping-quotes\n      name: shipping-quotes\n      description: Shipping quote generation\n      operations:\n      - method: POST\n        name: get-shipping-quote\n        description: Generate shipping quote before ordering\n        call: scansource-sales-order.get-shipping-quote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice summary and management\n      operations:\n      - method: GET\n        name: get-invoice-summary\n        description: Get invoice summary for a customer\n        call: scansource-invoice.get-invoice-summary\n        with:\n          customerNumber: rest.customerNumber\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceNumber}\n      name: invoice-detail\n      description: Invoice detail\n      operations:\n      -\
  \ method: GET\n        name: get-invoice-detail\n        description: Get comprehensive invoice details\n        call: scansource-invoice.get-invoice-detail\n        with:\n          customerNumber: rest.customerNumber\n          invoiceNumber: rest.invoiceNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceNumber}/pdf\n      name: invoice-pdf\n      description: Invoice PDF download\n      operations:\n      - method: GET\n        name: get-invoice-pdf\n        description: Download invoice as PDF\n        call: scansource-invoice.get-invoice-pdf\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: scansource-partner-commerce-mcp\n    transport: http\n    description: MCP server for AI-assisted ScanSource partner commerce workflows.\n    tools:\n    - name: search-products\n      description: Search for products in the ScanSource catalog by text, manufacturer,\
  \ or category\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-product.search-products\n      with:\n        customerNumber: tools.customerNumber\n        searchText: tools.searchText\n        manufacturer: tools.manufacturer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-detail\n      description: Get detailed specifications and information for a specific product\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-product.get-product-detail\n      with:\n        customerNumber: tools.customerNumber\n        itemNumber: tools.itemNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-pricing\n      description: Get real-time pricing for up to 40 products for a customer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-product.get-product-pricing\n      with:\n        items: tools.items\n\
  \        customerNumber: tools.customerNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-availability\n      description: Check real-time inventory availability for up to 40 products\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-product.get-product-availability\n      with:\n        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sales-order\n      description: Create a new sales order with line items and ship-to address\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scansource-sales-order.create-sales-order\n      with:\n        customerNumber: tools.customerNumber\n        poNumber: tools.poNumber\n        lineItems: tools.lineItems\n        shipToAddress: tools.shipToAddress\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-order-summary\n\
  \      description: Get a summary of sales orders for a customer with optional date range filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-sales-order.get-sales-order-summary\n      with:\n        customerNumber: tools.customerNumber\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-order-detail\n      description: Get comprehensive details for a specific sales order including all line items and pricing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-sales-order.get-sales-order-detail\n      with:\n        customerNumber: tools.customerNumber\n        salesOrderNumber: tools.salesOrderNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-sales-order\n      description: Cancel a pending sales order that has not yet shipped\n      hints:\n        readOnly: false\n\
  \        destructive: true\n        idempotent: true\n      call: scansource-sales-order.cancel-sales-order\n      with:\n        salesOrderNumber: tools.salesOrderNumber\n        customerNumber: tools.customerNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order-tracking\n      description: Get carrier tracking and delivery status for an order\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-sales-order.get-order-tracking\n      with:\n        orderNumber: tools.orderNumber\n        poNumber: tools.poNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipping-quote\n      description: Generate shipping quote options and costs before placing an order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scansource-sales-order.get-shipping-quote\n      with:\n        customerNumber: tools.customerNumber\n        shipToAddress: tools.shipToAddress\n\
  \        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice-summary\n      description: Get a summary of invoices for a customer with optional date range filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-invoice.get-invoice-summary\n      with:\n        customerNumber: tools.customerNumber\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice-detail\n      description: Get comprehensive invoice details including line items and serial numbers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scansource-invoice.get-invoice-detail\n      with:\n        customerNumber: tools.customerNumber\n        invoiceNumber: tools.invoiceNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scansource/refs/heads/main/capabilities/partner-commerce.yaml
tags:
- ScanSource
- Distribution
- E-Commerce
- Order Management
- Partner Integration
- Barcode
- Point Of Sale
tools:
- description: Search for products in the ScanSource catalog by text, manufacturer, or category
  hints:
    openWorld: true
    readOnly: true
  name: search-products
- description: Get detailed specifications and information for a specific product
  hints:
    openWorld: true
    readOnly: true
  name: get-product-detail
- description: Get real-time pricing for up to 40 products for a customer
  hints:
    openWorld: true
    readOnly: true
  name: get-product-pricing
- description: Check real-time inventory availability for up to 40 products
  hints:
    openWorld: true
    readOnly: true
  name: get-product-availability
- description: Create a new sales order with line items and ship-to address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-sales-order
- description: Get a summary of sales orders for a customer with optional date range filtering
  hints:
    openWorld: true
    readOnly: true
  name: get-sales-order-summary
- description: Get comprehensive details for a specific sales order including all line items and pricing
  hints:
    openWorld: true
    readOnly: true
  name: get-sales-order-detail
- description: Cancel a pending sales order that has not yet shipped
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-sales-order
- description: Get carrier tracking and delivery status for an order
  hints:
    openWorld: true
    readOnly: true
  name: get-order-tracking
- description: Generate shipping quote options and costs before placing an order
  hints:
    openWorld: false
    readOnly: true
  name: get-shipping-quote
- description: Get a summary of invoices for a customer with optional date range filtering
  hints:
    openWorld: true
    readOnly: true
  name: get-invoice-summary
- description: Get comprehensive invoice details including line items and serial numbers
  hints:
    openWorld: true
    readOnly: true
  name: get-invoice-detail
---
