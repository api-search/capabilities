---
categories: []
consumed_apis: []
description: Unified workflow for loyalty managers and marketing teams to manage loyalty programs, personalized offers, rewards, benefits, and the Priceless experiences platform.
layout: capability
name: Mastercard Loyalty and Offers
operations:
- description: List available loyalty promotions
  method: GET
  name: list-promotions
  path: /v1/promotions
- description: Get personalized offers for a cardholder
  method: POST
  name: get-personalized-offers
  path: /v1/offers
- description: List Priceless experiences
  method: GET
  name: list-experiences
  path: /v1/experiences
- description: Check cardholder benefit eligibility
  method: POST
  name: check-eligibility
  path: /v1/eligibility
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- list promotions
- loyalty promotions
- fraud detection
- get points balance
- enroll a cardholder in a loyalty promotion
- get personalized offers
- list priceless experiences
- create a loyalty program user
- pay with rewards
- get loyalty user details
- list experiences
- loyalty
- check cardholder benefit eligibility
- allocate benefit
- activate an offer for a cardholder
- create a charitable donation
- financial services
- get personalized merchant offers for a cardholder
- check eligibility
- create loyalty user
- get merchant offer content
- list available priceless experiences
- priceless
- credit cards
- submit insurance claim
- priceless experiences
- offers
- digital identity
- open banking
- get loyalty points balance
- get personalized offers for a cardholder
- allocate a benefit to a cardholder
- mastercard
- get merchant offer content and promotional materials
- list available loyalty promotions
- payments
- benefit eligibility checks
- get loyalty user
- submit a loyalty insurance claim
- rewards
- create donation
- personalized offers
- enroll in promotion
- check benefit eligibility
- apply loyalty rewards as payment
- check cardholder benefit eligibility by pan
- activate offer
slug: loyalty-and-offers
source_filename: loyalty-and-offers.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Loyalty and Offers\n  description: Unified workflow for loyalty managers and marketing teams to manage loyalty programs, personalized offers,\n    rewards, benefits, and the Priceless experiences platform.\n  tags:\n  - Mastercard\n  - Loyalty\n  - Offers\n  - Rewards\n  - Priceless\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: loyalty-promotions\n    baseUri: https://api.mastercard.com/loyalty/promotions\n    description: Mastercard Loyalty Promotions API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: promotions\n      path: /promotions\n      description: Loyalty promotion management\n      operations:\n\
  \      - name: list-promotions\n        method: GET\n        description: List available loyalty promotions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enroll-promotion\n        method: POST\n        description: Enroll a cardholder in a promotion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            enrollment: '{{tools.enrollment}}'\n  - type: http\n    namespace: loyalty-user-mgmt\n    baseUri: https://api.mastercard.com/loyalty/users\n    description: Mastercard Loyalty User Management API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: users\n      path: /users\n      description: Loyalty user management\n      operations:\n    \
  \  - name: create-user\n        method: POST\n        description: Create a loyalty program user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            user: '{{tools.user}}'\n      - name: get-user\n        method: GET\n        description: Get loyalty user details\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: loyalty-insurance\n    baseUri: https://api.mastercard.com/loyalty/insurance\n    description: Mastercard Loyalty Insurance API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n\
  \    - name: claims\n      path: /claims\n      description: Insurance claim operations\n      operations:\n      - name: submit-claim\n        method: POST\n        description: Submit an insurance claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            claim: '{{tools.claim}}'\n  - type: http\n    namespace: personalized-offers\n    baseUri: https://api.mastercard.com/personalized-offers\n    description: Mastercard Personalized Offers API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: offers\n      path: /offers\n      description: Personalized offer operations\n      operations:\n      - name: get-offers\n        method: POST\n        description: Get personalized offers for a cardholder\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cardholder: '{{tools.cardholder}}'\n      - name: activate-offer\n        method: POST\n        description: Activate an offer for a cardholder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            activation: '{{tools.activation}}'\n  - type: http\n    namespace: offers-merchant-content\n    baseUri: https://api.mastercard.com/offers/merchant-content\n    description: Mastercard Offers Merchant Content API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: content\n      path: /content\n      description: Merchant offer content\n      operations:\n      - name: get-merchant-content\n\
  \        method: GET\n        description: Get merchant offer content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: priceless-platform\n    baseUri: https://api.mastercard.com/priceless\n    description: Mastercard Priceless Platform API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: experiences\n      path: /experiences\n      description: Priceless experience management\n      operations:\n      - name: list-experiences\n        method: GET\n        description: List available Priceless experiences\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: benefit-eligibility\n    baseUri: https://api.mastercard.com/eligibility\n    description: Mastercard\
  \ Benefit Eligibility Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: eligibility\n      path: /eligibility\n      description: Benefit eligibility checks\n      operations:\n      - name: check-eligibility\n        method: POST\n        description: Check cardholder benefit eligibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            card: '{{tools.card}}'\n  - type: http\n    namespace: benefit-allocation\n    baseUri: https://api.mastercard.com/benefit-allocation\n    description: Mastercard Benefit Allocation Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: allocations\n      path:\
  \ /allocations\n      description: Benefit allocation operations\n      operations:\n      - name: allocate-benefit\n        method: POST\n        description: Allocate a benefit to a cardholder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            allocation: '{{tools.allocation}}'\n  - type: http\n    namespace: pay-with-rewards\n    baseUri: https://api.mastercard.com/pay-with-rewards\n    description: Mastercard Pay with Rewards API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: rewards\n      path: /rewards\n      description: Rewards payment operations\n      operations:\n      - name: pay-with-rewards\n        method: POST\n        description: Apply rewards as payment\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payment: '{{tools.payment}}'\n  - type: http\n    namespace: donate\n    baseUri: https://api.mastercard.com/donate\n    description: Mastercard Donate API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: donations\n      path: /donations\n      description: Donation operations\n      operations:\n      - name: create-donation\n        method: POST\n        description: Create a donation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            donation: '{{tools.donation}}'\n  - type: http\n    namespace: points-activity\n    baseUri: https://api.mastercard.com/loyalty/points\n    description: Mastercard\
  \ Points Activity Service API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: points\n      path: /points\n      description: Points activity operations\n      operations:\n      - name: get-points-balance\n        method: GET\n        description: Get loyalty points balance\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: loyalty-offers-api\n    description: Unified REST API for Mastercard loyalty and offers workflows.\n    resources:\n    - path: /v1/promotions\n      name: promotions\n      description: Loyalty promotions\n      operations:\n      - method: GET\n  \
  \      name: list-promotions\n        description: List available loyalty promotions\n        call: loyalty-promotions.list-promotions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/offers\n      name: offers\n      description: Personalized offers\n      operations:\n      - method: POST\n        name: get-personalized-offers\n        description: Get personalized offers for a cardholder\n        call: personalized-offers.get-offers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiences\n      name: experiences\n      description: Priceless experiences\n      operations:\n      - method: GET\n        name: list-experiences\n        description: List Priceless experiences\n        call: priceless-platform.list-experiences\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/eligibility\n      name: eligibility\n      description: Benefit eligibility checks\n\
  \      operations:\n      - method: POST\n        name: check-eligibility\n        description: Check cardholder benefit eligibility\n        call: benefit-eligibility.check-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9095\n    namespace: loyalty-offers-mcp\n    transport: http\n    description: MCP server for AI-assisted loyalty and offers management.\n    tools:\n    - name: list-promotions\n      description: List available loyalty promotions\n      hints:\n        readOnly: true\n      call: loyalty-promotions.list-promotions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enroll-in-promotion\n      description: Enroll a cardholder in a loyalty promotion\n      hints:\n        readOnly: false\n      call: loyalty-promotions.enroll-promotion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-loyalty-user\n      description: Create a loyalty program\
  \ user\n      hints:\n        readOnly: false\n      call: loyalty-user-mgmt.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-loyalty-user\n      description: Get loyalty user details\n      hints:\n        readOnly: true\n      call: loyalty-user-mgmt.get-user\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-personalized-offers\n      description: Get personalized merchant offers for a cardholder\n      hints:\n        readOnly: true\n      call: personalized-offers.get-offers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-offer\n      description: Activate an offer for a cardholder\n      hints:\n        readOnly: false\n      call: personalized-offers.activate-offer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-benefit-eligibility\n      description: Check cardholder benefit\
  \ eligibility by PAN\n      hints:\n        readOnly: true\n      call: benefit-eligibility.check-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: allocate-benefit\n      description: Allocate a benefit to a cardholder\n      hints:\n        readOnly: false\n      call: benefit-allocation.allocate-benefit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-with-rewards\n      description: Apply loyalty rewards as payment\n      hints:\n        readOnly: false\n      call: pay-with-rewards.pay-with-rewards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-points-balance\n      description: Get loyalty points balance\n      hints:\n        readOnly: true\n      call: points-activity.get-points-balance\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-priceless-experiences\n      description:\
  \ List available Priceless experiences\n      hints:\n        readOnly: true\n      call: priceless-platform.list-experiences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-insurance-claim\n      description: Submit a loyalty insurance claim\n      hints:\n        readOnly: false\n      call: loyalty-insurance.submit-claim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-donation\n      description: Create a charitable donation\n      hints:\n        readOnly: false\n      call: donate.create-donation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-merchant-offer-content\n      description: Get merchant offer content and promotional materials\n      hints:\n        readOnly: true\n      call: offers-merchant-content.get-merchant-content\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/loyalty-and-offers.yaml
