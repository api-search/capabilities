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
- google
- get purchase subscription
- list reviews
- list all subscription products for an app
- monetization
- list user reviews from google play store
- get purchase product
- google play
- wearables
- list cancelled, refunded, or charged-back purchases
- android
- list voided purchases
- subscription products
- ai
- create a new subscription product
- voided purchases
- tv
- reviews
- machine learning
- check subscription purchase validity and expiry
- get review
- mobile development
- list subscription products
- create subscription
- app reviews
- subscriptions
- list app reviews
- check in-app product purchase and consumption status
- sdk
- get a specific user review with comments
- in-app product purchases
- automotive
- get product purchase status
- list subscriptions
slug: app-monetization
source_filename: app-monetization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Android App Monetization and Reviews\"\n  description: \"Unified workflow for managing Android app monetization through in-app purchases, subscriptions, reviews, and order management using the Google Play Developer API. Designed for app developers and product managers managing app revenue and user feedback.\"\n  tags:\n    - Android\n    - Google Play\n    - Monetization\n    - Subscriptions\n    - Reviews\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_PLAY_OAUTH_TOKEN: GOOGLE_PLAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: google-play\n      location: ./shared/google-play-developer.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: monetization-api\n      description: \"Unified REST API for Android app monetization and review management.\"\n      resources:\n        - path: /v1/purchases/{packageName}/products/{productId}\n       \
  \   name: product-purchases\n          description: \"In-app product purchases\"\n          operations:\n            - method: GET\n              name: get-purchase-product\n              description: \"Get product purchase status\"\n              call: \"google-play.get-purchase-product\"\n              with:\n                packageName: \"rest.packageName\"\n                productId: \"rest.productId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions/{packageName}\n          name: subscriptions\n          description: \"Subscription products\"\n          operations:\n            - method: GET\n              name: list-subscriptions\n              description: \"List subscription products\"\n              call: \"google-play.list-subscriptions\"\n              with:\n                packageName: \"rest.packageName\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n        - path: /v1/reviews/{packageName}\n          name: reviews\n          description: \"App reviews\"\n          operations:\n            - method: GET\n              name: list-reviews\n              description: \"List app reviews\"\n              call: \"google-play.list-reviews\"\n              with:\n                packageName: \"rest.packageName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/voided-purchases/{packageName}\n          name: voided-purchases\n          description: \"Voided purchases\"\n          operations:\n            - method: GET\n              name: list-voided-purchases\n              description: \"List voided purchases\"\n              call: \"google-play.list-voided-purchases\"\n              with:\n                packageName: \"rest.packageName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    -\
  \ type: mcp\n      port: 9090\n      namespace: monetization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Android app monetization and review management.\"\n      tools:\n        - name: get-purchase-product\n          description: \"Check in-app product purchase and consumption status\"\n          hints:\n            readOnly: true\n          call: \"google-play.get-purchase-product\"\n          with:\n            packageName: \"tools.packageName\"\n            productId: \"tools.productId\"\n            token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-purchase-subscription\n          description: \"Check subscription purchase validity and expiry\"\n          hints:\n            readOnly: true\n          call: \"google-play.get-purchase-subscription\"\n          with:\n            packageName: \"tools.packageName\"\n            subscriptionId: \"tools.subscriptionId\"\n  \
  \          token: \"tools.token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: \"List all subscription products for an app\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-play.list-subscriptions\"\n          with:\n            packageName: \"tools.packageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscription\n          description: \"Create a new subscription product\"\n          hints:\n            readOnly: false\n          call: \"google-play.create-subscription\"\n          with:\n            packageName: \"tools.packageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reviews\n          description: \"List user reviews from Google Play Store\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"google-play.list-reviews\"\n          with:\n            packageName: \"tools.packageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-review\n          description: \"Get a specific user review with comments\"\n          hints:\n            readOnly: true\n          call: \"google-play.get-review\"\n          with:\n            packageName: \"tools.packageName\"\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-voided-purchases\n          description: \"List cancelled, refunded, or charged-back purchases\"\n          hints:\n            readOnly: true\n          call: \"google-play.list-voided-purchases\"\n          with:\n            packageName: \"tools.packageName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/android/refs/heads/main/capabilities/app-monetization.yaml
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
