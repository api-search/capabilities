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
- database changes feed for event-driven architectures
- json
- builds applications using couchdb as the document store via the http api or sdk
- get a document by id
- list documents
- replicate data between couchdb instances
- Data Engineer
- start replication
- get changes feed
- save document
- storing and retrieving json documents with mvcc
- nosql
- mango selectors, mapreduce views, and full-text search
- create a query index for faster mango queries
- manages couchdb cluster configuration, authentication, and performance
- delete a document
- get document
- document operations
- database operations
- delete document
- create a new database
- list documents in a database
- database
- apache
- couchdb
- create a new couchdb database
- replication and offline-first data sync via the couch replication protocol
- manages data pipelines, replication, and changes feed integrations with couchdb
- get couchdb server version and status
- query documents
- get session
- changes feed
- get server info
- list all databases in couchdb
- full document lifecycle management with mango queries, changes feed, and replication
- query documents with mango
- get changes
- replicate
- get the changes feed to track database updates
- document store
- mango
- create database
- create or update a document
- open source
- list databases
- get info about a database
- get current authentication session info
- replication
- create index
- get database
- Developer
- query documents with a mango selector
- rest
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
