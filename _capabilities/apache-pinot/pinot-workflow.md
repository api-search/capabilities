---
categories:
- analytics
consumed_apis: []
description: Workflow for executing real-time OLAP queries, managing schemas and tables, and monitoring the Pinot cluster.
layout: capability
name: Apache Pinot Analytics Workflow
operations:
- description: Execute SQL query
  method: POST
  name: query
  path: /v1/query
- description: List tables
  method: GET
  name: list-tables
  path: /v1/tables
personas: []
provider_name: Apache Pinot
provider_slug: apache-pinot
search_terms:
- analytics
- get schema
- sql
- get table
- distributed databases
- manages pinot cluster, tables, and schemas
- olap
- list all tables in the pinot cluster
- execute sql query
- list all registered schemas
- queries pinot for real-time analytics and dashboards
- get cluster info
- create table
- database
- real-time
- Data Analyst
- list segments
- create a new pinot table
- Platform Engineer
- get a specific schema definition
- real-time olap
- get the configuration of a specific table
- low latency
- get pinot cluster status and information
- apache
- query
- list schemas
- open source
- list tables
- apache pinot
- list all segments for a table
- execute a sql query against pinot tables
- query sql
slug: pinot-workflow
source_filename: pinot-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Pinot Analytics Workflow\"\n  description: \"Workflow for executing real-time OLAP queries, managing schemas and tables, and monitoring the Pinot cluster.\"\n  tags:\n    - Apache Pinot\n    - Analytics\n    - Real-Time OLAP\n    - SQL\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      PINOT_AUTH_TOKEN: PINOT_AUTH_TOKEN\ncapability:\n  consumes:\n    - type: http\n      namespace: pinot\n      baseUri: https://localhost:9000\n      description: \"Apache Pinot REST API\"\n      resources:\n        - name: queries\n          path: /query/sql\n          description: \"SQL query execution\"\n          operations:\n            - name: querySql\n              method: POST\n              description: \"Execute SQL query\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"\
  $.\"\n        - name: tables\n          path: /tables\n          description: \"Table management\"\n          operations:\n            - name: listTables\n              method: GET\n              description: \"List all tables\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pinot-api\n      description: \"Unified REST API for Pinot analytics.\"\n      resources:\n        - path: /v1/query\n          name: queries\n          operations:\n            - method: POST\n              name: query\n              description: \"Execute SQL query\"\n              call: \"pinot.querySql\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tables\n          name: tables\n          operations:\n            - method: GET\n              name: list-tables\n\
  \              description: \"List tables\"\n              call: \"pinot.listTables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: pinot-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Pinot analytics.\"\n      tools:\n        - name: query-sql\n          description: \"Execute a SQL query against Pinot tables\"\n          hints:\n            readOnly: true\n          call: \"pinot.querySql\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"List all tables in the Pinot cluster\"\n          hints:\n            readOnly: true\n          call: \"pinot.listTables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-table\n          description: \"Get the configuration of a specific table\"\n          hints:\n\
  \            readOnly: true\n          call: \"pinot.getTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-table\n          description: \"Create a new Pinot table\"\n          hints:\n            readOnly: false\n          call: \"pinot.createTable\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schemas\n          description: \"List all registered schemas\"\n          hints:\n            readOnly: true\n          call: \"pinot.listSchemas\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-schema\n          description: \"Get a specific schema definition\"\n          hints:\n            readOnly: true\n          call: \"pinot.getSchema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-segments\n          description: \"List all segments\
  \ for a table\"\n          hints:\n            readOnly: true\n          call: \"pinot.listSegments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cluster-info\n          description: \"Get Pinot cluster status and information\"\n          hints:\n            readOnly: true\n          call: \"pinot.getClusterInfo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-pinot/refs/heads/main/capabilities/pinot-workflow.yaml
tags:
- Apache Pinot
- Analytics
- Real-Time OLAP
- SQL
tools:
- description: Execute a SQL query against Pinot tables
  hints:
    readOnly: true
  name: query-sql
- description: List all tables in the Pinot cluster
  hints:
    readOnly: true
  name: list-tables
- description: Get the configuration of a specific table
  hints:
    readOnly: true
  name: get-table
- description: Create a new Pinot table
  hints:
    readOnly: false
  name: create-table
- description: List all registered schemas
  hints:
    readOnly: true
  name: list-schemas
- description: Get a specific schema definition
  hints:
    readOnly: true
  name: get-schema
- description: List all segments for a table
  hints:
    readOnly: true
  name: list-segments
- description: Get Pinot cluster status and information
  hints:
    readOnly: true
  name: get-cluster-info
---
