---
categories:
- payments
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
- Payment Integration Engineer
- e-commerce
- register apple pay domain
- initiating and completing apple pay payment authorizations
- payments
- apple
- register a domain for apple pay on the web
- registers a merchant domain to accept apple pay on the web payments
- validate merchant
- validates merchant identity with apple and returns a payment session object for completing checkout
- registering and managing merchant identity and domains for apple pay
- developer integrating apple pay into a web or mobile checkout experience
- validates merchant and obtains apple pay payment session
- register domain
- digital wallet
- apple pay
- validate apple pay merchant
- E Commerce Developer
- engineer building payment processing infrastructure supporting multiple payment methods
- mobile payments
- checkout
- contactless payments
- apple pay merchant validation and payment session
- merchant domain management for apple pay
- end-to-end apple pay checkout integration with merchant validation and payment token handling
slug: payment-processing
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apple Pay Payment Processing\n  description: >-\n    Workflow capability for integrating Apple Pay into e-commerce and mobile payment\n    flows. Combines merchant validation, payment session management, and payment token\n    processing into a unified workflow for e-commerce developers and payment integration\n    engineers enabling secure, one-touch checkout on Apple devices.\n  tags:\n    - Apple Pay\n    - Payments\n    - E-Commerce\n    - Checkout\n    - Mobile Payments\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPLE_PAY_MERCHANT_CERT: APPLE_PAY_MERCHANT_CERT\n\ncapability:\n  consumes:\n    - import: apple-pay-js\n      location: ./shared/apple-pay-js.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apple-pay-checkout-api\n      description: Unified REST API for Apple Pay checkout integration.\n      resources:\n        - path: /v1/payment-sessions\n\
  \          name: payment-sessions\n          description: Apple Pay merchant validation and payment session\n          operations:\n            - method: POST\n              name: validate-merchant\n              description: Validates merchant and obtains Apple Pay payment session\n              call: \"apple-pay-js.request-payment-session\"\n              with:\n                merchantIdentifier: \"rest.merchantIdentifier\"\n                domainName: \"rest.domainName\"\n                displayName: \"rest.displayName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/merchant-domains\n          name: merchant-domains\n          description: Merchant domain management for Apple Pay\n          operations:\n            - method: POST\n              name: register-domain\n              description: Register a domain for Apple Pay on the Web\n              call: \"apple-pay-js.register-merchant-domain\"\n      \
  \        with:\n                domainName: \"rest.domainName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apple-pay-checkout-mcp\n      transport: http\n      description: MCP server for AI-assisted Apple Pay checkout integration.\n      tools:\n        - name: validate-apple-pay-merchant\n          description: Validates merchant identity with Apple and returns a payment session object for completing checkout\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apple-pay-js.request-payment-session\"\n          with:\n            merchantIdentifier: \"tools.merchantIdentifier\"\n            domainName: \"tools.domainName\"\n            displayName: \"tools.displayName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: register-apple-pay-domain\n          description: Registers\
  \ a merchant domain to accept Apple Pay on the Web payments\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"apple-pay-js.register-merchant-domain\"\n          with:\n            domainName: \"tools.domainName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apple-pay/refs/heads/main/capabilities/payment-processing.yaml
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
