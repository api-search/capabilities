---
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
- check eligibility
- list experiences
- submit insurance claim
- check benefit eligibility
- personalized offers
- activate an offer for a cardholder
- get personalized merchant offers for a cardholder
- payments
- create a loyalty program user
- rewards
- create donation
- check cardholder benefit eligibility
- digital identity
- submit a loyalty insurance claim
- create a charitable donation
- credit cards
- get merchant offer content
- get personalized offers for a cardholder
- list available loyalty promotions
- allocate a benefit to a cardholder
- get loyalty user details
- fraud detection
- priceless
- apply loyalty rewards as payment
- mastercard
- get points balance
- enroll a cardholder in a loyalty promotion
- get loyalty user
- offers
- priceless experiences
- get merchant offer content and promotional materials
- loyalty
- check cardholder benefit eligibility by pan
- pay with rewards
- allocate benefit
- enroll in promotion
- financial services
- get personalized offers
- benefit eligibility checks
- create loyalty user
- list promotions
- open banking
- loyalty promotions
- activate offer
- list available priceless experiences
- list priceless experiences
- get loyalty points balance
slug: loyalty-and-offers
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
