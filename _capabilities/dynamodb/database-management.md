---
categories: []
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
- individual table management.
- get item
- batch write item
- nosql
- delete a table.
- delete an item.
- get items in a transaction.
- list on-demand backups.
- managed service
- batch get item
- query items.
- update table
- delete a dynamodb table.
- get multiple items from one or more tables.
- get an item.
- describe table
- put item
- create an on-demand backup.
- put or delete multiple items in batch.
- dynamodb
- query
- list backups
- aws
- scan an entire table or index.
- get an item by primary key.
- key-value
- list tables.
- scan a table.
- item operations.
- database management
- create table
- create a new dynamodb table.
- delete item
- transact write items
- update a table.
- create a table.
- cloud
- describe a table.
- database
- delete table
- update an item.
- write items in a transaction.
- scan
- transact get items
- describe a dynamodb table.
- serverless
- create backup
- document store
- list dynamodb tables.
- query items by primary key.
- list tables
- query operations.
- table management.
- update item
- create or replace an item.
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
