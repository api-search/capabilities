---
categories:
- payments
consumed_apis: []
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
- registering and managing merchant identity and domains for apple pay
- registers a merchant domain to accept apple pay on the web payments
- validate apple pay merchant
- apple pay
- E Commerce Developer
- developer integrating apple pay into a web or mobile checkout experience
- engineer building payment processing infrastructure supporting multiple payment methods
- e-commerce
- register apple pay domain
- register domain
- validate merchant
- merchant domain management for apple pay
- end-to-end apple pay checkout integration with merchant validation and payment token handling
- validates merchant and obtains apple pay payment session
- apple
- checkout
- contactless payments
- mobile payments
- digital wallet
- register a domain for apple pay on the web
- payments
- Payment Integration Engineer
- apple pay merchant validation and payment session
- validates merchant identity with apple and returns a payment session object for completing checkout
- initiating and completing apple pay payment authorizations
slug: payment-processing
source_filename: payment-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apple Pay Payment Processing\n  description: Workflow capability for integrating Apple Pay into e-commerce and mobile payment flows. Combines merchant validation,\n    payment session management, and payment token processing into a unified workflow for e-commerce developers and payment\n    integration engineers enabling secure, one-touch checkout on Apple devices.\n  tags:\n  - Apple Pay\n  - Payments\n  - E-Commerce\n  - Checkout\n  - Mobile Payments\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPLE_PAY_MERCHANT_CERT: APPLE_PAY_MERCHANT_CERT\ncapability:\n  consumes:\n  - type: http\n    namespace: apple-pay-js\n    baseUri: https://apple-pay-gateway.apple.com/paymentservices\n    description: Apple Pay JS API for merchant validation and payment session management\n    authentication:\n      type: apikey\n      key: X-Apple-Merchant-Certificate\n      value: '{{APPLE_PAY_MERCHANT_CERT}}'\n\
  \      placement: header\n    resources:\n    - name: payment-session\n      path: /paymentSession\n      description: Merchant validation and payment session creation\n      operations:\n      - name: request-payment-session\n        method: POST\n        description: Validates merchant identity and returns a payment session object\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            merchantIdentifier: '{{tools.merchantIdentifier}}'\n            domainName: '{{tools.domainName}}'\n            displayName: '{{tools.displayName}}'\n    - name: merchant-domains\n      path: /merchantDomains\n      description: Merchant domain registration\n      operations:\n      - name: register-merchant-domain\n        method: POST\n        description: Registers a domain for Apple Pay on the Web\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            domainName: '{{tools.domainName}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: apple-pay-checkout-api\n    description: Unified REST API for Apple Pay checkout integration.\n    resources:\n    - path: /v1/payment-sessions\n      name: payment-sessions\n      description: Apple Pay merchant validation and payment session\n      operations:\n      - method: POST\n        name: validate-merchant\n        description: Validates merchant and obtains Apple Pay payment session\n        call: apple-pay-js.request-payment-session\n        with:\n          merchantIdentifier: rest.merchantIdentifier\n          domainName: rest.domainName\n          displayName: rest.displayName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/merchant-domains\n      name: merchant-domains\n      description: Merchant domain management\
  \ for Apple Pay\n      operations:\n      - method: POST\n        name: register-domain\n        description: Register a domain for Apple Pay on the Web\n        call: apple-pay-js.register-merchant-domain\n        with:\n          domainName: rest.domainName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: apple-pay-checkout-mcp\n    transport: http\n    description: MCP server for AI-assisted Apple Pay checkout integration.\n    tools:\n    - name: validate-apple-pay-merchant\n      description: Validates merchant identity with Apple and returns a payment session object for completing checkout\n      hints:\n        readOnly: false\n        destructive: false\n      call: apple-pay-js.request-payment-session\n      with:\n        merchantIdentifier: tools.merchantIdentifier\n        domainName: tools.domainName\n        displayName: tools.displayName\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: register-apple-pay-domain\n      description: Registers a merchant domain to accept Apple Pay on the Web payments\n      hints:\n        readOnly: false\n        destructive: false\n      call: apple-pay-js.register-merchant-domain\n      with:\n        domainName: tools.domainName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
