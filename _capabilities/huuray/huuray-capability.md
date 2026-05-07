---
categories: []
consumed_apis: []
description: Huuray API for B2B customers (last updated april 2025)
layout: capability
name: Huuray API
operations:
- description: Used to get available balances
  method: GET
  name: get-v4-balance
  path: /v4/Balance
- description: Used to Cancel Orders or Giftcards
  method: DELETE
  name: delete-v4-cancel
  path: /v4/Cancel
- description: Used to get a list of the available products
  method: POST
  name: post-v4-catalogue
  path: /v4/Catalogue
- description: Used to retrieve current exchange rate data
  method: GET
  name: get-v4-exchangerates
  path: /v4/ExchangeRates
- description: Used to order giftcards
  method: POST
  name: post-v4-order
  path: /v4/Order
- description: Used to Resend Orders or Giftcards
  method: POST
  name: post-v4-resend
  path: /v4/Resend
- description: Used to search through giftcards from previous orders
  method: POST
  name: post-v4-search
  path: /v4/Search
- description: Used to check the current stock of a product
  method: POST
  name: post-v4-stock
  path: /v4/Stock
- description: Used to get a list of the available templates
  method: POST
  name: post-v4-template
  path: /v4/Template
personas: []
provider_name: Huuray
provider_slug: huuray
search_terms:
- used to get available balances
- huuray
- used to search through giftcards from previous orders
- post v4 resend
- api
- used to check the current stock of a product
- delete v4 cancel
- post v4 order
- used to cancel orders or giftcards
- used to get a list of the available templates
- used to resend orders or giftcards
- rewards
- get v4 exchangerates
- gift cards
- e-commerce
- get v4 balance
- used to retrieve current exchange rate data
- used to order giftcards
- post v4 catalogue
- payments
- post v4 stock
- post v4 template
- post v4 search
- used to get a list of the available products
slug: huuray-capability
source_filename: huuray-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Huuray API\n  description: Huuray API for B2B customers (last updated april 2025)\n  tags:\n  - Huuray\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: huuray\n    baseUri: https://api.example.com\n    description: Huuray API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-TOKEN\n      value: '{{HUURAY_TOKEN}}'\n    resources:\n    - name: v4-balance\n      path: /v4/Balance\n      operations:\n      - name: get-v4-balance\n        method: GET\n        description: Used to get available balances\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name:\
  \ X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-cancel\n      path: /v4/Cancel\n      operations:\n      - name: delete-v4-cancel\n        method: DELETE\n        description: Used to Cancel Orders or Giftcards\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n\
  \          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-catalogue\n      path: /v4/Catalogue\n      operations:\n      - name: post-v4-catalogue\n        method: POST\n        description: Used to get a list of the available products\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing\
  \ the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-exchangerates\n      path: /v4/ExchangeRates\n      operations:\n      - name: get-v4-exchangerates\n        method: GET\n        description: Used to retrieve current exchange rate data\n        inputParameters:\n        - name: FromCurrency\n          in: query\n          type: string\n        - name: ToCurrency\n          in: query\n          type: string\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required:\
  \ true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-order\n      path: /v4/Order\n      operations:\n      - name: post-v4-order\n        method: POST\n        description: Used to order giftcards\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET\
  \ + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-resend\n      path: /v4/Resend\n      operations:\n      - name: post-v4-resend\n        method: POST\n        description: Used to Resend Orders or Giftcards\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-search\n      path: /v4/Search\n      operations:\n      - name: post-v4-search\n        method: POST\n        description: Used to search through giftcards from previous orders\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: v4-stock\n      path: /v4/Stock\n      operations:\n      - name: post-v4-stock\n        method: POST\n        description: Used to check the current stock of a product\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v4-template\n\
  \      path: /v4/Template\n      operations:\n      - name: post-v4-template\n        method: POST\n        description: Used to get a list of the available templates\n        inputParameters:\n        - name: X-API-NONCE\n          in: header\n          type: string\n          required: true\n          description: A random value that can only be used once every 60 days. (max 50 characters)<br /><small>(this prevents\n            your message from being re-transmitted, and thereby also\n        - name: X-API-HASH\n          in: header\n          type: string\n          required: true\n          description: 'The SHA512 hash of a concatenated string containing the following: ( API-SECRET + NONCE ).<br /><small>(this\n            is used to authenticate you)</small>'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: huuray-rest\n    description: REST adapter\
  \ for Huuray API.\n    resources:\n    - path: /v4/Balance\n      name: get-v4-balance\n      operations:\n      - method: GET\n        name: get-v4-balance\n        description: Used to get available balances\n        call: huuray.get-v4-balance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Cancel\n      name: delete-v4-cancel\n      operations:\n      - method: DELETE\n        name: delete-v4-cancel\n        description: Used to Cancel Orders or Giftcards\n        call: huuray.delete-v4-cancel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Catalogue\n      name: post-v4-catalogue\n      operations:\n      - method: POST\n        name: post-v4-catalogue\n        description: Used to get a list of the available products\n        call: huuray.post-v4-catalogue\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/ExchangeRates\n      name: get-v4-exchangerates\n\
  \      operations:\n      - method: GET\n        name: get-v4-exchangerates\n        description: Used to retrieve current exchange rate data\n        call: huuray.get-v4-exchangerates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Order\n      name: post-v4-order\n      operations:\n      - method: POST\n        name: post-v4-order\n        description: Used to order giftcards\n        call: huuray.post-v4-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Resend\n      name: post-v4-resend\n      operations:\n      - method: POST\n        name: post-v4-resend\n        description: Used to Resend Orders or Giftcards\n        call: huuray.post-v4-resend\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Search\n      name: post-v4-search\n      operations:\n      - method: POST\n        name: post-v4-search\n        description: Used to search through giftcards\
  \ from previous orders\n        call: huuray.post-v4-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Stock\n      name: post-v4-stock\n      operations:\n      - method: POST\n        name: post-v4-stock\n        description: Used to check the current stock of a product\n        call: huuray.post-v4-stock\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v4/Template\n      name: post-v4-template\n      operations:\n      - method: POST\n        name: post-v4-template\n        description: Used to get a list of the available templates\n        call: huuray.post-v4-template\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: huuray-mcp\n    transport: http\n    description: MCP adapter for Huuray API for AI agent use.\n    tools:\n    - name: get-v4-balance\n      description: Used to get available balances\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: huuray.get-v4-balance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-v4-cancel\n      description: Used to Cancel Orders or Giftcards\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: huuray.delete-v4-cancel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-catalogue\n      description: Used to get a list of the available products\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: huuray.post-v4-catalogue\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-v4-exchangerates\n      description: Used to retrieve current exchange rate data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: huuray.get-v4-exchangerates\n      with:\n        FromCurrency:\
  \ tools.FromCurrency\n        ToCurrency: tools.ToCurrency\n      inputParameters:\n      - name: FromCurrency\n        type: string\n        description: FromCurrency\n      - name: ToCurrency\n        type: string\n        description: ToCurrency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-order\n      description: Used to order giftcards\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: huuray.post-v4-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-resend\n      description: Used to Resend Orders or Giftcards\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: huuray.post-v4-resend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-search\n      description: Used to search through giftcards from previous orders\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: huuray.post-v4-search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-stock\n      description: Used to check the current stock of a product\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: huuray.post-v4-stock\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-v4-template\n      description: Used to get a list of the available templates\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: huuray.post-v4-template\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HUURAY_TOKEN: HUURAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/huuray/refs/heads/main/capabilities/huuray-capability.yaml
tags:
- Huuray
- API
tools:
- description: Used to get available balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v4-balance
- description: Used to Cancel Orders or Giftcards
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v4-cancel
- description: Used to get a list of the available products
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-catalogue
- description: Used to retrieve current exchange rate data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v4-exchangerates
- description: Used to order giftcards
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-order
- description: Used to Resend Orders or Giftcards
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-resend
- description: Used to search through giftcards from previous orders
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-search
- description: Used to check the current stock of a product
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-stock
- description: Used to get a list of the available templates
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v4-template
---
