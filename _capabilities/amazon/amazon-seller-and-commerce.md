---
categories:
- payments
consumed_apis:
- selling-partner
- advertising
- pay
description: Unified workflow for Amazon sellers, advertisers, and merchants to manage marketplace listings and orders, run advertising campaigns, and process payments using Amazon Selling Partner API, Amazon Advertising API, and Amazon Pay API.
layout: capability
name: Amazon Seller and Commerce Workflow
operations:
- description: Get marketplace orders.
  method: GET
  name: get-orders
  path: /v1/orders
- description: Search Amazon product catalog.
  method: GET
  name: search-catalog
  path: /v1/catalog
- description: List advertising campaigns.
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create an advertising campaign.
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: Create a checkout session.
  method: POST
  name: create-checkout-session
  path: /v1/checkout-sessions
- description: Process a payment refund.
  method: POST
  name: create-refund
  path: /v1/refunds
personas: []
provider_name: Amazon
provider_slug: amazon
search_terms:
- create a new amazon pay checkout session for payment processing.
- Advertiser
- search the amazon product catalog by keywords.
- pay create checkout session
- create or update a product listing on amazon.
- advertising create campaign
- advertising
- create a checkout session.
- Merchant
- list advertising campaigns.
- selling partner put listing
- unified workflow for amazon sellers, advertisers, and merchants covering marketplace listings, orders, advertising campaigns, and payment processing.
- process a refund for an amazon pay charge.
- create an advertising campaign.
- e-commerce
- get amazon marketplace orders with filters by marketplace and date range.
- create a new amazon advertising campaign.
- pay create charge
- processes payments and refunds via amazon pay.
- request an advertising performance report.
- payments
- campaign management and performance reporting
- Amazon Seller
- product listings, catalog, and order management
- marketplace
- selling partner get orders
- search catalog
- create campaign
- list amazon advertising campaigns across all campaign types.
- create a payment charge via amazon pay.
- alexa
- payment refund processing.
- voice
- amazon pay checkout sessions.
- marketplace order management.
- checkout session and payment processing
- create checkout session
- amazon
- search amazon product catalog.
- pay create refund
- get orders
- create refund
- process a payment refund.
- product catalog search.
- advertising campaign management.
- advertising request report
- creates and optimizes amazon advertising campaigns.
- manages product listings, orders, and inventory on amazon marketplace.
- selling partner search catalog
- list campaigns
- advertising list campaigns
- get marketplace orders.
slug: amazon-seller-and-commerce
source_filename: amazon-seller-and-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Seller and Commerce Workflow\"\n  description: >-\n    Unified workflow for Amazon sellers, advertisers, and merchants to manage\n    marketplace listings and orders, run advertising campaigns, and process\n    payments using Amazon Selling Partner API, Amazon Advertising API, and\n    Amazon Pay API.\n  tags:\n    - Amazon\n    - E-Commerce\n    - Marketplace\n    - Advertising\n    - Payments\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      SP_API_ACCESS_TOKEN: SP_API_ACCESS_TOKEN\n      SP_API_REGION: SP_API_REGION\n      AMAZON_ADS_ACCESS_TOKEN: AMAZON_ADS_ACCESS_TOKEN\n      AMAZON_ADS_CLIENT_ID: AMAZON_ADS_CLIENT_ID\n      AMAZON_PAY_PUBLIC_KEY_ID: AMAZON_PAY_PUBLIC_KEY_ID\n      AMAZON_PAY_PRIVATE_KEY: AMAZON_PAY_PRIVATE_KEY\n      AMAZON_PAY_MERCHANT_ID: AMAZON_PAY_MERCHANT_ID\n\ncapability:\n  consumes:\n    - import: selling-partner\n      location: ./shared/selling-partner-api.yaml\n\
  \    - import: advertising\n      location: ./shared/advertising-api.yaml\n    - import: pay\n      location: ./shared/pay-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: amazon-commerce-api\n      description: \"Unified REST API for Amazon seller, advertising, and payment operations.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: \"Marketplace order management.\"\n          operations:\n            - method: GET\n              name: get-orders\n              description: \"Get marketplace orders.\"\n              call: \"selling-partner.get-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/catalog\n          name: catalog\n          description: \"Product catalog search.\"\n          operations:\n            - method: GET\n              name: search-catalog\n              description: \"Search Amazon product catalog.\"\n        \
  \      call: \"selling-partner.search-catalog-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/campaigns\n          name: campaigns\n          description: \"Advertising campaign management.\"\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: \"List advertising campaigns.\"\n              call: \"advertising.list-campaigns\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: \"Create an advertising campaign.\"\n              call: \"advertising.create-campaign\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/checkout-sessions\n          name: checkout-sessions\n          description: \"Amazon Pay checkout sessions.\"\n          operations:\n\
  \            - method: POST\n              name: create-checkout-session\n              description: \"Create a checkout session.\"\n              call: \"pay.create-checkout-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/refunds\n          name: refunds\n          description: \"Payment refund processing.\"\n          operations:\n            - method: POST\n              name: create-refund\n              description: \"Process a payment refund.\"\n              call: \"pay.create-refund\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: amazon-commerce-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon seller, advertising, and commerce operations.\"\n      tools:\n        - name: selling-partner-get-orders\n          description: \"Get Amazon marketplace orders with\
  \ filters by marketplace and date range.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"selling-partner.get-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: selling-partner-search-catalog\n          description: \"Search the Amazon product catalog by keywords.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"selling-partner.search-catalog-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: selling-partner-put-listing\n          description: \"Create or update a product listing on Amazon.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"selling-partner.put-listings-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: advertising-list-campaigns\n\
  \          description: \"List Amazon advertising campaigns across all campaign types.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"advertising.list-campaigns\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: advertising-create-campaign\n          description: \"Create a new Amazon advertising campaign.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"advertising.create-campaign\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: advertising-request-report\n          description: \"Request an advertising performance report.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"advertising.request-report\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: pay-create-checkout-session\n          description: \"Create a new Amazon Pay checkout session for payment processing.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pay.create-checkout-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pay-create-charge\n          description: \"Create a payment charge via Amazon Pay.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pay.create-charge\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pay-create-refund\n          description: \"Process a refund for an Amazon Pay charge.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"pay.create-refund\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon/refs/heads/main/capabilities/amazon-seller-and-commerce.yaml
tags:
- Amazon
- E-Commerce
- Marketplace
- Advertising
- Payments
tools:
- description: Get Amazon marketplace orders with filters by marketplace and date range.
  hints:
    openWorld: true
    readOnly: true
  name: selling-partner-get-orders
- description: Search the Amazon product catalog by keywords.
  hints:
    openWorld: true
    readOnly: true
  name: selling-partner-search-catalog
- description: Create or update a product listing on Amazon.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: selling-partner-put-listing
- description: List Amazon advertising campaigns across all campaign types.
  hints:
    openWorld: true
    readOnly: true
  name: advertising-list-campaigns
- description: Create a new Amazon advertising campaign.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: advertising-create-campaign
- description: Request an advertising performance report.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: advertising-request-report
- description: Create a new Amazon Pay checkout session for payment processing.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pay-create-checkout-session
- description: Create a payment charge via Amazon Pay.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pay-create-charge
- description: Process a refund for an Amazon Pay charge.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pay-create-refund
---
