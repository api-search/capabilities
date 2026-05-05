---
categories: []
consumed_apis:
- streamone-ion
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
- it distribution
- get report data
- list products
- list customers
- business intelligence reports
- access report data
- add a new end customer to the platform
- fortune 100
- technology distribution
- subscription management
- list available business intelligence reports
- streamone ion
- list all end customers in the td synnex partner account
- list customer subscriptions
- access business intelligence report data for distribution analytics
- cloud
- end customer account management
- get order
- get details for a specific end customer including cloud profiles
- msp
- td synnex
- cloud distribution
- streamone
- list available business intelligence reports for distribution analytics
- create a new technology product order
- reseller
- get details for a specific order
- browse available technology products in the td synnex distribution catalog
- get customer
- list all active cloud software subscriptions for a customer
- list all end customers in the partner account
- report data access
- product order management
- single order management
- b2b
- technology product catalog
- add a new end customer to the td synnex streamone platform
- get product
- list orders
- browse available technology products
- create order
- single customer management
- get status and details for a specific technology product order
- list all orders for the account
- list subscriptions
- create customer
- get details for a specific customer
- order management
- list reports
- list cloud subscriptions for a customer
- get detailed information for a specific technology product including pricing
- customer subscription management
- list all technology product orders for the partner account
- create a new technology product order for an end customer
slug: cloud-distribution
source_filename: cloud-distribution.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TD SYNNEX Cloud Distribution\"\n  description: >-\n    Workflow capability for TD SYNNEX StreamOne Ion cloud distribution management.\n    Enables MSPs and resellers to automate end-to-end cloud subscription lifecycle\n    management including customer provisioning, product ordering, subscription\n    tracking, and business intelligence reporting across multiple cloud vendors\n    through a single unified interface.\n  tags:\n    - TD SYNNEX\n    - StreamOne Ion\n    - Cloud Distribution\n    - Technology Distribution\n    - MSP\n    - Reseller\n    - Subscription Management\n    - Order Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TDSYNNEX_ACCESS_TOKEN: TDSYNNEX_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: streamone-ion\n      location: ./shared/streamone-ion.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tdsynnex-cloud-distribution-api\n\
  \      description: \"Unified REST API for TD SYNNEX cloud distribution lifecycle management.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"End customer account management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all end customers in the partner account\"\n              call: \"streamone-ion.list-customers\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Add a new end customer to the platform\"\n              call: \"streamone-ion.create-customer\"\n              with:\n                accountId: \"rest.accountId\"\n                companyName: \"rest.companyName\"\n                email: \"rest.email\"\n                phone: \"rest.phone\"\
  \n                address: \"rest.address\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}\n          name: customer-detail\n          description: \"Single customer management\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get details for a specific customer\"\n              call: \"streamone-ion.get-customer\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products\n          description: \"Technology product catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"Browse available technology products\"\n              call: \"streamone-ion.list-products\"\
  \n              with:\n                accountId: \"rest.accountId\"\n                vendor: \"rest.vendor\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Product order management\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List all orders for the account\"\n              call: \"streamone-ion.list-orders\"\n              with:\n                accountId: \"rest.accountId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new technology product order\"\n              call: \"streamone-ion.create-order\"\n              with:\n                accountId:\
  \ \"rest.accountId\"\n                customerId: \"rest.customerId\"\n                items: \"rest.items\"\n                notes: \"rest.notes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{orderId}\n          name: order-detail\n          description: \"Single order management\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get details for a specific order\"\n              call: \"streamone-ion.get-order\"\n              with:\n                accountId: \"rest.accountId\"\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{customerId}/subscriptions\n          name: subscriptions\n          description: \"Customer subscription management\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n\
  \              description: \"List cloud subscriptions for a customer\"\n              call: \"streamone-ion.list-subscriptions\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"rest.customerId\"\n                vendor: \"rest.vendor\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports\n          name: reports\n          description: \"Business intelligence reports\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List available business intelligence reports\"\n              call: \"streamone-ion.list-reports\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports/{reportId}/data\n          name: report-data\n\
  \          description: \"Report data access\"\n          operations:\n            - method: GET\n              name: get-report-data\n              description: \"Access report data\"\n              call: \"streamone-ion.get-report-data\"\n              with:\n                accountId: \"rest.accountId\"\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tdsynnex-cloud-distribution-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TD SYNNEX cloud distribution management.\"\n      tools:\n        - name: list-customers\n          description: \"List all end customers in the TD SYNNEX partner account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.list-customers\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: create-customer\n          description: \"Add a new end customer to the TD SYNNEX StreamOne platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.create-customer\"\n          with:\n            accountId: \"tools.accountId\"\n            companyName: \"tools.companyName\"\n            email: \"tools.email\"\n            phone: \"tools.phone\"\n            address: \"tools.address\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-customer\n          description: \"Get details for a specific end customer including cloud profiles\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-customer\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-products\n          description: \"Browse available technology products in the TD SYNNEX distribution catalog\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.list-products\"\n          with:\n            accountId: \"tools.accountId\"\n            vendor: \"tools.vendor\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product\n          description: \"Get detailed information for a specific technology product including pricing\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"streamone-ion.get-product\"\n          with:\n            accountId: \"tools.accountId\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-orders\n          description: \"List all technology product orders for the partner account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.list-orders\"\n          with:\n            accountId: \"tools.accountId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-order\n          description: \"Create a new technology product order for an end customer\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"streamone-ion.create-order\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n            items: \"tools.items\"\n            notes: \"tools.notes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n\n        - name: get-order\n          description: \"Get status and details for a specific technology product order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-order\"\n          with:\n            accountId: \"tools.accountId\"\n            orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-customer-subscriptions\n          description: \"List all active cloud software subscriptions for a customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.list-subscriptions\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n            vendor: \"tools.vendor\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-reports\n\
  \          description: \"List available business intelligence reports for distribution analytics\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.list-reports\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-report-data\n          description: \"Access business intelligence report data for distribution analytics\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"streamone-ion.get-report-data\"\n          with:\n            accountId: \"tools.accountId\"\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
