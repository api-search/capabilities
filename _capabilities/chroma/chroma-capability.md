---
categories: []
consumed_apis: []
description: Chroma Cloud is a managed, serverless vector database service that provides fast and scalable vector, full-text, and metadata search across terabytes of data. It is backed by Chroma's Apache 2.0 distributed database and offers usage-based pricing with starter and team plans. The Cloud API extends the Chroma Server API with additional search capabilities including hybrid search with reciprocal rank fusion, custom ranking expressions, and batch search operations.
layout: capability
name: Chroma Cloud API
operations:
- description: Check server heartbeat
  method: GET
  name: heartbeat
  path: /api/v2/heartbeat
- description: Get server version
  method: GET
  name: getversion
  path: /api/v2/version
- description: Create a tenant
  method: POST
  name: createtenant
  path: /api/v2/tenants
- description: Get a tenant
  method: GET
  name: gettenant
  path: /api/v2/tenants/{tenantName}
- description: List databases
  method: GET
  name: listdatabases
  path: /api/v2/tenants/{tenantName}/databases
- description: Create a database
  method: POST
  name: createdatabase
  path: /api/v2/tenants/{tenantName}/databases
- description: Get a database
  method: GET
  name: getdatabase
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}
- description: Delete a database
  method: DELETE
  name: deletedatabase
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}
- description: List collections
  method: GET
  name: listcollections
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections
- description: Create a collection
  method: POST
  name: createcollection
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections
- description: Get a collection
  method: GET
  name: getcollection
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}
- description: Update a collection
  method: PUT
  name: updatecollection
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}
- description: Delete a collection
  method: DELETE
  name: deletecollection
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}
- description: Count records in a collection
  method: GET
  name: countrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/count
- description: Add records to a collection
  method: POST
  name: addrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/add
- description: Get records from a collection
  method: POST
  name: getrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/get
- description: Update records in a collection
  method: POST
  name: updaterecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/update
- description: Upsert records in a collection
  method: POST
  name: upsertrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/upsert
- description: Delete records from a collection
  method: POST
  name: deleterecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/delete
- description: Query records in a collection
  method: POST
  name: queryrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/query
- description: Search records in a collection
  method: POST
  name: searchrecords
  path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/search
