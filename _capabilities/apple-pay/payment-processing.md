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
- initiating and completing apple pay payment authorizations
- mobile payments
- register a domain for apple pay on the web
- contactless payments
- validates merchant and obtains apple pay payment session
- developer integrating apple pay into a web or mobile checkout experience
- checkout
- apple pay merchant validation and payment session
- validates merchant identity with apple and returns a payment session object for completing checkout
- registers a merchant domain to accept apple pay on the web payments
- validate merchant
- register apple pay domain
- register domain
- e-commerce
- registering and managing merchant identity and domains for apple pay
- apple pay
- validate apple pay merchant
- engineer building payment processing infrastructure supporting multiple payment methods
- digital wallet
- payments
- E Commerce Developer
- Payment Integration Engineer
- apple
- merchant domain management for apple pay
- end-to-end apple pay checkout integration with merchant validation and payment token handling
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
