---
categories: []
consumed_apis: []
description: Oracle REST Data Services (ORDS) on Oracle Database 19c. Exposes RESTful endpoints for SQL queries, PL/SQL execution, schema management, AutoREST table access, SODA document collections, and the data dictionary catalog.
layout: capability
name: Oracle Database 19c - Oracle REST Data Services (ORDS) API
operations:
- description: Execute SQL
  method: POST
  name: executesql
  path: /{schema}/_/sql
- description: List the schema's REST endpoints catalog
  method: GET
  name: getmetadatacatalog
  path: /{schema}/metadata-catalog/
- description: Query an AutoREST-enabled table or view
  method: GET
  name: querytable
  path: /{schema}/{table}/
- description: Insert a row
  method: POST
  name: insertrow
  path: /{schema}/{table}/
- description: Get a row by primary key
  method: GET
  name: getrow
  path: /{schema}/{table}/{id}
- description: Update a row by primary key
  method: PUT
  name: updaterow
  path: /{schema}/{table}/{id}
- description: Delete a row
  method: DELETE
  name: deleterow
  path: /{schema}/{table}/{id}
- description: List documents in a SODA collection
  method: GET
  name: listsodadocuments
  path: /{schema}/soda/latest/{collection}
- description: Insert a document into a SODA collection
  method: POST
  name: insertsodadocument
  path: /{schema}/soda/latest/{collection}
- description: Get a SODA document by key
  method: GET
  name: getsodadocument
  path: /{schema}/soda/latest/{collection}/{key}
- description: Replace a SODA document
  method: PUT
  name: replacesodadocument
  path: /{schema}/soda/latest/{collection}/{key}
- description: Delete a SODA document
  method: DELETE
  name: deletesodadocument
  path: /{schema}/soda/latest/{collection}/{key}
