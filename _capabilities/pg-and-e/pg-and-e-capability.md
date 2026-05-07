---
categories: []
consumed_apis: []
description: The PG&E Share My Data API provides customer-authorized access to energy usage data following the Energy Service Provider Interface (ESPI) standard and Green Button Connect My Data specification. Third-party companies can access interval data for both electricity and gas usage through RESTful web services with OAuth 2.0 authorization.
layout: capability
name: PG&E Share My Data API
operations:
- description: List authorizations
  method: GET
  name: listauthorizations
  path: /GreenButtonConnect/espi/1_1/resource/Authorization
- description: List subscriptions
  method: GET
  name: listsubscriptions
  path: /GreenButtonConnect/espi/1_1/resource/Subscription
- description: List usage points
  method: GET
  name: listusagepoints
  path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint
- description: List meter readings
  method: GET
  name: listmeterreadings
  path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading
- description: List interval blocks
  method: GET
  name: listintervalblocks
  path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading/{meterReadingId}/IntervalBlock
personas: []
provider_name: pg-and-e
provider_slug: pg-and-e
search_terms:
- pg
- list authorizations
- api
- listusagepoints
- list interval blocks
- listintervalblocks
- list subscriptions
- list meter readings
- and
- list usage points
- listauthorizations
- listmeterreadings
- listsubscriptions
slug: pg-and-e-capability
source_filename: pg-and-e-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PG&E Share My Data API\n  description: The PG&E Share My Data API provides customer-authorized access to energy usage data following the Energy Service\n    Provider Interface (ESPI) standard and Green Button Connect My Data specification. Third-party companies can access interval\n    data for both electricity and gas usage through RESTful web services with OAuth 2.0 authorization.\n  tags:\n  - Pg\n  - And\n  - E\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pg-and-e\n    baseUri: https://api.pge.com\n    description: PG&E Share My Data API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PG_AND_E_TOKEN}}'\n    resources:\n    - name: greenbuttonconnect-espi-1-1-resource-authorizati\n      path: /GreenButtonConnect/espi/1_1/resource/Authorization\n      operations:\n      - name: listauthorizations\n        method: GET\n        description: List\
  \ authorizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: greenbuttonconnect-espi-1-1-resource-subscriptio\n      path: /GreenButtonConnect/espi/1_1/resource/Subscription\n      operations:\n      - name: listsubscriptions\n        method: GET\n        description: List subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: greenbuttonconnect-espi-1-1-resource-subscriptio\n      path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint\n      operations:\n      - name: listusagepoints\n        method: GET\n        description: List usage points\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The subscription identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: greenbuttonconnect-espi-1-1-resource-subscriptio\n      path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading\n      operations:\n      - name: listmeterreadings\n        method: GET\n        description: List meter readings\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The subscription identifier.\n        - name: usagePointId\n          in: path\n          type: string\n          required: true\n          description: The usage point identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: greenbuttonconnect-espi-1-1-resource-subscriptio\n      path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading/{meterReadingId}/IntervalBlock\n\
  \      operations:\n      - name: listintervalblocks\n        method: GET\n        description: List interval blocks\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The subscription identifier.\n        - name: usagePointId\n          in: path\n          type: string\n          required: true\n          description: The usage point identifier.\n        - name: meterReadingId\n          in: path\n          type: string\n          required: true\n          description: The meter reading identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pg-and-e-rest\n    description: REST adapter for PG&E Share My Data API.\n    resources:\n    - path: /GreenButtonConnect/espi/1_1/resource/Authorization\n      name: listauthorizations\n      operations:\n\
  \      - method: GET\n        name: listauthorizations\n        description: List authorizations\n        call: pg-and-e.listauthorizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GreenButtonConnect/espi/1_1/resource/Subscription\n      name: listsubscriptions\n      operations:\n      - method: GET\n        name: listsubscriptions\n        description: List subscriptions\n        call: pg-and-e.listsubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint\n      name: listusagepoints\n      operations:\n      - method: GET\n        name: listusagepoints\n        description: List usage points\n        call: pg-and-e.listusagepoints\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading\n\
  \      name: listmeterreadings\n      operations:\n      - method: GET\n        name: listmeterreadings\n        description: List meter readings\n        call: pg-and-e.listmeterreadings\n        with:\n          subscriptionId: rest.subscriptionId\n          usagePointId: rest.usagePointId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GreenButtonConnect/espi/1_1/resource/Subscription/{subscriptionId}/UsagePoint/{usagePointId}/MeterReading/{meterReadingId}/IntervalBlock\n      name: listintervalblocks\n      operations:\n      - method: GET\n        name: listintervalblocks\n        description: List interval blocks\n        call: pg-and-e.listintervalblocks\n        with:\n          subscriptionId: rest.subscriptionId\n          usagePointId: rest.usagePointId\n          meterReadingId: rest.meterReadingId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pg-and-e-mcp\n  \
  \  transport: http\n    description: MCP adapter for PG&E Share My Data API for AI agent use.\n    tools:\n    - name: listauthorizations\n      description: List authorizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pg-and-e.listauthorizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubscriptions\n      description: List subscriptions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pg-and-e.listsubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusagepoints\n      description: List usage points\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pg-and-e.listusagepoints\n      with:\n        subscriptionId: tools.subscriptionId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description:\
  \ The subscription identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmeterreadings\n      description: List meter readings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pg-and-e.listmeterreadings\n      with:\n        subscriptionId: tools.subscriptionId\n        usagePointId: tools.usagePointId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The subscription identifier.\n        required: true\n      - name: usagePointId\n        type: string\n        description: The usage point identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listintervalblocks\n      description: List interval blocks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pg-and-e.listintervalblocks\n      with:\n        subscriptionId:\
  \ tools.subscriptionId\n        usagePointId: tools.usagePointId\n        meterReadingId: tools.meterReadingId\n      inputParameters:\n      - name: subscriptionId\n        type: string\n        description: The subscription identifier.\n        required: true\n      - name: usagePointId\n        type: string\n        description: The usage point identifier.\n        required: true\n      - name: meterReadingId\n        type: string\n        description: The meter reading identifier.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PG_AND_E_TOKEN: PG_AND_E_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pg-and-e/refs/heads/main/capabilities/pg-and-e-capability.yaml
tags:
- Pg
- And
- E
- API
tools:
- description: List authorizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthorizations
- description: List subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubscriptions
- description: List usage points
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusagepoints
- description: List meter readings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmeterreadings
- description: List interval blocks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listintervalblocks
---
