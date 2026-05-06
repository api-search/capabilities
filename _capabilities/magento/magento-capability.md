---
categories: []
consumed_apis: []
description: 'The Adobe Commerce (Magento) REST API provides a comprehensive set of endpoints for interacting with all major aspects of an e-commerce store, including catalog management, orders, customers, inventory, shipping, and payments. It supports three authentication mechanisms: OAuth 1.0a for third-party integrations, token-based authentication for mobile apps and administrators, and guest access for select public endpoints. The API follows REST conventions and returns JSON responses, enabling developers to build integrations, automate store operations, and power headless commerce storefronts. All en'
layout: capability
name: Magento REST API
operations:
- description: Get admin authentication token
  method: POST
  name: createadmintoken
  path: /V1/integration/admin/token
- description: Get customer authentication token
  method: POST
  name: createcustomertoken
  path: /V1/integration/customer/token
- description: List products
  method: GET
  name: listproducts
  path: /V1/products
- description: Create a product
  method: POST
  name: createproduct
  path: /V1/products
- description: Get product by SKU
  method: GET
  name: getproduct
  path: /V1/products/{sku}
- description: Update a product
  method: PUT
  name: updateproduct
  path: /V1/products/{sku}
- description: Delete a product
  method: DELETE
  name: deleteproduct
  path: /V1/products/{sku}
- description: List categories
  method: GET
  name: listcategories
  path: /V1/categories
- description: Create a category
  method: POST
  name: createcategory
  path: /V1/categories
- description: Get category by ID
  method: GET
  name: getcategory
  path: /V1/categories/{categoryId}
- description: Update a category
  method: PUT
  name: updatecategory
  path: /V1/categories/{categoryId}
- description: Delete a category
  method: DELETE
  name: deletecategory
  path: /V1/categories/{categoryId}
- description: Create a customer
  method: POST
  name: createcustomer
  path: /V1/customers
- description: Search customers
  method: GET
  name: searchcustomers
  path: /V1/customers/search
- description: Get customer by ID
  method: GET
  name: getcustomer
  path: /V1/customers/{customerId}
- description: Update a customer
  method: PUT
  name: updatecustomer
  path: /V1/customers/{customerId}
- description: Delete a customer
  method: DELETE
  name: deletecustomer
  path: /V1/customers/{customerId}
- description: List orders
  method: GET
  name: listorders
  path: /V1/orders
- description: Create an order
  method: POST
  name: createorder
  path: /V1/orders
- description: Get order by ID
  method: GET
  name: getorder
  path: /V1/orders/{orderId}
- description: Cancel an order
  method: POST
  name: cancelorder
  path: /V1/orders/{orderId}/cancel
- description: Add a comment to an order
  method: POST
  name: addordercomment
  path: /V1/orders/{orderId}/comments
- description: List invoices
  method: GET
  name: listinvoices
  path: /V1/invoices
- description: Get invoice by ID
  method: GET
  name: getinvoice
  path: /V1/invoices/{invoiceId}
- description: Create an invoice for an order
  method: POST
  name: createinvoice
  path: /V1/order/{orderId}/invoice
- description: Create a shipment
  method: POST
  name: createshipment
  path: /V1/shipment
- description: Get shipment by ID
  method: GET
  name: getshipment
  path: /V1/shipment/{shipmentId}
- description: Create a cart for the authenticated customer
  method: POST
  name: createcustomercart
  path: /V1/carts/mine
- description: Add item to customer cart
  method: POST
  name: additemtocart
  path: /V1/carts/mine/items
- description: Create a guest cart
  method: POST
  name: createguestcart
  path: /V1/guest-carts
- description: List inventory sources
  method: GET
  name: listinventorysources
  path: /V1/inventory/sources
- description: Create an inventory source
  method: POST
  name: createinventorysource
  path: /V1/inventory/sources
- description: Get inventory source by code
  method: GET
  name: getinventorysource
  path: /V1/inventory/sources/{sourceCode}
- description: Update an inventory source
  method: PUT
  name: updateinventorysource
  path: /V1/inventory/sources/{sourceCode}
- description: List source item quantities
  method: GET
  name: listsourceitems
  path: /V1/inventory/source-items
- description: Update source item quantities
  method: POST
  name: updatesourceitems
  path: /V1/inventory/source-items
- description: List tax rates
  method: GET
  name: listtaxrates
  path: /V1/taxRates