personas: []
provider_name: Chroma
provider_slug: chroma
search_terms:
- query records in a collection
- delete a database
- updatecollection
- search records in a collection
- getrecords
- multi-modal
- vector database
- get a collection
- retrieval
- delete a collection
- update records in a collection
- add records to a collection
- check server heartbeat
- get a database
- serverless
- create a tenant
- getcollection
- updaterecords
- cloud
- createtenant
- typescript
- get a tenant
- embeddings
- ai
- getdatabase
- deletecollection
- deletedatabase
- rag
- hybrid search
- open source
- upsertrecords
- sdk
- get server version
- llm
- upsert records in a collection
- apache 2.0
- update a collection
- machine learning
- javascript
- createdatabase
- gettenant
- api
- getversion
- get records from a collection
- ai native
- search
- count records in a collection
- create a database
- searchrecords
- python
- create a collection
- list databases
- countrecords
- listdatabases
- createcollection
- delete records from a collection
- queryrecords
- addrecords
- heartbeat
- listcollections
- deleterecords
- list collections
- chroma
slug: chroma-capability
source_filename: chroma-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Chroma Cloud API\n  description: Chroma Cloud is a managed, serverless vector database service that provides fast and scalable vector, full-text,\n    and metadata search across terabytes of data. It is backed by Chroma's Apache 2.0 distributed database and offers usage-based\n    pricing with starter and team plans. The Cloud API extends the Chroma Server API with additional search capabilities including\n    hybrid search with reciprocal rank fusion, custom ranking expressions, and batch search operations.\n  tags:\n  - Chroma\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chroma\n    baseUri: https://api.trychroma.com\n    description: Chroma Cloud API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{CHROMA_TOKEN}}'\n    resources:\n    - name: api-v2-heartbeat\n      path: /api/v2/heartbeat\n      operations:\n      - name: heartbeat\n       \
  \ method: GET\n        description: Check server heartbeat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-version\n      path: /api/v2/version\n      operations:\n      - name: getversion\n        method: GET\n        description: Get server version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants\n      path: /api/v2/tenants\n      operations:\n      - name: createtenant\n        method: POST\n        description: Create a tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname\n      path: /api/v2/tenants/{tenantName}\n      operations:\n      - name: gettenant\n        method: GET\n        description: Get a tenant\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases\n      path: /api/v2/tenants/{tenantName}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: List databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatabase\n        method: POST\n        description: Create a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Get a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatabase\n\
  \        method: DELETE\n        description: Delete a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections\n      operations:\n      - name: listcollections\n        method: GET\n        description: List collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcollection\n        method: POST\n        description: Create a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}\n      operations:\n      - name: getcollection\n  \
  \      method: GET\n        description: Get a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecollection\n        method: PUT\n        description: Update a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecollection\n        method: DELETE\n        description: Delete a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/count\n      operations:\n      - name: countrecords\n        method: GET\n        description: Count records in a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/add\n      operations:\n      - name: addrecords\n        method: POST\n        description: Add records to a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/get\n      operations:\n      - name: getrecords\n        method: POST\n        description: Get records from a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/update\n\
  \      operations:\n      - name: updaterecords\n        method: POST\n        description: Update records in a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/upsert\n      operations:\n      - name: upsertrecords\n        method: POST\n        description: Upsert records in a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/delete\n      operations:\n      - name: deleterecords\n        method: POST\n        description: Delete records from a collection\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/query\n      operations:\n      - name: queryrecords\n        method: POST\n        description: Query records in a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tenants-tenantname-databases-databasename\n      path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/search\n      operations:\n      - name: searchrecords\n        method: POST\n        description: Search records in a collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chroma-rest\n    description: REST adapter for Chroma\
  \ Cloud API.\n    resources:\n    - path: /api/v2/heartbeat\n      name: heartbeat\n      operations:\n      - method: GET\n        name: heartbeat\n        description: Check server heartbeat\n        call: chroma.heartbeat\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/version\n      name: getversion\n      operations:\n      - method: GET\n        name: getversion\n        description: Get server version\n        call: chroma.getversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants\n      name: createtenant\n      operations:\n      - method: POST\n        name: createtenant\n        description: Create a tenant\n        call: chroma.createtenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}\n      name: gettenant\n      operations:\n      - method: GET\n        name: gettenant\n        description: Get a tenant\n\
  \        call: chroma.gettenant\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: List databases\n        call: chroma.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases\n      name: createdatabase\n      operations:\n      - method: POST\n        name: createdatabase\n        description: Create a database\n        call: chroma.createdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Get a database\n        call: chroma.getdatabase\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n        description: Delete a database\n        call: chroma.deletedatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections\n      name: listcollections\n      operations:\n      - method: GET\n        name: listcollections\n        description: List collections\n        call: chroma.listcollections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections\n      name: createcollection\n      operations:\n      - method: POST\n        name: createcollection\n        description: Create a collection\n        call: chroma.createcollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}\n      name: getcollection\n      operations:\n      - method: GET\n        name: getcollection\n        description: Get a collection\n        call: chroma.getcollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}\n      name: updatecollection\n      operations:\n      - method: PUT\n        name: updatecollection\n        description: Update a collection\n        call: chroma.updatecollection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}\n      name: deletecollection\n      operations:\n      - method: DELETE\n        name: deletecollection\n        description: Delete a collection\n        call: chroma.deletecollection\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/count\n      name: countrecords\n      operations:\n      - method: GET\n        name: countrecords\n        description: Count records in a collection\n        call: chroma.countrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/add\n      name: addrecords\n      operations:\n      - method: POST\n        name: addrecords\n        description: Add records to a collection\n        call: chroma.addrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/get\n      name: getrecords\n      operations:\n      - method: POST\n        name: getrecords\n        description: Get records from a collection\n        call: chroma.getrecords\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/update\n      name: updaterecords\n      operations:\n      - method: POST\n        name: updaterecords\n        description: Update records in a collection\n        call: chroma.updaterecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/upsert\n      name: upsertrecords\n      operations:\n      - method: POST\n        name: upsertrecords\n        description: Upsert records in a collection\n        call: chroma.upsertrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/delete\n      name: deleterecords\n      operations:\n      - method: POST\n        name: deleterecords\n    \
  \    description: Delete records from a collection\n        call: chroma.deleterecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/query\n      name: queryrecords\n      operations:\n      - method: POST\n        name: queryrecords\n        description: Query records in a collection\n        call: chroma.queryrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tenants/{tenantName}/databases/{databaseName}/collections/{collectionId}/search\n      name: searchrecords\n      operations:\n      - method: POST\n        name: searchrecords\n        description: Search records in a collection\n        call: chroma.searchrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chroma-mcp\n    transport: http\n    description: MCP adapter for Chroma Cloud\
  \ API for AI agent use.\n    tools:\n    - name: heartbeat\n      description: Check server heartbeat\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.heartbeat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getversion\n      description: Get server version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.getversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtenant\n      description: Create a tenant\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.createtenant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettenant\n      description: Get a tenant\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.gettenant\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.listdatabases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatabase\n      description: Create a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.createdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.getdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedatabase\n      description: Delete a database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: chroma.deletedatabase\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcollections\n      description: List collections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.listcollections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcollection\n      description: Create a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.createcollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcollection\n      description: Get a collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.getcollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecollection\n      description: Update a collection\n      hints:\n        readOnly: false\n        destructive: false\n    \
  \    idempotent: true\n      call: chroma.updatecollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecollection\n      description: Delete a collection\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: chroma.deletecollection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: countrecords\n      description: Count records in a collection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chroma.countrecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addrecords\n      description: Add records to a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.addrecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecords\n      description: Get records from a collection\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.getrecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterecords\n      description: Update records in a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.updaterecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upsertrecords\n      description: Upsert records in a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.upsertrecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleterecords\n      description: Delete records from a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.deleterecords\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: queryrecords\n      description: Query records in a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.queryrecords\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchrecords\n      description: Search records in a collection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chroma.searchrecords\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHROMA_TOKEN: CHROMA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chroma/refs/heads/main/capabilities/chroma-capability.yaml
tags:
- Chroma
- API
tools:
- description: Check server heartbeat
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: heartbeat
- description: Get server version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversion
- description: Create a tenant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtenant
- description: Get a tenant
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettenant
- description: List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: List collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollections
- description: Create a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcollection
- description: Get a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollection
- description: Update a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecollection
- description: Delete a collection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecollection
- description: Count records in a collection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: countrecords
- description: Add records to a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addrecords
- description: Get records from a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getrecords
- description: Update records in a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterecords
- description: Upsert records in a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upsertrecords
- description: Delete records from a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleterecords
- description: Query records in a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: queryrecords
- description: Search records in a collection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchrecords
---
