---
categories: []
consumed_apis: []
description: The Handwrite API allows you to send handwritten notes in an automated manner using REST endpoints. Integrate personalized handwritten correspondence into your workflows and applications at scale.
layout: capability
name: Handwrite IO API
operations:
- description: Get Handwritings
  method: GET
  name: gethandwritings
  path: /handwriting
- description: Get Stationery
  method: GET
  name: getstationery
  path: /stationery
- description: Send a Letter
  method: POST
  name: sendletter
  path: /send
- description: Get an Order
  method: GET
  name: getorder
  path: /order/{orderId}
personas: []
provider_name: Handwrite IO
provider_slug: handwrite-io
search_terms:
- marketing
- direct mail
- gethandwritings
- get handwritings
- getorder
- api
- io
- get an order
- notes
- getstationery
- handwrite
- handwritten
- get stationery
- send a letter
- sendletter
slug: handwrite-io-capability
source_filename: handwrite-io-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Handwrite IO API\n  description: The Handwrite API allows you to send handwritten notes in an automated manner using REST endpoints. Integrate\n    personalized handwritten correspondence into your workflows and applications at scale.\n  tags:\n  - Handwrite\n  - Io\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: handwrite-io\n    baseUri: https://api.handwrite.io/v1\n    description: Handwrite IO API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{HANDWRITE_IO_TOKEN}}'\n    resources:\n    - name: handwriting\n      path: /handwriting\n      operations:\n      - name: gethandwritings\n        method: GET\n        description: Get Handwritings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stationery\n      path:\
  \ /stationery\n      operations:\n      - name: getstationery\n        method: GET\n        description: Get Stationery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: send\n      path: /send\n      operations:\n      - name: sendletter\n        method: POST\n        description: Send a Letter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-orderid\n      path: /order/{orderId}\n      operations:\n      - name: getorder\n        method: GET\n        description: Get an Order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: handwrite-io-rest\n  \
  \  description: REST adapter for Handwrite IO API.\n    resources:\n    - path: /handwriting\n      name: gethandwritings\n      operations:\n      - method: GET\n        name: gethandwritings\n        description: Get Handwritings\n        call: handwrite-io.gethandwritings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stationery\n      name: getstationery\n      operations:\n      - method: GET\n        name: getstationery\n        description: Get Stationery\n        call: handwrite-io.getstationery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /send\n      name: sendletter\n      operations:\n      - method: POST\n        name: sendletter\n        description: Send a Letter\n        call: handwrite-io.sendletter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /order/{orderId}\n      name: getorder\n      operations:\n      - method: GET\n        name: getorder\n\
  \        description: Get an Order\n        call: handwrite-io.getorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: handwrite-io-mcp\n    transport: http\n    description: MCP adapter for Handwrite IO API for AI agent use.\n    tools:\n    - name: gethandwritings\n      description: Get Handwritings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: handwrite-io.gethandwritings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstationery\n      description: Get Stationery\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: handwrite-io.getstationery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendletter\n      description: Send a Letter\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: handwrite-io.sendletter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorder\n      description: Get an Order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: handwrite-io.getorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HANDWRITE_IO_TOKEN: HANDWRITE_IO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/handwrite-io/refs/heads/main/capabilities/handwrite-io-capability.yaml
tags:
- Handwrite
- Io
- API
tools:
- description: Get Handwritings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethandwritings
- description: Get Stationery
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstationery
- description: Send a Letter
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendletter
- description: Get an Order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorder
---
