---
categories: []
consumed_apis:
- couchdb
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
- get current authentication session info
- list databases
- get couchdb server version and status
- get a document by id
- create a new couchdb database
- nosql
- manages data pipelines, replication, and changes feed integrations with couchdb
- delete document
- get info about a database
- save document
- get session
- replicate data between couchdb instances
- list all databases in couchdb
- couchdb
- get changes
- get changes feed
- document operations
- replicate
- create or update a document
- get database
- json
- create database
- start replication
- database
- mango
- create index
- document store
- get document
- full document lifecycle management with mango queries, changes feed, and replication
- storing and retrieving json documents with mvcc
- mango selectors, mapreduce views, and full-text search
- open source
- query documents
- changes feed
- query documents with mango
- database changes feed for event-driven architectures
- get server info
- create a new database
- query documents with a mango selector
- get the changes feed to track database updates
- Data Engineer
- builds applications using couchdb as the document store via the http api or sdk
- list all databases
- apache
- replication
- list documents
- list documents in a database
- create a query index for faster mango queries
- manages couchdb cluster configuration, authentication, and performance
- Developer
- replication and offline-first data sync via the couch replication protocol
- rest
- delete a document
- database operations
slug: couchdb-document-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Apache CouchDB Document Management\n  description: Workflow capability for managing CouchDB documents, databases, and queries. Combines document CRUD, Mango queries, changes feed, and replication for developers and data engineers.\n  tags:\n  - Apache\n  - CouchDB\n  - Database\n  - Document Store\n  - Mango\n  - NoSQL\n  - Replication\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    COUCHDB_USER: COUCHDB_USER\n    COUCHDB_PASSWORD: COUCHDB_PASSWORD\ncapability:\n  consumes:\n  - import: couchdb\n    location: ./shared/couchdb-http-api.yaml\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: couchdb-document-management-api\n    description: Unified REST API for CouchDB document and database management.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Database operations\n      operations:\n      - method: GET\n        name: list-databases\n        description:\
  \ List all databases\n        call: couchdb.get-all-dbs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: create-database\n        description: Create a new database\n        call: couchdb.create-database\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/databases/{db}/documents\n      name: documents\n      description: Document operations\n      operations:\n      - method: GET\n        name: list-documents\n        description: List documents in a database\n        call: couchdb.get-all-docs\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: query-documents\n        description: Query documents with Mango\n        call: couchdb.find-documents\n        with:\n          db: rest.db\n          selector: rest.selector\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /v1/databases/{db}/changes\n      name: changes\n      description: Changes feed\n      operations:\n      - method: GET\n        name: get-changes\n        description: Get changes feed\n        call: couchdb.get-changes\n        with:\n          db: rest.db\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/replication\n      name: replication\n      description: Replication\n      operations:\n      - method: POST\n        name: replicate\n        description: Start replication\n        call: couchdb.replicate\n        with:\n          source: rest.source\n          target: rest.target\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: couchdb-document-management-mcp\n    transport: http\n    description: MCP server for AI-assisted CouchDB document database management.\n    tools:\n    - name: list-databases\n      description:\
  \ List all databases in CouchDB\n      hints:\n        readOnly: true\n        openWorld: true\n      call: couchdb.get-all-dbs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-database\n      description: Create a new CouchDB database\n      hints:\n        readOnly: false\n      call: couchdb.create-database\n      with:\n        db: tools.db\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-database\n      description: Get info about a database\n      hints:\n        readOnly: true\n      call: couchdb.get-database-info\n      with:\n        db: tools.db\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-documents\n      description: List documents in a database\n      hints:\n        readOnly: true\n      call: couchdb.get-all-docs\n      with:\n        db: tools.db\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n\
  \      description: Get a document by ID\n      hints:\n        readOnly: true\n      call: couchdb.get-document\n      with:\n        db: tools.db\n        docid: tools.docid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: save-document\n      description: Create or update a document\n      hints:\n        readOnly: false\n        idempotent: true\n      call: couchdb.create-or-update-document\n      with:\n        db: tools.db\n        docid: tools.docid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document\n      description: Delete a document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: couchdb.delete-document\n      with:\n        db: tools.db\n        docid: tools.docid\n        rev: tools.rev\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-documents\n      description: Query documents with a Mango selector\n\
  \      hints:\n        readOnly: true\n      call: couchdb.find-documents\n      with:\n        db: tools.db\n        selector: tools.selector\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-index\n      description: Create a query index for faster Mango queries\n      hints:\n        readOnly: false\n        idempotent: true\n      call: couchdb.create-index\n      with:\n        db: tools.db\n        index: tools.index\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-changes\n      description: Get the changes feed to track database updates\n      hints:\n        readOnly: true\n      call: couchdb.get-changes\n      with:\n        db: tools.db\n        since: tools.since\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replicate\n      description: Replicate data between CouchDB instances\n      hints:\n        readOnly:\
  \ false\n        openWorld: true\n      call: couchdb.replicate\n      with:\n        source: tools.source\n        target: tools.target\n        continuous: tools.continuous\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-server-info\n      description: Get CouchDB server version and status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: couchdb.get-server-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-session\n      description: Get current authentication session info\n      hints:\n        readOnly: true\n      call: couchdb.get-session\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
