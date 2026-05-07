---
categories: []
consumed_apis: []
description: The Fauna Core HTTP API provides direct access to the Fauna serverless document database through HTTPS endpoints. It allows developers to execute Fauna Query Language (FQL) queries, manage databases, perform CRUD operations on documents, manage schema as FSL files, and consume change data capture events via event feeds. The API uses token-based authentication and supports features such as transactions, indexes, and set operations. It serves as the foundation upon which Fauna's client drivers and SDKs are built.
layout: capability
name: Fauna Core HTTP API
operations:
- description: Execute an FQL query
  method: POST
  name: executequery
  path: /query/1
- description: Poll an event feed
  method: POST
  name: polleventfeed
  path: /feed/1
- description: Get schema files
  method: GET
  name: getschemafiles
  path: /schema/1/files
- description: Update schema files
  method: POST
  name: updateschemafiles
  path: /schema/1/update
- description: Validate schema files
  method: POST
  name: validateschemafiles
  path: /schema/1/validate
- description: Get staged schema status
  method: GET
  name: getstagedschemastatus
  path: /schema/1/status
- description: Commit staged schema
  method: POST
  name: commitstagedschema
  path: /schema/1/staged/commit
- description: Abandon staged schema
  method: POST
  name: abandonstagedschema
  path: /schema/1/staged/abandon
