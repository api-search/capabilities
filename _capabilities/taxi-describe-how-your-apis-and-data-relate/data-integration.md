---
categories: []
consumed_apis:
- taxi-api
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
- taxiql federated query execution
- list services
- compile and validate a taxi schema, returning parsed types and any errors
- convert openapi to taxi
- list all registered services
- discover types
- open source
- list all registered taxi schemas
- semantic types
- register schema
- schema
- api description
- execute query
- register a new taxi schema in the registry
- list all api services registered with semantic annotations in the schema registry
- discover all semantic types defined across registered taxi schemas
- compile a taxi schema and return types and validation errors
- compile and validate taxi schemas
- list types
- convert openapi specs to taxi
- execute a taxiql query — taxi automatically discovers api call paths and assembles results
- execute a taxiql query across registered data sources
- register a taxi schema
- taxiql
- compile taxi schema
- data integration
- convert openapi to taxi schema
- list schemas
- list all types
- list all registered taxi schemas in the registry
- semantic
- schema registry
- execute taxiql query
- convert from openapi
- type discovery across registered schemas
- convert an existing openapi specification to taxi schema format with semantic type annotations
- compile schema
- service registry
- query language
- schema registry — list and register taxi schemas
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Taxi Data Integration\"\n  description: >-\n    Workflow capability for schema-driven data integration using the Taxi language.\n    Covers schema authoring, TaxiQL query execution, type and service discovery,\n    and conversion of existing API specs to Taxi format. Designed for API platform\n    teams, data engineers, and integration developers.\n  tags:\n    - API Description\n    - Data Integration\n    - Open Source\n    - Schema Registry\n    - Semantic Types\n    - TaxiQL\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TAXI_API_KEY: TAXI_API_KEY\n\ncapability:\n  consumes:\n    - import: taxi-api\n      location: ./shared/taxi-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: taxi-data-integration-api\n      description: \"Unified REST API for Taxi-driven data integration workflows.\"\n      resources:\n        - path: /v1/schemas\n       \
  \   name: schemas\n          description: \"Schema registry — list and register Taxi schemas\"\n          operations:\n            - method: GET\n              name: list-schemas\n              description: \"List all registered Taxi schemas\"\n              call: \"taxi-api.list-schemas\"\n              with:\n                namespace: \"rest.namespace\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: register-schema\n              description: \"Register a Taxi schema\"\n              call: \"taxi-api.register-schema\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/schemas/compile\n          name: schema-compile\n          description: \"Compile and validate Taxi schemas\"\n          operations:\n            - method: POST\n              name: compile-schema\n            \
  \  description: \"Compile a Taxi schema and return types and validation errors\"\n              call: \"taxi-api.compile-schema\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: \"TaxiQL federated query execution\"\n          operations:\n            - method: POST\n              name: execute-query\n              description: \"Execute a TaxiQL query across registered data sources\"\n              call: \"taxi-api.execute-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/types\n          name: types\n          description: \"Type discovery across registered schemas\"\n          operations:\n            - method: GET\n              name: list-types\n              description: \"List all types\"\n              call: \"taxi-api.list-types\"\n              with:\n                namespace:\
  \ \"rest.namespace\"\n                search: \"rest.search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"Service registry\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"List all registered services\"\n              call: \"taxi-api.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/convert/openapi\n          name: openapi-conversion\n          description: \"Convert OpenAPI specs to Taxi\"\n          operations:\n            - method: POST\n              name: convert-from-openapi\n              description: \"Convert OpenAPI to Taxi schema\"\n              call: \"taxi-api.convert-from-openapi\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \n    - type: mcp\n      port: 9081\n      namespace: taxi-data-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Taxi schema authoring and data integration.\"\n      tools:\n        - name: list-schemas\n          description: \"List all registered Taxi schemas in the registry\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"taxi-api.list-schemas\"\n          with:\n            namespace: \"tools.namespace\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: compile-taxi-schema\n          description: \"Compile and validate a Taxi schema, returning parsed types and any errors\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"taxi-api.compile-schema\"\n          with:\n            content: \"tools.content\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n        - name: register-schema\n          description: \"Register a new Taxi schema in the registry\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"taxi-api.register-schema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-taxiql-query\n          description: \"Execute a TaxiQL query — Taxi automatically discovers API call paths and assembles results\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"taxi-api.execute-query\"\n          with:\n            query: \"tools.query\"\n            facts: \"tools.facts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-types\n          description: \"Discover all semantic types defined across registered Taxi schemas\"\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"taxi-api.list-types\"\n          with:\n            namespace: \"tools.namespace\"\n            search: \"tools.search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-services\n          description: \"List all API services registered with semantic annotations in the schema registry\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"taxi-api.list-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: convert-openapi-to-taxi\n          description: \"Convert an existing OpenAPI specification to Taxi schema format with semantic type annotations\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"taxi-api.convert-from-openapi\"\n          with:\n            spec_content: \"tools.spec_content\"\n            namespace: \"tools.namespace\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
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
