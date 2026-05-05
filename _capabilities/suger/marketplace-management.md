---
api_specs:
- filename: suger-openapi.yml
  format: yaml
  label: suger
  slug: suger
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/suger/refs/heads/main/openapi/suger-openapi.yml
categories: []
consumed_apis:
- suger
description: Unified workflow capability for ISVs managing cloud marketplace listings, customer entitlements, and revenue reporting across AWS, Azure, GCP, and Snowflake marketplaces via the Suger platform.
layout: capability
name: Suger Cloud Marketplace Management
operations:
- description: List all marketplace products
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new marketplace product
  method: POST
  name: create-product
  path: /v1/products
- description: Get a specific marketplace product
  method: GET
  name: get-product
  path: /v1/products/{productId}
- description: Update a marketplace product
  method: PATCH
  name: update-product
  path: /v1/products/{productId}
- description: Delete a marketplace product
  method: DELETE
  name: delete-product
  path: /v1/products/{productId}
- description: List all marketplace offers
  method: GET
  name: list-offers
  path: /v1/offers
- description: Create a new marketplace offer
  method: POST
  name: create-offer
  path: /v1/offers
- description: Get a specific marketplace offer
  method: GET
  name: get-offer
  path: /v1/offers/{offerId}
- description: Delete a marketplace offer
  method: DELETE
  name: delete-offer
  path: /v1/offers/{offerId}
- description: List all customer entitlements
  method: GET
  name: list-entitlements
  path: /v1/entitlements
- description: Create a new entitlement
  method: POST
  name: create-entitlement
  path: /v1/entitlements
- description: Get a specific entitlement
  method: GET
  name: get-entitlement
  path: /v1/entitlements/{entitlementId}
- description: List all buyers
  method: GET
  name: list-buyers
  path: /v1/buyers
- description: Create a new buyer
  method: POST
  name: create-buyer
  path: /v1/buyers
- description: List all invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: List revenue records for a cloud partner
  method: GET
  name: list-revenue-records
  path: /v1/revenue-records