tags:
- Mastercard
- Loyalty
- Offers
- Rewards
- Priceless
tools:
- description: List available loyalty promotions
  hints:
    readOnly: true
  name: list-promotions
- description: Enroll a cardholder in a loyalty promotion
  hints:
    readOnly: false
  name: enroll-in-promotion
- description: Create a loyalty program user
  hints:
    readOnly: false
  name: create-loyalty-user
- description: Get loyalty user details
  hints:
    readOnly: true
  name: get-loyalty-user
- description: Get personalized merchant offers for a cardholder
  hints:
    readOnly: true
  name: get-personalized-offers
- description: Activate an offer for a cardholder
  hints:
    readOnly: false
  name: activate-offer
- description: Check cardholder benefit eligibility by PAN
  hints:
    readOnly: true
  name: check-benefit-eligibility
- description: Allocate a benefit to a cardholder
  hints:
    readOnly: false
  name: allocate-benefit
- description: Apply loyalty rewards as payment
  hints:
    readOnly: false
  name: pay-with-rewards
- description: Get loyalty points balance
  hints:
    readOnly: true
  name: get-points-balance
- description: List available Priceless experiences
  hints:
    readOnly: true
  name: list-priceless-experiences
- description: Submit a loyalty insurance claim
  hints:
    readOnly: false
  name: submit-insurance-claim
- description: Create a charitable donation
  hints:
    readOnly: false
  name: create-donation
- description: Get merchant offer content and promotional materials
  hints:
    readOnly: true
  name: get-merchant-offer-content
---
