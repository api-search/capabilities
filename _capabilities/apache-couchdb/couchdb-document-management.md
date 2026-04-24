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
- list all databases
- manages couchdb cluster configuration, authentication, and performance
- document store
- json
- builds applications using couchdb as the document store via the http api or sdk
- get session
- create database
- manages data pipelines, replication, and changes feed integrations with couchdb
- query documents
- get server info
- replication
- create a new database
- save document
- get current authentication session info
- create or update a document
- delete a document
- get a document by id
- get couchdb server version and status
- database changes feed for event-driven architectures
- apache
- get info about a database
- rest
- document operations
- list databases
- list all databases in couchdb
- open source
- get changes
- query documents with a mango selector
- list documents in a database
- mango
- list documents
- storing and retrieving json documents with mvcc
- start replication
- couchdb
- get database
- Data Engineer
- mango selectors, mapreduce views, and full-text search
- replication and offline-first data sync via the couch replication protocol
- nosql
- replicate
- delete document
- create a query index for faster mango queries
- database
- get changes feed
- create index
- create a new couchdb database
- query documents with mango
- changes feed
- get document
- get the changes feed to track database updates
- replicate data between couchdb instances
- Developer
- database operations
- full document lifecycle management with mango queries, changes feed, and replication
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
