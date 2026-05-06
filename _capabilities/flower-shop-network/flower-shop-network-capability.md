---
categories: []
consumed_apis: []
description: The Flower Shop Network (FSN) JSON API is a REST-style HTTPS interface that allows florist point-of-sale systems and partners to authenticate, look up products and florists, and exchange wire orders across the FSN florist network. All endpoints accept and return JSON and require an API token.
layout: capability
name: Flower Shop Network JSON API
operations:
- description: Issue API token
  method: POST
  name: post-api-foreignsystem-apigetpostoken
  path: /API/ForeignSystem.apiGetPosToken
- description: Validate token
  method: POST
  name: post-api-token-apicheck
  path: /API/Token.apiCheck
- description: Load product data
  method: POST
  name: post-myfsnproduct-apiloadproductdata
  path: /MyfsnProduct.apiLoadProductData
- description: Search filling florists
  method: POST
  name: post-relayutil-apisearchflorists
  path: /RelayUtil.apiSearchFlorists
- description: Retrieve order details
  method: POST
  name: post-relayorder-apigetorder
  path: /RelayOrder.apiGetOrder
- description: Receive incoming orders awaiting accept/refuse
  method: POST
  name: post-relayorder-apireceiveorders
  path: /RelayOrder.apiReceiveOrders
- description: Accept an incoming order
  method: POST
  name: post-relayorder-apiacceptorder
  path: /RelayOrder.apiAcceptOrder
- description: Refuse an incoming order
  method: POST
  name: post-relayorder-apirefuseorder
  path: /RelayOrder.apiRefuseOrder
- description: Send a florist-to-florist order
  method: POST
  name: post-relayorder-apisendorder
  path: /RelayOrder.apiSendOrder
- description: Confirm order delivery
  method: POST
  name: post-relayorder-apiconfirmdelivery
  path: /RelayOrder.apiConfirmDelivery
- description: Retrieve delivery confirmation
  method: POST
  name: post-relayorder-apigetdeliveryconfirmation
  path: /RelayOrder.apiGetDeliveryConfirmation
