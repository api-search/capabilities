---
consumed_apis:
- dynamodb
description: Unified workflow for managing DynamoDB tables, items, queries, batch operations, transactions, and backups. Used by backend developers and data engineers.
layout: capability
name: Amazon DynamoDB Database Management
operations:
- description: List tables.
  method: GET
  name: list-tables
  path: /v1/tables
- description: Create a table.
  method: POST
  name: create-table
  path: /v1/tables
- description: Describe a table.
  method: GET
  name: describe-table
  path: /v1/tables/{id}
- description: Update a table.
  method: PUT
  name: update-table
  path: /v1/tables/{id}
- description: Delete a table.
  method: DELETE
  name: delete-table
  path: /v1/tables/{id}
- description: Create or replace an item.
  method: POST
  name: put-item
  path: /v1/items
- description: Get an item.
  method: GET
  name: get-item
  path: /v1/items
- description: Query items.
  method: POST
  name: query
  path: /v1/queries
- description: Scan a table.
  method: POST
  name: scan
  path: /v1/queries
personas: []
provider_name: Amazon DynamoDB
provider_slug: dynamodb
search_terms:
- document store
- write items in a transaction.
- item operations.
- create a new dynamodb table.
- update a table.
- batch get item
- table management.
- individual table management.
- put item
- serverless
- key-value
- get multiple items from one or more tables.
- update an item.
- cloud
- create a table.
- list tables.
- get an item by primary key.
- update table
- query items.
- delete a dynamodb table.
- put or delete multiple items in batch.
- create backup
- describe a table.
- get item
- batch write item
- scan
- query operations.
- create an on-demand backup.
- update item
- describe table
- delete a table.
- create table
- get an item.
- get items in a transaction.
- list dynamodb tables.
- describe a dynamodb table.
- scan an entire table or index.
- scan a table.
- delete an item.
- managed service
- aws
- dynamodb
- nosql
- delete table
- query items by primary key.
- transact get items
- list on-demand backups.
- database
- list tables
- list backups
- transact write items
- create or replace an item.
- delete item
- database management
- query
slug: database-management
tags:
- AWS
- DynamoDB
- NoSQL
- Database Management
tools:
- description: List DynamoDB tables.
  hints:
    openWorld: true
    readOnly: true
  name: list-tables
- description: Describe a DynamoDB table.
  hints:
    readOnly: true
  name: describe-table
- description: Create a new DynamoDB table.
  hints:
    readOnly: false
  name: create-table
- description: Delete a DynamoDB table.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-table
- description: Create or replace an item.
  hints:
    idempotent: true
    readOnly: false
  name: put-item
- description: Get an item by primary key.
  hints:
    readOnly: true
  name: get-item
- description: Update an item.
  hints:
    idempotent: true
    readOnly: false
  name: update-item
- description: Delete an item.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-item
- description: Query items by primary key.
  hints:
    readOnly: true
  name: query
- description: Scan an entire table or index.
  hints:
    openWorld: true
    readOnly: true
  name: scan
- description: Get multiple items from one or more tables.
  hints:
    readOnly: true
  name: batch-get-item
- description: Put or delete multiple items in batch.
  hints:
    readOnly: false
  name: batch-write-item
- description: Get items in a transaction.
  hints:
    readOnly: true
  name: transact-get-items
- description: Write items in a transaction.
  hints:
    readOnly: false
  name: transact-write-items
- description: Create an on-demand backup.
  hints:
    readOnly: false
  name: create-backup
- description: List on-demand backups.
  hints:
    openWorld: true
    readOnly: true
  name: list-backups
---
