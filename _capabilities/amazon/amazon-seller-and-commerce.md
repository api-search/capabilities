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
- payment refund processing.
- advertising list campaigns
- amazon
- campaign management and performance reporting
- marketplace
- pay create charge
- create a payment charge via amazon pay.
- process a payment refund.
- pay create refund
- processes payments and refunds via amazon pay.
- advertising
- get marketplace orders.
- list amazon advertising campaigns across all campaign types.
- manages product listings, orders, and inventory on amazon marketplace.
- alexa
- list campaigns
- Advertiser
- create or update a product listing on amazon.
- amazon pay checkout sessions.
- checkout session and payment processing
- product catalog search.
- pay create checkout session
- selling partner get orders
- create a new amazon advertising campaign.
- create refund
- creates and optimizes amazon advertising campaigns.
- get orders
- process a refund for an amazon pay charge.
- product listings, catalog, and order management
- Merchant
- advertising campaign management.
- advertising request report
- search amazon product catalog.
- payments
- create campaign
- search the amazon product catalog by keywords.
- selling partner put listing
- advertising create campaign
- unified workflow for amazon sellers, advertisers, and merchants covering marketplace listings, orders, advertising campaigns, and payment processing.
- create a checkout session.
- search catalog
- create an advertising campaign.
- voice
- Amazon Seller
- create a new amazon pay checkout session for payment processing.
- request an advertising performance report.
- get amazon marketplace orders with filters by marketplace and date range.
- marketplace order management.
- e-commerce
- create checkout session
- list advertising campaigns.
- selling partner search catalog
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
