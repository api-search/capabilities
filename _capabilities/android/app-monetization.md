---
categories:
- payments
consumed_apis:
- google-play
description: Unified workflow for managing Android app monetization through in-app purchases, subscriptions, reviews, and order management using the Google Play Developer API. Designed for app developers and product managers managing app revenue and user feedback.
layout: capability
name: Android App Monetization and Reviews
operations:
- description: Get product purchase status
  method: GET
  name: get-purchase-product
  path: /v1/purchases/{packageName}/products/{productId}
- description: List subscription products
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions/{packageName}
- description: List app reviews
  method: GET
  name: list-reviews
  path: /v1/reviews/{packageName}
- description: List voided purchases
  method: GET
  name: list-voided-purchases
  path: /v1/voided-purchases/{packageName}
personas: []
provider_name: Android
provider_slug: android
search_terms:
- check subscription purchase validity and expiry
- list cancelled, refunded, or charged-back purchases
- google play
- list all subscription products for an app
- create subscription
- google
- sdk
- subscription products
- subscriptions
- list subscription products
- get product purchase status
- list subscriptions
- wearables
- mobile development
- list reviews
- check in-app product purchase and consumption status
- reviews
- machine learning
- ai
- list user reviews from google play store
- get review
- create a new subscription product
- voided purchases
- automotive
- monetization
- list app reviews
- list voided purchases
- app reviews
- in-app product purchases
- get a specific user review with comments
- get purchase subscription
- android
- get purchase product
- tv
slug: app-monetization
tags:
- Android
- Google Play
- Monetization
- Subscriptions
- Reviews
tools:
- description: Check in-app product purchase and consumption status
  hints:
    readOnly: true
  name: get-purchase-product
- description: Check subscription purchase validity and expiry
  hints:
    readOnly: true
  name: get-purchase-subscription
- description: List all subscription products for an app
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Create a new subscription product
  hints:
    readOnly: false
  name: create-subscription
- description: List user reviews from Google Play Store
  hints:
    openWorld: true
    readOnly: true
  name: list-reviews
- description: Get a specific user review with comments
  hints:
    readOnly: true
  name: get-review
- description: List cancelled, refunded, or charged-back purchases
  hints:
    readOnly: true
  name: list-voided-purchases
---