personas: []
provider_name: Suger
provider_slug: suger
search_terms:
- create a new buyer
- create product
- list all marketplace products
- get a specific cloud marketplace product by id
- saas
- invoice management
- update a marketplace product
- list products
- delete a marketplace product
- get entitlement
- billing
- list offers
- list usage metering record groups for billing
- create a new entitlement
- cloud marketplace product listings
- entitlement
- get a specific marketplace offer by id
- create a new cloud marketplace product listing
- cancel a customer entitlement
- update product
- create offer
- list invoices
- create a new marketplace offer
- list all buyers/customers for an organization
- revenue records
- create a new buyer/customer record
- customer entitlements
- co-sell
- approve entitlement
- list all invoices
- list all invoices for an organization
- create entitlement
- marketplace offers
- individual offer operations
- get a specific customer entitlement by id
- buyer management
- approve a pending customer entitlement
- list usage record groups
- delete product
- list all customer entitlements
- cancel entitlement
- list revenue records for a cloud marketplace partner (aws, azure, gcp)
- get product
- list all buyers
- delete a marketplace offer
- list all marketplace offers for an organization
- list revenue records for a cloud partner
- individual entitlement operations
- list all cloud marketplace products for an organization
- create a new marketplace offer for a product
- gtm
- get offer
- individual product operations
- list entitlements
- create a new marketplace product
- get a specific marketplace product
- list all marketplace offers
- cloud marketplace
- list revenue records
- get a specific entitlement
- delete offer
- create buyer
- list all customer entitlements, optionally filtered by buyer or product
- update an existing cloud marketplace product
- revenue
- list buyers
- get a specific marketplace offer
slug: marketplace-management
source_filename: marketplace-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Suger Cloud Marketplace Management\"\n  description: >-\n    Unified workflow capability for ISVs managing cloud marketplace listings,\n    customer entitlements, and revenue reporting across AWS, Azure, GCP,\n    and Snowflake marketplaces via the Suger platform.\n  tags:\n    - Cloud Marketplace\n    - GTM\n    - SaaS\n    - Billing\n    - Entitlement\n    - Revenue\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SUGER_API_KEY: SUGER_API_KEY\n\ncapability:\n  consumes:\n    - import: suger\n      location: ./shared/suger.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: suger-marketplace-api\n      description: \"Unified REST API for cloud marketplace management.\"\n      resources:\n        - path: /v1/products\n          name: products\n          description: \"Cloud marketplace product listings\"\n          operations:\n            - method: GET\n\
  \              name: list-products\n              description: \"List all marketplace products\"\n              call: \"suger.list-products\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new marketplace product\"\n              call: \"suger.create-product\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products/{productId}\n          name: product\n          description: \"Individual product operations\"\n          operations:\n            - method: GET\n              name: get-product\n              description: \"Get a specific marketplace product\"\n              call: \"suger.get-product\"\n              with:\n                orgId:\
  \ \"rest.orgId\"\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-product\n              description: \"Update a marketplace product\"\n              call: \"suger.update-product\"\n              with:\n                orgId: \"rest.orgId\"\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-product\n              description: \"Delete a marketplace product\"\n              call: \"suger.delete-product\"\n              with:\n                orgId: \"rest.orgId\"\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/offers\n          name: offers\n          description: \"\
  Marketplace offers\"\n          operations:\n            - method: GET\n              name: list-offers\n              description: \"List all marketplace offers\"\n              call: \"suger.list-offers\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-offer\n              description: \"Create a new marketplace offer\"\n              call: \"suger.create-offer\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/offers/{offerId}\n          name: offer\n          description: \"Individual offer operations\"\n          operations:\n            - method: GET\n              name: get-offer\n              description: \"Get a specific marketplace offer\"\n              call: \"suger.get-offer\"\n\
  \              with:\n                orgId: \"rest.orgId\"\n                offerId: \"rest.offerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-offer\n              description: \"Delete a marketplace offer\"\n              call: \"suger.delete-offer\"\n              with:\n                orgId: \"rest.orgId\"\n                offerId: \"rest.offerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entitlements\n          name: entitlements\n          description: \"Customer entitlements\"\n          operations:\n            - method: GET\n              name: list-entitlements\n              description: \"List all customer entitlements\"\n              call: \"suger.list-entitlements\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-entitlement\n              description: \"Create a new entitlement\"\n              call: \"suger.create-entitlement\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/entitlements/{entitlementId}\n          name: entitlement\n          description: \"Individual entitlement operations\"\n          operations:\n            - method: GET\n              name: get-entitlement\n              description: \"Get a specific entitlement\"\n              call: \"suger.get-entitlement\"\n              with:\n                orgId: \"rest.orgId\"\n                entitlementId: \"rest.entitlementId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buyers\n          name: buyers\n          description:\
  \ \"Buyer management\"\n          operations:\n            - method: GET\n              name: list-buyers\n              description: \"List all buyers\"\n              call: \"suger.list-buyers\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-buyer\n              description: \"Create a new buyer\"\n              call: \"suger.create-buyer\"\n              with:\n                orgId: \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List all invoices\"\n              call: \"suger.list-invoices\"\n              with:\n                orgId:\
  \ \"rest.orgId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/revenue-records\n          name: revenue-records\n          description: \"Revenue records\"\n          operations:\n            - method: GET\n              name: list-revenue-records\n              description: \"List revenue records for a cloud partner\"\n              call: \"suger.list-revenue-records\"\n              with:\n                orgId: \"rest.orgId\"\n                partner: \"rest.partner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: suger-marketplace-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud marketplace management.\"\n      tools:\n        - name: list-products\n          description: \"List all cloud marketplace products for an organization\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"suger.list-products\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-product\n          description: \"Get a specific cloud marketplace product by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.get-product\"\n          with:\n            orgId: \"tools.orgId\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-product\n          description: \"Create a new cloud marketplace product listing\"\n          hints:\n            readOnly: false\n          call: \"suger.create-product\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-product\n      \
  \    description: \"Update an existing cloud marketplace product\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"suger.update-product\"\n          with:\n            orgId: \"tools.orgId\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-offers\n          description: \"List all marketplace offers for an organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.list-offers\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-offer\n          description: \"Get a specific marketplace offer by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.get-offer\"\n          with:\n            orgId: \"tools.orgId\"\n      \
  \      offerId: \"tools.offerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-offer\n          description: \"Create a new marketplace offer for a product\"\n          hints:\n            readOnly: false\n          call: \"suger.create-offer\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-entitlements\n          description: \"List all customer entitlements, optionally filtered by buyer or product\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.list-entitlements\"\n          with:\n            orgId: \"tools.orgId\"\n            buyerId: \"tools.buyerId\"\n            productId: \"tools.productId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-entitlement\n          description: \"Get a specific\
  \ customer entitlement by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.get-entitlement\"\n          with:\n            orgId: \"tools.orgId\"\n            entitlementId: \"tools.entitlementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: approve-entitlement\n          description: \"Approve a pending customer entitlement\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"suger.approve-entitlement\"\n          with:\n            orgId: \"tools.orgId\"\n            entitlementId: \"tools.entitlementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-entitlement\n          description: \"Cancel a customer entitlement\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"suger.cancel-entitlement\"\n          with:\n\
  \            orgId: \"tools.orgId\"\n            entitlementId: \"tools.entitlementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-buyers\n          description: \"List all buyers/customers for an organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.list-buyers\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-buyer\n          description: \"Create a new buyer/customer record\"\n          hints:\n            readOnly: false\n          call: \"suger.create-buyer\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List all invoices for an organization\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"suger.list-invoices\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-revenue-records\n          description: \"List revenue records for a cloud marketplace partner (aws, azure, gcp)\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.list-revenue-records\"\n          with:\n            orgId: \"tools.orgId\"\n            partner: \"tools.partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-usage-record-groups\n          description: \"List usage metering record groups for billing\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"suger.list-usage-record-groups\"\n          with:\n            orgId: \"tools.orgId\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/suger/refs/heads/main/capabilities/marketplace-management.yaml
