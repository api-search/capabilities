---
categories: []
consumed_apis: []
description: Workflow capability for TD SYNNEX StreamOne Ion cloud distribution management. Enables MSPs and resellers to automate end-to-end cloud subscription lifecycle management including customer provisioning, product ordering, subscription tracking, and business intelligence reporting across multiple cloud vendors through a single unified interface.
layout: capability
name: TD SYNNEX Cloud Distribution
operations:
- description: List all end customers in the partner account
  method: GET
  name: list-customers
  path: /v1/customers
- description: Add a new end customer to the platform
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get details for a specific customer
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: Browse available technology products
  method: GET
  name: list-products
  path: /v1/products
- description: List all orders for the account
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new technology product order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get details for a specific order
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: List cloud subscriptions for a customer
  method: GET
  name: list-subscriptions
  path: /v1/customers/{customerId}/subscriptions
- description: List available business intelligence reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Access report data
  method: GET
  name: get-report-data
  path: /v1/reports/{reportId}/data
personas: []
provider_name: TD SYNNEX
provider_slug: td-synnex
search_terms:
- msp
- add a new end customer to the td synnex streamone platform
- create customer
- get detailed information for a specific technology product including pricing
- access report data
- create order
- subscription management
- get product
- list products
- get status and details for a specific technology product order
- list customer subscriptions
- b2b
- list reports
- order management
- browse available technology products
- list cloud subscriptions for a customer
- product order management
- single customer management
- list all end customers in the td synnex partner account
- list all technology product orders for the partner account
- get details for a specific order
- get report data
- business intelligence reports
- list available business intelligence reports for distribution analytics
- create a new technology product order
- fortune 100
- streamone
- browse available technology products in the td synnex distribution catalog
- list all end customers in the partner account
- it distribution
- add a new end customer to the platform
- reseller
- td synnex
- list orders
- get details for a specific customer
- single order management
- get customer
- list subscriptions
- list available business intelligence reports
- technology product catalog
- streamone ion
- access business intelligence report data for distribution analytics
- report data access
- list customers
- cloud
- list all orders for the account
- get details for a specific end customer including cloud profiles
- technology distribution
- customer subscription management
- create a new technology product order for an end customer
- cloud distribution
- list all active cloud software subscriptions for a customer
- end customer account management
- get order
slug: cloud-distribution
source_filename: cloud-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TD SYNNEX Cloud Distribution\n  description: Workflow capability for TD SYNNEX StreamOne Ion cloud distribution management. Enables MSPs and resellers to\n    automate end-to-end cloud subscription lifecycle management including customer provisioning, product ordering, subscription\n    tracking, and business intelligence reporting across multiple cloud vendors through a single unified interface.\n  tags:\n  - TD SYNNEX\n  - StreamOne Ion\n  - Cloud Distribution\n  - Technology Distribution\n  - MSP\n  - Reseller\n  - Subscription Management\n  - Order Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TDSYNNEX_ACCESS_TOKEN: TDSYNNEX_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: streamone-ion\n    baseUri: https://ion.tdsynnex.com\n    description: TD SYNNEX StreamOne Ion Partner API for cloud distribution\n    authentication:\n      type: bearer\n      token:\
  \ '{{TDSYNNEX_ACCESS_TOKEN}}'\n    resources:\n    - name: customers\n      path: /v3/accounts/{accountId}/customers\n      description: End customer account management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all end customers\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Add a new end customer to the platform\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n\
  \          data:\n            companyName: '{{tools.companyName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            address: '{{tools.address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Get details for a specific customer\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PUT\n        description: Update an existing customer's information\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            companyName: '{{tools.companyName}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /v3/accounts/{accountId}/products\n      description: Technology product catalog\n      operations:\n      - name: list-products\n        method: GET\n        description: List available technology products\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: vendor\n          in: query\n          type: string\n          required: false\n        - name: category\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Get details for a specific product\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: productId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /v3/accounts/{accountId}/orders\n      description: Order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List all orders for the account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new technology product order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customerId}}'\n            items: '{{tools.items}}'\n            notes: '{{tools.notes}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Get details for a specific order\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /v3/accounts/{accountId}/customers/{customerId}/subscriptions\n      description: Cloud subscription management\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List all subscriptions for a customer\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        - name: vendor\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v3/accounts/{accountId}/reports\n      description: Business intelligence reports\n \
  \     operations:\n      - name: list-reports\n        method: GET\n        description: List available business intelligence reports\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report-data\n        method: GET\n        description: Access report data\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tdsynnex-cloud-distribution-api\n\
  \    description: Unified REST API for TD SYNNEX cloud distribution lifecycle management.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: End customer account management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all end customers in the partner account\n        call: streamone-ion.list-customers\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Add a new end customer to the platform\n        call: streamone-ion.create-customer\n        with:\n          accountId: rest.accountId\n          companyName: rest.companyName\n          email: rest.email\n          phone: rest.phone\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n      name: customer-detail\n\
  \      description: Single customer management\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get details for a specific customer\n        call: streamone-ion.get-customer\n        with:\n          accountId: rest.accountId\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Technology product catalog\n      operations:\n      - method: GET\n        name: list-products\n        description: Browse available technology products\n        call: streamone-ion.list-products\n        with:\n          accountId: rest.accountId\n          vendor: rest.vendor\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Product order management\n      operations:\n      - method: GET\n        name: list-orders\n    \
  \    description: List all orders for the account\n        call: streamone-ion.list-orders\n        with:\n          accountId: rest.accountId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new technology product order\n        call: streamone-ion.create-order\n        with:\n          accountId: rest.accountId\n          customerId: rest.customerId\n          items: rest.items\n          notes: rest.notes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order-detail\n      description: Single order management\n      operations:\n      - method: GET\n        name: get-order\n        description: Get details for a specific order\n        call: streamone-ion.get-order\n        with:\n          accountId: rest.accountId\n          orderId: rest.orderId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}/subscriptions\n      name: subscriptions\n      description: Customer subscription management\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List cloud subscriptions for a customer\n        call: streamone-ion.list-subscriptions\n        with:\n          accountId: rest.accountId\n          customerId: rest.customerId\n          vendor: rest.vendor\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Business intelligence reports\n      operations:\n      - method: GET\n        name: list-reports\n        description: List available business intelligence reports\n        call: streamone-ion.list-reports\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/reports/{reportId}/data\n      name: report-data\n      description: Report data access\n      operations:\n      - method: GET\n        name: get-report-data\n        description: Access report data\n        call: streamone-ion.get-report-data\n        with:\n          accountId: rest.accountId\n          reportId: rest.reportId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tdsynnex-cloud-distribution-mcp\n    transport: http\n    description: MCP server for AI-assisted TD SYNNEX cloud distribution management.\n    tools:\n    - name: list-customers\n      description: List all end customers in the TD SYNNEX partner account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.list-customers\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Add a new end\
  \ customer to the TD SYNNEX StreamOne platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.create-customer\n      with:\n        accountId: tools.accountId\n        companyName: tools.companyName\n        email: tools.email\n        phone: tools.phone\n        address: tools.address\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get details for a specific end customer including cloud profiles\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-customer\n      with:\n        accountId: tools.accountId\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: Browse available technology products in the TD SYNNEX distribution catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.list-products\n\
  \      with:\n        accountId: tools.accountId\n        vendor: tools.vendor\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get detailed information for a specific technology product including pricing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: streamone-ion.get-product\n      with:\n        accountId: tools.accountId\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List all technology product orders for the partner account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.list-orders\n      with:\n        accountId: tools.accountId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Create a new technology product order for\
  \ an end customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: streamone-ion.create-order\n      with:\n        accountId: tools.accountId\n        customerId: tools.customerId\n        items: tools.items\n        notes: tools.notes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get status and details for a specific technology product order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-order\n      with:\n        accountId: tools.accountId\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customer-subscriptions\n      description: List all active cloud software subscriptions for a customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.list-subscriptions\n      with:\n        accountId: tools.accountId\n\
  \        customerId: tools.customerId\n        vendor: tools.vendor\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available business intelligence reports for distribution analytics\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.list-reports\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-data\n      description: Access business intelligence report data for distribution analytics\n      hints:\n        readOnly: true\n        openWorld: false\n      call: streamone-ion.get-report-data\n      with:\n        accountId: tools.accountId\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/td-synnex/refs/heads/main/capabilities/cloud-distribution.yaml
tags:
- TD SYNNEX
- StreamOne Ion
- Cloud Distribution
- Technology Distribution
- MSP
- Reseller
- Subscription Management
- Order Management
tools:
- description: List all end customers in the TD SYNNEX partner account
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Add a new end customer to the TD SYNNEX StreamOne platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: Get details for a specific end customer including cloud profiles
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Browse available technology products in the TD SYNNEX distribution catalog
  hints:
    openWorld: true
    readOnly: true
  name: list-products
- description: Get detailed information for a specific technology product including pricing
  hints:
    openWorld: true
    readOnly: true
  name: get-product
- description: List all technology product orders for the partner account
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Create a new technology product order for an end customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Get status and details for a specific technology product order
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: List all active cloud software subscriptions for a customer
  hints:
    openWorld: false
    readOnly: true
  name: list-customer-subscriptions
- description: List available business intelligence reports for distribution analytics
  hints:
    openWorld: false
    readOnly: true
  name: list-reports
- description: Access business intelligence report data for distribution analytics
  hints:
    openWorld: false
    readOnly: true
  name: get-report-data
---
