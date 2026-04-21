---
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
- nosql
- open source
- delete document
- database
- query documents with a mango selector
- get document
- create a query index for faster mango queries
- get database
- storing and retrieving json documents with mvcc
- get session
- get changes
- document operations
- mango
- create a new database
- get couchdb server version and status
- get current authentication session info
- replication and offline-first data sync via the couch replication protocol
- list documents
- create a new couchdb database
- apache
- list databases
- create database
- query documents
- Data Engineer
- manages data pipelines, replication, and changes feed integrations with couchdb
- query documents with mango
- get server info
- start replication
- full document lifecycle management with mango queries, changes feed, and replication
- manages couchdb cluster configuration, authentication, and performance
- json
- database operations
- mango selectors, mapreduce views, and full-text search
- create index
- create or update a document
- document store
- get a document by id
- changes feed
- rest
- replication
- get info about a database
- list documents in a database
- save document
- get the changes feed to track database updates
- builds applications using couchdb as the document store via the http api or sdk
- get changes feed
- couchdb
- Developer
- replicate
- database changes feed for event-driven architectures
- replicate data between couchdb instances
- delete a document
- list all databases in couchdb
- list all databases
slug: couchdb-document-management
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
