---
categories: []
consumed_apis: []
description: Enterprise-grade APIs for AT&T wireline business services including service qualification, quoting, ordering, and provisioning. The Alliance API suite supports automated ordering of AVPN, IPBB, ATTPhone, ASE, and AT&T Internet Air for Business services.
layout: capability
name: AT&T Enterprise Connectivity APIs
operations:
- description: Check AT&T Service Qualification
  method: POST
  name: checkservicequalification
  path: /alliance/serviceQualification/v1/check
- description: Create AT&T Enterprise Product Order
  method: POST
  name: createproductorder
  path: /alliance/productOrder/v1
- description: List AT&T Enterprise Product Orders
  method: GET
  name: listproductorders
  path: /alliance/productOrder/v1
- description: Get AT&T Enterprise Product Order
  method: GET
  name: getproductorder
  path: /alliance/productOrder/v1/{orderId}
personas: []
provider_name: AT&T
provider_slug: atandt
search_terms:
- Identity Developer
- network
- sms and in-app messaging services
- Enterprise Developer
- developer implementing frictionless mobile authentication via at&t network
- create at&t enterprise product order
- engineer integrating enterprise wireline services and ebonding systems
- wireline
- Security Developer
- camara network-based fraud prevention using sim swap and number verification
- oauth and network-based authentication
- 5g
- enterprise
- network-based fraud detection and threat intelligence
- sms messaging and oauth authentication for consumer and business applications
- getproductorder
- wireless
- check at&t service qualification
- developer integrating at&t enterprise connectivity and ebonding apis
- api
- telecommunications
- atandt
- mobile or web developer building consumer applications on at&t apis
- checkservicequalification
- device status, roaming, and qos management
- list at&t enterprise product orders
- broadband
- createproductorder
- listproductorders
- mobile virtual network operator managing subscribers on at&t infrastructure
- wireline service ordering and qualification
- get at&t enterprise product order
- App Developer
- fortune 100
- developer building fraud prevention and identity verification using at&t network signals
slug: atandt-capability
source_filename: atandt-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AT&T Enterprise Connectivity APIs\n  description: Enterprise-grade APIs for AT&T wireline business services including service qualification, quoting, ordering,\n    and provisioning. The Alliance API suite supports automated ordering of AVPN, IPBB, ATTPhone, ASE, and AT&T Internet Air\n    for Business services.\n  tags:\n  - Atandt\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: atandt\n    baseUri: https://devex-web.att.com\n    description: AT&T Enterprise Connectivity APIs HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ATANDT_TOKEN}}'\n    resources:\n    - name: alliance-servicequalification-v1-check\n      path: /alliance/serviceQualification/v1/check\n      operations:\n      - name: checkservicequalification\n        method: POST\n        description: Check AT&T Service Qualification\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: alliance-productorder-v1\n      path: /alliance/productOrder/v1\n      operations:\n      - name: createproductorder\n        method: POST\n        description: Create AT&T Enterprise Product Order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listproductorders\n        method: GET\n        description: List AT&T Enterprise Product Orders\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          description: Filter by order state\n        - name: requestedStartDate.gt\n          in: query\n          type: string\n          description: Filter orders with requested start date after this date\n        - name: externalId\n          in: query\n          type: string\n          description: Filter by external order ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: alliance-productorder-v1-orderid\n      path: /alliance/productOrder/v1/{orderId}\n      operations:\n      - name: getproductorder\n        method: GET\n        description: Get AT&T Enterprise Product Order\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: atandt-rest\n    description: REST adapter for AT&T Enterprise Connectivity APIs.\n    resources:\n    - path: /alliance/serviceQualification/v1/check\n      name: checkservicequalification\n      operations:\n      - method: POST\n        name: checkservicequalification\n        description: Check AT&T Service Qualification\n        call: atandt.checkservicequalification\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /alliance/productOrder/v1\n      name: createproductorder\n      operations:\n      - method: POST\n        name: createproductorder\n        description: Create AT&T Enterprise Product Order\n        call: atandt.createproductorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alliance/productOrder/v1\n      name: listproductorders\n      operations:\n      - method: GET\n        name: listproductorders\n        description: List AT&T Enterprise Product Orders\n        call: atandt.listproductorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alliance/productOrder/v1/{orderId}\n      name: getproductorder\n      operations:\n      - method: GET\n        name: getproductorder\n        description: Get AT&T Enterprise Product Order\n        call: atandt.getproductorder\n        with:\n          orderId: rest.orderId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: atandt-mcp\n    transport: http\n    description: MCP adapter for AT&T Enterprise Connectivity APIs for AI agent use.\n    tools:\n    - name: checkservicequalification\n      description: Check AT&T Service Qualification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: atandt.checkservicequalification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproductorder\n      description: Create AT&T Enterprise Product Order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: atandt.createproductorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproductorders\n      description: List AT&T Enterprise Product Orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n     \
  \ call: atandt.listproductorders\n      with:\n        state: tools.state\n        requestedStartDate.gt: tools.requestedStartDate.gt\n        externalId: tools.externalId\n      inputParameters:\n      - name: state\n        type: string\n        description: Filter by order state\n      - name: requestedStartDate.gt\n        type: string\n        description: Filter orders with requested start date after this date\n      - name: externalId\n        type: string\n        description: Filter by external order ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproductorder\n      description: Get AT&T Enterprise Product Order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: atandt.getproductorder\n      with:\n        orderId: tools.orderId\n      inputParameters:\n      - name: orderId\n        type: string\n        description: orderId\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ATANDT_TOKEN: ATANDT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/atandt/refs/heads/main/capabilities/atandt-capability.yaml
tags:
- Atandt
- API
tools:
- description: Check AT&T Service Qualification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checkservicequalification
- description: Create AT&T Enterprise Product Order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproductorder
- description: List AT&T Enterprise Product Orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproductorders
- description: Get AT&T Enterprise Product Order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproductorder
---
