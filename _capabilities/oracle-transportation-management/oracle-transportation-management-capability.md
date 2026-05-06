---
categories: []
consumed_apis: []
description: Oracle Transportation Management (OTM) Business Object Resources REST API provides programmatic access to shipment orders, carriers, lanes, rates, transportation plans, and logistics data in Oracle Fusion Cloud Transportation and Global Trade Management.
layout: capability
name: Oracle Transportation Management Business Object Resources REST API
operations:
- description: List shipment orders
  method: GET
  name: listshipmentorders
  path: /shipment-orders
- description: Create a shipment order
  method: POST
  name: createshipmentorder
  path: /shipment-orders
- description: Get a shipment order
  method: GET
  name: getshipmentorder
  path: /shipment-orders/{gid}
- description: Update a shipment order
  method: PUT
  name: updateshipmentorder
  path: /shipment-orders/{gid}
- description: Delete a shipment order
  method: DELETE
  name: deleteshipmentorder
  path: /shipment-orders/{gid}
- description: List carriers
  method: GET
  name: listcarriers
  path: /carriers
- description: Get a carrier
  method: GET
  name: getcarrier
  path: /carriers/{gid}
- description: List locations
  method: GET
  name: listlocations
  path: /locations
- description: List rate records
  method: GET
  name: listrates
  path: /rates
