---
api_specs:
- filename: shopper-approved-openapi.yml
  format: yaml
  label: shopper-approved
  slug: shopper-approved
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shopper-approved/refs/heads/main/openapi/shopper-approved-openapi.yml
categories: []
consumed_apis:
- shopper-approved
description: Workflow capability for managing customer reviews and ratings through Shopper Approved. Covers review collection via order submission, review retrieval for display, product review management, site statistics for reporting, and review follow-up scheduling for merchants and developers integrating Shopper Approved into their e-commerce platforms.
layout: capability
name: Shopper Approved Review Management
operations:
- description: Get overall site rating, review count, and star distribution
  method: GET
  name: get-site-stats
  path: /v1/stats
- description: List customer reviews with date range and pagination
  method: GET
  name: list-reviews
  path: /v1/reviews
- description: Retrieve a specific customer review
  method: GET
  name: get-review
  path: /v1/reviews/{id}
- description: Reschedule or cancel a review follow-up
  method: PUT
  name: update-review
  path: /v1/reviews/{id}
- description: List product reviews across the catalog
  method: GET
  name: list-product-reviews
  path: /v1/product-reviews
- description: Submit a completed order to trigger review request
  method: POST
  name: submit-order
  path: /v1/orders
personas: []
provider_name: Shopper Approved
provider_slug: shopper-approved
search_terms:
- retrieve a specific customer review
- submit a completed order to trigger review request
- get review
- update review
- list product reviews across the catalog
- list reviews
- get site stats
- ratings
- get overall site rating, review count, and star distribution
- submit order
- individual review management
- list product reviews
- reviews
- submit a completed order to trigger a review collection email at a specified follow-up date
- google seller ratings
- retrieve a specific customer review by its order id
- get overall site review statistics including average rating and count by star level
- order submission for review collection
- list customer reviews with date range and pagination
- list customer site reviews with optional date range filtering and page navigation
- social proof
- update a review's follow-up date or cancel the review request
- product-specific reviews for pdp display
- customer feedback
- reschedule or cancel a review follow-up
- ecommerce
- site review statistics for dashboards and reporting
- list product-level reviews for display on product detail pages
- customer site reviews for display and analysis
slug: review-management
source_filename: review-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shopper Approved Review Management\"\n  description: >-\n    Workflow capability for managing customer reviews and ratings through\n    Shopper Approved. Covers review collection via order submission, review\n    retrieval for display, product review management, site statistics for\n    reporting, and review follow-up scheduling for merchants and developers\n    integrating Shopper Approved into their e-commerce platforms.\n  tags:\n    - Reviews\n    - Ratings\n    - Ecommerce\n    - Customer Feedback\n    - Social Proof\n    - Google Seller Ratings\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHOPPER_APPROVED_SITE_ID: SHOPPER_APPROVED_SITE_ID\n      SHOPPER_APPROVED_TOKEN: SHOPPER_APPROVED_TOKEN\n\ncapability:\n  consumes:\n    - import: shopper-approved\n      location: ./shared/shopper-approved.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ shopper-approved-review-management-api\n      description: \"Unified REST API for Shopper Approved review management workflows.\"\n      resources:\n        - path: /v1/stats\n          name: stats\n          description: Site review statistics for dashboards and reporting\n          operations:\n            - method: GET\n              name: get-site-stats\n              description: Get overall site rating, review count, and star distribution\n              call: \"shopper-approved.get-site-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews\n          name: reviews\n          description: Customer site reviews for display and analysis\n          operations:\n            - method: GET\n              name: list-reviews\n              description: List customer reviews with date range and pagination\n              call: \"shopper-approved.list-reviews\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.\"\n        - path: /v1/reviews/{id}\n          name: review-detail\n          description: Individual review management\n          operations:\n            - method: GET\n              name: get-review\n              description: Retrieve a specific customer review\n              call: \"shopper-approved.get-review\"\n              with:\n                review_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-review\n              description: Reschedule or cancel a review follow-up\n              call: \"shopper-approved.update-review\"\n              with:\n                review_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/product-reviews\n          name: product-reviews\n          description: Product-specific reviews for\
  \ PDP display\n          operations:\n            - method: GET\n              name: list-product-reviews\n              description: List product reviews across the catalog\n              call: \"shopper-approved.list-product-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: Order submission for review collection\n          operations:\n            - method: POST\n              name: submit-order\n              description: Submit a completed order to trigger review request\n              call: \"shopper-approved.submit-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shopper-approved-review-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Shopper Approved review management.\"\n      tools:\n        -\
  \ name: get-site-stats\n          description: Get overall site review statistics including average rating and count by star level\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopper-approved.get-site-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reviews\n          description: List customer site reviews with optional date range filtering and page navigation\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopper-approved.list-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-review\n          description: Retrieve a specific customer review by its order ID\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopper-approved.get-review\"\n          with:\n            review_id: \"tools.review_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-product-reviews\n          description: List product-level reviews for display on product detail pages\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shopper-approved.list-product-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-order\n          description: Submit a completed order to trigger a review collection email at a specified follow-up date\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"shopper-approved.submit-order\"\n          with:\n            orderid: \"tools.orderid\"\n            email: \"tools.email\"\n            name: \"tools.name\"\n            date: \"tools.date\"\n            followup: \"tools.followup\"\n            products: \"tools.products\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: update-review\n          description: Update a review's follow-up date or cancel the review request\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"shopper-approved.update-review\"\n          with:\n            review_id: \"tools.review_id\"\n            followup: \"tools.followup\"\n            cancelled: \"tools.cancelled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shopper-approved/refs/heads/main/capabilities/review-management.yaml
tags:
- Reviews
- Ratings
- Ecommerce
- Customer Feedback
- Social Proof
- Google Seller Ratings
tools:
- description: Get overall site review statistics including average rating and count by star level
  hints:
    openWorld: true
    readOnly: true
  name: get-site-stats
- description: List customer site reviews with optional date range filtering and page navigation
  hints:
    openWorld: true
    readOnly: true
  name: list-reviews
- description: Retrieve a specific customer review by its order ID
  hints:
    openWorld: true
    readOnly: true
  name: get-review
- description: List product-level reviews for display on product detail pages
  hints:
    openWorld: true
    readOnly: true
  name: list-product-reviews
- description: Submit a completed order to trigger a review collection email at a specified follow-up date
  hints:
    destructive: false
    readOnly: false
  name: submit-order
- description: Update a review's follow-up date or cancel the review request
  hints:
    idempotent: true
    readOnly: false
  name: update-review
---
