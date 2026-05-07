---
categories: []
consumed_apis: []
description: The Keen Cached Queries API allows developers to create, manage, and retrieve pre-defined queries that are automatically refreshed on a schedule. Cached queries improve performance for frequently accessed analytics by storing pre-computed results, making them ideal for powering dashboards and embedded analytics experiences without incurring per-request rate limits.
layout: capability
name: Keen Cached Queries API
operations:
- description: Keen List cached queries
  method: GET
  name: listcachedqueries
  path: /projects/{projectId}/queries/cached
- description: Keen Get a cached query
  method: GET
  name: getcachedquery
  path: /projects/{projectId}/queries/cached/{queryName}
- description: Keen Create or update a cached query
  method: PUT
  name: createorupdatecachedquery
  path: /projects/{projectId}/queries/cached/{queryName}
- description: Keen Delete a cached query
  method: DELETE
  name: deletecachedquery
  path: /projects/{projectId}/queries/cached/{queryName}
- description: Keen Get cached query result
  method: GET
  name: getcachedqueryresult
  path: /projects/{projectId}/queries/cached/{queryName}/result
personas: []
provider_name: Keen
provider_slug: keen
search_terms:
- getcachedqueryresult
- analytics
- keen
- keen create or update a cached query
- keen delete a cached query
- listcachedqueries
- createorupdatecachedquery
- data collection
- deletecachedquery
- keen get cached query result
- custom events
- event analytics
- getcachedquery
- api
- keen list cached queries
- embedded analytics
- keen get a cached query
slug: keen-capability
source_filename: keen-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Keen Cached Queries API\n  description: The Keen Cached Queries API allows developers to create, manage, and retrieve pre-defined queries that are\n    automatically refreshed on a schedule. Cached queries improve performance for frequently accessed analytics by storing\n    pre-computed results, making them ideal for powering dashboards and embedded analytics experiences without incurring per-request\n    rate limits.\n  tags:\n  - Keen\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: keen\n    baseUri: https://api.keen.io/3.0\n    description: Keen Cached Queries API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{KEEN_TOKEN}}'\n    resources:\n    - name: projects-projectid-queries-cached\n      path: /projects/{projectId}/queries/cached\n      operations:\n      - name: listcachedqueries\n        method:\
  \ GET\n        description: Keen List cached queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-queries-cached-queryname\n      path: /projects/{projectId}/queries/cached/{queryName}\n      operations:\n      - name: getcachedquery\n        method: GET\n        description: Keen Get a cached query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorupdatecachedquery\n        method: PUT\n        description: Keen Create or update a cached query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecachedquery\n        method: DELETE\n        description: Keen Delete a cached query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: projects-projectid-queries-cached-queryname-resu\n      path: /projects/{projectId}/queries/cached/{queryName}/result\n      operations:\n      - name: getcachedqueryresult\n        method: GET\n        description: Keen Get cached query result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: keen-rest\n    description: REST adapter for Keen Cached Queries API.\n    resources:\n    - path: /projects/{projectId}/queries/cached\n      name: listcachedqueries\n      operations:\n      - method: GET\n        name: listcachedqueries\n        description: Keen List cached queries\n        call: keen.listcachedqueries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries/cached/{queryName}\n      name: getcachedquery\n      operations:\n      - method: GET\n   \
  \     name: getcachedquery\n        description: Keen Get a cached query\n        call: keen.getcachedquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries/cached/{queryName}\n      name: createorupdatecachedquery\n      operations:\n      - method: PUT\n        name: createorupdatecachedquery\n        description: Keen Create or update a cached query\n        call: keen.createorupdatecachedquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries/cached/{queryName}\n      name: deletecachedquery\n      operations:\n      - method: DELETE\n        name: deletecachedquery\n        description: Keen Delete a cached query\n        call: keen.deletecachedquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/queries/cached/{queryName}/result\n      name: getcachedqueryresult\n      operations:\n   \
  \   - method: GET\n        name: getcachedqueryresult\n        description: Keen Get cached query result\n        call: keen.getcachedqueryresult\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: keen-mcp\n    transport: http\n    description: MCP adapter for Keen Cached Queries API for AI agent use.\n    tools:\n    - name: listcachedqueries\n      description: Keen List cached queries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keen.listcachedqueries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcachedquery\n      description: Keen Get a cached query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keen.getcachedquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorupdatecachedquery\n      description: Keen Create or update\
  \ a cached query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: keen.createorupdatecachedquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecachedquery\n      description: Keen Delete a cached query\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: keen.deletecachedquery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcachedqueryresult\n      description: Keen Get cached query result\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: keen.getcachedqueryresult\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KEEN_TOKEN: KEEN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/keen/refs/heads/main/capabilities/keen-capability.yaml
tags:
- Keen
- API
tools:
- description: Keen List cached queries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcachedqueries
- description: Keen Get a cached query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcachedquery
- description: Keen Create or update a cached query
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorupdatecachedquery
- description: Keen Delete a cached query
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecachedquery
- description: Keen Get cached query result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcachedqueryresult
---
