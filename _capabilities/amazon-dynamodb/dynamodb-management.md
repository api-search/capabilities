---
categories: []
consumed_apis:
- dynamodb
description: Unified capability for managing DynamoDB tables, items, queries, and transactions for application developers and data engineers.
layout: capability
name: Amazon DynamoDB NoSQL Database Operations
operations:
- description: Amazon DynamoDB Create a DynamoDB Table
  method: POST
  name: createTable
  path: /v1/resource
- description: Amazon DynamoDB Describe a DynamoDB Table
  method: POST
  name: describeTable
  path: /v1/#DescribeTable
- description: Amazon DynamoDB List DynamoDB Tables
  method: POST
  name: listTables
  path: /v1/#ListTables
- description: Amazon DynamoDB Update a DynamoDB Table
  method: POST
  name: updateTable
  path: /v1/#UpdateTable
- description: Amazon DynamoDB Delete a DynamoDB Table
  method: POST
  name: deleteTable
  path: /v1/#DeleteTable
- description: Amazon DynamoDB Put an Item Into a Table
  method: POST
  name: putItem
  path: /v1/#PutItem
- description: Amazon DynamoDB Get an Item from a Table
  method: POST
  name: getItem
  path: /v1/#GetItem
- description: Amazon DynamoDB Update an Item in a Table
  method: POST
  name: updateItem
  path: /v1/#UpdateItem
- description: Amazon DynamoDB Delete an Item from a Table
  method: POST
  name: deleteItem
  path: /v1/#DeleteItem
- description: Amazon DynamoDB Query Items in a Table or Index
  method: POST
  name: query
  path: /v1/#Query
