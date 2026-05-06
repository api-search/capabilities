---
categories:
- payments
consumed_apis: []
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
- check in-app product purchase and consumption status
- list user reviews from google play store
- app reviews
- list cancelled, refunded, or charged-back purchases
- create a new subscription product
- get review
- subscription products
- wearables
- tv
- create subscription
- google play
- voided purchases
- google
- check subscription purchase validity and expiry
- list subscription products
- get a specific user review with comments
- ai
- list voided purchases
- list subscriptions
- in-app product purchases
- automotive
- list all subscription products for an app
- mobile development
- sdk
- monetization
- machine learning
- get product purchase status
- get purchase subscription
- list app reviews
- subscriptions
- list reviews
- android
- get purchase product
- reviews
slug: app-monetization
source_filename: app-monetization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Android App Monetization and Reviews\n  description: Unified workflow for managing Android app monetization through in-app purchases, subscriptions, reviews, and\n    order management using the Google Play Developer API. Designed for app developers and product managers managing app revenue\n    and user feedback.\n  tags:\n  - Android\n  - Google Play\n  - Monetization\n  - Subscriptions\n  - Reviews\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_PLAY_OAUTH_TOKEN: GOOGLE_PLAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: google-play\n    baseUri: https://androidpublisher.googleapis.com/androidpublisher/v3\n    description: Google Play Developer API v3\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_PLAY_OAUTH_TOKEN}}'\n    resources:\n    - name: product-purchases\n      path: /applications/{packageName}/purchases/products/{productId}/tokens/{token}\n\
  \      description: In-app product purchases\n      operations:\n      - name: get-purchase-product\n        method: GET\n        description: Get in-app product purchase status\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product ID\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: Purchase token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscription-purchases\n      path: /applications/{packageName}/purchases/subscriptions/{subscriptionId}/tokens/{token}\n      description: Subscription purchases\n      operations:\n      - name: get-purchase-subscription\n        method: GET\n\
  \        description: Get subscription purchase status\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: Purchase token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /applications/{packageName}/monetization/subscriptions\n      description: Subscription products\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List subscription products\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n         \
  \ required: true\n          description: Application package name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscription\n        method: POST\n        description: Create a subscription product\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reviews\n      path: /applications/{packageName}/reviews\n      description: App reviews\n      operations:\n      - name: list-reviews\n        method: GET\n        description: List app reviews\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: review-details\n      path: /applications/{packageName}/reviews/{reviewId}\n      description: Review details\n      operations:\n      - name: get-review\n        method: GET\n        description: Get a single review\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        - name: reviewId\n          in: path\n          type: string\n          required: true\n          description: Review ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: voided-purchases\n      path: /applications/{packageName}/purchases/voidedpurchases\n      description: Voided purchases\n      operations:\n      - name: list-voided-purchases\n        method: GET\n        description: List\
  \ voided purchases\n        inputParameters:\n        - name: packageName\n          in: path\n          type: string\n          required: true\n          description: Application package name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: monetization-api\n    description: Unified REST API for Android app monetization and review management.\n    resources:\n    - path: /v1/purchases/{packageName}/products/{productId}\n      name: product-purchases\n      description: In-app product purchases\n      operations:\n      - method: GET\n        name: get-purchase-product\n        description: Get product purchase status\n        call: google-play.get-purchase-product\n        with:\n          packageName: rest.packageName\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions/{packageName}\n\
  \      name: subscriptions\n      description: Subscription products\n      operations:\n      - method: GET\n        name: list-subscriptions\n        description: List subscription products\n        call: google-play.list-subscriptions\n        with:\n          packageName: rest.packageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reviews/{packageName}\n      name: reviews\n      description: App reviews\n      operations:\n      - method: GET\n        name: list-reviews\n        description: List app reviews\n        call: google-play.list-reviews\n        with:\n          packageName: rest.packageName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/voided-purchases/{packageName}\n      name: voided-purchases\n      description: Voided purchases\n      operations:\n      - method: GET\n        name: list-voided-purchases\n        description: List voided purchases\n        call: google-play.list-voided-purchases\n\
  \        with:\n          packageName: rest.packageName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: monetization-mcp\n    transport: http\n    description: MCP server for AI-assisted Android app monetization and review management.\n    tools:\n    - name: get-purchase-product\n      description: Check in-app product purchase and consumption status\n      hints:\n        readOnly: true\n      call: google-play.get-purchase-product\n      with:\n        packageName: tools.packageName\n        productId: tools.productId\n        token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-purchase-subscription\n      description: Check subscription purchase validity and expiry\n      hints:\n        readOnly: true\n      call: google-play.get-purchase-subscription\n      with:\n        packageName: tools.packageName\n        subscriptionId: tools.subscriptionId\n       \
  \ token: tools.token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-subscriptions\n      description: List all subscription products for an app\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-play.list-subscriptions\n      with:\n        packageName: tools.packageName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a new subscription product\n      hints:\n        readOnly: false\n      call: google-play.create-subscription\n      with:\n        packageName: tools.packageName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reviews\n      description: List user reviews from Google Play Store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-play.list-reviews\n      with:\n        packageName: tools.packageName\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: get-review\n      description: Get a specific user review with comments\n      hints:\n        readOnly: true\n      call: google-play.get-review\n      with:\n        packageName: tools.packageName\n        reviewId: tools.reviewId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-voided-purchases\n      description: List cancelled, refunded, or charged-back purchases\n      hints:\n        readOnly: true\n      call: google-play.list-voided-purchases\n      with:\n        packageName: tools.packageName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