- description: List store configurations
  method: GET
  name: liststoreconfigs
  path: /V1/store/storeConfigs
personas: []
provider_name: magento
provider_slug: magento
search_terms:
- create a product
- get product by sku
- add a comment to an order
- get category by id
- delete a category
- update a category
- list inventory sources
- deleteproduct
- create an order
- createproduct
- create an inventory source
- createinvoice
- get customer by id
- listorders
- get invoice by id
- getinventorysource
- createguestcart
- api
- list categories
- listinvoices
- cancelorder
- create a customer
- updatecustomer
- getshipment
- deletecustomer
- list invoices
- updatesourceitems
- delete a customer
- list tax rates
- create a guest cart
- getcategory
- deletecategory
- getcustomer
- listproducts
- createcustomertoken
- listsourceitems
- createcustomer
- list orders
- updateproduct
- getproduct
- liststoreconfigs
- updateinventorysource
- get order by id
- create an invoice for an order
- listtaxrates
- get shipment by id
- createcategory
- magento
- update a product
- createshipment
- searchcustomers
- get customer authentication token
- delete a product
- listinventorysources
- update a customer
- cancel an order
- create a shipment
- getinvoice
- get admin authentication token
- list store configurations
- updatecategory
- getorder
- createcustomercart
- search customers
- listcategories
- createorder
- update source item quantities
- addordercomment
- add item to customer cart
- create a category
- create a cart for the authenticated customer
- list products
- createinventorysource
- update an inventory source
- list source item quantities
- additemtocart
- get inventory source by code
- createadmintoken
slug: magento-capability
source_filename: magento-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Magento REST API\n  description: 'The Adobe Commerce (Magento) REST API provides a comprehensive set of endpoints for interacting with all major\n    aspects of an e-commerce store, including catalog management, orders, customers, inventory, shipping, and payments. It\n    supports three authentication mechanisms: OAuth 1.0a for third-party integrations, token-based authentication for mobile\n    apps and administrators, and guest access for select public endpoints. The API follows REST conventions and returns JSON\n    responses, enabling developers to build integrations, automate store operations, and power headless commerce storefronts.\n    All en'\n  tags:\n  - Magento\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: magento\n    baseUri: https://your-store.example.com/rest/V1\n    description: Magento REST API HTTP API.\n    authentication:\n      type: bearer\n\
  \      token: '{{MAGENTO_TOKEN}}'\n    resources:\n    - name: v1-integration-admin-token\n      path: /V1/integration/admin/token\n      operations:\n      - name: createadmintoken\n        method: POST\n        description: Get admin authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-integration-customer-token\n      path: /V1/integration/customer/token\n      operations:\n      - name: createcustomertoken\n        method: POST\n        description: Get customer authentication token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-products\n      path: /V1/products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List products\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: createproduct\n        method: POST\n        description: Create a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-products-sku\n      path: /V1/products/{sku}\n      operations:\n      - name: getproduct\n        method: GET\n        description: Get product by SKU\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproduct\n        method: PUT\n        description: Update a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproduct\n        method: DELETE\n        description: Delete a product\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-categories\n      path:\
  \ /V1/categories\n      operations:\n      - name: listcategories\n        method: GET\n        description: List categories\n        inputParameters:\n        - name: rootCategoryId\n          in: query\n          type: integer\n          description: Root category ID to start the tree from. Defaults to the default root category.\n        - name: depth\n          in: query\n          type: integer\n          description: Maximum depth of the category tree to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcategory\n        method: POST\n        description: Create a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-categories-categoryid\n      path: /V1/categories/{categoryId}\n      operations:\n      - name: getcategory\n        method: GET\n        description: Get category by\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecategory\n        method: PUT\n        description: Update a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecategory\n        method: DELETE\n        description: Delete a category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-customers\n      path: /V1/customers\n      operations:\n      - name: createcustomer\n        method: POST\n        description: Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-customers-search\n      path: /V1/customers/search\n      operations:\n      - name: searchcustomers\n        method: GET\n\
  \        description: Search customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-customers-customerid\n      path: /V1/customers/{customerId}\n      operations:\n      - name: getcustomer\n        method: GET\n        description: Get customer by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecustomer\n        method: PUT\n        description: Update a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecustomer\n        method: DELETE\n        description: Delete a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-orders\n      path: /V1/orders\n      operations:\n      - name: listorders\n\
  \        method: GET\n        description: List orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorder\n        method: POST\n        description: Create an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-orders-orderid\n      path: /V1/orders/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Get order by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-orders-orderid-cancel\n      path: /V1/orders/{orderId}/cancel\n      operations:\n      - name: cancelorder\n        method: POST\n        description: Cancel an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: v1-orders-orderid-comments\n      path: /V1/orders/{orderId}/comments\n      operations:\n      - name: addordercomment\n        method: POST\n        description: Add a comment to an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-invoices\n      path: /V1/invoices\n      operations:\n      - name: listinvoices\n        method: GET\n        description: List invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-invoices-invoiceid\n      path: /V1/invoices/{invoiceId}\n      operations:\n      - name: getinvoice\n        method: GET\n        description: Get invoice by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-order-orderid-invoice\n      path: /V1/order/{orderId}/invoice\n \
  \     operations:\n      - name: createinvoice\n        method: POST\n        description: Create an invoice for an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-shipment\n      path: /V1/shipment\n      operations:\n      - name: createshipment\n        method: POST\n        description: Create a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-shipment-shipmentid\n      path: /V1/shipment/{shipmentId}\n      operations:\n      - name: getshipment\n        method: GET\n        description: Get shipment by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-carts-mine\n      path: /V1/carts/mine\n      operations:\n      - name: createcustomercart\n        method: POST\n        description:\
  \ Create a cart for the authenticated customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-carts-mine-items\n      path: /V1/carts/mine/items\n      operations:\n      - name: additemtocart\n        method: POST\n        description: Add item to customer cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-guest-carts\n      path: /V1/guest-carts\n      operations:\n      - name: createguestcart\n        method: POST\n        description: Create a guest cart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-inventory-sources\n      path: /V1/inventory/sources\n      operations:\n      - name: listinventorysources\n        method: GET\n        description: List inventory sources\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinventorysource\n        method: POST\n        description: Create an inventory source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-inventory-sources-sourcecode\n      path: /V1/inventory/sources/{sourceCode}\n      operations:\n      - name: getinventorysource\n        method: GET\n        description: Get inventory source by code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinventorysource\n        method: PUT\n        description: Update an inventory source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-inventory-source-items\n      path: /V1/inventory/source-items\n  \
  \    operations:\n      - name: listsourceitems\n        method: GET\n        description: List source item quantities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesourceitems\n        method: POST\n        description: Update source item quantities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-taxrates\n      path: /V1/taxRates\n      operations:\n      - name: listtaxrates\n        method: GET\n        description: List tax rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-store-storeconfigs\n      path: /V1/store/storeConfigs\n      operations:\n      - name: liststoreconfigs\n        method: GET\n        description: List store configurations\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: magento-rest\n    description: REST adapter for Magento REST API.\n    resources:\n    - path: /V1/integration/admin/token\n      name: createadmintoken\n      operations:\n      - method: POST\n        name: createadmintoken\n        description: Get admin authentication token\n        call: magento.createadmintoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/integration/customer/token\n      name: createcustomertoken\n      operations:\n      - method: POST\n        name: createcustomertoken\n        description: Get customer authentication token\n        call: magento.createcustomertoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List products\n\
  \        call: magento.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/products\n      name: createproduct\n      operations:\n      - method: POST\n        name: createproduct\n        description: Create a product\n        call: magento.createproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/products/{sku}\n      name: getproduct\n      operations:\n      - method: GET\n        name: getproduct\n        description: Get product by SKU\n        call: magento.getproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/products/{sku}\n      name: updateproduct\n      operations:\n      - method: PUT\n        name: updateproduct\n        description: Update a product\n        call: magento.updateproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/products/{sku}\n      name: deleteproduct\n      operations:\n\
  \      - method: DELETE\n        name: deleteproduct\n        description: Delete a product\n        call: magento.deleteproduct\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/categories\n      name: listcategories\n      operations:\n      - method: GET\n        name: listcategories\n        description: List categories\n        call: magento.listcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/categories\n      name: createcategory\n      operations:\n      - method: POST\n        name: createcategory\n        description: Create a category\n        call: magento.createcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/categories/{categoryId}\n      name: getcategory\n      operations:\n      - method: GET\n        name: getcategory\n        description: Get category by ID\n        call: magento.getcategory\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /V1/categories/{categoryId}\n      name: updatecategory\n      operations:\n      - method: PUT\n        name: updatecategory\n        description: Update a category\n        call: magento.updatecategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/categories/{categoryId}\n      name: deletecategory\n      operations:\n      - method: DELETE\n        name: deletecategory\n        description: Delete a category\n        call: magento.deletecategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/customers\n      name: createcustomer\n      operations:\n      - method: POST\n        name: createcustomer\n        description: Create a customer\n        call: magento.createcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/customers/search\n      name: searchcustomers\n      operations:\n      - method:\
  \ GET\n        name: searchcustomers\n        description: Search customers\n        call: magento.searchcustomers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/customers/{customerId}\n      name: getcustomer\n      operations:\n      - method: GET\n        name: getcustomer\n        description: Get customer by ID\n        call: magento.getcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/customers/{customerId}\n      name: updatecustomer\n      operations:\n      - method: PUT\n        name: updatecustomer\n        description: Update a customer\n        call: magento.updatecustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/customers/{customerId}\n      name: deletecustomer\n      operations:\n      - method: DELETE\n        name: deletecustomer\n        description: Delete a customer\n        call: magento.deletecustomer\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /V1/orders\n      name: listorders\n      operations:\n      - method: GET\n        name: listorders\n        description: List orders\n        call: magento.listorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/orders\n      name: createorder\n      operations:\n      - method: POST\n        name: createorder\n        description: Create an order\n        call: magento.createorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/orders/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n        description: Get order by ID\n        call: magento.getorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/orders/{orderId}/cancel\n      name: cancelorder\n      operations:\n      - method: POST\n        name: cancelorder\n        description: Cancel an order\n\
  \        call: magento.cancelorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/orders/{orderId}/comments\n      name: addordercomment\n      operations:\n      - method: POST\n        name: addordercomment\n        description: Add a comment to an order\n        call: magento.addordercomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/invoices\n      name: listinvoices\n      operations:\n      - method: GET\n        name: listinvoices\n        description: List invoices\n        call: magento.listinvoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/invoices/{invoiceId}\n      name: getinvoice\n      operations:\n      - method: GET\n        name: getinvoice\n        description: Get invoice by ID\n        call: magento.getinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/order/{orderId}/invoice\n \
  \     name: createinvoice\n      operations:\n      - method: POST\n        name: createinvoice\n        description: Create an invoice for an order\n        call: magento.createinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/shipment\n      name: createshipment\n      operations:\n      - method: POST\n        name: createshipment\n        description: Create a shipment\n        call: magento.createshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/shipment/{shipmentId}\n      name: getshipment\n      operations:\n      - method: GET\n        name: getshipment\n        description: Get shipment by ID\n        call: magento.getshipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/carts/mine\n      name: createcustomercart\n      operations:\n      - method: POST\n        name: createcustomercart\n        description: Create a cart for the authenticated\
  \ customer\n        call: magento.createcustomercart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/carts/mine/items\n      name: additemtocart\n      operations:\n      - method: POST\n        name: additemtocart\n        description: Add item to customer cart\n        call: magento.additemtocart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/guest-carts\n      name: createguestcart\n      operations:\n      - method: POST\n        name: createguestcart\n        description: Create a guest cart\n        call: magento.createguestcart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/inventory/sources\n      name: listinventorysources\n      operations:\n      - method: GET\n        name: listinventorysources\n        description: List inventory sources\n        call: magento.listinventorysources\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /V1/inventory/sources\n      name: createinventorysource\n      operations:\n      - method: POST\n        name: createinventorysource\n        description: Create an inventory source\n        call: magento.createinventorysource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/inventory/sources/{sourceCode}\n      name: getinventorysource\n      operations:\n      - method: GET\n        name: getinventorysource\n        description: Get inventory source by code\n        call: magento.getinventorysource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/inventory/sources/{sourceCode}\n      name: updateinventorysource\n      operations:\n      - method: PUT\n        name: updateinventorysource\n        description: Update an inventory source\n        call: magento.updateinventorysource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/inventory/source-items\n\
  \      name: listsourceitems\n      operations:\n      - method: GET\n        name: listsourceitems\n        description: List source item quantities\n        call: magento.listsourceitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/inventory/source-items\n      name: updatesourceitems\n      operations:\n      - method: POST\n        name: updatesourceitems\n        description: Update source item quantities\n        call: magento.updatesourceitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/taxRates\n      name: listtaxrates\n      operations:\n      - method: GET\n        name: listtaxrates\n        description: List tax rates\n        call: magento.listtaxrates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /V1/store/storeConfigs\n      name: liststoreconfigs\n      operations:\n      - method: GET\n        name: liststoreconfigs\n        description:\
  \ List store configurations\n        call: magento.liststoreconfigs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: magento-mcp\n    transport: http\n    description: MCP adapter for Magento REST API for AI agent use.\n    tools:\n    - name: createadmintoken\n      description: Get admin authentication token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createadmintoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomertoken\n      description: Get customer authentication token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createcustomertoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproducts\n      description: List products\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: magento.listproducts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproduct\n      description: Create a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproduct\n      description: Get product by SKU\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproduct\n      description: Update a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: magento.updateproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproduct\n      description: Delete a product\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n        idempotent: true\n      call: magento.deleteproduct\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcategories\n      description: List categories\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listcategories\n      with:\n        rootCategoryId: tools.rootCategoryId\n        depth: tools.depth\n      inputParameters:\n      - name: rootCategoryId\n        type: integer\n        description: Root category ID to start the tree from. Defaults to the default root category.\n      - name: depth\n        type: integer\n        description: Maximum depth of the category tree to return.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcategory\n      description: Create a category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createcategory\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcategory\n      description: Get category by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecategory\n      description: Update a category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: magento.updatecategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecategory\n      description: Delete a category\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: magento.deletecategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomer\n      description: Create a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: magento.createcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcustomers\n      description: Search customers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.searchcustomers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomer\n      description: Get customer by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecustomer\n      description: Update a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: magento.updatecustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecustomer\n      description: Delete a customer\n      hints:\n        readOnly: false\n\
  \        destructive: true\n        idempotent: true\n      call: magento.deletecustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorders\n      description: List orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorder\n      description: Create an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Get order by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelorder\n      description: Cancel an order\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: magento.cancelorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addordercomment\n      description: Add a comment to an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.addordercomment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinvoices\n      description: List invoices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listinvoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinvoice\n      description: Get invoice by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinvoice\n      description: Create\
  \ an invoice for an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createshipment\n      description: Create a shipment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshipment\n      description: Get shipment by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getshipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomercart\n      description: Create a cart for the authenticated customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createcustomercart\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: additemtocart\n      description: Add item to customer cart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.additemtocart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createguestcart\n      description: Create a guest cart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.createguestcart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinventorysources\n      description: List inventory sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listinventorysources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinventorysource\n      description: Create an inventory source\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: magento.createinventorysource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinventorysource\n      description: Get inventory source by code\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.getinventorysource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinventorysource\n      description: Update an inventory source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: magento.updateinventorysource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsourceitems\n      description: List source item quantities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listsourceitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ updatesourceitems\n      description: Update source item quantities\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: magento.updatesourceitems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaxrates\n      description: List tax rates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.listtaxrates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststoreconfigs\n      description: List store configurations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: magento.liststoreconfigs\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MAGENTO_TOKEN: MAGENTO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/magento/refs/heads/main/capabilities/magento-capability.yaml
