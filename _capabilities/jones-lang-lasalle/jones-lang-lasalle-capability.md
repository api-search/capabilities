---
categories: []
consumed_apis: []
description: The JLL Corrigo Enterprise REST API provides programmatic access to JLL Technologies' cloud-based facility management platform. The API enables integration with work order management, asset tracking, procurement, billing, and vendor management systems.
layout: capability
name: JLL Corrigo Enterprise REST API
operations:
- description: Query work orders
  method: POST
  name: queryworkorders
  path: /query/WorkOrder
- description: Create a work order
  method: POST
  name: createworkorder
  path: /command/WorkOrder
- description: Query assets
  method: POST
  name: queryassets
  path: /query/Asset
- description: Query contacts
  method: POST
  name: querycontacts
  path: /query/Contact
- description: Query locations
  method: POST
  name: querylocations
  path: /query/Location
personas: []
provider_name: Jones Lang LaSalle
provider_slug: jones-lang-lasalle
search_terms:
- create a work order
- queryassets
- asset management
- query work orders
- queryworkorders
- createworkorder
- query assets
- query contacts
- jones
- commercial real estate
- facility management
- lang
- api
- work orders
- querycontacts
- lasalle
- querylocations
- query locations
slug: jones-lang-lasalle-capability
source_filename: jones-lang-lasalle-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JLL Corrigo Enterprise REST API\n  description: The JLL Corrigo Enterprise REST API provides programmatic access to JLL Technologies' cloud-based facility\n    management platform. The API enables integration with work order management, asset tracking, procurement, billing, and\n    vendor management systems.\n  tags:\n  - Jones\n  - Lang\n  - Lasalle\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jones-lang-lasalle\n    baseUri: https://am-ce98c.corrigo.com/api/v1\n    description: JLL Corrigo Enterprise REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JONES_LANG_LASALLE_TOKEN}}'\n    resources:\n    - name: query-workorder\n      path: /query/WorkOrder\n      operations:\n      - name: queryworkorders\n        method: POST\n        description: Query work orders\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: command-workorder\n      path: /command/WorkOrder\n      operations:\n      - name: createworkorder\n        method: POST\n        description: Create a work order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-asset\n      path: /query/Asset\n      operations:\n      - name: queryassets\n        method: POST\n        description: Query assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-contact\n      path: /query/Contact\n      operations:\n      - name: querycontacts\n        method: POST\n        description: Query contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-location\n      path: /query/Location\n      operations:\n\
  \      - name: querylocations\n        method: POST\n        description: Query locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jones-lang-lasalle-rest\n    description: REST adapter for JLL Corrigo Enterprise REST API.\n    resources:\n    - path: /query/WorkOrder\n      name: queryworkorders\n      operations:\n      - method: POST\n        name: queryworkorders\n        description: Query work orders\n        call: jones-lang-lasalle.queryworkorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /command/WorkOrder\n      name: createworkorder\n      operations:\n      - method: POST\n        name: createworkorder\n        description: Create a work order\n        call: jones-lang-lasalle.createworkorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /query/Asset\n\
  \      name: queryassets\n      operations:\n      - method: POST\n        name: queryassets\n        description: Query assets\n        call: jones-lang-lasalle.queryassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /query/Contact\n      name: querycontacts\n      operations:\n      - method: POST\n        name: querycontacts\n        description: Query contacts\n        call: jones-lang-lasalle.querycontacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /query/Location\n      name: querylocations\n      operations:\n      - method: POST\n        name: querylocations\n        description: Query locations\n        call: jones-lang-lasalle.querylocations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jones-lang-lasalle-mcp\n    transport: http\n    description: MCP adapter for JLL Corrigo Enterprise REST API for AI agent use.\n  \
  \  tools:\n    - name: queryworkorders\n      description: Query work orders\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jones-lang-lasalle.queryworkorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkorder\n      description: Create a work order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jones-lang-lasalle.createworkorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: queryassets\n      description: Query assets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jones-lang-lasalle.queryassets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querycontacts\n      description: Query contacts\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jones-lang-lasalle.querycontacts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querylocations\n      description: Query locations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jones-lang-lasalle.querylocations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JONES_LANG_LASALLE_TOKEN: JONES_LANG_LASALLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jones-lang-lasalle/refs/heads/main/capabilities/jones-lang-lasalle-capability.yaml
tags:
- Jones
- Lang
- Lasalle
- API
tools:
- description: Query work orders
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryworkorders
- description: Create a work order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkorder
- description: Query assets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryassets
- description: Query contacts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querycontacts
- description: Query locations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querylocations
---
