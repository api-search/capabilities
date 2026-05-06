---
categories: []
consumed_apis: []
description: The Cloud Firestore API provides RESTful access to Google Cloud Firestore, a flexible, scalable NoSQL cloud database for storing and syncing data. It enables CRUD operations on documents and collections, querying with filters and ordering, managing indexes, and handling real-time data synchronization across client apps.
layout: capability
name: Google Cloud Firestore API
operations:
- description: Google Cloud Firestore List databases
  method: GET
  name: listdatabases
  path: /projects/{project}/databases
- description: Google Cloud Firestore Create a database
  method: POST
  name: createdatabase
  path: /projects/{project}/databases
- description: Google Cloud Firestore Get a database
  method: GET
  name: getdatabase
  path: /projects/{project}/databases/{database}
- description: Google Cloud Firestore Delete a database
  method: DELETE
  name: deletedatabase
  path: /projects/{project}/databases/{database}
- description: Google Cloud Firestore List documents
  method: GET
  name: listdocuments
  path: /projects/{project}/databases/{database}/documents/{collectionId}
- description: Google Cloud Firestore Create a document
  method: POST
  name: createdocument
  path: /projects/{project}/databases/{database}/documents/{collectionId}
- description: Google Cloud Firestore Get a document
  method: GET
  name: getdocument
  path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}
- description: Google Cloud Firestore Update a document
  method: PATCH
  name: updatedocument
  path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}
- description: Google Cloud Firestore Delete a document
  method: DELETE
  name: deletedocument
  path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}
- description: Google Cloud Firestore Run a query
  method: POST
  name: runquery
  path: /projects/{project}/databases/{database}/documents:runQuery
