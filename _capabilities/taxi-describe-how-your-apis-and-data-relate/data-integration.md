---
categories: []
consumed_apis: []
description: Workflow capability for schema-driven data integration using the Taxi language. Covers schema authoring, TaxiQL query execution, type and service discovery, and conversion of existing API specs to Taxi format. Designed for API platform teams, data engineers, and integration developers.
layout: capability
name: Taxi Data Integration
operations:
- description: List all registered Taxi schemas
  method: GET
  name: list-schemas
  path: /v1/schemas
- description: Register a Taxi schema
  method: POST
  name: register-schema
  path: /v1/schemas
- description: Compile a Taxi schema and return types and validation errors
  method: POST
  name: compile-schema
  path: /v1/schemas/compile
- description: Execute a TaxiQL query across registered data sources
  method: POST
  name: execute-query
  path: /v1/queries
- description: List all types
  method: GET
  name: list-types
  path: /v1/types
- description: List all registered services
  method: GET
  name: list-services
  path: /v1/services
- description: Convert OpenAPI to Taxi schema
  method: POST
  name: convert-from-openapi
  path: /v1/convert/openapi
personas: []
provider_name: Taxi - Describe How Your APIs and Data Relate
provider_slug: taxi-describe-how-your-apis-and-data-relate
search_terms:
- schema registry — list and register taxi schemas
- list types
- list services
- compile a taxi schema and return types and validation errors
- query language
- taxiql
- compile schema
- semantic
- api description
- execute taxiql query
- register a taxi schema
- list all registered services
- convert openapi to taxi
- open source
- schema registry
- list all registered taxi schemas in the registry
- list all types
- service registry
- semantic types
- type discovery across registered schemas
- list all api services registered with semantic annotations in the schema registry
- convert openapi to taxi schema
- convert openapi specs to taxi
- execute a taxiql query across registered data sources
- execute a taxiql query — taxi automatically discovers api call paths and assembles results
- compile and validate taxi schemas
- execute query
- convert from openapi
- list all registered taxi schemas
- register a new taxi schema in the registry
- discover types
- register schema
- discover all semantic types defined across registered taxi schemas
- convert an existing openapi specification to taxi schema format with semantic type annotations
- compile and validate a taxi schema, returning parsed types and any errors
- compile taxi schema
- data integration
- taxiql federated query execution
- list schemas
- schema
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Taxi Data Integration\n  description: Workflow capability for schema-driven data integration using the Taxi language. Covers schema authoring, TaxiQL\n    query execution, type and service discovery, and conversion of existing API specs to Taxi format. Designed for API platform\n    teams, data engineers, and integration developers.\n  tags:\n  - API Description\n  - Data Integration\n  - Open Source\n  - Schema Registry\n  - Semantic Types\n  - TaxiQL\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TAXI_API_KEY: TAXI_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: taxi-api\n    baseUri: https://api.taxilang.org\n    description: Taxi language API for schema management and query execution\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{TAXI_API_KEY}}'\n      placement: header\n    resources:\n    - name: schemas\n      path: /schemas\n      description:\
  \ Schema registry operations\n      operations:\n      - name: list-schemas\n        method: GET\n        description: List all registered Taxi schemas\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter by namespace\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: register-schema\n        method: POST\n        description: Register a new Taxi schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            content: '{{tools.content}}'\n            version: '{{tools.version}}'\n    - name:\
  \ compile\n      path: /schemas/compile\n      description: Schema compilation and validation\n      operations:\n      - name: compile-schema\n        method: POST\n        description: Compile and validate a Taxi schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n    - name: queries\n      path: /queries\n      description: TaxiQL query execution\n      operations:\n      - name: execute-query\n        method: POST\n        description: Execute a TaxiQL query across registered data sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            facts: '{{tools.facts}}'\n    - name: types\n      path: /types\n      description: Type registry\n\
  \      operations:\n      - name: list-types\n        method: GET\n        description: List all types across registered schemas\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          required: false\n          description: Filter by namespace\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by type name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      description: Service registry\n      operations:\n      - name: list-services\n        method: GET\n        description: List all registered services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: convert-openapi\n      path: /convert/openapi\n      description: Convert OpenAPI to Taxi\n \
  \     operations:\n      - name: convert-from-openapi\n        method: POST\n        description: Convert an OpenAPI spec to Taxi schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            spec_content: '{{tools.spec_content}}'\n            namespace: '{{tools.namespace}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: taxi-data-integration-api\n    description: Unified REST API for Taxi-driven data integration workflows.\n    resources:\n    - path: /v1/schemas\n      name: schemas\n      description: Schema registry — list and register Taxi schemas\n      operations:\n      - method: GET\n        name: list-schemas\n        description: List all registered Taxi schemas\n        call: taxi-api.list-schemas\n        with:\n          namespace: rest.namespace\n          limit: rest.limit\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: register-schema\n        description: Register a Taxi schema\n        call: taxi-api.register-schema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schemas/compile\n      name: schema-compile\n      description: Compile and validate Taxi schemas\n      operations:\n      - method: POST\n        name: compile-schema\n        description: Compile a Taxi schema and return types and validation errors\n        call: taxi-api.compile-schema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries\n      name: queries\n      description: TaxiQL federated query execution\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute a TaxiQL query across registered data sources\n        call: taxi-api.execute-query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/types\n \
  \     name: types\n      description: Type discovery across registered schemas\n      operations:\n      - method: GET\n        name: list-types\n        description: List all types\n        call: taxi-api.list-types\n        with:\n          namespace: rest.namespace\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: services\n      description: Service registry\n      operations:\n      - method: GET\n        name: list-services\n        description: List all registered services\n        call: taxi-api.list-services\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/convert/openapi\n      name: openapi-conversion\n      description: Convert OpenAPI specs to Taxi\n      operations:\n      - method: POST\n        name: convert-from-openapi\n        description: Convert OpenAPI to Taxi schema\n        call: taxi-api.convert-from-openapi\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: taxi-data-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Taxi schema authoring and data integration.\n    tools:\n    - name: list-schemas\n      description: List all registered Taxi schemas in the registry\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taxi-api.list-schemas\n      with:\n        namespace: tools.namespace\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compile-taxi-schema\n      description: Compile and validate a Taxi schema, returning parsed types and any errors\n      hints:\n        readOnly: true\n        openWorld: false\n      call: taxi-api.compile-schema\n      with:\n        content: tools.content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-schema\n      description: Register a new Taxi schema in\
  \ the registry\n      hints:\n        readOnly: false\n        openWorld: false\n      call: taxi-api.register-schema\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-taxiql-query\n      description: Execute a TaxiQL query — Taxi automatically discovers API call paths and assembles results\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taxi-api.execute-query\n      with:\n        query: tools.query\n        facts: tools.facts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-types\n      description: Discover all semantic types defined across registered Taxi schemas\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taxi-api.list-types\n      with:\n        namespace: tools.namespace\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: List all API services registered\
  \ with semantic annotations in the schema registry\n      hints:\n        readOnly: true\n        openWorld: true\n      call: taxi-api.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: convert-openapi-to-taxi\n      description: Convert an existing OpenAPI specification to Taxi schema format with semantic type annotations\n      hints:\n        readOnly: false\n        openWorld: false\n      call: taxi-api.convert-from-openapi\n      with:\n        spec_content: tools.spec_content\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/taxi-describe-how-your-apis-and-data-relate/refs/heads/main/capabilities/data-integration.yaml
tags:
- API Description
- Data Integration
- Open Source
- Schema Registry
- Semantic Types
- TaxiQL
tools:
- description: List all registered Taxi schemas in the registry
  hints:
    openWorld: true
    readOnly: true
  name: list-schemas
- description: Compile and validate a Taxi schema, returning parsed types and any errors
  hints:
    openWorld: false
    readOnly: true
  name: compile-taxi-schema
- description: Register a new Taxi schema in the registry
  hints:
    openWorld: false
    readOnly: false
  name: register-schema
- description: Execute a TaxiQL query — Taxi automatically discovers API call paths and assembles results
  hints:
    openWorld: true
    readOnly: true
  name: execute-taxiql-query
- description: Discover all semantic types defined across registered Taxi schemas
  hints:
    openWorld: true
    readOnly: true
  name: discover-types
- description: List all API services registered with semantic annotations in the schema registry
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Convert an existing OpenAPI specification to Taxi schema format with semantic type annotations
  hints:
    openWorld: false
    readOnly: false
  name: convert-openapi-to-taxi
---