personas: []
provider_name: fauna
provider_slug: fauna
search_terms:
- commitstagedschema
- commit staged schema
- polleventfeed
- abandon staged schema
- getschemafiles
- validateschemafiles
- abandonstagedschema
- execute an fql query
- updateschemafiles
- getstagedschemastatus
- update schema files
- executequery
- poll an event feed
- fauna
- validate schema files
- api
- get schema files
- get staged schema status
slug: fauna-capability
source_filename: fauna-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fauna Core HTTP API\n  description: The Fauna Core HTTP API provides direct access to the Fauna serverless document database through HTTPS endpoints.\n    It allows developers to execute Fauna Query Language (FQL) queries, manage databases, perform CRUD operations on documents,\n    manage schema as FSL files, and consume change data capture events via event feeds. The API uses token-based authentication\n    and supports features such as transactions, indexes, and set operations. It serves as the foundation upon which Fauna's\n    client drivers and SDKs are built.\n  tags:\n  - Fauna\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fauna\n    baseUri: https://db.fauna.com\n    description: Fauna Core HTTP API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FAUNA_TOKEN}}'\n    resources:\n    - name: query-1\n      path: /query/1\n      operations:\n\
  \      - name: executequery\n        method: POST\n        description: Execute an FQL query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: feed-1\n      path: /feed/1\n      operations:\n      - name: polleventfeed\n        method: POST\n        description: Poll an event feed\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-files\n      path: /schema/1/files\n      operations:\n      - name: getschemafiles\n        method: GET\n        description: Get schema files\n        inputParameters:\n        - name: staged\n          in: query\n          type: boolean\n          description: If true, return staged schema files instead of active schema files.\n        - name: version\n          in: query\n          type: integer\n          description: Schema version timestamp to retrieve a specific version\
  \ of the schema files.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-update\n      path: /schema/1/update\n      operations:\n      - name: updateschemafiles\n        method: POST\n        description: Update schema files\n        inputParameters:\n        - name: staged\n          in: query\n          type: boolean\n          description: If true, stage the schema changes instead of applying immediately.\n        - name: version\n          in: query\n          type: integer\n          description: Expected schema version. The request fails if the version does not match the current schema version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-validate\n      path: /schema/1/validate\n      operations:\n      - name: validateschemafiles\n        method: POST\n        description: Validate\
  \ schema files\n        inputParameters:\n        - name: staged\n          in: query\n          type: boolean\n          description: If true, validate against staged schema instead of active schema.\n        - name: version\n          in: query\n          type: integer\n          description: Expected schema version for validation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-status\n      path: /schema/1/status\n      operations:\n      - name: getstagedschemastatus\n        method: GET\n        description: Get staged schema status\n        inputParameters:\n        - name: version\n          in: query\n          type: integer\n          description: Expected schema version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-staged-commit\n      path: /schema/1/staged/commit\n      operations:\n\
  \      - name: commitstagedschema\n        method: POST\n        description: Commit staged schema\n        inputParameters:\n        - name: version\n          in: query\n          type: integer\n          description: Expected schema version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-1-staged-abandon\n      path: /schema/1/staged/abandon\n      operations:\n      - name: abandonstagedschema\n        method: POST\n        description: Abandon staged schema\n        inputParameters:\n        - name: version\n          in: query\n          type: integer\n          description: Expected schema version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fauna-rest\n    description: REST adapter for Fauna Core HTTP API.\n    resources:\n    - path: /query/1\n\
  \      name: executequery\n      operations:\n      - method: POST\n        name: executequery\n        description: Execute an FQL query\n        call: fauna.executequery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /feed/1\n      name: polleventfeed\n      operations:\n      - method: POST\n        name: polleventfeed\n        description: Poll an event feed\n        call: fauna.polleventfeed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/files\n      name: getschemafiles\n      operations:\n      - method: GET\n        name: getschemafiles\n        description: Get schema files\n        call: fauna.getschemafiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/update\n      name: updateschemafiles\n      operations:\n      - method: POST\n        name: updateschemafiles\n        description: Update schema files\n        call: fauna.updateschemafiles\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/validate\n      name: validateschemafiles\n      operations:\n      - method: POST\n        name: validateschemafiles\n        description: Validate schema files\n        call: fauna.validateschemafiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/status\n      name: getstagedschemastatus\n      operations:\n      - method: GET\n        name: getstagedschemastatus\n        description: Get staged schema status\n        call: fauna.getstagedschemastatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/staged/commit\n      name: commitstagedschema\n      operations:\n      - method: POST\n        name: commitstagedschema\n        description: Commit staged schema\n        call: fauna.commitstagedschema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schema/1/staged/abandon\n\
  \      name: abandonstagedschema\n      operations:\n      - method: POST\n        name: abandonstagedschema\n        description: Abandon staged schema\n        call: fauna.abandonstagedschema\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fauna-mcp\n    transport: http\n    description: MCP adapter for Fauna Core HTTP API for AI agent use.\n    tools:\n    - name: executequery\n      description: Execute an FQL query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.executequery\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: polleventfeed\n      description: Poll an event feed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.polleventfeed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getschemafiles\n      description:\
  \ Get schema files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fauna.getschemafiles\n      with:\n        staged: tools.staged\n        version: tools.version\n      inputParameters:\n      - name: staged\n        type: boolean\n        description: If true, return staged schema files instead of active schema files.\n      - name: version\n        type: integer\n        description: Schema version timestamp to retrieve a specific version of the schema files.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateschemafiles\n      description: Update schema files\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.updateschemafiles\n      with:\n        staged: tools.staged\n        version: tools.version\n      inputParameters:\n      - name: staged\n        type: boolean\n        description: If true, stage the schema changes instead\
  \ of applying immediately.\n      - name: version\n        type: integer\n        description: Expected schema version. The request fails if the version does not match the current schema version.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validateschemafiles\n      description: Validate schema files\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.validateschemafiles\n      with:\n        staged: tools.staged\n        version: tools.version\n      inputParameters:\n      - name: staged\n        type: boolean\n        description: If true, validate against staged schema instead of active schema.\n      - name: version\n        type: integer\n        description: Expected schema version for validation.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstagedschemastatus\n      description: Get staged schema status\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: fauna.getstagedschemastatus\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: integer\n        description: Expected schema version.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: commitstagedschema\n      description: Commit staged schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.commitstagedschema\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: integer\n        description: Expected schema version.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: abandonstagedschema\n      description: Abandon staged schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fauna.abandonstagedschema\n      with:\n        version: tools.version\n\
  \      inputParameters:\n      - name: version\n        type: integer\n        description: Expected schema version.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FAUNA_TOKEN: FAUNA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fauna/refs/heads/main/capabilities/fauna-capability.yaml
tags:
- Fauna
- API
tools:
- description: Execute an FQL query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executequery
- description: Poll an event feed
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: polleventfeed
- description: Get schema files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschemafiles
- description: Update schema files
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateschemafiles
- description: Validate schema files
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateschemafiles
- description: Get staged schema status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstagedschemastatus
- description: Commit staged schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: commitstagedschema
- description: Abandon staged schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: abandonstagedschema
---