personas: []
provider_name: Google Cloud Firestore
provider_slug: google-cloud-firestore
search_terms:
- createdocument
- updatedocument
- real-time
- runquery
- google cloud firestore list databases
- getdocument
- firestore
- cloud
- google
- google cloud firestore delete a document
- listdocuments
- google cloud firestore run a query
- google cloud firestore list documents
- getdatabase
- nosql
- deletedatabase
- google cloud firestore create a database
- google cloud firestore delete a database
- database
- createdatabase
- api
- deletedocument
- google cloud firestore update a document
- google cloud firestore get a database
- listdatabases
- documents
- google cloud firestore create a document
- google cloud
- google cloud firestore get a document
slug: google-cloud-firestore-capability
source_filename: google-cloud-firestore-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Firestore API\n  description: The Cloud Firestore API provides RESTful access to Google Cloud Firestore, a flexible, scalable NoSQL cloud\n    database for storing and syncing data. It enables CRUD operations on documents and collections, querying with filters\n    and ordering, managing indexes, and handling real-time data synchronization across client apps.\n  tags:\n  - Google\n  - Cloud\n  - Firestore\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-firestore\n    baseUri: https://firestore.googleapis.com/v1\n    description: Google Cloud Firestore API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_FIRESTORE_TOKEN}}'\n    resources:\n    - name: projects-project-databases\n      path: /projects/{project}/databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: Google\
  \ Cloud Firestore List databases\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatabase\n        method: POST\n        description: Google Cloud Firestore Create a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: databaseId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-databases-database\n      path: /projects/{project}/databases/{database}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Google Cloud Firestore Get a database\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatabase\n        method: DELETE\n        description: Google Cloud Firestore Delete a database\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-databases-database-documents-co\n      path: /projects/{project}/databases/{database}/documents/{collectionId}\n      operations:\n      - name: listdocuments\n        method: GET\n        description:\
  \ Google Cloud Firestore List documents\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdocument\n        method: POST\n        description: Google Cloud Firestore Create a document\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n\
  \          required: true\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        - name: documentId\n          in: query\n          type: string\n          description: Optional client-assigned document ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-databases-database-documents-co\n      path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}\n      operations:\n      - name: getdocument\n        method: GET\n        description: Google Cloud Firestore Get a document\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        - name:\
  \ documentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocument\n        method: PATCH\n        description: Google Cloud Firestore Update a document\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        - name: documentId\n          in: path\n          type: string\n          required: true\n        - name: updateMask.fieldPaths\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocument\n        method: DELETE\n\
  \        description: Google Cloud Firestore Delete a document\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: database\n          in: path\n          type: string\n          required: true\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        - name: documentId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-databases-database-documents-ru\n      path: /projects/{project}/databases/{database}/documents:runQuery\n      operations:\n      - name: runquery\n        method: POST\n        description: Google Cloud Firestore Run a query\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name:\
  \ database\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-firestore-rest\n    description: REST adapter for Google Cloud Firestore API.\n    resources:\n    - path: /projects/{project}/databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: Google Cloud Firestore List databases\n        call: google-cloud-firestore.listdatabases\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases\n      name: createdatabase\n      operations:\n      - method: POST\n        name: createdatabase\n        description: Google Cloud Firestore Create a database\n        call: google-cloud-firestore.createdatabase\n\
  \        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Google Cloud Firestore Get a database\n        call: google-cloud-firestore.getdatabase\n        with:\n          project: rest.project\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}\n      name: deletedatabase\n      operations:\n      - method: DELETE\n        name: deletedatabase\n        description: Google Cloud Firestore Delete a database\n        call: google-cloud-firestore.deletedatabase\n        with:\n          project: rest.project\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents/{collectionId}\n\
  \      name: listdocuments\n      operations:\n      - method: GET\n        name: listdocuments\n        description: Google Cloud Firestore List documents\n        call: google-cloud-firestore.listdocuments\n        with:\n          project: rest.project\n          database: rest.database\n          collectionId: rest.collectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents/{collectionId}\n      name: createdocument\n      operations:\n      - method: POST\n        name: createdocument\n        description: Google Cloud Firestore Create a document\n        call: google-cloud-firestore.createdocument\n        with:\n          project: rest.project\n          database: rest.database\n          collectionId: rest.collectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}\n    \
  \  name: getdocument\n      operations:\n      - method: GET\n        name: getdocument\n        description: Google Cloud Firestore Get a document\n        call: google-cloud-firestore.getdocument\n        with:\n          project: rest.project\n          database: rest.database\n          collectionId: rest.collectionId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}\n      name: updatedocument\n      operations:\n      - method: PATCH\n        name: updatedocument\n        description: Google Cloud Firestore Update a document\n        call: google-cloud-firestore.updatedocument\n        with:\n          project: rest.project\n          database: rest.database\n          collectionId: rest.collectionId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents/{collectionId}/{documentId}\n\
  \      name: deletedocument\n      operations:\n      - method: DELETE\n        name: deletedocument\n        description: Google Cloud Firestore Delete a document\n        call: google-cloud-firestore.deletedocument\n        with:\n          project: rest.project\n          database: rest.database\n          collectionId: rest.collectionId\n          documentId: rest.documentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/databases/{database}/documents:runQuery\n      name: runquery\n      operations:\n      - method: POST\n        name: runquery\n        description: Google Cloud Firestore Run a query\n        call: google-cloud-firestore.runquery\n        with:\n          project: rest.project\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-firestore-mcp\n    transport: http\n    description: MCP adapter\
  \ for Google Cloud Firestore API for AI agent use.\n    tools:\n    - name: listdatabases\n      description: Google Cloud Firestore List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-firestore.listdatabases\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatabase\n      description: Google Cloud Firestore Create a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-firestore.createdatabase\n      with:\n        project: tools.project\n        databaseId: tools.databaseId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: databaseId\n      \
  \  type: string\n        description: databaseId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Google Cloud Firestore Get a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-firestore.getdatabase\n      with:\n        project: tools.project\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedatabase\n      description: Google Cloud Firestore Delete a database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-firestore.deletedatabase\n      with:\n        project: tools.project\n\
  \        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdocuments\n      description: Google Cloud Firestore List documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-firestore.listdocuments\n      with:\n        project: tools.project\n        database: tools.database\n        collectionId: tools.collectionId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n\
  \      - name: collectionId\n        type: string\n        description: collectionId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdocument\n      description: Google Cloud Firestore Create a document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-firestore.createdocument\n      with:\n        project: tools.project\n        database: tools.database\n        collectionId: tools.collectionId\n        documentId: tools.documentId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n\
  \        required: true\n      - name: collectionId\n        type: string\n        description: collectionId\n        required: true\n      - name: documentId\n        type: string\n        description: Optional client-assigned document ID.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocument\n      description: Google Cloud Firestore Get a document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-firestore.getdocument\n      with:\n        project: tools.project\n        database: tools.database\n        collectionId: tools.collectionId\n        documentId: tools.documentId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      - name: collectionId\n        type: string\n        description: collectionId\n\
  \        required: true\n      - name: documentId\n        type: string\n        description: documentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedocument\n      description: Google Cloud Firestore Update a document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-firestore.updatedocument\n      with:\n        project: tools.project\n        database: tools.database\n        collectionId: tools.collectionId\n        documentId: tools.documentId\n        updateMask.fieldPaths: tools.updateMask.fieldPaths\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      - name: collectionId\n        type: string\n        description: collectionId\n        required: true\n      - name: documentId\n\
  \        type: string\n        description: documentId\n        required: true\n      - name: updateMask.fieldPaths\n        type: array\n        description: updateMask.fieldPaths\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedocument\n      description: Google Cloud Firestore Delete a document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-firestore.deletedocument\n      with:\n        project: tools.project\n        database: tools.database\n        collectionId: tools.collectionId\n        documentId: tools.documentId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      - name: collectionId\n        type: string\n        description: collectionId\n        required: true\n      - name: documentId\n\
  \        type: string\n        description: documentId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runquery\n      description: Google Cloud Firestore Run a query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-firestore.runquery\n      with:\n        project: tools.project\n        database: tools.database\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: database\n        type: string\n        description: database\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_FIRESTORE_TOKEN: GOOGLE_CLOUD_FIRESTORE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-firestore/refs/heads/main/capabilities/google-cloud-firestore-capability.yaml
tags:
- Google
- Cloud
- Firestore
- API
tools:
- description: Google Cloud Firestore List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Google Cloud Firestore Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Google Cloud Firestore Get a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: Google Cloud Firestore Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatabase
- description: Google Cloud Firestore List documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocuments
- description: Google Cloud Firestore Create a document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocument
- description: Google Cloud Firestore Get a document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocument
- description: Google Cloud Firestore Update a document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocument
- description: Google Cloud Firestore Delete a document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocument
- description: Google Cloud Firestore Run a query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runquery
---
