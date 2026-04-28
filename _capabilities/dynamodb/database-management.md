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
- update an item.
- transact write items
- list tables
- list backups
- put or delete multiple items in batch.
- create backup
- delete an item.
- get an item.
- batch get item
- scan a table.
- delete a table.
- update table
- query items by primary key.
- describe table
- item operations.
- describe a table.
- document store
- query items.
- scan an entire table or index.
- update item
- delete table
- batch write item
- get items in a transaction.
- delete a dynamodb table.
- update a table.
- list on-demand backups.
- table management.
- put item
- get an item by primary key.
- query
- create table
- create an on-demand backup.
- query operations.
- delete item
- managed service
- key-value
- nosql
- serverless
- transact get items
- get multiple items from one or more tables.
- list dynamodb tables.
- get item
- create a new dynamodb table.
- describe a dynamodb table.
- create a table.
- database management
- individual table management.
- create or replace an item.
- cloud
- list tables.
- database
- scan
- aws
- write items in a transaction.
- dynamodb
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