personas: []
provider_name: Oracle Database 19c
provider_slug: oracle-database-19c
search_terms:
- replacesodadocument
- 19c
- updaterow
- insert a row
- api
- replace a soda document
- execute sql
- get a row by primary key
- rest
- deletesodadocument
- insertsodadocument
- querytable
- query an autorest-enabled table or view
- machine-learning
- update a row by primary key
- getrow
- sql
- list documents in a soda collection
- deleterow
- enterprise
- database
- delete a row
- executesql
- json
- list the schema's rest endpoints catalog
- insertrow
- delete a soda document
- nosql
- getsodadocument
- get a soda document by key
- listsodadocuments
- getmetadatacatalog
- oracle
- insert a document into a soda collection
slug: oracle-database-19c-capability
source_filename: oracle-database-19c-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Database 19c - Oracle REST Data Services (ORDS) API\n  description: Oracle REST Data Services (ORDS) on Oracle Database 19c. Exposes RESTful endpoints for SQL queries, PL/SQL\n    execution, schema management, AutoREST table access, SODA document collections, and the data dictionary catalog.\n  tags:\n  - Oracle\n  - Database\n  - 19c\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-database-19c\n    baseUri: https://localhost:8443/ords\n    description: Oracle Database 19c - Oracle REST Data Services (ORDS) API HTTP API.\n    authentication:\n      type: basic\n      username: '{{ORACLE_DATABASE_19C_USERNAME}}'\n      password: '{{ORACLE_DATABASE_19C_PASSWORD}}'\n    resources:\n    - name: schema-sql\n      path: /{schema}/_/sql\n      operations:\n      - name: executesql\n        method: POST\n        description: Execute SQL\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-metadata-catalog\n      path: /{schema}/metadata-catalog/\n      operations:\n      - name: getmetadatacatalog\n        method: GET\n        description: List the schema's REST endpoints catalog\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-table\n      path: /{schema}/{table}/\n      operations:\n      - name: querytable\n        method: GET\n        description: Query an AutoREST-enabled table or view\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n        - name: q\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: insertrow\n        method: POST\n        description: Insert a row\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-table-id\n      path: /{schema}/{table}/{id}\n      operations:\n      - name: getrow\n        method: GET\n        description: Get a row by primary key\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterow\n        method: PUT\n        description: Update a row by primary key\n\
  \        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleterow\n        method: DELETE\n        description: Delete a row\n        inputParameters:\n        - name: table\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-soda-latest-collection\n      path: /{schema}/soda/latest/{collection}\n      operations:\n      - name: listsodadocuments\n        method: GET\n        description: List documents in a SODA collection\n        inputParameters:\n\
  \        - name: collection\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertsodadocument\n        method: POST\n        description: Insert a document into a SODA collection\n        inputParameters:\n        - name: collection\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schema-soda-latest-collection-key\n      path: /{schema}/soda/latest/{collection}/{key}\n      operations:\n      - name: getsodadocument\n        method: GET\n        description: Get a SODA document by key\n        inputParameters:\n        - name: collection\n\
  \          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replacesodadocument\n        method: PUT\n        description: Replace a SODA document\n        inputParameters:\n        - name: collection\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesodadocument\n        method: DELETE\n        description: Delete a SODA document\n        inputParameters:\n        - name: collection\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-database-19c-rest\n    description: REST adapter for Oracle Database 19c - Oracle REST Data Services (ORDS) API.\n    resources:\n    - path: /{schema}/_/sql\n      name: executesql\n      operations:\n      - method: POST\n        name: executesql\n        description: Execute SQL\n        call: oracle-database-19c.executesql\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/metadata-catalog/\n      name: getmetadatacatalog\n      operations:\n      - method: GET\n        name: getmetadatacatalog\n        description: List the schema's REST endpoints catalog\n        call: oracle-database-19c.getmetadatacatalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/{table}/\n\
  \      name: querytable\n      operations:\n      - method: GET\n        name: querytable\n        description: Query an AutoREST-enabled table or view\n        call: oracle-database-19c.querytable\n        with:\n          table: rest.table\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/{table}/\n      name: insertrow\n      operations:\n      - method: POST\n        name: insertrow\n        description: Insert a row\n        call: oracle-database-19c.insertrow\n        with:\n          table: rest.table\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/{table}/{id}\n      name: getrow\n      operations:\n      - method: GET\n        name: getrow\n        description: Get a row by primary key\n        call: oracle-database-19c.getrow\n        with:\n          table: rest.table\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/{table}/{id}\n\
  \      name: updaterow\n      operations:\n      - method: PUT\n        name: updaterow\n        description: Update a row by primary key\n        call: oracle-database-19c.updaterow\n        with:\n          table: rest.table\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/{table}/{id}\n      name: deleterow\n      operations:\n      - method: DELETE\n        name: deleterow\n        description: Delete a row\n        call: oracle-database-19c.deleterow\n        with:\n          table: rest.table\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/soda/latest/{collection}\n      name: listsodadocuments\n      operations:\n      - method: GET\n        name: listsodadocuments\n        description: List documents in a SODA collection\n        call: oracle-database-19c.listsodadocuments\n        with:\n          collection: rest.collection\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /{schema}/soda/latest/{collection}\n      name: insertsodadocument\n      operations:\n      - method: POST\n        name: insertsodadocument\n        description: Insert a document into a SODA collection\n        call: oracle-database-19c.insertsodadocument\n        with:\n          collection: rest.collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/soda/latest/{collection}/{key}\n      name: getsodadocument\n      operations:\n      - method: GET\n        name: getsodadocument\n        description: Get a SODA document by key\n        call: oracle-database-19c.getsodadocument\n        with:\n          collection: rest.collection\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/soda/latest/{collection}/{key}\n      name: replacesodadocument\n      operations:\n      - method: PUT\n        name: replacesodadocument\n\
  \        description: Replace a SODA document\n        call: oracle-database-19c.replacesodadocument\n        with:\n          collection: rest.collection\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{schema}/soda/latest/{collection}/{key}\n      name: deletesodadocument\n      operations:\n      - method: DELETE\n        name: deletesodadocument\n        description: Delete a SODA document\n        call: oracle-database-19c.deletesodadocument\n        with:\n          collection: rest.collection\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-database-19c-mcp\n    transport: http\n    description: MCP adapter for Oracle Database 19c - Oracle REST Data Services (ORDS) API for AI agent use.\n    tools:\n    - name: executesql\n      description: Execute SQL\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: oracle-database-19c.executesql\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetadatacatalog\n      description: List the schema's REST endpoints catalog\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.getmetadatacatalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querytable\n      description: Query an AutoREST-enabled table or view\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.querytable\n      with:\n        table: tools.table\n        q: tools.q\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: table\n        type: string\n        description: table\n        required: true\n      - name: q\n        type: string\n        description: q\n      - name: limit\n    \
  \    type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertrow\n      description: Insert a row\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database-19c.insertrow\n      with:\n        table: tools.table\n      inputParameters:\n      - name: table\n        type: string\n        description: table\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrow\n      description: Get a row by primary key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.getrow\n      with:\n        table: tools.table\n        id: tools.id\n      inputParameters:\n      - name: table\n        type: string\n        description: table\n        required: true\n      - name:\
  \ id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterow\n      description: Update a row by primary key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.updaterow\n      with:\n        table: tools.table\n        id: tools.id\n      inputParameters:\n      - name: table\n        type: string\n        description: table\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterow\n      description: Delete a row\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-database-19c.deleterow\n      with:\n        table: tools.table\n        id: tools.id\n      inputParameters:\n      - name: table\n        type:\
  \ string\n        description: table\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsodadocuments\n      description: List documents in a SODA collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.listsodadocuments\n      with:\n        collection: tools.collection\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: collection\n        type: string\n        description: collection\n        required: true\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertsodadocument\n      description: Insert a document into a SODA collection\n     \
  \ hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-database-19c.insertsodadocument\n      with:\n        collection: tools.collection\n      inputParameters:\n      - name: collection\n        type: string\n        description: collection\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsodadocument\n      description: Get a SODA document by key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.getsodadocument\n      with:\n        collection: tools.collection\n        key: tools.key\n      inputParameters:\n      - name: collection\n        type: string\n        description: collection\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replacesodadocument\n\
  \      description: Replace a SODA document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-database-19c.replacesodadocument\n      with:\n        collection: tools.collection\n        key: tools.key\n      inputParameters:\n      - name: collection\n        type: string\n        description: collection\n        required: true\n      - name: key\n        type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesodadocument\n      description: Delete a SODA document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-database-19c.deletesodadocument\n      with:\n        collection: tools.collection\n        key: tools.key\n      inputParameters:\n      - name: collection\n        type: string\n        description: collection\n        required: true\n      - name: key\n   \
  \     type: string\n        description: key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_DATABASE_19C_USERNAME: ORACLE_DATABASE_19C_USERNAME\n    ORACLE_DATABASE_19C_PASSWORD: ORACLE_DATABASE_19C_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-database-19c/refs/heads/main/capabilities/oracle-database-19c-capability.yaml
tags:
- Oracle
- Database
- 19c
- API
tools:
- description: Execute SQL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executesql
- description: List the schema's REST endpoints catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetadatacatalog
- description: Query an AutoREST-enabled table or view
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querytable
- description: Insert a row
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertrow
- description: Get a row by primary key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrow
- description: Update a row by primary key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updaterow
- description: Delete a row
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleterow
- description: List documents in a SODA collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsodadocuments
- description: Insert a document into a SODA collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertsodadocument
- description: Get a SODA document by key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsodadocument
- description: Replace a SODA document
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: replacesodadocument
- description: Delete a SODA document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesodadocument
---
