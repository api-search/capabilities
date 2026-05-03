---
categories: []
consumed_apis:
- synnex-ion
description: Unified cloud marketplace capability for TD SYNNEX resellers. Combines customer management, product catalog browsing, order creation, subscription lifecycle management, and reporting through the StreamOne ION API. Enables resellers to automate cloud subscription operations for Microsoft, Google, and other vendor products.
layout: capability
name: TD SYNNEX Cloud Marketplace
operations:
- description: List all end customers for the reseller account.
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new end customer account.
  method: POST
  name: create-customer
  path: /v1/customers
- description: Browse available cloud products and SKUs.
  method: GET
  name: list-products
  path: /v1/products
- description: List orders for the reseller account.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new cloud product order for a customer.
  method: POST
  name: create-order
  path: /v1/orders
- description: List cloud subscriptions for an end customer.
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: List available usage and billing reports.
  method: GET
  name: list-reports
  path: /v1/reports
personas: []
provider_name: Synnex
provider_slug: synnex
search_terms:
- technology distribution
- supply chain
- list subscriptions
- create a new cloud product order for a customer.
- create order
- end customer account management.
- list reports
- td synnex
- cloud marketplace
- create a new end customer account.
- subscription management
- it distribution
- create a new cloud product order for an end customer through td synnex.
- list available usage and billing reports.
- browse the td synnex cloud product catalog with filtering by vendor and category.
- list orders for the reseller account.
- fortune 100
- order management
- list cloud product orders for the reseller account.
- order management.
- list customers
- browse available cloud products and skus.
- usage and billing reports.
- list available usage and billing reports for the reseller account.
- list all end customers for the reseller account.
- list cloud subscriptions for an end customer.
- create a new end customer account in the td synnex cloud marketplace.
- list products
- list active cloud subscriptions for an end customer.
- create customer
- list orders
- list end customers managed by the reseller in the td synnex cloud marketplace.
- cloud subscription management.
- cloud product catalog.
slug: cloud-marketplace
source_filename: cloud-marketplace.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"TD SYNNEX Cloud Marketplace\"\n  description: >-\n    Unified cloud marketplace capability for TD SYNNEX resellers. Combines customer\n    management, product catalog browsing, order creation, subscription lifecycle\n    management, and reporting through the StreamOne ION API. Enables resellers to\n    automate cloud subscription operations for Microsoft, Google, and other vendor products.\n  tags:\n    - TD SYNNEX\n    - Cloud Marketplace\n    - Subscription Management\n    - IT Distribution\n    - Order Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SYNNEX_ION_ACCESS_TOKEN: SYNNEX_ION_ACCESS_TOKEN\n      SYNNEX_ACCOUNT_ID: SYNNEX_ACCOUNT_ID\n\ncapability:\n  consumes:\n    - import: synnex-ion\n      location: ./shared/streamone-ion.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: synnex-cloud-marketplace-api\n      description: \"Unified\
  \ REST API for TD SYNNEX cloud marketplace operations.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"End customer account management.\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all end customers for the reseller account.\"\n              call: \"synnex-ion.list-customers\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new end customer account.\"\n              call: \"synnex-ion.create-customer\"\n              with:\n                accountId: \"rest.accountId\"\n                companyName: \"rest.companyName\"\n                email: \"rest.email\"\n                country: \"rest.country\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products\n          description: \"Cloud product catalog.\"\n          operations:\n            - method: GET\n              name: list-products\n              description: \"Browse available cloud products and SKUs.\"\n              call: \"synnex-ion.list-products\"\n              with:\n                accountId: \"rest.accountId\"\n                vendor: \"rest.vendor\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"Order management.\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List orders for the reseller account.\"\n              call: \"synnex-ion.list-orders\"\n              with:\n                accountId: \"rest.accountId\"\
  \n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-order\n              description: \"Create a new cloud product order for a customer.\"\n              call: \"synnex-ion.create-order\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Cloud subscription management.\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List cloud subscriptions for an end customer.\"\n              call: \"synnex-ion.list-subscriptions\"\n              with:\n                accountId: \"rest.accountId\"\n                customerId: \"\
  rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports\n          name: reports\n          description: \"Usage and billing reports.\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List available usage and billing reports.\"\n              call: \"synnex-ion.list-reports\"\n              with:\n                accountId: \"rest.accountId\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: synnex-cloud-marketplace-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud marketplace operations via TD SYNNEX StreamOne ION.\"\n      tools:\n        - name: list-customers\n          description: \"List end customers managed by the reseller in the TD SYNNEX cloud marketplace.\"\
  \n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"synnex-ion.list-customers\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-customer\n          description: \"Create a new end customer account in the TD SYNNEX cloud marketplace.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"synnex-ion.create-customer\"\n          with:\n            accountId: \"tools.accountId\"\n            companyName: \"tools.companyName\"\n            email: \"tools.email\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-products\n          description: \"Browse the TD SYNNEX cloud product catalog with filtering by vendor and\
  \ category.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"synnex-ion.list-products\"\n          with:\n            accountId: \"tools.accountId\"\n            vendor: \"tools.vendor\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-orders\n          description: \"List cloud product orders for the reseller account.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"synnex-ion.list-orders\"\n          with:\n            accountId: \"tools.accountId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-order\n          description: \"Create a new cloud product order for an end customer through TD SYNNEX.\"\n          hints:\n \
  \           readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"synnex-ion.create-order\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-subscriptions\n          description: \"List active cloud subscriptions for an end customer.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"synnex-ion.list-subscriptions\"\n          with:\n            accountId: \"tools.accountId\"\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-reports\n          description: \"List available usage and billing reports for the reseller account.\"\n          hints:\n            readOnly: true\n            destructive:\
  \ false\n            idempotent: true\n          call: \"synnex-ion.list-reports\"\n          with:\n            accountId: \"tools.accountId\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/synnex/refs/heads/main/capabilities/cloud-marketplace.yaml
tags:
- TD SYNNEX
- Cloud Marketplace
- Subscription Management
- IT Distribution
- Order Management
tools:
- description: List end customers managed by the reseller in the TD SYNNEX cloud marketplace.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-customers
- description: Create a new end customer account in the TD SYNNEX cloud marketplace.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: Browse the TD SYNNEX cloud product catalog with filtering by vendor and category.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-products
- description: List cloud product orders for the reseller account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-orders
- description: Create a new cloud product order for an end customer through TD SYNNEX.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: List active cloud subscriptions for an end customer.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: List available usage and billing reports for the reseller account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-reports
---
