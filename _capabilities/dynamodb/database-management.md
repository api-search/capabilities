---
api_specs:
- filename: dynamodb-openapi.yml
  format: yaml
  label: dynamodb
  slug: dynamodb
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/dynamodb/refs/heads/main/openapi/dynamodb-openapi.yml
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
- managed service
- describe a table.
- list dynamodb tables.
- delete table
- query operations.
- delete an item.
- delete item
- key-value
- get an item.
- describe table
- update an item.
- list tables
- write items in a transaction.
- create table
- document store
- table management.
- query items.
- create backup
- transact get items
- create an on-demand backup.
- create or replace an item.
- describe a dynamodb table.
- individual table management.
- list tables.
- aws
- list on-demand backups.
- delete a table.
- create a new dynamodb table.
- put or delete multiple items in batch.
- update table
- cloud
- list backups
- batch write item
- update item
- dynamodb
- database management
- get items in a transaction.
- database
- scan an entire table or index.
- query
- nosql
- update a table.
- query items by primary key.
- get multiple items from one or more tables.
- transact write items
- scan
- get an item by primary key.
- put item
- create a table.
- get item
- delete a dynamodb table.
- serverless
- batch get item
- scan a table.
- item operations.
slug: database-management
source_filename: database-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon DynamoDB Database Management\"\n  description: \"Unified workflow for managing DynamoDB tables, items, queries, batch operations, transactions, and backups. Used by backend developers and data engineers.\"\n  tags:\n    - AWS\n    - DynamoDB\n    - NoSQL\n    - Database Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: dynamodb\n      location: ./shared/dynamodb.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: dynamodb-management-api\n      description: \"Unified REST API for DynamoDB database management.\"\n      resources:\n        - path: /v1/tables\n          name: tables\n          description: \"Table management.\"\n          operations:\n            - method: GET\n              name: list-tables\n\
  \              description: \"List tables.\"\n              call: \"dynamodb.list-tables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-table\n              description: \"Create a table.\"\n              call: \"dynamodb.create-table\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tables/{id}\n          name: table-details\n          description: \"Individual table management.\"\n          operations:\n            - method: GET\n              name: describe-table\n              description: \"Describe a table.\"\n              call: \"dynamodb.describe-table\"\n              with:\n                tableName: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-table\n              description:\
  \ \"Update a table.\"\n              call: \"dynamodb.update-table\"\n              with:\n                tableName: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-table\n              description: \"Delete a table.\"\n              call: \"dynamodb.delete-table\"\n              with:\n                tableName: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items\n          name: items\n          description: \"Item operations.\"\n          operations:\n            - method: POST\n              name: put-item\n              description: \"Create or replace an item.\"\n              call: \"dynamodb.put-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-item\n             \
  \ description: \"Get an item.\"\n              call: \"dynamodb.get-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: \"Query operations.\"\n          operations:\n            - method: POST\n              name: query\n              description: \"Query items.\"\n              call: \"dynamodb.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: scan\n              description: \"Scan a table.\"\n              call: \"dynamodb.scan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: dynamodb-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted DynamoDB database management.\"\n      tools:\n        - name: list-tables\n\
  \          description: \"List DynamoDB tables.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dynamodb.list-tables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-table\n          description: \"Describe a DynamoDB table.\"\n          hints:\n            readOnly: true\n          call: \"dynamodb.describe-table\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-table\n          description: \"Create a new DynamoDB table.\"\n          hints:\n            readOnly: false\n          call: \"dynamodb.create-table\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-table\n          description: \"Delete a DynamoDB table.\"\n       \
  \   hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"dynamodb.delete-table\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-item\n          description: \"Create or replace an item.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"dynamodb.put-item\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-item\n          description: \"Get an item by primary key.\"\n          hints:\n            readOnly: true\n          call: \"dynamodb.get-item\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-item\n          description:\
  \ \"Update an item.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"dynamodb.update-item\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-item\n          description: \"Delete an item.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"dynamodb.delete-item\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query\n          description: \"Query items by primary key.\"\n          hints:\n            readOnly: true\n          call: \"dynamodb.query\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: scan\n    \
  \      description: \"Scan an entire table or index.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dynamodb.scan\"\n          with:\n            tableName: \"tools.tableName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-get-item\n          description: \"Get multiple items from one or more tables.\"\n          hints:\n            readOnly: true\n          call: \"dynamodb.batch-get-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-write-item\n          description: \"Put or delete multiple items in batch.\"\n          hints:\n            readOnly: false\n          call: \"dynamodb.batch-write-item\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: transact-get-items\n          description: \"Get items in a transaction.\"\n          hints:\n        \
  \    readOnly: true\n          call: \"dynamodb.transact-get-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: transact-write-items\n          description: \"Write items in a transaction.\"\n          hints:\n            readOnly: false\n          call: \"dynamodb.transact-write-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-backup\n          description: \"Create an on-demand backup.\"\n          hints:\n            readOnly: false\n          call: \"dynamodb.create-backup\"\n          with:\n            tableName: \"tools.tableName\"\n            backupName: \"tools.backupName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-backups\n          description: \"List on-demand backups.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dynamodb.list-backups\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dynamodb/refs/heads/main/capabilities/database-management.yaml
tags:
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
