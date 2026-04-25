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
- Merchant
- pay create refund
- process a refund for an amazon pay charge.
- create a payment charge via amazon pay.
- create checkout session
- create a new amazon advertising campaign.
- create a new amazon pay checkout session for payment processing.
- selling partner get orders
- processes payments and refunds via amazon pay.
- list amazon advertising campaigns across all campaign types.
- create an advertising campaign.
- advertising list campaigns
- create a checkout session.
- selling partner search catalog
- list campaigns
- get orders
- pay create charge
- campaign management and performance reporting
- alexa
- search the amazon product catalog by keywords.
- product listings, catalog, and order management
- voice
- request an advertising performance report.
- advertising campaign management.
- create campaign
- Advertiser
- advertising create campaign
- marketplace
- checkout session and payment processing
- payments
- Amazon Seller
- amazon pay checkout sessions.
- advertising
- get marketplace orders.
- marketplace order management.
- e-commerce
- get amazon marketplace orders with filters by marketplace and date range.
- process a payment refund.
- manages product listings, orders, and inventory on amazon marketplace.
- search amazon product catalog.
- search catalog
- pay create checkout session
- creates and optimizes amazon advertising campaigns.
- payment refund processing.
- unified workflow for amazon sellers, advertisers, and merchants covering marketplace listings, orders, advertising campaigns, and payment processing.
- create refund
- create or update a product listing on amazon.
- amazon
- selling partner put listing
- list advertising campaigns.
- advertising request report
- product catalog search.
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
