---
categories: []
consumed_apis: []
description: Unified cloud distribution workflow for TD SYNNEX reseller partners. Combines customer lifecycle management, product catalog browsing, order processing, subscription management, and business reporting through the StreamOne Ion API. Designed for partner sales engineers, managed service providers, and cloud resellers who need to automate their TD SYNNEX distribution workflows.
layout: capability
name: TD SYNNEX Cloud Distribution
operations:
- description: List all end customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new end customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get customer details
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: List customer subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/customers/{customerId}/subscriptions
- description: Browse available products
  method: GET
  name: list-products
  path: /v1/products
- description: List all orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order details
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Cancel an order
  method: DELETE
  name: cancel-order
  path: /v1/orders/{orderId}
- description: List shopping carts
  method: GET
  name: list-carts
  path: /v1/carts
- description: Create a new cart
  method: POST
  name: create-cart
  path: /v1/carts
- description: List available reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Get data for a report
  method: GET
  name: get-report-data
  path: /v1/reports/{reportId}/data
personas: []
provider_name: Tech Data
provider_slug: tech-data
search_terms:
- list available billing and business reports
- report data retrieval
- create customer
- get details for a specific end customer
- get customer details
- list available reports
- create order
- list carts
- list all orders
- get product
- list products
- list customer subscriptions
- single order operations
- product catalog
- create cart
- add cart item
- browse available products
- list reports
- order management
- get details for a specific order
- get report data
- cancel an unprocessed order
- cancel an order
- shopping cart management
- partner
- list all end customers for the reseller account
- reseller
- get data for a report
- list all end customers
- list orders
- information technology
- cancel order
- browse the td synnex product catalog
- e-commerce
- create a new order
- create a new end customer
- get customer
- create a new shopping cart for order building
- add a product to a shopping cart
- list active subscriptions for a customer
- list subscriptions
- checkout cart
- distribution
- single customer operations
- create a new cart
- list customers
- cloud
- list all orders for the account
- customer subscription management
- list shopping carts
- get order details
- create a new end customer account
- get details for a specific product
- business and billing reports
- check out a cart to create an order
- get data from a billing or business report
- end customer account management
- get order
- create a new product order for a customer
slug: cloud-distribution
source_filename: cloud-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TD SYNNEX Cloud Distribution\n  description: Unified cloud distribution workflow for TD SYNNEX reseller partners. Combines customer lifecycle management,\n    product catalog browsing, order processing, subscription management, and business reporting through the StreamOne Ion\n    API. Designed for partner sales engineers, managed service providers, and cloud resellers who need to automate their TD\n    SYNNEX distribution workflows.\n  tags:\n  - Cloud\n  - Distribution\n  - E-Commerce\n  - Partner\n  - Reseller\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STREAMONE_ION_BEARER_TOKEN: STREAMONE_ION_BEARER_TOKEN\n    STREAMONE_ION_ACCOUNT_ID: STREAMONE_ION_ACCOUNT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: streamone-ion\n    baseUri: https://ion.tdsynnex.com/api\n    description: TD SYNNEX StreamOne Ion reseller partner API\n    authentication:\n      type: bearer\n      token:\
  \ '{{STREAMONE_ION_BEARER_TOKEN}}'\n    resources:\n    - name: customers\n      path: /v3/accounts/{accountId}/customers\n      description: End customer account management\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve paginated list of customers for the reseller account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter customers by status\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new end customer account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n    - name: customer\n      path: /v3/accounts/{accountId}/customers/{customerId}\n      description: Single customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Retrieve details for a specific customer\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n\
  \          required: true\n          description: Reseller account identifier\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PUT\n        description: Update an existing customer account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n       \
  \     status: '{{tools.status}}'\n    - name: customer-cloud-profiles\n      path: /v3/accounts/{accountId}/customers/{customerId}/cloudProfiles\n      description: Customer cloud provider profile management\n      operations:\n      - name: get-customer-cloud-profiles\n        method: GET\n        description: Retrieve cloud provider profiles for a customer\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /v3/accounts/{accountId}/products\n      description: Product catalog management\n      operations:\n      - name: list-products\n        method: GET\n        description:\
  \ Retrieve list of available products\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: vendorId\n          in: query\n          type: string\n          required: false\n          description: Filter by vendor\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: product\n      path: /v3/accounts/{accountId}/products/{productId}\n      description: Single product\
  \ operations\n      operations:\n      - name: get-product\n        method: GET\n        description: Retrieve details for a specific product\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /v3/accounts/{accountId}/orders\n      description: Order management\n      operations:\n      - name: list-account-orders\n        method: GET\n        description: Retrieve all orders for the account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n    \
  \    - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by order status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId:\
  \ '{{tools.customerId}}'\n            items: '{{tools.items}}'\n    - name: order\n      path: /v3/accounts/{accountId}/orders/{orderId}\n      description: Single order operations\n      operations:\n      - name: get-order\n        method: GET\n        description: Retrieve a specific order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-order\n        method: PUT\n        description: Update an existing order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n\
  \        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n      - name: cancel-order\n        method: DELETE\n        description: Cancel an order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-subscriptions\n      path: /v3/accounts/{accountId}/customers/{customerId}/subscriptions\n    \
  \  description: Customer subscription management\n      operations:\n      - name: list-customer-subscriptions\n        method: GET\n        description: List all subscriptions for a customer\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-subscription\n      path: /v3/accounts/{accountId}/customers/{customerId}/subscriptions/{subscriptionId}\n      description: Single subscription operations\n      operations:\n      - name: get-customer-subscription\n        method: GET\n        description: Get a specific customer subscription\n        inputParameters:\n        - name: accountId\n\
  \          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carts\n      path: /v3/accounts/{accountId}/carts\n      description: Shopping cart management\n      operations:\n      - name: list-carts\n        method: GET\n        description: List all shopping carts for the account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-cart\n        method: POST\n        description: Create a new shopping cart\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n    - name: cart\n      path: /v3/accounts/{accountId}/carts/{cartId}\n      description: Single cart operations\n      operations:\n      - name: get-cart\n        method: GET\n        description: Get a specific shopping cart\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: cartId\n\
  \          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cart-checkout\n      path: /v3/accounts/{accountId}/carts/{cartId}/checkout\n      description: Cart checkout\n      operations:\n      - name: checkout-cart\n        method: POST\n        description: Submit a shopping cart to create an order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cart-items\n      path: /v3/accounts/{accountId}/carts/{cartId}/items\n\
  \      description: Cart item management\n      operations:\n      - name: list-cart-items\n        method: GET\n        description: List all items in a cart\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-cart-item\n        method: POST\n        description: Add a product to a cart\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: cartId\n          in: path\n          type: string\n          required: true\n          description: Cart identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            productId: '{{tools.productId}}'\n            quantity: '{{tools.quantity}}'\n    - name: reports\n      path: /v3/accounts/{accountId}/reports\n      description: Business reporting\n      operations:\n      - name: list-reports\n        method: GET\n        description: List all available reports\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: report-data\n      path: /v3/accounts/{accountId}/reports/{reportId}/data\n      description: Report data retrieval\n      operations:\n      - name: get-report-data\n        method: GET\n  \
  \      description: Get data for a specific report\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Reseller account identifier\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloud-distribution-api\n    description: Unified REST API for TD SYNNEX cloud distribution partner workflows.\n    resources:\n    - path: /v1/customers\n\
  \      name: customers\n      description: End customer account management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all end customers\n        call: streamone-ion.list-customers\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new end customer\n        call: streamone-ion.create-customer\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer\n      description: Single customer operations\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get customer details\n        call: streamone-ion.get-customer\n        with:\n          accountId: rest.accountId\n          customerId: rest.customerId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}/subscriptions\n      name: customer-subscriptions\n      description: Customer subscription management\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List customer subscriptions\n        call: streamone-ion.list-customer-subscriptions\n        with:\n          accountId: rest.accountId\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product catalog\n      operations:\n      - method: GET\n        name: list-products\n        description: Browse available products\n        call: streamone-ion.list-products\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order management\n      operations:\n\
  \      - method: GET\n        name: list-orders\n        description: List all orders\n        call: streamone-ion.list-account-orders\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new order\n        call: streamone-ion.create-order\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order\n      description: Single order operations\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order details\n        call: streamone-ion.get-order\n        with:\n          accountId: rest.accountId\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-order\n        description: Cancel\
  \ an order\n        call: streamone-ion.cancel-order\n        with:\n          accountId: rest.accountId\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carts\n      name: carts\n      description: Shopping cart management\n      operations:\n      - method: GET\n        name: list-carts\n        description: List shopping carts\n        call: streamone-ion.list-carts\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cart\n        description: Create a new cart\n        call: streamone-ion.create-cart\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Business and billing reports\n      operations:\n      - method: GET\n        name: list-reports\n      \
  \  description: List available reports\n        call: streamone-ion.list-reports\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{reportId}/data\n      name: report-data\n      description: Report data retrieval\n      operations:\n      - method: GET\n        name: get-report-data\n        description: Get data for a report\n        call: streamone-ion.get-report-data\n        with:\n          accountId: rest.accountId\n          reportId: rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: cloud-distribution-mcp\n    transport: http\n    description: MCP server for AI-assisted TD SYNNEX cloud distribution partner workflows.\n    tools:\n    - name: list-customers\n      description: List all end customers for the reseller account\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ streamone-ion.list-customers\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get details for a specific end customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-customer\n      with:\n        accountId: tools.accountId\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new end customer account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.create-customer\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List active subscriptions for a customer\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.list-customer-subscriptions\n\
  \      with:\n        accountId: tools.accountId\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: Browse the TD SYNNEX product catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.list-products\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get details for a specific product\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-product\n      with:\n        accountId: tools.accountId\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List all orders for the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.list-account-orders\n      with:\n  \
  \      accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get details for a specific order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-order\n      with:\n        accountId: tools.accountId\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Create a new product order for a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.create-order\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order\n      description: Cancel an unprocessed order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: streamone-ion.cancel-order\n      with:\n        accountId:\
  \ tools.accountId\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cart\n      description: Create a new shopping cart for order building\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.create-cart\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-cart-item\n      description: Add a product to a shopping cart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.add-cart-item\n      with:\n        accountId: tools.accountId\n        cartId: tools.cartId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: checkout-cart\n      description: Check out a cart to create an order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: streamone-ion.checkout-cart\n      with:\n        accountId: tools.accountId\n        cartId: tools.cartId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available billing and business reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.list-reports\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-data\n      description: Get data from a billing or business report\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-report-data\n      with:\n        accountId: tools.accountId\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tech-data/refs/heads/main/capabilities/cloud-distribution.yaml
tags:
- Cloud
- Distribution
- E-Commerce
- Partner
- Reseller
tools:
- description: List all end customers for the reseller account
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get details for a specific end customer
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Create a new end customer account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: List active subscriptions for a customer
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Browse the TD SYNNEX product catalog
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get details for a specific product
  hints:
    openWorld: false
    readOnly: true
  name: get-product
- description: List all orders for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Get details for a specific order
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Create a new product order for a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Cancel an unprocessed order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order
- description: Create a new shopping cart for order building
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-cart
- description: Add a product to a shopping cart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-cart-item
- description: Check out a cart to create an order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkout-cart
- description: List available billing and business reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get data from a billing or business report
  hints:
    openWorld: false
    readOnly: true
  name: get-report-data
---
