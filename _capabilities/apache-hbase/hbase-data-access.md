---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Hbase Data Access
operations: []
personas: []
provider_name: Apache HBase
provider_slug: apache-hbase
search_terms:
- apache
- bigtable
- open source
- nosql
- wide column
- hadoop
- big data
- database
slug: hbase-data-access
source_filename: hbase-data-access.yaml
source_heading: Capability Spec
source_yaml: "name: Apache HBase Data Access\ndescription: Workflow capability for reading and writing data in Apache HBase distributed NoSQL database\npersona: Data Engineer\nworkflow:\n  - step: list-tables\n    name: List HBase Tables\n    description: Discover available tables in the HBase cluster\n    capability: hbase-rest\n    operation: listTables\n    server:\n      rest: http://localhost:8080\n      mcp: http://localhost:9090\n\n  - step: get-schema\n    name: Get Table Schema\n    description: Retrieve column family configuration for a target table\n    capability: hbase-rest\n    operation: getTableSchema\n    server:\n      rest: http://localhost:8080\n      mcp: http://localhost:9090\n\n  - step: write-row\n    name: Write Row\n    description: Put a row with cell data into an HBase table\n    capability: hbase-rest\n    operation: putRow\n    server:\n      rest: http://localhost:8080\n      mcp: http://localhost:9090\n\n  - step: read-row\n    name: Read Row\n    description:\
  \ Get all cells for a row key from an HBase table\n    capability: hbase-rest\n    operation: getRow\n    server:\n      rest: http://localhost:8080\n      mcp: http://localhost:9090\n\ntools:\n  - name: listTables\n    description: List all tables in the HBase cluster\n    server:\n      rest:\n        baseUrl: http://localhost:8080\n        path: /\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listTables\n        method: POST\n\n  - name: getTableSchema\n    description: Get the column family schema for an HBase table\n    server:\n      rest:\n        baseUrl: http://localhost:8080\n        path: /{tableName}/schema\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getTableSchema\n        method: POST\n\n  - name: putRow\n    description: Write cells to a row in an HBase table\n    server:\n      rest:\n        baseUrl: http://localhost:8080\n        path: /{tableName}/{rowKey}\n        method:\
  \ PUT\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/putRow\n        method: POST\n\n  - name: getRow\n    description: Read all cells for a row key from an HBase table\n    server:\n      rest:\n        baseUrl: http://localhost:8080\n        path: /{tableName}/{rowKey}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getRow\n        method: POST\n\n  - name: createScanner\n    description: Create a scanner to iterate over rows in an HBase table\n    server:\n      rest:\n        baseUrl: http://localhost:8080\n        path: /{tableName}/scanner\n        method: PUT\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/createScanner\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-hbase/refs/heads/main/capabilities/hbase-data-access.yaml
tags: []
tools: []
---
