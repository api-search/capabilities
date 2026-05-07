---
categories: []
consumed_apis: []
description: The DoorDash Drive Classic API is the legacy version of the Drive API, designed for large enterprises and middleware providers who require extensive configuration and customizability for their delivery integrations. It provides endpoints for managing businesses, stores, and deliveries through DoorDash's logistics platform. While still supported, DoorDash recommends new integrations use the newer Drive API (v2) instead.
layout: capability
name: DoorDash Drive Classic API
operations:
- description: Create a delivery estimate
  method: POST
  name: createdeliveryestimate
  path: /estimates
- description: Create a delivery
  method: POST
  name: createdelivery
  path: /deliveries
- description: Get delivery details
  method: GET
  name: getdelivery
  path: /deliveries/{external_delivery_id}
- description: Update a delivery
  method: PATCH
  name: updatedelivery
  path: /deliveries/{external_delivery_id}
- description: Cancel a delivery
  method: PUT
  name: canceldelivery
  path: /deliveries/{external_delivery_id}/cancel
- description: List businesses
  method: GET
  name: listbusinesses
  path: /businesses
- description: Create a business
  method: POST
  name: createbusiness
  path: /businesses
- description: Get business details
  method: GET
  name: getbusiness
  path: /businesses/{external_business_id}
- description: Update a business
  method: PATCH
  name: updatebusiness
  path: /businesses/{external_business_id}
- description: Create a store
  method: POST
  name: createstore
  path: /businesses/{external_business_id}/stores
- description: Get store details
  method: GET
  name: getstore
  path: /businesses/{external_business_id}/stores/{external_store_id}
- description: Update a store
  method: PATCH
  name: updatestore
  path: /businesses/{external_business_id}/stores/{external_store_id}
