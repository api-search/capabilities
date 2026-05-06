---
categories: []
consumed_apis: []
description: Workflow capability for managing CouchDB documents, databases, and queries. Combines document CRUD, Mango queries, changes feed, and replication for developers and data engineers.
layout: capability
name: Apache CouchDB Document Management
operations:
- description: List all databases
  method: GET
  name: list-databases
  path: /v1/databases
- description: Create a new database
  method: PUT
  name: create-database
  path: /v1/databases
- description: List documents in a database
  method: GET
  name: list-documents
  path: /v1/databases/{db}/documents
- description: Query documents with Mango
  method: POST
  name: query-documents
  path: /v1/databases/{db}/documents
- description: Get changes feed
  method: GET
  name: get-changes
  path: /v1/databases/{db}/changes
- description: Start replication
  method: POST
  name: replicate
  path: /v1/replication
personas: []
provider_name: Apache CouchDB
provider_slug: apache-couchdb
search_terms:
- get changes
- get database
- document operations
- get session
- get the changes feed to track database updates
- delete a document
- document store
- full document lifecycle management with mango queries, changes feed, and replication
- manages couchdb cluster configuration, authentication, and performance
- get a document by id
- get changes feed
- get document
- get info about a database
- storing and retrieving json documents with mvcc
- couchdb
- create a new couchdb database
- get couchdb server version and status
- rest
- get server info
- Developer
- database operations
- create index
- list documents
- changes feed
- json
- start replication
- delete document
- create or update a document
- create a new database
- apache
- Data Engineer
- replicate
- nosql
- create a query index for faster mango queries
- open source
- database changes feed for event-driven architectures
- database
- list all databases in couchdb
- query documents with mango
- list all databases
- query documents with a mango selector
- list databases
- create database
- query documents
- list documents in a database
- save document
- replicate data between couchdb instances
- mango selectors, mapreduce views, and full-text search
- builds applications using couchdb as the document store via the http api or sdk
- manages data pipelines, replication, and changes feed integrations with couchdb
- mango
- replication and offline-first data sync via the couch replication protocol
- get current authentication session info
- replication
slug: couchdb-document-management
source_filename: couchdb-document-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache CouchDB Document Management\n  description: Workflow capability for managing CouchDB documents, databases, and queries. Combines document CRUD, Mango queries,\n    changes feed, and replication for developers and data engineers.\n  tags:\n  - Apache\n  - CouchDB\n  - Database\n  - Document Store\n  - Mango\n  - NoSQL\n  - Replication\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    COUCHDB_USER: COUCHDB_USER\n    COUCHDB_PASSWORD: COUCHDB_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: couchdb\n    baseUri: http://localhost:5984\n    description: Apache CouchDB REST API\n    authentication:\n      type: basic\n      username: '{{COUCHDB_USER}}'\n      password: '{{COUCHDB_PASSWORD}}'\n    resources:\n    - name: server\n      path: /\n      description: Server information and utilities\n      operations:\n      - name: get-server-info\n        method: GET\n        description:\
  \ Get server info and version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all-dbs\n        method: GET\n        description: List all databases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: database\n      path: /{db}\n      description: Database management\n      operations:\n      - name: get-database-info\n        method: GET\n        description: Get database info\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database\n        method: PUT\n        description: Create a database\n        inputParameters:\n        - name: db\n          in:\
  \ path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-database\n        method: DELETE\n        description: Delete a database\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all-docs\n        method: GET\n        description: List all documents\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: include_docs\n          in: query\n          type: boolean\n          required: false\n          description: Include document bodies\n     \
  \   - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /{db}/{docid}\n      description: Document CRUD operations\n      operations:\n      - name: get-document\n        method: GET\n        description: Retrieve a document by ID\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: docid\n          in: path\n          type: string\n          required: true\n          description: Document ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-document\n        method: PUT\n        description: Create or update a document\n        inputParameters:\n\
  \        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: docid\n          in: path\n          type: string\n          required: true\n          description: Document ID\n        body:\n          type: json\n          data:\n            _rev: '{{tools.rev}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-document\n        method: DELETE\n        description: Delete a document\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: docid\n          in: path\n          type: string\n          required: true\n          description: Document ID\n        - name: rev\n          in: query\n          type: string\n          required: true\n          description: Current revision\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mango\n      path: /{db}/_find\n      description: Mango declarative query API\n      operations:\n      - name: find-documents\n        method: POST\n        description: Query documents with Mango selector\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        body:\n          type: json\n          data:\n            selector: '{{tools.selector}}'\n            limit: '{{tools.limit}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-index\n        method: POST\n        description: Create a Mango index\n        inputParameters:\n        - name: db\n          in: path\n          type: string\n          required: true\n          description: Database name\n        body:\n\
  \          type: json\n          data:\n            index: '{{tools.index}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: replication\n      path: /_replicate\n      description: Replication management\n      operations:\n      - name: replicate\n        method: POST\n        description: Start a replication task\n        body:\n          type: json\n          data:\n            source: '{{tools.source}}'\n            target: '{{tools.target}}'\n            continuous: '{{tools.continuous}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changes\n      path: /{db}/_changes\n      description: Database changes feed\n      operations:\n      - name: get-changes\n        method: GET\n        description: Get database changes feed\n        inputParameters:\n        - name: db\n          in: path\n       \
  \   type: string\n          required: true\n          description: Database name\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Start sequence\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authentication\n      path: /_session\n      description: Session authentication\n      operations:\n      - name: get-session\n        method: GET\n        description: Get current session info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-session\n        method: POST\n        description: Authenticate and create session\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            password: '{{tools.password}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: couchdb-document-management-api\n    description: Unified REST API for CouchDB document and database management.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Database operations\n      operations:\n      - method: GET\n        name: list-databases\n        description: List all databases\n        call: couchdb.get-all-dbs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: create-database\n        description: Create a new database\n        call: couchdb.create-database\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{db}/documents\n      name: documents\n      description:\
  \ Document operations\n      operations:\n      - method: GET\n        name: list-documents\n        description: List documents in a database\n        call: couchdb.get-all-docs\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: query-documents\n        description: Query documents with Mango\n        call: couchdb.find-documents\n        with:\n          db: rest.db\n          selector: rest.selector\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{db}/changes\n      name: changes\n      description: Changes feed\n      operations:\n      - method: GET\n        name: get-changes\n        description: Get changes feed\n        call: couchdb.get-changes\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/replication\n      name: replication\n      description: Replication\n\
  \      operations:\n      - method: POST\n        name: replicate\n        description: Start replication\n        call: couchdb.replicate\n        with:\n          source: rest.source\n          target: rest.target\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: couchdb-document-management-mcp\n    transport: http\n    description: MCP server for AI-assisted CouchDB document database management.\n    tools:\n    - name: list-databases\n      description: List all databases in CouchDB\n      hints:\n        readOnly: true\n        openWorld: true\n      call: couchdb.get-all-dbs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-database\n      description: Create a new CouchDB database\n      hints:\n        readOnly: false\n      call: couchdb.create-database\n      with:\n        db: tools.db\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database\n\
  \      description: Get info about a database\n      hints:\n        readOnly: true\n      call: couchdb.get-database-info\n      with:\n        db: tools.db\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-documents\n      description: List documents in a database\n      hints:\n        readOnly: true\n      call: couchdb.get-all-docs\n      with:\n        db: tools.db\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n      description: Get a document by ID\n      hints:\n        readOnly: true\n      call: couchdb.get-document\n      with:\n        db: tools.db\n        docid: tools.docid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: save-document\n      description: Create or update a document\n      hints:\n        readOnly: false\n        idempotent: true\n      call: couchdb.create-or-update-document\n      with:\n        db: tools.db\n\
  \        docid: tools.docid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Delete a document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: couchdb.delete-document\n      with:\n        db: tools.db\n        docid: tools.docid\n        rev: tools.rev\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-documents\n      description: Query documents with a Mango selector\n      hints:\n        readOnly: true\n      call: couchdb.find-documents\n      with:\n        db: tools.db\n        selector: tools.selector\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-index\n      description: Create a query index for faster Mango queries\n      hints:\n        readOnly: false\n        idempotent: true\n      call: couchdb.create-index\n      with:\n        db: tools.db\n\
  \        index: tools.index\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-changes\n      description: Get the changes feed to track database updates\n      hints:\n        readOnly: true\n      call: couchdb.get-changes\n      with:\n        db: tools.db\n        since: tools.since\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replicate\n      description: Replicate data between CouchDB instances\n      hints:\n        readOnly: false\n        openWorld: true\n      call: couchdb.replicate\n      with:\n        source: tools.source\n        target: tools.target\n        continuous: tools.continuous\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-info\n      description: Get CouchDB server version and status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: couchdb.get-server-info\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-session\n      description: Get current authentication session info\n      hints:\n        readOnly: true\n      call: couchdb.get-session\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-couchdb/refs/heads/main/capabilities/couchdb-document-management.yaml
tags:
- Apache
- CouchDB
- Database
- Document Store
- Mango
- NoSQL
- Replication
tools:
- description: List all databases in CouchDB
  hints:
    openWorld: true
    readOnly: true
  name: list-databases
- description: Create a new CouchDB database
  hints:
    readOnly: false
  name: create-database
- description: Get info about a database
  hints:
    readOnly: true
  name: get-database
- description: List documents in a database
  hints:
    readOnly: true
  name: list-documents
- description: Get a document by ID
  hints:
    readOnly: true
  name: get-document
- description: Create or update a document
  hints:
    idempotent: true
    readOnly: false
  name: save-document
- description: Delete a document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document
- description: Query documents with a Mango selector
  hints:
    readOnly: true
  name: query-documents
- description: Create a query index for faster Mango queries
  hints:
    idempotent: true
    readOnly: false
  name: create-index
- description: Get the changes feed to track database updates
  hints:
    readOnly: true
  name: get-changes
- description: Replicate data between CouchDB instances
  hints:
    openWorld: true
    readOnly: false
  name: replicate
- description: Get CouchDB server version and status
  hints:
    openWorld: true
    readOnly: true
  name: get-server-info
- description: Get current authentication session info
  hints:
    readOnly: true
  name: get-session
---
