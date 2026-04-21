---
consumed_apis:
- apple-pay-js
description: Workflow capability for integrating Apple Pay into e-commerce and mobile payment flows. Combines merchant validation, payment session management, and payment token processing into a unified workflow for e-commerce developers and payment integration engineers enabling secure, one-touch checkout on Apple devices.
layout: capability
name: Apple Pay Payment Processing
operations:
- description: Validates merchant and obtains Apple Pay payment session
  method: POST
  name: validate-merchant
  path: /v1/payment-sessions
- description: Register a domain for Apple Pay on the Web
  method: POST
  name: register-domain
  path: /v1/merchant-domains
personas: []
provider_name: Apple Pay
provider_slug: apple-pay
search_terms:
- developer integrating apple pay into a web or mobile checkout experience
- register a domain for apple pay on the web
- registering and managing merchant identity and domains for apple pay
- registers a merchant domain to accept apple pay on the web payments
- E Commerce Developer
- checkout
- engineer building payment processing infrastructure supporting multiple payment methods
- apple pay
- validates merchant and obtains apple pay payment session
- contactless payments
- payments
- digital wallet
- register apple pay domain
- e-commerce
- validate apple pay merchant
- apple pay merchant validation and payment session
- mobile payments
- Payment Integration Engineer
- validate merchant
- validates merchant identity with apple and returns a payment session object for completing checkout
- end-to-end apple pay checkout integration with merchant validation and payment token handling
- initiating and completing apple pay payment authorizations
- apple
- merchant domain management for apple pay
- register domain
slug: payment-processing
tags:
- Apple Pay
- Payments
- E-Commerce
- Checkout
- Mobile Payments
tools:
- description: Validates merchant identity with Apple and returns a payment session object for completing checkout
  hints:
    destructive: false
    readOnly: false
  name: validate-apple-pay-merchant
- description: Registers a merchant domain to accept Apple Pay on the Web payments
  hints:
    destructive: false
    readOnly: false
  name: register-apple-pay-domain
---