personas: []
provider_name: doordash
provider_slug: doordash
search_terms:
- create a business
- canceldelivery
- getdelivery
- get store details
- list businesses
- update a delivery
- api
- getbusiness
- listbusinesses
- update a business
- doordash
- get delivery details
- createdelivery
- createstore
- create a store
- updatebusiness
- createbusiness
- getstore
- create a delivery estimate
- get business details
- cancel a delivery
- createdeliveryestimate
- create a delivery
- updatestore
- update a store
- updatedelivery
slug: doordash-capability
source_filename: doordash-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: DoorDash Drive Classic API\n  description: The DoorDash Drive Classic API is the legacy version of the Drive API, designed for large enterprises and middleware\n    providers who require extensive configuration and customizability for their delivery integrations. It provides endpoints\n    for managing businesses, stores, and deliveries through DoorDash's logistics platform. While still supported, DoorDash\n    recommends new integrations use the newer Drive API (v2) instead.\n  tags:\n  - Doordash\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: doordash\n    baseUri: https://openapi.doordash.com/drive/v1\n    description: DoorDash Drive Classic API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DOORDASH_TOKEN}}'\n    resources:\n    - name: estimates\n      path: /estimates\n      operations:\n      - name: createdeliveryestimate\n        method:\
  \ POST\n        description: Create a delivery estimate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deliveries\n      path: /deliveries\n      operations:\n      - name: createdelivery\n        method: POST\n        description: Create a delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deliveries-external-delivery-id\n      path: /deliveries/{external_delivery_id}\n      operations:\n      - name: getdelivery\n        method: GET\n        description: Get delivery details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedelivery\n        method: PATCH\n        description: Update a delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: deliveries-external-delivery-id-cancel\n      path: /deliveries/{external_delivery_id}/cancel\n      operations:\n      - name: canceldelivery\n        method: PUT\n        description: Cancel a delivery\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses\n      path: /businesses\n      operations:\n      - name: listbusinesses\n        method: GET\n        description: List businesses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbusiness\n        method: POST\n        description: Create a business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses-external-business-id\n      path: /businesses/{external_business_id}\n      operations:\n      - name: getbusiness\n\
  \        method: GET\n        description: Get business details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebusiness\n        method: PATCH\n        description: Update a business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses-external-business-id-stores\n      path: /businesses/{external_business_id}/stores\n      operations:\n      - name: createstore\n        method: POST\n        description: Create a store\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: businesses-external-business-id-stores-external-\n      path: /businesses/{external_business_id}/stores/{external_store_id}\n      operations:\n      - name: getstore\n        method: GET\n        description: Get store details\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatestore\n        method: PATCH\n        description: Update a store\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: doordash-rest\n    description: REST adapter for DoorDash Drive Classic API.\n    resources:\n    - path: /estimates\n      name: createdeliveryestimate\n      operations:\n      - method: POST\n        name: createdeliveryestimate\n        description: Create a delivery estimate\n        call: doordash.createdeliveryestimate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deliveries\n      name: createdelivery\n      operations:\n      - method: POST\n        name: createdelivery\n        description: Create a delivery\n        call: doordash.createdelivery\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deliveries/{external_delivery_id}\n      name: getdelivery\n      operations:\n      - method: GET\n        name: getdelivery\n        description: Get delivery details\n        call: doordash.getdelivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deliveries/{external_delivery_id}\n      name: updatedelivery\n      operations:\n      - method: PATCH\n        name: updatedelivery\n        description: Update a delivery\n        call: doordash.updatedelivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /deliveries/{external_delivery_id}/cancel\n      name: canceldelivery\n      operations:\n      - method: PUT\n        name: canceldelivery\n        description: Cancel a delivery\n        call: doordash.canceldelivery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses\n\
  \      name: listbusinesses\n      operations:\n      - method: GET\n        name: listbusinesses\n        description: List businesses\n        call: doordash.listbusinesses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses\n      name: createbusiness\n      operations:\n      - method: POST\n        name: createbusiness\n        description: Create a business\n        call: doordash.createbusiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{external_business_id}\n      name: getbusiness\n      operations:\n      - method: GET\n        name: getbusiness\n        description: Get business details\n        call: doordash.getbusiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{external_business_id}\n      name: updatebusiness\n      operations:\n      - method: PATCH\n        name: updatebusiness\n        description: Update a business\n\
  \        call: doordash.updatebusiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{external_business_id}/stores\n      name: createstore\n      operations:\n      - method: POST\n        name: createstore\n        description: Create a store\n        call: doordash.createstore\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{external_business_id}/stores/{external_store_id}\n      name: getstore\n      operations:\n      - method: GET\n        name: getstore\n        description: Get store details\n        call: doordash.getstore\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /businesses/{external_business_id}/stores/{external_store_id}\n      name: updatestore\n      operations:\n      - method: PATCH\n        name: updatestore\n        description: Update a store\n        call: doordash.updatestore\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: doordash-mcp\n    transport: http\n    description: MCP adapter for DoorDash Drive Classic API for AI agent use.\n    tools:\n    - name: createdeliveryestimate\n      description: Create a delivery estimate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.createdeliveryestimate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdelivery\n      description: Create a delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.createdelivery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdelivery\n      description: Get delivery details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doordash.getdelivery\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: updatedelivery\n      description: Update a delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.updatedelivery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: canceldelivery\n      description: Cancel a delivery\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: doordash.canceldelivery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbusinesses\n      description: List businesses\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doordash.listbusinesses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbusiness\n      description: Create a business\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.createbusiness\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbusiness\n      description: Get business details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doordash.getbusiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebusiness\n      description: Update a business\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.updatebusiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstore\n      description: Create a store\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.createstore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstore\n      description: Get store details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: doordash.getstore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatestore\n      description: Update a store\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doordash.updatestore\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DOORDASH_TOKEN: DOORDASH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/doordash/refs/heads/main/capabilities/doordash-capability.yaml
tags:
- Doordash
- API
tools:
- description: Create a delivery estimate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeliveryestimate
- description: Create a delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdelivery
- description: Get delivery details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdelivery
- description: Update a delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedelivery
- description: Cancel a delivery
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: canceldelivery
- description: List businesses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbusinesses
- description: Create a business
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbusiness
- description: Get business details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbusiness
- description: Update a business
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebusiness
- description: Create a store
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstore
- description: Get store details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstore
- description: Update a store
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatestore
---
