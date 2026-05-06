---
categories:
- payments
consumed_apis: []
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
- marketplace
- process a refund for an amazon pay charge.
- search the amazon product catalog by keywords.
- alexa
- get marketplace orders.
- create a payment charge via amazon pay.
- amazon
- checkout session and payment processing
- Merchant
- search catalog
- process a payment refund.
- amazon pay checkout sessions.
- selling partner search catalog
- create a new amazon advertising campaign.
- voice
- advertising request report
- e-commerce
- get amazon marketplace orders with filters by marketplace and date range.
- create checkout session
- list campaigns
- create a checkout session.
- request an advertising performance report.
- advertising campaign management.
- create refund
- advertising list campaigns
- campaign management and performance reporting
- advertising
- Advertiser
- marketplace order management.
- product catalog search.
- manages product listings, orders, and inventory on amazon marketplace.
- creates and optimizes amazon advertising campaigns.
- create or update a product listing on amazon.
- pay create charge
- Amazon Seller
- list advertising campaigns.
- payments
- search amazon product catalog.
- product listings, catalog, and order management
- processes payments and refunds via amazon pay.
- selling partner put listing
- create a new amazon pay checkout session for payment processing.
- create an advertising campaign.
- list amazon advertising campaigns across all campaign types.
- selling partner get orders
- unified workflow for amazon sellers, advertisers, and merchants covering marketplace listings, orders, advertising campaigns, and payment processing.
- advertising create campaign
- create campaign
- get orders
- pay create refund
- pay create checkout session
- payment refund processing.
slug: amazon-seller-and-commerce
source_filename: amazon-seller-and-commerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Seller and Commerce Workflow\n  description: Unified workflow for Amazon sellers, advertisers, and merchants to manage marketplace listings and orders,\n    run advertising campaigns, and process payments using Amazon Selling Partner API, Amazon Advertising API, and Amazon Pay\n    API.\n  tags:\n  - Amazon\n  - E-Commerce\n  - Marketplace\n  - Advertising\n  - Payments\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SP_API_ACCESS_TOKEN: SP_API_ACCESS_TOKEN\n    SP_API_REGION: SP_API_REGION\n    AMAZON_ADS_ACCESS_TOKEN: AMAZON_ADS_ACCESS_TOKEN\n    AMAZON_ADS_CLIENT_ID: AMAZON_ADS_CLIENT_ID\n    AMAZON_PAY_PUBLIC_KEY_ID: AMAZON_PAY_PUBLIC_KEY_ID\n    AMAZON_PAY_PRIVATE_KEY: AMAZON_PAY_PRIVATE_KEY\n    AMAZON_PAY_MERCHANT_ID: AMAZON_PAY_MERCHANT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: selling-partner\n    baseUri: https://sellingpartnerapi-na.amazon.com\n    description:\
  \ Amazon SP-API for marketplace seller operations.\n    authentication:\n      type: bearer\n      token: '{{SP_API_ACCESS_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders/v0/orders\n      description: Manage marketplace orders.\n      operations:\n      - name: get-orders\n        method: GET\n        description: Get orders based on filters.\n        inputParameters:\n        - name: MarketplaceIds\n          in: query\n          type: string\n          required: true\n          description: Marketplace IDs to filter orders.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog-items\n      path: /catalog/2022-04-01/items\n      description: Search and retrieve catalog items.\n      operations:\n      - name: search-catalog-items\n        method: GET\n        description: Search Amazon catalog for items.\n        inputParameters:\n        - name: keywords\n          in: query\n\
  \          type: string\n          required: false\n          description: Search keywords.\n        - name: marketplaceIds\n          in: query\n          type: string\n          required: true\n          description: Marketplace IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listings\n      path: /listings/2021-08-01/items/{sellerId}\n      description: Manage product listings.\n      operations:\n      - name: put-listings-item\n        method: PUT\n        description: Create or update a product listing.\n        inputParameters:\n        - name: sellerId\n          in: path\n          type: string\n          required: true\n          description: Seller identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            productType: '{{tools.product_type}}'\n\
  \  - type: http\n    namespace: advertising\n    baseUri: https://advertising-api.amazon.com\n    description: Amazon Advertising API for campaign management.\n    authentication:\n      type: bearer\n      token: '{{AMAZON_ADS_ACCESS_TOKEN}}'\n    resources:\n    - name: campaigns\n      path: /v2/campaigns\n      description: Manage advertising campaigns.\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List advertising campaigns.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-campaign\n        method: POST\n        description: Create a new advertising campaign.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.campaign_name}}'\n            campaignType: '{{tools.campaign_type}}'\n  \
  \  - name: ad-groups\n      path: /v2/adGroups\n      description: Manage ad groups within campaigns.\n      operations:\n      - name: list-ad-groups\n        method: GET\n        description: List ad groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v2/reports\n      description: Request advertising performance reports.\n      operations:\n      - name: request-report\n        method: POST\n        description: Request an advertising report.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: pay\n    baseUri: https://pay-api.amazon.com\n    description: Amazon Pay REST API for payment processing.\n    authentication:\n      type: bearer\n      token: '{{AMAZON_PAY_PUBLIC_KEY_ID}}'\n    resources:\n    - name: checkout-sessions\n      path: /live/v2/checkoutSessions\n\
  \      description: Manage Amazon Pay checkout sessions.\n      operations:\n      - name: create-checkout-session\n        method: POST\n        description: Create a new checkout session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            storeId: '{{tools.store_id}}'\n      - name: get-checkout-session\n        method: GET\n        description: Get checkout session details.\n        inputParameters:\n        - name: checkoutSessionId\n          in: path\n          type: string\n          required: true\n          description: Checkout session ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charges\n      path: /live/v2/charges\n      description: Manage payment charges.\n      operations:\n      - name: create-charge\n        method: POST\n       \
  \ description: Create a payment charge.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refunds\n      path: /live/v2/refunds\n      description: Process payment refunds.\n      operations:\n      - name: create-refund\n        method: POST\n        description: Create a refund for a charge.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-commerce-api\n    description: Unified REST API for Amazon seller, advertising, and payment operations.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Marketplace order management.\n      operations:\n      - method: GET\n        name: get-orders\n        description: Get marketplace orders.\n        call: selling-partner.get-orders\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Product catalog search.\n      operations:\n      - method: GET\n        name: search-catalog\n        description: Search Amazon product catalog.\n        call: selling-partner.search-catalog-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/campaigns\n      name: campaigns\n      description: Advertising campaign management.\n      operations:\n      - method: GET\n        name: list-campaigns\n        description: List advertising campaigns.\n        call: advertising.list-campaigns\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-campaign\n        description: Create an advertising campaign.\n        call: advertising.create-campaign\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/checkout-sessions\n      name: checkout-sessions\n      description:\
  \ Amazon Pay checkout sessions.\n      operations:\n      - method: POST\n        name: create-checkout-session\n        description: Create a checkout session.\n        call: pay.create-checkout-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/refunds\n      name: refunds\n      description: Payment refund processing.\n      operations:\n      - method: POST\n        name: create-refund\n        description: Process a payment refund.\n        call: pay.create-refund\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-commerce-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon seller, advertising, and commerce operations.\n    tools:\n    - name: selling-partner-get-orders\n      description: Get Amazon marketplace orders with filters by marketplace and date range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ selling-partner.get-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: selling-partner-search-catalog\n      description: Search the Amazon product catalog by keywords.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: selling-partner.search-catalog-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: selling-partner-put-listing\n      description: Create or update a product listing on Amazon.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: selling-partner.put-listings-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: advertising-list-campaigns\n      description: List Amazon advertising campaigns across all campaign types.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: advertising.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n  \
  \  - name: advertising-create-campaign\n      description: Create a new Amazon advertising campaign.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advertising.create-campaign\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: advertising-request-report\n      description: Request an advertising performance report.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advertising.request-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-create-checkout-session\n      description: Create a new Amazon Pay checkout session for payment processing.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pay.create-checkout-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-create-charge\n      description: Create a payment\
  \ charge via Amazon Pay.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pay.create-charge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-create-refund\n      description: Process a refund for an Amazon Pay charge.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pay.create-refund\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
