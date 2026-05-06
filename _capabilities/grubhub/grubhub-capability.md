---
categories: []
consumed_apis: []
description: The Grubhub Deliveries API enables partners to manage delivery logistics and interact with Grubhub's nationwide courier network. It provides delivery status tracking through key states including driver assignment, pickup ready, and out for delivery. Partners can leverage Grubhub Connect, a full-service delivery solution for delivery aggregators, marketplaces, and enterprise merchants to fulfill orders using Grubhub drivers. The API also supports driver communication through proxy phone numbers.
layout: capability
name: Grubhub Deliveries API
operations:
- description: Get delivery status for an order
  method: GET
  name: getdeliverystatus
  path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery
- description: Create proxy courier phone number
  method: POST
  name: createproxycourierphone
  path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery/proxy-phone
personas: []
provider_name: grubhub
provider_slug: grubhub
search_terms:
- create proxy courier phone number
- api
- get delivery status for an order
- getdeliverystatus
- grubhub
- createproxycourierphone
slug: grubhub-capability
source_filename: grubhub-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grubhub Deliveries API\n  description: The Grubhub Deliveries API enables partners to manage delivery logistics and interact with Grubhub's nationwide\n    courier network. It provides delivery status tracking through key states including driver assignment, pickup ready, and\n    out for delivery. Partners can leverage Grubhub Connect, a full-service delivery solution for delivery aggregators, marketplaces,\n    and enterprise merchants to fulfill orders using Grubhub drivers. The API also supports driver communication through proxy\n    phone numbers.\n  tags:\n  - Grubhub\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grubhub\n    baseUri: https://api-third-party-gtm.grubhub.com\n    description: Grubhub Deliveries API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{GRUBHUB_TOKEN}}'\n    resources:\n\
  \    - name: pos-v1-merchant-merchant-long-id-orders-order-uu\n      path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery\n      operations:\n      - name: getdeliverystatus\n        method: GET\n        description: Get delivery status for an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pos-v1-merchant-merchant-long-id-orders-order-uu\n      path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery/proxy-phone\n      operations:\n      - name: createproxycourierphone\n        method: POST\n        description: Create proxy courier phone number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grubhub-rest\n    description: REST adapter for Grubhub Deliveries API.\n    resources:\n    - path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery\n\
  \      name: getdeliverystatus\n      operations:\n      - method: GET\n        name: getdeliverystatus\n        description: Get delivery status for an order\n        call: grubhub.getdeliverystatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pos/v1/merchant/{merchant_long_id}/orders/{order_uuid}/delivery/proxy-phone\n      name: createproxycourierphone\n      operations:\n      - method: POST\n        name: createproxycourierphone\n        description: Create proxy courier phone number\n        call: grubhub.createproxycourierphone\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grubhub-mcp\n    transport: http\n    description: MCP adapter for Grubhub Deliveries API for AI agent use.\n    tools:\n    - name: getdeliverystatus\n      description: Get delivery status for an order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: grubhub.getdeliverystatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproxycourierphone\n      description: Create proxy courier phone number\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grubhub.createproxycourierphone\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GRUBHUB_TOKEN: GRUBHUB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grubhub/refs/heads/main/capabilities/grubhub-capability.yaml
tags:
- Grubhub
- API
tools:
- description: Get delivery status for an order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeliverystatus
- description: Create proxy courier phone number
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproxycourierphone
---