personas: []
provider_name: Oracle Transportation Management
provider_slug: oracle-transportation-management
search_terms:
- logistics
- delete a shipment order
- create a shipment order
- update a shipment order
- createshipmentorder
- list locations
- updateshipmentorder
- listrates
- freight
- supply chain
- transportation
- oracle
- global trade
- getcarrier
- shipping
- api
- listcarriers
- list carriers
- get a carrier
- deleteshipmentorder
- listlocations
- list shipment orders
- listshipmentorders
- management
- list rate records
- getshipmentorder
- get a shipment order
slug: oracle-transportation-management-capability
source_filename: oracle-transportation-management-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Transportation Management Business Object Resources REST API\n  description: Oracle Transportation Management (OTM) Business Object Resources REST API provides programmatic access to shipment\n    orders, carriers, lanes, rates, transportation plans, and logistics data in Oracle Fusion Cloud Transportation and Global\n    Trade Management.\n  tags:\n  - Oracle\n  - Transportation\n  - Management\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-transportation-management\n    baseUri: https://otm.example.com/GC3/glog.integration.servlet.WMServlet/otm/rest/v1\n    description: Oracle Transportation Management Business Object Resources REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_TRANSPORTATION_MANAGEMENT_TOKEN}}'\n    resources:\n    - name: shipment-orders\n      path: /shipment-orders\n      operations:\n      - name:\
  \ listshipmentorders\n        method: GET\n        description: List shipment orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by order status\n        - name: startDate\n          in: query\n          type: string\n          description: Early pickup date filter (ISO 8601)\n        - name: endDate\n          in: query\n          type: string\n        - name: sourceLocationGid\n          in: query\n          type: string\n          description: Filter by origin location GID\n        - name: destLocationGid\n          in: query\n          type: string\n          description: Filter by destination location GID\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createshipmentorder\n\
  \        method: POST\n        description: Create a shipment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shipment-orders-gid\n      path: /shipment-orders/{gid}\n      operations:\n      - name: getshipmentorder\n        method: GET\n        description: Get a shipment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateshipmentorder\n        method: PUT\n        description: Update a shipment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteshipmentorder\n        method: DELETE\n        description: Delete a shipment order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers\n      path:\
  \ /carriers\n      operations:\n      - name: listcarriers\n        method: GET\n        description: List carriers\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: carriers-gid\n      path: /carriers/{gid}\n      operations:\n      - name: getcarrier\n        method: GET\n        description: Get a carrier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: List locations\n        inputParameters:\n        - name: locationType\n          in: query\n       \
  \   type: string\n        - name: country\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rates\n      path: /rates\n      operations:\n      - name: listrates\n        method: GET\n        description: List rate records\n        inputParameters:\n        - name: carrierGid\n          in: query\n          type: string\n        - name: effectiveDate\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-transportation-management-rest\n\
  \    description: REST adapter for Oracle Transportation Management Business Object Resources REST API.\n    resources:\n    - path: /shipment-orders\n      name: listshipmentorders\n      operations:\n      - method: GET\n        name: listshipmentorders\n        description: List shipment orders\n        call: oracle-transportation-management.listshipmentorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipment-orders\n      name: createshipmentorder\n      operations:\n      - method: POST\n        name: createshipmentorder\n        description: Create a shipment order\n        call: oracle-transportation-management.createshipmentorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipment-orders/{gid}\n      name: getshipmentorder\n      operations:\n      - method: GET\n        name: getshipmentorder\n        description: Get a shipment order\n        call: oracle-transportation-management.getshipmentorder\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipment-orders/{gid}\n      name: updateshipmentorder\n      operations:\n      - method: PUT\n        name: updateshipmentorder\n        description: Update a shipment order\n        call: oracle-transportation-management.updateshipmentorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shipment-orders/{gid}\n      name: deleteshipmentorder\n      operations:\n      - method: DELETE\n        name: deleteshipmentorder\n        description: Delete a shipment order\n        call: oracle-transportation-management.deleteshipmentorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /carriers\n      name: listcarriers\n      operations:\n      - method: GET\n        name: listcarriers\n        description: List carriers\n        call: oracle-transportation-management.listcarriers\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /carriers/{gid}\n      name: getcarrier\n      operations:\n      - method: GET\n        name: getcarrier\n        description: Get a carrier\n        call: oracle-transportation-management.getcarrier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: List locations\n        call: oracle-transportation-management.listlocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /rates\n      name: listrates\n      operations:\n      - method: GET\n        name: listrates\n        description: List rate records\n        call: oracle-transportation-management.listrates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-transportation-management-mcp\n    transport: http\n    description:\
  \ MCP adapter for Oracle Transportation Management Business Object Resources REST API for AI agent use.\n    tools:\n    - name: listshipmentorders\n      description: List shipment orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.listshipmentorders\n      with:\n        status: tools.status\n        startDate: tools.startDate\n        endDate: tools.endDate\n        sourceLocationGid: tools.sourceLocationGid\n        destLocationGid: tools.destLocationGid\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by order status\n      - name: startDate\n        type: string\n        description: Early pickup date filter (ISO 8601)\n      - name: endDate\n        type: string\n        description: endDate\n      - name: sourceLocationGid\n        type: string\n        description: Filter by origin\
  \ location GID\n      - name: destLocationGid\n        type: string\n        description: Filter by destination location GID\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createshipmentorder\n      description: Create a shipment order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-transportation-management.createshipmentorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshipmentorder\n      description: Get a shipment order\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.getshipmentorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateshipmentorder\n      description: Update a\
  \ shipment order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.updateshipmentorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteshipmentorder\n      description: Delete a shipment order\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-transportation-management.deleteshipmentorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcarriers\n      description: List carriers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.listcarriers\n      with:\n        status: tools.status\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: offset\n        type: integer\n\
  \        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcarrier\n      description: Get a carrier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.getcarrier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocations\n      description: List locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.listlocations\n      with:\n        locationType: tools.locationType\n        country: tools.country\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: locationType\n        type: string\n        description: locationType\n      - name: country\n        type: string\n        description: country\n      - name:\
  \ offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrates\n      description: List rate records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-transportation-management.listrates\n      with:\n        carrierGid: tools.carrierGid\n        effectiveDate: tools.effectiveDate\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: carrierGid\n        type: string\n        description: carrierGid\n      - name: effectiveDate\n        type: string\n        description: effectiveDate\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n\
  \    ORACLE_TRANSPORTATION_MANAGEMENT_TOKEN: ORACLE_TRANSPORTATION_MANAGEMENT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-transportation-management/refs/heads/main/capabilities/oracle-transportation-management-capability.yaml
tags:
- Oracle
- Transportation
- Management
- API
tools:
- description: List shipment orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshipmentorders
- description: Create a shipment order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createshipmentorder
- description: Get a shipment order
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshipmentorder
- description: Update a shipment order
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateshipmentorder
- description: Delete a shipment order
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteshipmentorder
- description: List carriers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcarriers
- description: Get a carrier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcarrier
- description: List locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: List rate records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrates
---
