---
categories: []
consumed_apis: []
description: The NATS server exposes a monitoring HTTP endpoint that provides real-time server statistics including connection info, route details, subscription data, JetStream metrics, and health checks for observability and operations.
layout: capability
name: NATS Monitoring HTTP API
operations:
- description: General server information
  method: GET
  name: getvarz
  path: /varz
- description: Connection information
  method: GET
  name: getconnz
  path: /connz
- description: Route information
  method: GET
  name: getroutez
  path: /routez
- description: Gateway information
  method: GET
  name: getgatewayz
  path: /gatewayz
- description: Leaf node information
  method: GET
  name: getleafz
  path: /leafz
- description: Subscription information
  method: GET
  name: getsubsz
  path: /subsz
- description: JetStream information
  method: GET
  name: getjsz
  path: /jsz
- description: Account information
  method: GET
  name: getaccountz
  path: /accountz
- description: Health check
  method: GET
  name: gethealthz
  path: /healthz
- description: IP queue sizes
  method: GET
  name: getipqueuesz
  path: /ipqueuesz
personas: []
provider_name: NATS
provider_slug: nats
search_terms:
- connection information
- leaf node information
- api
- nats
- getgatewayz
- pub sub
- cloud native
- getjsz
- health check
- jetstream information
- getipqueuesz
- ip queue sizes
- general server information
- message broker
- getaccountz
- iot
- subscription information
- gateway information
- getsubsz
- route information
- account information
- getconnz
- microservices
- getleafz
- gethealthz
- getvarz
- getroutez
slug: nats-capability
source_filename: nats-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NATS Monitoring HTTP API\n  description: The NATS server exposes a monitoring HTTP endpoint that provides real-time server statistics including connection\n    info, route details, subscription data, JetStream metrics, and health checks for observability and operations.\n  tags:\n  - Nats\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nats\n    baseUri: http://localhost:8222\n    description: NATS Monitoring HTTP API HTTP API.\n    resources:\n    - name: varz\n      path: /varz\n      operations:\n      - name: getvarz\n        method: GET\n        description: General server information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connz\n      path: /connz\n      operations:\n      - name: getconnz\n        method: GET\n        description: Connection information\n     \
  \   inputParameters:\n        - name: sort\n          in: query\n          type: string\n        - name: auth\n          in: query\n          type: boolean\n        - name: subs\n          in: query\n          type: boolean\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        - name: cid\n          in: query\n          type: integer\n        - name: state\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routez\n      path: /routez\n      operations:\n      - name: getroutez\n        method: GET\n        description: Route information\n        inputParameters:\n        - name: subs\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ gatewayz\n      path: /gatewayz\n      operations:\n      - name: getgatewayz\n        method: GET\n        description: Gateway information\n        inputParameters:\n        - name: accs\n          in: query\n          type: boolean\n        - name: gw_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leafz\n      path: /leafz\n      operations:\n      - name: getleafz\n        method: GET\n        description: Leaf node information\n        inputParameters:\n        - name: subs\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subsz\n      path: /subsz\n      operations:\n      - name: getsubsz\n        method: GET\n        description: Subscription information\n        inputParameters:\n        - name: subs\n\
  \          in: query\n          type: boolean\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        - name: test\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jsz\n      path: /jsz\n      operations:\n      - name: getjsz\n        method: GET\n        description: JetStream information\n        inputParameters:\n        - name: acc\n          in: query\n          type: string\n        - name: accounts\n          in: query\n          type: boolean\n        - name: streams\n          in: query\n          type: boolean\n        - name: consumers\n          in: query\n          type: boolean\n        - name: config\n          in: query\n          type: boolean\n        - name: leader-only\n          in: query\n          type: boolean\n        - name: offset\n \
  \         in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accountz\n      path: /accountz\n      operations:\n      - name: getaccountz\n        method: GET\n        description: Account information\n        inputParameters:\n        - name: acc\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: healthz\n      path: /healthz\n      operations:\n      - name: gethealthz\n        method: GET\n        description: Health check\n        inputParameters:\n        - name: js-enabled-only\n          in: query\n          type: boolean\n        - name: js-server-only\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: ipqueuesz\n      path: /ipqueuesz\n      operations:\n      - name: getipqueuesz\n        method: GET\n        description: IP queue sizes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nats-rest\n    description: REST adapter for NATS Monitoring HTTP API.\n    resources:\n    - path: /varz\n      name: getvarz\n      operations:\n      - method: GET\n        name: getvarz\n        description: General server information\n        call: nats.getvarz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /connz\n      name: getconnz\n      operations:\n      - method: GET\n        name: getconnz\n        description: Connection information\n        call: nats.getconnz\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /routez\n      name: getroutez\n      operations:\n      - method: GET\n        name: getroutez\n        description: Route information\n        call: nats.getroutez\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gatewayz\n      name: getgatewayz\n      operations:\n      - method: GET\n        name: getgatewayz\n        description: Gateway information\n        call: nats.getgatewayz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /leafz\n      name: getleafz\n      operations:\n      - method: GET\n        name: getleafz\n        description: Leaf node information\n        call: nats.getleafz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subsz\n      name: getsubsz\n      operations:\n      - method: GET\n        name: getsubsz\n        description: Subscription information\n        call: nats.getsubsz\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /jsz\n      name: getjsz\n      operations:\n      - method: GET\n        name: getjsz\n        description: JetStream information\n        call: nats.getjsz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accountz\n      name: getaccountz\n      operations:\n      - method: GET\n        name: getaccountz\n        description: Account information\n        call: nats.getaccountz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /healthz\n      name: gethealthz\n      operations:\n      - method: GET\n        name: gethealthz\n        description: Health check\n        call: nats.gethealthz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ipqueuesz\n      name: getipqueuesz\n      operations:\n      - method: GET\n        name: getipqueuesz\n        description: IP queue sizes\n        call: nats.getipqueuesz\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nats-mcp\n    transport: http\n    description: MCP adapter for NATS Monitoring HTTP API for AI agent use.\n    tools:\n    - name: getvarz\n      description: General server information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getvarz\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnz\n      description: Connection information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getconnz\n      with:\n        sort: tools.sort\n        auth: tools.auth\n        subs: tools.subs\n        offset: tools.offset\n        limit: tools.limit\n        cid: tools.cid\n        state: tools.state\n      inputParameters:\n      - name: sort\n        type: string\n        description: sort\n      - name: auth\n        type: boolean\n        description:\
  \ auth\n      - name: subs\n        type: boolean\n        description: subs\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      - name: cid\n        type: integer\n        description: cid\n      - name: state\n        type: string\n        description: state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroutez\n      description: Route information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getroutez\n      with:\n        subs: tools.subs\n      inputParameters:\n      - name: subs\n        type: boolean\n        description: subs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgatewayz\n      description: Gateway information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getgatewayz\n\
  \      with:\n        accs: tools.accs\n        gw_name: tools.gw_name\n      inputParameters:\n      - name: accs\n        type: boolean\n        description: accs\n      - name: gw_name\n        type: string\n        description: gw_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getleafz\n      description: Leaf node information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getleafz\n      with:\n        subs: tools.subs\n      inputParameters:\n      - name: subs\n        type: boolean\n        description: subs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsubsz\n      description: Subscription information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getsubsz\n      with:\n        subs: tools.subs\n        offset: tools.offset\n        limit: tools.limit\n        test: tools.test\n\
  \      inputParameters:\n      - name: subs\n        type: boolean\n        description: subs\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      - name: test\n        type: string\n        description: test\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getjsz\n      description: JetStream information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getjsz\n      with:\n        acc: tools.acc\n        accounts: tools.accounts\n        streams: tools.streams\n        consumers: tools.consumers\n        config: tools.config\n        leader-only: tools.leader-only\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: acc\n        type: string\n        description: acc\n      - name: accounts\n        type: boolean\n        description: accounts\n      -\
  \ name: streams\n        type: boolean\n        description: streams\n      - name: consumers\n        type: boolean\n        description: consumers\n      - name: config\n        type: boolean\n        description: config\n      - name: leader-only\n        type: boolean\n        description: leader-only\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountz\n      description: Account information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getaccountz\n      with:\n        acc: tools.acc\n      inputParameters:\n      - name: acc\n        type: string\n        description: acc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealthz\n      description: Health check\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: nats.gethealthz\n      with:\n        js-enabled-only: tools.js-enabled-only\n        js-server-only: tools.js-server-only\n      inputParameters:\n      - name: js-enabled-only\n        type: boolean\n        description: js-enabled-only\n      - name: js-server-only\n        type: boolean\n        description: js-server-only\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getipqueuesz\n      description: IP queue sizes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nats.getipqueuesz\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nats/refs/heads/main/capabilities/nats-capability.yaml
tags:
- Nats
- API
tools:
- description: General server information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvarz
- description: Connection information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnz
- description: Route information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutez
- description: Gateway information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgatewayz
- description: Leaf node information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getleafz
- description: Subscription information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubsz
- description: JetStream information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getjsz
- description: Account information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountz
- description: Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthz
- description: IP queue sizes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getipqueuesz
---
