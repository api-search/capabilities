---
categories: []
consumed_apis: []
description: Unified workflow for managing commerce operations across platforms like Shopify, WooCommerce, Amazon, BigCommerce, and Magento. Enables operations teams to read and manage orders, products, customers, and fulfillments through a single interface regardless of the underlying commerce platform.
layout: capability
name: Rutter Commerce Operations
operations:
- description: List orders from connected commerce platform
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order in connected commerce platform
  method: POST
  name: create-order
  path: /v1/orders
- description: Get a specific order by ID
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Mark an order as fulfilled
  method: POST
  name: fulfill-order
  path: /v1/orders/{orderId}/fulfillments
- description: List products from connected commerce platform
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product in connected commerce platform
  method: POST
  name: create-product
  path: /v1/products
- description: Get a specific product by ID
  method: GET
  name: get-product
  path: /v1/products/{productId}
- description: Update a product in connected commerce platform
  method: PUT
  name: update-product
  path: /v1/products/{productId}
- description: List customers from connected platform
  method: GET
  name: list-customers
  path: /v1/customers
- description: Get a specific customer by ID
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
personas: []
provider_name: Rutter
provider_slug: rutter
search_terms:
- create order
- create a new product in connected commerce platform
- accounting
- get product
- create product
- unified api
- list products
- product catalog
- b2b
- orders
- get a specific product by id from connected commerce platform
- get a specific customer by id
- list customers from connected commerce or accounting platform
- update a product in connected commerce platform
- update product
- single order
- products
- get a specific customer by id from connected platform
- financial data
- get a specific order by id
- list orders from connected commerce platform (shopify, woocommerce, amazon)
- get a specific product by id
- list orders
- list orders from connected commerce platform
- e-commerce
- single product
- list customers from connected platform
- mark an order as fulfilled
- get customer
- create a new order in the connected commerce platform
- mark an order as fulfilled with tracking information
- fulfill order
- update an existing product in the connected commerce platform
- create a new product in the connected commerce platform
- single customer
- list customers
- order fulfillments
- commerce orders
- payments
- create a new order in connected commerce platform
- customer data
- commerce
- list products from connected commerce platform
- get order
- get a specific order by id from connected commerce platform
slug: commerce-operations
source_filename: commerce-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rutter Commerce Operations\n  description: Unified workflow for managing commerce operations across platforms like Shopify, WooCommerce, Amazon, BigCommerce,\n    and Magento. Enables operations teams to read and manage orders, products, customers, and fulfillments through a single\n    interface regardless of the underlying commerce platform.\n  tags:\n  - B2B\n  - Commerce\n  - E-Commerce\n  - Orders\n  - Products\n  - Unified API\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUTTER_CLIENT_ID: RUTTER_CLIENT_ID\n    RUTTER_CLIENT_SECRET: RUTTER_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: rutter\n    baseUri: https://production.rutterapi.com/versioned\n    description: Rutter Unified API for B2B financial platform data\n    authentication:\n      type: basic\n      username: '{{RUTTER_CLIENT_ID}}'\n      password: '{{RUTTER_CLIENT_SECRET}}'\n    resources:\n    -\
  \ name: connections\n      path: /connections\n      description: Manage platform connections\n      operations:\n      - name: list-connections\n        method: GET\n        description: Retrieve all connections for the authenticated client\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version (e.g. 2024-08-31)\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connection\n        method: GET\n        description: Retrieve details for a specific platform connection\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name:\
  \ connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: exchange-token\n        method: POST\n        description: Exchange Rutter Link public token for permanent access token\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            public_token: '{{tools.public_token}}'\n    - name: accounts\n      path: /accounts\n      description: Chart of accounts from connected accounting platforms\n      operations:\n      - name: list-accounts\n        method: GET\n        description:\
  \ Retrieve chart of accounts from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      description: Financial transactions from connected platforms\n      operations:\n      - name: list-transactions\n        method: GET\n        description: Retrieve financial transactions from the connected platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in:\
  \ header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: updated_at_min\n          in: query\n          type: string\n          required: false\n          description: Filter updated after this timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoices from connected accounting platforms\n      operations:\n      - name: list-invoices\n        method: GET\n        description: Retrieve invoices from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n       \
  \   in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Create a new invoice in the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            currency: '{{tools.currency}}'\n            due_date: '{{tools.due_date}}'\n      - name: get-invoice\n        method: GET\n        description: Retrieve a specific invoice by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bills\n      path:\
  \ /bills\n      description: Bills (vendor invoices) from connected accounting platforms\n      operations:\n      - name: list-bills\n        method: GET\n        description: Retrieve bills from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bill\n        method: POST\n        description: Create a new bill in the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n\
  \          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            vendor_id: '{{tools.vendor_id}}'\n            currency: '{{tools.currency}}'\n            due_date: '{{tools.due_date}}'\n    - name: expenses\n      path: /expenses\n      description: Expense records from connected accounting platforms\n      operations:\n      - name: list-expenses\n        method: GET\n        description: Retrieve expense records from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description:\
  \ API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Orders from connected commerce platforms\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieve orders from the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        -\
  \ name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: expand\n          in: query\n          type: string\n          required: false\n          description: Expand with platform_data\n        - name: updated_at_min\n          in: query\n          type: string\n          required: false\n          description: Filter updated after this timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access\
  \ token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            currency: '{{tools.currency}}'\n      - name: get-order\n        method: GET\n        description: Retrieve a specific order by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fulfill-order\n      \
  \  method: POST\n        description: Mark an order as fulfilled with fulfillment details\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tracking_number: '{{tools.tracking_number}}'\n            carrier: '{{tools.carrier}}'\n    - name: products\n      path: /products\n      description: Products from connected commerce platforms\n      operations:\n      - name: list-products\n        method: GET\n\
  \        description: Retrieve products from the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new product in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in:\
  \ query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            price: '{{tools.price}}'\n      - name: get-product\n        method: GET\n        description: Retrieve a specific product by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an existing product in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            price: '{{tools.price}}'\n    - name: customers\n      path: /customers\n      description: Customers from connected commerce or accounting\
  \ platforms\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve customers from the connected platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Retrieve details for a specific customer\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description:\
  \ API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bank-accounts\n      path: /bank-accounts\n      description: Bank accounts from connected banking platforms\n      operations:\n      - name: list-bank-accounts\n        method: GET\n        description: Retrieve bank accounts from the connected banking platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description:\
  \ Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /config-webhooks\n      description: Webhook configuration and management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: Retrieve all configured webhooks\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Configure a new webhook endpoint\n        inputParameters:\n        - name: X-Rutter-Version\n          in:\
  \ header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Remove a webhook configuration\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: Webhook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: rutter-commerce-ops-api\n    description: Unified\
  \ REST API for commerce operations across e-commerce platforms.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Commerce orders\n      operations:\n      - method: GET\n        name: list-orders\n        description: List orders from connected commerce platform\n        call: rutter.list-orders\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          cursor: rest.query.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new order in connected commerce platform\n        call: rutter.create-order\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order\n      description: Single order\n\
  \      operations:\n      - method: GET\n        name: get-order\n        description: Get a specific order by ID\n        call: rutter.get-order\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          orderId: rest.path.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}/fulfillments\n      name: fulfillments\n      description: Order fulfillments\n      operations:\n      - method: POST\n        name: fulfill-order\n        description: Mark an order as fulfilled\n        call: rutter.fulfill-order\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          orderId: rest.path.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product catalog\n      operations:\n      - method:\
  \ GET\n        name: list-products\n        description: List products from connected commerce platform\n        call: rutter.list-products\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Create a new product in connected commerce platform\n        call: rutter.create-product\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{productId}\n      name: product\n      description: Single product\n      operations:\n      - method: GET\n        name: get-product\n        description: Get a specific product by ID\n        call: rutter.get-product\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n\
  \          access_token: rest.query.access_token\n          productId: rest.path.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-product\n        description: Update a product in connected commerce platform\n        call: rutter.update-product\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          productId: rest.path.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer data\n      operations:\n      - method: GET\n        name: list-customers\n        description: List customers from connected platform\n        call: rutter.list-customers\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/customers/{customerId}\n      name: customer\n      description: Single customer\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get a specific customer by ID\n        call: rutter.get-customer\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          customerId: rest.path.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: rutter-commerce-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted commerce operations across e-commerce platforms.\n    tools:\n    - name: list-orders\n      description: List orders from connected commerce platform (Shopify, WooCommerce, Amazon)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-orders\n      with:\n        access_token: tools.access_token\n        cursor: tools.cursor\n \
  \       updated_at_min: tools.updated_at_min\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get a specific order by ID from connected commerce platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rutter.get-order\n      with:\n        access_token: tools.access_token\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Create a new order in the connected commerce platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rutter.create-order\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fulfill-order\n      description: Mark an order as fulfilled with tracking information\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: rutter.fulfill-order\n      with:\n        access_token: tools.access_token\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: List products from connected commerce platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-products\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get a specific product by ID from connected commerce platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rutter.get-product\n      with:\n        access_token: tools.access_token\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Create a new product in the connected commerce platform\n      hints:\n       \
  \ readOnly: false\n        destructive: false\n        idempotent: false\n      call: rutter.create-product\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-product\n      description: Update an existing product in the connected commerce platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: rutter.update-product\n      with:\n        access_token: tools.access_token\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List customers from connected commerce or accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-customers\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description:\
  \ Get a specific customer by ID from connected platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rutter.get-customer\n      with:\n        access_token: tools.access_token\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rutter/refs/heads/main/capabilities/commerce-operations.yaml
tags:
- B2B
- Commerce
- E-Commerce
- Orders
- Products
- Unified API
tools:
- description: List orders from connected commerce platform (Shopify, WooCommerce, Amazon)
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get a specific order by ID from connected commerce platform
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Create a new order in the connected commerce platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Mark an order as fulfilled with tracking information
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfill-order
- description: List products from connected commerce platform
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get a specific product by ID from connected commerce platform
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: Create a new product in the connected commerce platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-product
- description: Update an existing product in the connected commerce platform
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-product
- description: List customers from connected commerce or accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get a specific customer by ID from connected platform
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
---
