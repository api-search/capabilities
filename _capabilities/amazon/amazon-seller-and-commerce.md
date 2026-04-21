---
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
- creates and optimizes amazon advertising campaigns.
- manages product listings, orders, and inventory on amazon marketplace.
- selling partner search catalog
- unified workflow for amazon sellers, advertisers, and merchants covering marketplace listings, orders, advertising campaigns, and payment processing.
- Merchant
- pay create checkout session
- search amazon product catalog.
- product listings, catalog, and order management
- payments
- search catalog
- create refund
- selling partner get orders
- create a payment charge via amazon pay.
- process a refund for an amazon pay charge.
- create checkout session
- campaign management and performance reporting
- process a payment refund.
- create an advertising campaign.
- marketplace
- processes payments and refunds via amazon pay.
- get marketplace orders.
- alexa
- search the amazon product catalog by keywords.
- create or update a product listing on amazon.
- pay create charge
- amazon
- advertising list campaigns
- payment refund processing.
- amazon pay checkout sessions.
- list advertising campaigns.
- Amazon Seller
- advertising request report
- list amazon advertising campaigns across all campaign types.
- product catalog search.
- create a new amazon advertising campaign.
- advertising
- Advertiser
- request an advertising performance report.
- voice
- e-commerce
- pay create refund
- marketplace order management.
- list campaigns
- create campaign
- get orders
- create a new amazon pay checkout session for payment processing.
- selling partner put listing
- advertising campaign management.
- get amazon marketplace orders with filters by marketplace and date range.
- create a checkout session.
- checkout session and payment processing
- advertising create campaign
slug: amazon-seller-and-commerce
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
