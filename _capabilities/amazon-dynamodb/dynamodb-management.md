---
categories: []
consumed_apis: []
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
- workflow capability for nosql database operations.
- getItem
- describe table
- update item
- document store
- amazon dynamodb query items in a table or index
- amazon dynamodb describe a dynamodb table
- deleteItem
- create table
- query
- put item
- updateTable
- amazon dynamodb
- engineers managing amazon dynamodb resources on aws.
- createTable
- listTables
- key-value
- amazon dynamodb update an item in a table
- serverless
- list tables
- nosql database operations business domain for amazon dynamodb.
- amazon dynamodb get an item from a table
- amazon dynamodb list dynamodb tables
- updateItem
- amazon dynamodb update a dynamodb table
- putItem
- database
- delete table
- delete item
- amazon dynamodb create a dynamodb table
- update table
- amazon dynamodb delete a dynamodb table
- amazon dynamodb put an item into a table
- amazon dynamodb delete an item from a table
- deleteTable
- aws
- nosql
- get item
- describeTable
slug: dynamodb-management
source_filename: dynamodb-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon DynamoDB NoSQL Database Operations\n  description: Unified capability for managing DynamoDB tables, items, queries, and transactions for application developers\n    and data engineers.\n  tags:\n  - Amazon DynamoDB\n  - AWS\n  - Database\n  - NoSQL\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: dynamodb\n    baseUri: https://dynamodb.amazonaws.com\n    description: Amazon DynamoDB serverless NoSQL database service.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 Credential={{env.AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: root\n      path: /\n      description: Operations for root resources.\n      operations:\n      - name: createTable\n        method: POST\n    \
  \    description: Amazon DynamoDB Create a DynamoDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DescribeTable\n      description: 'Operations for #DescribeTable resources.'\n      operations:\n      - name: describeTable\n        method: POST\n        description: Amazon DynamoDB Describe a DynamoDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#ListTables\n      description: 'Operations for #ListTables resources.'\n      operations:\n      - name: listTables\n        method: POST\n        description: Amazon DynamoDB List DynamoDB Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#UpdateTable\n      description: 'Operations for #UpdateTable\
  \ resources.'\n      operations:\n      - name: updateTable\n        method: POST\n        description: Amazon DynamoDB Update a DynamoDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DeleteTable\n      description: 'Operations for #DeleteTable resources.'\n      operations:\n      - name: deleteTable\n        method: POST\n        description: Amazon DynamoDB Delete a DynamoDB Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#PutItem\n      description: 'Operations for #PutItem resources.'\n      operations:\n      - name: putItem\n        method: POST\n        description: Amazon DynamoDB Put an Item Into a Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n\
  \      path: /#GetItem\n      description: 'Operations for #GetItem resources.'\n      operations:\n      - name: getItem\n        method: POST\n        description: Amazon DynamoDB Get an Item from a Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#UpdateItem\n      description: 'Operations for #UpdateItem resources.'\n      operations:\n      - name: updateItem\n        method: POST\n        description: Amazon DynamoDB Update an Item in a Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#DeleteItem\n      description: 'Operations for #DeleteItem resources.'\n      operations:\n      - name: deleteItem\n        method: POST\n        description: Amazon DynamoDB Delete an Item from a Table\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#Query\n      description: 'Operations for #Query resources.'\n      operations:\n      - name: query\n        method: POST\n        description: Amazon DynamoDB Query Items in a Table or Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#Scan\n      description: 'Operations for #Scan resources.'\n      operations:\n      - name: scan\n        method: POST\n        description: Amazon DynamoDB Scan Items in a Table or Index\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#BatchGetItem\n      description: 'Operations for #BatchGetItem resources.'\n      operations:\n      - name: batchGetItem\n        method: POST\n        description: Amazon DynamoDB Get Multiple Items from\
  \ One or More Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#BatchWriteItem\n      description: 'Operations for #BatchWriteItem resources.'\n      operations:\n      - name: batchWriteItem\n        method: POST\n        description: Amazon DynamoDB Put or Delete Multiple Items in One or More Tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#TransactGetItems\n      description: 'Operations for #TransactGetItems resources.'\n      operations:\n      - name: transactGetItems\n        method: POST\n        description: Amazon DynamoDB Get Items in a Transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: null\n      path: /#TransactWriteItems\n      description:\
  \ 'Operations for #TransactWriteItems resources.'\n      operations:\n      - name: transactWriteItems\n        method: POST\n        description: Amazon DynamoDB Write Items in a Transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: dynamodb-api\n    description: Unified REST API for NoSQL Database Operations.\n    resources:\n    - path: /v1/resource\n      name: createTable\n      description: Amazon DynamoDB Create a DynamoDB Table\n      operations:\n      - method: POST\n        name: createTable\n        description: Amazon DynamoDB Create a DynamoDB Table\n        call: dynamodb.createTable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DescribeTable\n      name: describeTable\n      description: Amazon DynamoDB Describe a DynamoDB Table\n      operations:\n      - method: POST\n        name:\
  \ describeTable\n        description: Amazon DynamoDB Describe a DynamoDB Table\n        call: dynamodb.describeTable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#ListTables\n      name: listTables\n      description: Amazon DynamoDB List DynamoDB Tables\n      operations:\n      - method: POST\n        name: listTables\n        description: Amazon DynamoDB List DynamoDB Tables\n        call: dynamodb.listTables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#UpdateTable\n      name: updateTable\n      description: Amazon DynamoDB Update a DynamoDB Table\n      operations:\n      - method: POST\n        name: updateTable\n        description: Amazon DynamoDB Update a DynamoDB Table\n        call: dynamodb.updateTable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DeleteTable\n      name: deleteTable\n      description: Amazon DynamoDB Delete a DynamoDB\
  \ Table\n      operations:\n      - method: POST\n        name: deleteTable\n        description: Amazon DynamoDB Delete a DynamoDB Table\n        call: dynamodb.deleteTable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#PutItem\n      name: putItem\n      description: Amazon DynamoDB Put an Item Into a Table\n      operations:\n      - method: POST\n        name: putItem\n        description: Amazon DynamoDB Put an Item Into a Table\n        call: dynamodb.putItem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#GetItem\n      name: getItem\n      description: Amazon DynamoDB Get an Item from a Table\n      operations:\n      - method: POST\n        name: getItem\n        description: Amazon DynamoDB Get an Item from a Table\n        call: dynamodb.getItem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#UpdateItem\n      name: updateItem\n      description:\
  \ Amazon DynamoDB Update an Item in a Table\n      operations:\n      - method: POST\n        name: updateItem\n        description: Amazon DynamoDB Update an Item in a Table\n        call: dynamodb.updateItem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#DeleteItem\n      name: deleteItem\n      description: Amazon DynamoDB Delete an Item from a Table\n      operations:\n      - method: POST\n        name: deleteItem\n        description: Amazon DynamoDB Delete an Item from a Table\n        call: dynamodb.deleteItem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/#Query\n      name: query\n      description: Amazon DynamoDB Query Items in a Table or Index\n      operations:\n      - method: POST\n        name: query\n        description: Amazon DynamoDB Query Items in a Table or Index\n        call: dynamodb.query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9091\n    namespace: dynamodb-mcp\n    transport: http\n    description: MCP server for AI-assisted NoSQL Database Operations.\n    tools:\n    - name: create-table\n      description: Amazon DynamoDB Create a DynamoDB Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.createTable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-table\n      description: Amazon DynamoDB Describe a DynamoDB Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.describeTable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tables\n      description: Amazon DynamoDB List DynamoDB Tables\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.listTables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-table\n      description: Amazon DynamoDB Update a DynamoDB\
  \ Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.updateTable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-table\n      description: Amazon DynamoDB Delete a DynamoDB Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.deleteTable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-item\n      description: Amazon DynamoDB Put an Item Into a Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.putItem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-item\n      description: Amazon DynamoDB Get an Item from a Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.getItem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-item\n      description: Amazon DynamoDB Update an Item\
  \ in a Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.updateItem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-item\n      description: Amazon DynamoDB Delete an Item from a Table\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.deleteItem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query\n      description: Amazon DynamoDB Query Items in a Table or Index\n      hints:\n        readOnly: false\n        destructive: false\n      call: dynamodb.query\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-dynamodb/refs/heads/main/capabilities/dynamodb-management.yaml
tags:
- Amazon DynamoDB
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