personas: []
provider_name: Flower Shop Network
provider_slug: flower-shop-network
search_terms:
- network
- post relayorder apiconfirmdelivery
- retrieve delivery confirmation
- confirm order delivery
- post relayutil apisearchflorists
- post relayorder apireceiveorders
- retrieve order details
- post relayorder apisendorder
- flowers
- refuse an incoming order
- flower
- post relayorder apigetorder
- load product data
- accept an incoming order
- shop
- api
- post relayorder apiacceptorder
- post api token apicheck
- issue api token
- point of sale
- post relayorder apigetdeliveryconfirmation
- post api foreignsystem apigetpostoken
- wire orders
- validate token
- receive incoming orders awaiting accept/refuse
- florists
- post relayorder apirefuseorder
- post myfsnproduct apiloadproductdata
- search filling florists
- send a florist-to-florist order
slug: flower-shop-network-capability
source_filename: flower-shop-network-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Flower Shop Network JSON API\n  description: The Flower Shop Network (FSN) JSON API is a REST-style HTTPS interface that allows florist point-of-sale systems\n    and partners to authenticate, look up products and florists, and exchange wire orders across the FSN florist network.\n    All endpoints accept and return JSON and require an API token.\n  tags:\n  - Flower\n  - Shop\n  - Network\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flower-shop-network\n    baseUri: https://api.flowershopnetwork.com/api\n    description: Flower Shop Network JSON API HTTP API.\n    resources:\n    - name: api-foreignsystem-apigetpostoken\n      path: /API/ForeignSystem.apiGetPosToken\n      operations:\n      - name: post-api-foreignsystem-apigetpostoken\n        method: POST\n        description: Issue API token\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: api-token-apicheck\n      path: /API/Token.apiCheck\n      operations:\n      - name: post-api-token-apicheck\n        method: POST\n        description: Validate token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: myfsnproduct-apiloadproductdata\n      path: /MyfsnProduct.apiLoadProductData\n      operations:\n      - name: post-myfsnproduct-apiloadproductdata\n        method: POST\n        description: Load product data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayutil-apisearchflorists\n      path: /RelayUtil.apiSearchFlorists\n      operations:\n      - name: post-relayutil-apisearchflorists\n        method: POST\n        description: Search filling florists\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: relayorder-apigetorder\n      path: /RelayOrder.apiGetOrder\n      operations:\n      - name: post-relayorder-apigetorder\n        method: POST\n        description: Retrieve order details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apireceiveorders\n      path: /RelayOrder.apiReceiveOrders\n      operations:\n      - name: post-relayorder-apireceiveorders\n        method: POST\n        description: Receive incoming orders awaiting accept/refuse\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apiacceptorder\n      path: /RelayOrder.apiAcceptOrder\n      operations:\n      - name: post-relayorder-apiacceptorder\n        method: POST\n        description: Accept an incoming order\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apirefuseorder\n      path: /RelayOrder.apiRefuseOrder\n      operations:\n      - name: post-relayorder-apirefuseorder\n        method: POST\n        description: Refuse an incoming order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apisendorder\n      path: /RelayOrder.apiSendOrder\n      operations:\n      - name: post-relayorder-apisendorder\n        method: POST\n        description: Send a florist-to-florist order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apiconfirmdelivery\n      path: /RelayOrder.apiConfirmDelivery\n      operations:\n      - name: post-relayorder-apiconfirmdelivery\n        method: POST\n        description: Confirm order delivery\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: relayorder-apigetdeliveryconfirmation\n      path: /RelayOrder.apiGetDeliveryConfirmation\n      operations:\n      - name: post-relayorder-apigetdeliveryconfirmation\n        method: POST\n        description: Retrieve delivery confirmation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flower-shop-network-rest\n    description: REST adapter for Flower Shop Network JSON API.\n    resources:\n    - path: /API/ForeignSystem.apiGetPosToken\n      name: post-api-foreignsystem-apigetpostoken\n      operations:\n      - method: POST\n        name: post-api-foreignsystem-apigetpostoken\n        description: Issue API token\n        call: flower-shop-network.post-api-foreignsystem-apigetpostoken\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /API/Token.apiCheck\n      name: post-api-token-apicheck\n      operations:\n      - method: POST\n        name: post-api-token-apicheck\n        description: Validate token\n        call: flower-shop-network.post-api-token-apicheck\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /MyfsnProduct.apiLoadProductData\n      name: post-myfsnproduct-apiloadproductdata\n      operations:\n      - method: POST\n        name: post-myfsnproduct-apiloadproductdata\n        description: Load product data\n        call: flower-shop-network.post-myfsnproduct-apiloadproductdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayUtil.apiSearchFlorists\n      name: post-relayutil-apisearchflorists\n      operations:\n      - method: POST\n        name: post-relayutil-apisearchflorists\n        description: Search filling florists\n        call: flower-shop-network.post-relayutil-apisearchflorists\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiGetOrder\n      name: post-relayorder-apigetorder\n      operations:\n      - method: POST\n        name: post-relayorder-apigetorder\n        description: Retrieve order details\n        call: flower-shop-network.post-relayorder-apigetorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiReceiveOrders\n      name: post-relayorder-apireceiveorders\n      operations:\n      - method: POST\n        name: post-relayorder-apireceiveorders\n        description: Receive incoming orders awaiting accept/refuse\n        call: flower-shop-network.post-relayorder-apireceiveorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiAcceptOrder\n      name: post-relayorder-apiacceptorder\n      operations:\n      - method: POST\n        name: post-relayorder-apiacceptorder\n        description: Accept\
  \ an incoming order\n        call: flower-shop-network.post-relayorder-apiacceptorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiRefuseOrder\n      name: post-relayorder-apirefuseorder\n      operations:\n      - method: POST\n        name: post-relayorder-apirefuseorder\n        description: Refuse an incoming order\n        call: flower-shop-network.post-relayorder-apirefuseorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiSendOrder\n      name: post-relayorder-apisendorder\n      operations:\n      - method: POST\n        name: post-relayorder-apisendorder\n        description: Send a florist-to-florist order\n        call: flower-shop-network.post-relayorder-apisendorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiConfirmDelivery\n      name: post-relayorder-apiconfirmdelivery\n      operations:\n      - method:\
  \ POST\n        name: post-relayorder-apiconfirmdelivery\n        description: Confirm order delivery\n        call: flower-shop-network.post-relayorder-apiconfirmdelivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /RelayOrder.apiGetDeliveryConfirmation\n      name: post-relayorder-apigetdeliveryconfirmation\n      operations:\n      - method: POST\n        name: post-relayorder-apigetdeliveryconfirmation\n        description: Retrieve delivery confirmation\n        call: flower-shop-network.post-relayorder-apigetdeliveryconfirmation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: flower-shop-network-mcp\n    transport: http\n    description: MCP adapter for Flower Shop Network JSON API for AI agent use.\n    tools:\n    - name: post-api-foreignsystem-apigetpostoken\n      description: Issue API token\n      hints:\n        readOnly: false\n        destructive: false\n \
  \       idempotent: false\n      call: flower-shop-network.post-api-foreignsystem-apigetpostoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-api-token-apicheck\n      description: Validate token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-api-token-apicheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-myfsnproduct-apiloadproductdata\n      description: Load product data\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-myfsnproduct-apiloadproductdata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayutil-apisearchflorists\n      description: Search filling florists\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayutil-apisearchflorists\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apigetorder\n      description: Retrieve order details\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apigetorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apireceiveorders\n      description: Receive incoming orders awaiting accept/refuse\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apireceiveorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apiacceptorder\n      description: Accept an incoming order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apiacceptorder\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: post-relayorder-apirefuseorder\n      description: Refuse an incoming order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apirefuseorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apisendorder\n      description: Send a florist-to-florist order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apisendorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apiconfirmdelivery\n      description: Confirm order delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apiconfirmdelivery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-relayorder-apigetdeliveryconfirmation\n\
  \      description: Retrieve delivery confirmation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flower-shop-network.post-relayorder-apigetdeliveryconfirmation\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flower-shop-network/refs/heads/main/capabilities/flower-shop-network-capability.yaml
tags:
- Flower
- Shop
- Network
- API
tools:
- description: Issue API token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-foreignsystem-apigetpostoken
- description: Validate token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-token-apicheck
- description: Load product data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-myfsnproduct-apiloadproductdata
- description: Search filling florists
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayutil-apisearchflorists
- description: Retrieve order details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apigetorder
- description: Receive incoming orders awaiting accept/refuse
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apireceiveorders
- description: Accept an incoming order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apiacceptorder
- description: Refuse an incoming order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apirefuseorder
- description: Send a florist-to-florist order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apisendorder
- description: Confirm order delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apiconfirmdelivery
- description: Retrieve delivery confirmation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-relayorder-apigetdeliveryconfirmation
---
