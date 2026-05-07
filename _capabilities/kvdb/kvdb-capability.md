---
categories: []
consumed_apis: []
description: KVdb is a hosted serverless key-value database with a simple REST API. Buckets are namespaces of key-value pairs accessed over HTTPS using standard methods (GET, POST, PATCH, DELETE). KVdb supports access control via secret, read, and write keys, custom Lua scripts, and per-bucket TTLs.
layout: capability
name: KVdb API
operations:
- description: Create bucket
  method: POST
  name: createbucket
  path: /
- description: Update bucket
  method: PATCH
  name: updatebucket
  path: /{bucket_id}
- description: Delete bucket
  method: DELETE
  name: deletebucket
  path: /{bucket_id}
- description: List keys
  method: GET
  name: listkeys
  path: /{bucket_id}
- description: Get key value
  method: GET
  name: getkey
  path: /{bucket_id}/{key}
- description: Set key value
  method: POST
  name: setkey
  path: /{bucket_id}/{key}
- description: Increment or decrement numeric value
  method: PATCH
  name: patchkey
  path: /{bucket_id}/{key}
- description: Delete key
  method: DELETE
  name: deletekey
  path: /{bucket_id}/{key}
- description: Upload script
  method: PUT
  name: uploadscript
  path: /{bucket_id}/scripts/{script_name}
- description: Execute script
  method: GET
  name: executescript
  path: /{bucket_id}/scripts/{script_name}
personas: []
provider_name: KVdb
provider_slug: kvdb
search_terms:
- increment or decrement numeric value
- set key value
- get key value
- update bucket
- api
- kvdb
- patchkey
- key-value
- list keys
- serverless
- create bucket
- deletekey
- createbucket
- listkeys
- setkey
- delete key
- updatebucket
- getkey
- uploadscript
- delete bucket
- upload script
- execute script
- nosql
- executescript
- deletebucket
- databases
slug: kvdb-capability
source_filename: kvdb-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: KVdb API\n  description: KVdb is a hosted serverless key-value database with a simple REST API. Buckets are namespaces of key-value\n    pairs accessed over HTTPS using standard methods (GET, POST, PATCH, DELETE). KVdb supports access control via secret,\n    read, and write keys, custom Lua scripts, and per-bucket TTLs.\n  tags:\n  - Kvdb\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kvdb\n    baseUri: https://kvdb.io\n    description: KVdb API HTTP API.\n    authentication:\n      type: basic\n      username: '{{KVDB_USERNAME}}'\n      password: '{{KVDB_PASSWORD}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: createbucket\n        method: POST\n        description: Create bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-id\n\
  \      path: /{bucket_id}\n      operations:\n      - name: updatebucket\n        method: PATCH\n        description: Update bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebucket\n        method: DELETE\n        description: Delete bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listkeys\n        method: GET\n        description: List keys\n        inputParameters:\n        - name: prefix\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-id-key\n      path: /{bucket_id}/{key}\n      operations:\n      - name:\
  \ getkey\n        method: GET\n        description: Get key value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setkey\n        method: POST\n        description: Set key value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchkey\n        method: PATCH\n        description: Increment or decrement numeric value\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletekey\n        method: DELETE\n        description: Delete key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bucket-id-scripts-script-name\n      path: /{bucket_id}/scripts/{script_name}\n      operations:\n      - name: uploadscript\n        method: PUT\n\
  \        description: Upload script\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: executescript\n        method: GET\n        description: Execute script\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kvdb-rest\n    description: REST adapter for KVdb API.\n    resources:\n    - path: /\n      name: createbucket\n      operations:\n      - method: POST\n        name: createbucket\n        description: Create bucket\n        call: kvdb.createbucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}\n      name: updatebucket\n      operations:\n      - method: PATCH\n        name: updatebucket\n        description: Update bucket\n        call: kvdb.updatebucket\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /{bucket_id}\n      name: deletebucket\n      operations:\n      - method: DELETE\n        name: deletebucket\n        description: Delete bucket\n        call: kvdb.deletebucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}\n      name: listkeys\n      operations:\n      - method: GET\n        name: listkeys\n        description: List keys\n        call: kvdb.listkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}/{key}\n      name: getkey\n      operations:\n      - method: GET\n        name: getkey\n        description: Get key value\n        call: kvdb.getkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}/{key}\n      name: setkey\n      operations:\n      - method: POST\n        name: setkey\n        description: Set key value\n        call: kvdb.setkey\n        outputParameters:\n      \
  \  - type: object\n          mapping: $.\n    - path: /{bucket_id}/{key}\n      name: patchkey\n      operations:\n      - method: PATCH\n        name: patchkey\n        description: Increment or decrement numeric value\n        call: kvdb.patchkey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}/{key}\n      name: deletekey\n      operations:\n      - method: DELETE\n        name: deletekey\n        description: Delete key\n        call: kvdb.deletekey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}/scripts/{script_name}\n      name: uploadscript\n      operations:\n      - method: PUT\n        name: uploadscript\n        description: Upload script\n        call: kvdb.uploadscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{bucket_id}/scripts/{script_name}\n      name: executescript\n      operations:\n      - method: GET\n        name: executescript\n\
  \        description: Execute script\n        call: kvdb.executescript\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kvdb-mcp\n    transport: http\n    description: MCP adapter for KVdb API for AI agent use.\n    tools:\n    - name: createbucket\n      description: Create bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kvdb.createbucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebucket\n      description: Update bucket\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kvdb.updatebucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebucket\n      description: Delete bucket\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kvdb.deletebucket\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listkeys\n      description: List keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kvdb.listkeys\n      with:\n        prefix: tools.prefix\n        limit: tools.limit\n        format: tools.format\n      inputParameters:\n      - name: prefix\n        type: string\n        description: prefix\n      - name: limit\n        type: integer\n        description: limit\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getkey\n      description: Get key value\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kvdb.getkey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setkey\n      description: Set key value\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: kvdb.setkey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchkey\n      description: Increment or decrement numeric value\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: kvdb.patchkey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletekey\n      description: Delete key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: kvdb.deletekey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadscript\n      description: Upload script\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: kvdb.uploadscript\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executescript\n      description: Execute script\n      hints:\n        readOnly: true\n        destructive: false\n       \
  \ idempotent: true\n      call: kvdb.executescript\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KVDB_USERNAME: KVDB_USERNAME\n    KVDB_PASSWORD: KVDB_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kvdb/refs/heads/main/capabilities/kvdb-capability.yaml
tags:
- Kvdb
- API
tools:
- description: Create bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbucket
- description: Update bucket
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebucket
- description: Delete bucket
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucket
- description: List keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listkeys
- description: Get key value
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkey
- description: Set key value
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setkey
- description: Increment or decrement numeric value
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchkey
- description: Delete key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletekey
- description: Upload script
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: uploadscript
- description: Execute script
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: executescript
---
