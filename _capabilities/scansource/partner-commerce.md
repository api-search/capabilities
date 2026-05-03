---
categories: []
consumed_apis:
- scansource-product
- scansource-sales-order
- scansource-invoice
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
- get carrier tracking for an order
- invoice pdf download
- real-time product availability
- aidc
- get sales order summary
- invoice summary and management
- cancel a pending order
- get invoice summary
- get comprehensive details for a specific sales order including all line items and pricing
- get comprehensive order details
- get invoice summary for a customer
- search for products in the scansource catalog
- get sales order detail
- get a summary of sales orders for a customer with optional date range filtering
- download invoice as pdf
- get carrier tracking and delivery status for an order
- shipping quote generation
- get comprehensive invoice details including line items and serial numbers
- e-commerce
- product detail
- create a new sales order with line items and ship-to address
- get real-time pricing for products
- get detailed specifications and information for a specific product
- product search and catalog
- distribution
- barcode
- check real-time inventory availability
- sales order creation and summary
- get order tracking
- inventory
- create sales order
- get product pricing
- get real-time pricing for up to 40 products for a customer
- search for products in the scansource catalog by text, manufacturer, or category
- cancel a pending sales order that has not yet shipped
- check real-time inventory availability for up to 40 products
- invoice detail
- cancel sales order
- generate shipping quote options and costs before placing an order
- order management
- get a summary of invoices for a customer with optional date range filtering
- order tracking
- get invoice detail
- search products
- get product availability
- sales order detail and management
- create a new sales order
- scansource
- get invoice pdf
- point of sale
- get shipping quote
- generate shipping quote before ordering
- get comprehensive invoice details
- partner integration
- real-time product pricing
- get detailed product information
- get product detail
slug: partner-commerce
source_filename: partner-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ScanSource Partner Commerce\"\n  description: \"Unified capability for ScanSource technology distribution partners. Combines product catalog, pricing, availability, order management, tracking, and invoicing into a single partner commerce workflow. Used by partner ERP systems, sales tools, and customer self-service portals to automate the full purchase-to-payment cycle.\"\n  tags:\n  - ScanSource\n  - Distribution\n  - E-Commerce\n  - Order Management\n  - Partner Integration\n  - Barcode\n  - Point Of Sale\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n- namespace: env\n  keys:\n    SCANSOURCE_API_KEY: SCANSOURCE_API_KEY\n\ncapability:\n  consumes:\n  - import: scansource-product\n    location: ./shared/product.yaml\n  - import: scansource-sales-order\n    location: ./shared/sales-order.yaml\n  - import: scansource-invoice\n    location: ./shared/invoice.yaml\n\n  exposes:\n  - type: rest\n    port: 8080\n  \
  \  namespace: scansource-partner-commerce-api\n    description: \"Unified REST API for ScanSource partner commerce workflows.\"\n    resources:\n    - path: /v1/products\n      name: products\n      description: \"Product search and catalog\"\n      operations:\n      - method: GET\n        name: search-products\n        description: \"Search for products in the ScanSource catalog\"\n        call: \"scansource-product.search-products\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n          searchText: \"rest.searchText\"\n          manufacturer: \"rest.manufacturer\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/products/{itemNumber}\n      name: product-detail\n      description: \"Product detail\"\n      operations:\n      - method: GET\n        name: get-product-detail\n        description: \"Get detailed product information\"\n        call: \"scansource-product.get-product-detail\"\n        with:\n          customerNumber:\
  \ \"rest.customerNumber\"\n          itemNumber: \"rest.itemNumber\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/pricing\n      name: pricing\n      description: \"Real-time product pricing\"\n      operations:\n      - method: POST\n        name: get-product-pricing\n        description: \"Get real-time pricing for products\"\n        call: \"scansource-product.get-product-pricing\"\n        with:\n          items: \"rest.items\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/availability\n      name: availability\n      description: \"Real-time product availability\"\n      operations:\n      - method: POST\n        name: get-product-availability\n        description: \"Check real-time inventory availability\"\n        call: \"scansource-product.get-product-availability\"\n        with:\n          items: \"rest.items\"\n        outputParameters:\n        - type: object\n          mapping:\
  \ \"$.\"\n    - path: /v1/orders\n      name: orders\n      description: \"Sales order creation and summary\"\n      operations:\n      - method: POST\n        name: create-sales-order\n        description: \"Create a new sales order\"\n        call: \"scansource-sales-order.create-sales-order\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n      - method: GET\n        name: get-sales-order-summary\n        description: \"Get sales order summary\"\n        call: \"scansource-sales-order.get-sales-order-summary\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n          fromDate: \"rest.fromDate\"\n          toDate: \"rest.toDate\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/orders/{salesOrderNumber}\n      name: order-detail\n      description: \"Sales order detail and management\"\n      operations:\n      - method: GET\n\
  \        name: get-sales-order-detail\n        description: \"Get comprehensive order details\"\n        call: \"scansource-sales-order.get-sales-order-detail\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n          salesOrderNumber: \"rest.salesOrderNumber\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n      - method: DELETE\n        name: cancel-sales-order\n        description: \"Cancel a pending order\"\n        call: \"scansource-sales-order.cancel-sales-order\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/tracking\n      name: tracking\n      description: \"Order tracking\"\n      operations:\n      - method: GET\n        name: get-order-tracking\n        description: \"Get carrier tracking for an order\"\n        call: \"scansource-sales-order.get-order-tracking\"\n        with:\n          orderNumber: \"rest.orderNumber\"\n          poNumber: \"rest.poNumber\"\n        outputParameters:\n\
  \        - type: object\n          mapping: \"$.\"\n    - path: /v1/shipping-quotes\n      name: shipping-quotes\n      description: \"Shipping quote generation\"\n      operations:\n      - method: POST\n        name: get-shipping-quote\n        description: \"Generate shipping quote before ordering\"\n        call: \"scansource-sales-order.get-shipping-quote\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/invoices\n      name: invoices\n      description: \"Invoice summary and management\"\n      operations:\n      - method: GET\n        name: get-invoice-summary\n        description: \"Get invoice summary for a customer\"\n        call: \"scansource-invoice.get-invoice-summary\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n          fromDate: \"rest.fromDate\"\n          toDate: \"rest.toDate\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/invoices/{invoiceNumber}\n\
  \      name: invoice-detail\n      description: \"Invoice detail\"\n      operations:\n      - method: GET\n        name: get-invoice-detail\n        description: \"Get comprehensive invoice details\"\n        call: \"scansource-invoice.get-invoice-detail\"\n        with:\n          customerNumber: \"rest.customerNumber\"\n          invoiceNumber: \"rest.invoiceNumber\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n    - path: /v1/invoices/{invoiceNumber}/pdf\n      name: invoice-pdf\n      description: \"Invoice PDF download\"\n      operations:\n      - method: GET\n        name: get-invoice-pdf\n        description: \"Download invoice as PDF\"\n        call: \"scansource-invoice.get-invoice-pdf\"\n        outputParameters:\n        - type: object\n          mapping: \"$.\"\n\n  - type: mcp\n    port: 9090\n    namespace: scansource-partner-commerce-mcp\n    transport: http\n    description: \"MCP server for AI-assisted ScanSource partner commerce workflows.\"\
  \n    tools:\n    - name: search-products\n      description: \"Search for products in the ScanSource catalog by text, manufacturer, or category\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-product.search-products\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        searchText: \"tools.searchText\"\n        manufacturer: \"tools.manufacturer\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-product-detail\n      description: \"Get detailed specifications and information for a specific product\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-product.get-product-detail\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        itemNumber: \"tools.itemNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-product-pricing\n      description: \"Get real-time pricing for up to 40 products\
  \ for a customer\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-product.get-product-pricing\"\n      with:\n        items: \"tools.items\"\n        customerNumber: \"tools.customerNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-product-availability\n      description: \"Check real-time inventory availability for up to 40 products\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-product.get-product-availability\"\n      with:\n        items: \"tools.items\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: create-sales-order\n      description: \"Create a new sales order with line items and ship-to address\"\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: \"scansource-sales-order.create-sales-order\"\n      with:\n        customerNumber: \"tools.customerNumber\"\
  \n        poNumber: \"tools.poNumber\"\n        lineItems: \"tools.lineItems\"\n        shipToAddress: \"tools.shipToAddress\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-sales-order-summary\n      description: \"Get a summary of sales orders for a customer with optional date range filtering\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-sales-order.get-sales-order-summary\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        fromDate: \"tools.fromDate\"\n        toDate: \"tools.toDate\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-sales-order-detail\n      description: \"Get comprehensive details for a specific sales order including all line items and pricing\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-sales-order.get-sales-order-detail\"\n      with:\n        customerNumber: \"tools.customerNumber\"\
  \n        salesOrderNumber: \"tools.salesOrderNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: cancel-sales-order\n      description: \"Cancel a pending sales order that has not yet shipped\"\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: \"scansource-sales-order.cancel-sales-order\"\n      with:\n        salesOrderNumber: \"tools.salesOrderNumber\"\n        customerNumber: \"tools.customerNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-order-tracking\n      description: \"Get carrier tracking and delivery status for an order\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-sales-order.get-order-tracking\"\n      with:\n        orderNumber: \"tools.orderNumber\"\n        poNumber: \"tools.poNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-shipping-quote\n\
  \      description: \"Generate shipping quote options and costs before placing an order\"\n      hints:\n        readOnly: true\n        openWorld: false\n      call: \"scansource-sales-order.get-shipping-quote\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        shipToAddress: \"tools.shipToAddress\"\n        items: \"tools.items\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-invoice-summary\n      description: \"Get a summary of invoices for a customer with optional date range filtering\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-invoice.get-invoice-summary\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        fromDate: \"tools.fromDate\"\n        toDate: \"tools.toDate\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n    - name: get-invoice-detail\n      description: \"Get comprehensive invoice details including line items and\
  \ serial numbers\"\n      hints:\n        readOnly: true\n        openWorld: true\n      call: \"scansource-invoice.get-invoice-detail\"\n      with:\n        customerNumber: \"tools.customerNumber\"\n        invoiceNumber: \"tools.invoiceNumber\"\n      outputParameters:\n      - type: object\n        mapping: \"$.\"\n"
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