tags:
- Cloud Marketplace
- GTM
- SaaS
- Billing
- Entitlement
- Revenue
tools:
- description: List all cloud marketplace products for an organization
  hints:
    idempotent: true
    readOnly: true
  name: list-products
- description: Get a specific cloud marketplace product by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-product
- description: Create a new cloud marketplace product listing
  hints:
    readOnly: false
  name: create-product
- description: Update an existing cloud marketplace product
  hints:
    idempotent: true
    readOnly: false
  name: update-product
- description: List all marketplace offers for an organization
  hints:
    idempotent: true
    readOnly: true
  name: list-offers
- description: Get a specific marketplace offer by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-offer
- description: Create a new marketplace offer for a product
  hints:
    readOnly: false
  name: create-offer
- description: List all customer entitlements, optionally filtered by buyer or product
  hints:
    idempotent: true
    readOnly: true
  name: list-entitlements
- description: Get a specific customer entitlement by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-entitlement
- description: Approve a pending customer entitlement
  hints:
    idempotent: true
    readOnly: false
  name: approve-entitlement
- description: Cancel a customer entitlement
  hints:
    destructive: true
    readOnly: false
  name: cancel-entitlement
- description: List all buyers/customers for an organization
  hints:
    idempotent: true
    readOnly: true
  name: list-buyers
- description: Create a new buyer/customer record
  hints:
    readOnly: false
  name: create-buyer
- description: List all invoices for an organization
  hints:
    idempotent: true
    readOnly: true
  name: list-invoices
- description: List revenue records for a cloud marketplace partner (aws, azure, gcp)
  hints:
    idempotent: true
    readOnly: true
  name: list-revenue-records
- description: List usage metering record groups for billing
  hints:
    idempotent: true
    readOnly: true
  name: list-usage-record-groups
---