tags:
- Magento
- API
tools:
- description: Get admin authentication token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadmintoken
- description: Get customer authentication token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomertoken
- description: List products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
- description: Create a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproduct
- description: Get product by SKU
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproduct
- description: Update a product
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproduct
- description: Delete a product
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproduct
- description: List categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcategories
- description: Create a category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcategory
- description: Get category by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcategory
- description: Update a category
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecategory
- description: Delete a category
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecategory
- description: Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomer
- description: Search customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcustomers
- description: Get customer by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomer
- description: Update a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecustomer
- description: Delete a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecustomer
- description: List orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorders
- description: Create an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorder
- description: Get order by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
- description: Cancel an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelorder
- description: Add a comment to an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addordercomment
- description: List invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinvoices
- description: Get invoice by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinvoice
- description: Create an invoice for an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinvoice
- description: Create a shipment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshipment
- description: Get shipment by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipment
- description: Create a cart for the authenticated customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomercart
- description: Add item to customer cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: additemtocart
- description: Create a guest cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createguestcart
- description: List inventory sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinventorysources
- description: Create an inventory source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinventorysource
- description: Get inventory source by code
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinventorysource
- description: Update an inventory source
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinventorysource
- description: List source item quantities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsourceitems
- description: Update source item quantities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesourceitems
- description: List tax rates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaxrates
- description: List store configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststoreconfigs
---
