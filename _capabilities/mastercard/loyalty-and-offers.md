---
categories: []
consumed_apis:
- loyalty-promotions
- loyalty-user-mgmt
- loyalty-insurance
- personalized-offers
- offers-merchant-content
- priceless-platform
- benefit-eligibility
- benefit-allocation
- pay-with-rewards
- donate
- points-activity
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
- loyalty promotions
- list available priceless experiences
- list available loyalty promotions
- personalized offers
- list experiences
- digital identity
- get points balance
- pay with rewards
- activate an offer for a cardholder
- offers
- create a loyalty program user
- list promotions
- get merchant offer content
- get merchant offer content and promotional materials
- get personalized merchant offers for a cardholder
- rewards
- get loyalty user
- create loyalty user
- allocate benefit
- list priceless experiences
- get loyalty points balance
- get loyalty user details
- enroll in promotion
- submit a loyalty insurance claim
- financial services
- submit insurance claim
- get personalized offers for a cardholder
- open banking
- priceless
- check cardholder benefit eligibility
- benefit eligibility checks
- apply loyalty rewards as payment
- allocate a benefit to a cardholder
- check cardholder benefit eligibility by pan
- create a charitable donation
- fraud detection
- credit cards
- activate offer
- create donation
- priceless experiences
- check benefit eligibility
- get personalized offers
- mastercard
- enroll a cardholder in a loyalty promotion
- loyalty
- check eligibility
- payments
slug: loyalty-and-offers
source_filename: loyalty-and-offers.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Mastercard Loyalty and Offers\"\n  description: \"Unified workflow for loyalty managers and marketing teams to manage loyalty programs, personalized offers, rewards, benefits, and the Priceless experiences platform.\"\n  tags:\n    - Mastercard\n    - Loyalty\n    - Offers\n    - Rewards\n    - Priceless\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n      MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\n\ncapability:\n  consumes:\n    - import: loyalty-promotions\n      location: ./shared/loyalty-promotions.yaml\n    - import: loyalty-user-mgmt\n      location: ./shared/loyalty-user-management.yaml\n    - import: loyalty-insurance\n      location: ./shared/loyalty-insurance.yaml\n    - import: personalized-offers\n      location: ./shared/personalized-offers.yaml\n    - import: offers-merchant-content\n      location: ./shared/offers-merchant-content.yaml\n\
  \    - import: priceless-platform\n      location: ./shared/priceless-platform.yaml\n    - import: benefit-eligibility\n      location: ./shared/benefit-eligibility.yaml\n    - import: benefit-allocation\n      location: ./shared/benefit-allocation.yaml\n    - import: pay-with-rewards\n      location: ./shared/pay-with-rewards.yaml\n    - import: donate\n      location: ./shared/donate.yaml\n    - import: points-activity\n      location: ./shared/points-activity.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: loyalty-offers-api\n      description: \"Unified REST API for Mastercard loyalty and offers workflows.\"\n      resources:\n        - path: /v1/promotions\n          name: promotions\n          description: \"Loyalty promotions\"\n          operations:\n            - method: GET\n              name: list-promotions\n              description: \"List available loyalty promotions\"\n              call: \"loyalty-promotions.list-promotions\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/offers\n          name: offers\n          description: \"Personalized offers\"\n          operations:\n            - method: POST\n              name: get-personalized-offers\n              description: \"Get personalized offers for a cardholder\"\n              call: \"personalized-offers.get-offers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/experiences\n          name: experiences\n          description: \"Priceless experiences\"\n          operations:\n            - method: GET\n              name: list-experiences\n              description: \"List Priceless experiences\"\n              call: \"priceless-platform.list-experiences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/eligibility\n          name: eligibility\n          description: \"\
  Benefit eligibility checks\"\n          operations:\n            - method: POST\n              name: check-eligibility\n              description: \"Check cardholder benefit eligibility\"\n              call: \"benefit-eligibility.check-eligibility\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9095\n      namespace: loyalty-offers-mcp\n      transport: http\n      description: \"MCP server for AI-assisted loyalty and offers management.\"\n      tools:\n        - name: list-promotions\n          description: \"List available loyalty promotions\"\n          hints:\n            readOnly: true\n          call: \"loyalty-promotions.list-promotions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: enroll-in-promotion\n          description: \"Enroll a cardholder in a loyalty promotion\"\n          hints:\n            readOnly: false\n          call:\
  \ \"loyalty-promotions.enroll-promotion\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-loyalty-user\n          description: \"Create a loyalty program user\"\n          hints:\n            readOnly: false\n          call: \"loyalty-user-mgmt.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-loyalty-user\n          description: \"Get loyalty user details\"\n          hints:\n            readOnly: true\n          call: \"loyalty-user-mgmt.get-user\"\n          with:\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-personalized-offers\n          description: \"Get personalized merchant offers for a cardholder\"\n          hints:\n            readOnly: true\n          call: \"personalized-offers.get-offers\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: activate-offer\n          description: \"Activate an offer for a cardholder\"\n          hints:\n            readOnly: false\n          call: \"personalized-offers.activate-offer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-benefit-eligibility\n          description: \"Check cardholder benefit eligibility by PAN\"\n          hints:\n            readOnly: true\n          call: \"benefit-eligibility.check-eligibility\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: allocate-benefit\n          description: \"Allocate a benefit to a cardholder\"\n          hints:\n            readOnly: false\n          call: \"benefit-allocation.allocate-benefit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pay-with-rewards\n          description: \"Apply loyalty rewards\
  \ as payment\"\n          hints:\n            readOnly: false\n          call: \"pay-with-rewards.pay-with-rewards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-points-balance\n          description: \"Get loyalty points balance\"\n          hints:\n            readOnly: true\n          call: \"points-activity.get-points-balance\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-priceless-experiences\n          description: \"List available Priceless experiences\"\n          hints:\n            readOnly: true\n          call: \"priceless-platform.list-experiences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-insurance-claim\n          description: \"Submit a loyalty insurance claim\"\n          hints:\n            readOnly: false\n \
  \         call: \"loyalty-insurance.submit-claim\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-donation\n          description: \"Create a charitable donation\"\n          hints:\n            readOnly: false\n          call: \"donate.create-donation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-merchant-offer-content\n          description: \"Get merchant offer content and promotional materials\"\n          hints:\n            readOnly: true\n          call: \"offers-merchant-content.get-merchant-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