personas: []
provider_name: Amazon DynamoDB
provider_slug: amazon-dynamodb
search_terms:
- amazon dynamodb describe a dynamodb table
- update table
- amazon dynamodb query items in a table or index
- amazon dynamodb
- nosql database operations business domain for amazon dynamodb.
- updateItem
- deleteItem
- nosql
- create table
- deleteTable
- delete table
- createTable
- putItem
- amazon dynamodb get an item from a table
- amazon dynamodb delete a dynamodb table
- describe table
- database
- amazon dynamodb put an item into a table
- amazon dynamodb list dynamodb tables
- serverless
- document store
- query
- update item
- list tables
- updateTable
- amazon dynamodb update a dynamodb table
- describeTable
- put item
- amazon dynamodb create a dynamodb table
- getItem
- get item
- delete item
- key-value
- engineers managing amazon dynamodb resources on aws.
- aws
- amazon dynamodb update an item in a table
- amazon dynamodb delete an item from a table
- listTables
- workflow capability for nosql database operations.
slug: dynamodb-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon DynamoDB NoSQL Database Operations\"\n  description: \"Unified capability for managing DynamoDB tables, items, queries, and transactions for application developers and data engineers.\"\n  tags:\n    - Amazon DynamoDB\n    - AWS\n    - Database\n    - NoSQL\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n\ncapability:\n  consumes:\n    - import: dynamodb\n      location: ./shared/dynamodb.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: dynamodb-api\n      description: \"Unified REST API for NoSQL Database Operations.\"\n      resources:\n        - path: /v1/resource\n          name: createTable\n          description: \"Amazon DynamoDB Create a DynamoDB Table\"\n          operations:\n            - method: POST\n              name: createTable\n        \
  \      description: \"Amazon DynamoDB Create a DynamoDB Table\"\n              call: \"dynamodb.createTable\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DescribeTable\n          name: describeTable\n          description: \"Amazon DynamoDB Describe a DynamoDB Table\"\n          operations:\n            - method: POST\n              name: describeTable\n              description: \"Amazon DynamoDB Describe a DynamoDB Table\"\n              call: \"dynamodb.describeTable\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#ListTables\n          name: listTables\n          description: \"Amazon DynamoDB List DynamoDB Tables\"\n          operations:\n            - method: POST\n              name: listTables\n              description: \"Amazon DynamoDB List DynamoDB Tables\"\n              call: \"dynamodb.listTables\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#UpdateTable\n          name: updateTable\n          description: \"Amazon DynamoDB Update a DynamoDB Table\"\n          operations:\n            - method: POST\n              name: updateTable\n              description: \"Amazon DynamoDB Update a DynamoDB Table\"\n              call: \"dynamodb.updateTable\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DeleteTable\n          name: deleteTable\n          description: \"Amazon DynamoDB Delete a DynamoDB Table\"\n          operations:\n            - method: POST\n              name: deleteTable\n              description: \"Amazon DynamoDB Delete a DynamoDB Table\"\n              call: \"dynamodb.deleteTable\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#PutItem\n          name: putItem\n          description:\
  \ \"Amazon DynamoDB Put an Item Into a Table\"\n          operations:\n            - method: POST\n              name: putItem\n              description: \"Amazon DynamoDB Put an Item Into a Table\"\n              call: \"dynamodb.putItem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#GetItem\n          name: getItem\n          description: \"Amazon DynamoDB Get an Item from a Table\"\n          operations:\n            - method: POST\n              name: getItem\n              description: \"Amazon DynamoDB Get an Item from a Table\"\n              call: \"dynamodb.getItem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#UpdateItem\n          name: updateItem\n          description: \"Amazon DynamoDB Update an Item in a Table\"\n          operations:\n            - method: POST\n              name: updateItem\n              description:\
  \ \"Amazon DynamoDB Update an Item in a Table\"\n              call: \"dynamodb.updateItem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#DeleteItem\n          name: deleteItem\n          description: \"Amazon DynamoDB Delete an Item from a Table\"\n          operations:\n            - method: POST\n              name: deleteItem\n              description: \"Amazon DynamoDB Delete an Item from a Table\"\n              call: \"dynamodb.deleteItem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/#Query\n          name: query\n          description: \"Amazon DynamoDB Query Items in a Table or Index\"\n          operations:\n            - method: POST\n              name: query\n              description: \"Amazon DynamoDB Query Items in a Table or Index\"\n              call: \"dynamodb.query\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: dynamodb-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NoSQL Database Operations.\"\n      tools:\n        - name: create-table\n          description: \"Amazon DynamoDB Create a DynamoDB Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.createTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-table\n          description: \"Amazon DynamoDB Describe a DynamoDB Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.describeTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"Amazon DynamoDB List DynamoDB Tables\"\n          hints:\n            readOnly: false\n\
  \            destructive: false\n          call: \"dynamodb.listTables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-table\n          description: \"Amazon DynamoDB Update a DynamoDB Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.updateTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-table\n          description: \"Amazon DynamoDB Delete a DynamoDB Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.deleteTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: put-item\n          description: \"Amazon DynamoDB Put an Item Into a Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.putItem\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-item\n          description: \"Amazon DynamoDB Get an Item from a Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.getItem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-item\n          description: \"Amazon DynamoDB Update an Item in a Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.updateItem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-item\n          description: \"Amazon DynamoDB Delete an Item from a Table\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.deleteItem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query\n\
  \          description: \"Amazon DynamoDB Query Items in a Table or Index\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dynamodb.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-dynamodb/refs/heads/main/capabilities/dynamodb-management.yaml
tags:
- Amazon DynamoDB
- AWS
- Database
- NoSQL
tools:
- description: Amazon DynamoDB Create a DynamoDB Table
  hints:
    destructive: false
    readOnly: false
  name: create-table
- description: Amazon DynamoDB Describe a DynamoDB Table
  hints:
    destructive: false
    readOnly: false
  name: describe-table
- description: Amazon DynamoDB List DynamoDB Tables
  hints:
    destructive: false
    readOnly: false
  name: list-tables
- description: Amazon DynamoDB Update a DynamoDB Table
  hints:
    destructive: false
    readOnly: false
  name: update-table
- description: Amazon DynamoDB Delete a DynamoDB Table
  hints:
    destructive: false
    readOnly: false
  name: delete-table
- description: Amazon DynamoDB Put an Item Into a Table
  hints:
    destructive: false
    readOnly: false
  name: put-item
- description: Amazon DynamoDB Get an Item from a Table
  hints:
    destructive: false
    readOnly: false
  name: get-item
- description: Amazon DynamoDB Update an Item in a Table
  hints:
    destructive: false
    readOnly: false
  name: update-item
- description: Amazon DynamoDB Delete an Item from a Table
  hints:
    destructive: false
    readOnly: false
  name: delete-item
- description: Amazon DynamoDB Query Items in a Table or Index
  hints:
    destructive: false
    readOnly: false
  name: query
---
