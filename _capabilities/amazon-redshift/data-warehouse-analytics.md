---
categories:
- analytics
consumed_apis:
- redshift-data
description: Data warehouse analytics workflow combining Redshift Data API for SQL execution, statement management, and database metadata exploration. Used by data analysts and engineers for ad-hoc queries, ETL processing, and serverless data warehouse operations.
layout: capability
name: Amazon Redshift Data Warehouse Analytics
operations:
- description: Execute a SQL statement
  method: POST
  name: execute-statement
  path: /v1/statements
- description: List SQL statements
  method: GET
  name: list-statements
  path: /v1/statements
- description: List databases
  method: GET
  name: list-databases
  path: /v1/databases
- description: List tables in a schema
  method: GET
  name: list-tables
  path: /v1/tables
personas: []
provider_name: Amazon Redshift
provider_slug: amazon-redshift
search_terms:
- list sql statement executions
- execute a sql statement asynchronously against redshift
- etl
- aws
- cancel statement
- table metadata
- amazon
- get statement result
- analytics
- list statements
- execute a sql statement
- execute statement
- list tables in a schema
- big data
- sql
- execute multiple sql statements in a batch transaction
- list databases in a redshift cluster or workgroup
- data warehouse
- list schemas in a database
- list schemas
- database metadata
- cloud
- get details about a sql statement execution
- data lake
- machine learning
- describe table
- list databases
- describe statement
- list tables
- list sql statements
- describe the columns of a table
- batch execute statement
- serverless
- retrieve results from a completed sql statement
- sql statement execution
- cancel a running sql statement
slug: data-warehouse-analytics
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Redshift Data Warehouse Analytics\"\n  description: \"Data warehouse analytics workflow combining Redshift Data API for SQL execution, statement management, and database metadata exploration. Used by data analysts and engineers for ad-hoc queries, ETL processing, and serverless data warehouse operations.\"\n  tags:\n    - Amazon\n    - AWS\n    - Analytics\n    - Data Warehouse\n    - SQL\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: redshift-data\n      location: ./shared/redshift-data.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: redshift-analytics-api\n      description: \"Unified REST API for Amazon Redshift data warehouse analytics.\"\n      resources:\n        - path: /v1/statements\n\
  \          name: statements\n          description: \"SQL statement execution\"\n          operations:\n            - method: POST\n              name: execute-statement\n              description: \"Execute a SQL statement\"\n              call: \"redshift-data.execute-statement\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-statements\n              description: \"List SQL statements\"\n              call: \"redshift-data.list-statements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/databases\n          name: databases\n          description: \"Database metadata\"\n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List databases\"\n              call: \"redshift-data.list-databases\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/tables\n          name: tables\n          description: \"Table metadata\"\n          operations:\n            - method: GET\n              name: list-tables\n              description: \"List tables in a schema\"\n              call: \"redshift-data.list-tables\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: redshift-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Redshift data warehouse analytics.\"\n      tools:\n        - name: execute-statement\n          description: \"Execute a SQL statement asynchronously against Redshift\"\n          hints:\n            readOnly: false\n          call: \"redshift-data.execute-statement\"\n          with:\n            sql: \"tools.sql\"\n            database: \"tools.database\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: batch-execute-statement\n          description: \"Execute multiple SQL statements in a batch transaction\"\n          hints:\n            readOnly: false\n          call: \"redshift-data.batch-execute-statement\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-statement\n          description: \"Get details about a SQL statement execution\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.describe-statement\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-statements\n          description: \"List SQL statement executions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"redshift-data.list-statements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-statement\n          description:\
  \ \"Cancel a running SQL statement\"\n          hints:\n            destructive: true\n          call: \"redshift-data.cancel-statement\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-statement-result\n          description: \"Retrieve results from a completed SQL statement\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.get-statement-result\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-databases\n          description: \"List databases in a Redshift cluster or workgroup\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.list-databases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schemas\n          description: \"List schemas in a database\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.list-schemas\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"List tables in a schema\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.list-tables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-table\n          description: \"Describe the columns of a table\"\n          hints:\n            readOnly: true\n          call: \"redshift-data.describe-table\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-redshift/refs/heads/main/capabilities/data-warehouse-analytics.yaml
tags:
- Amazon
- AWS
- Analytics
- Data Warehouse
- SQL
tools:
- description: Execute a SQL statement asynchronously against Redshift
  hints:
    readOnly: false
  name: execute-statement
- description: Execute multiple SQL statements in a batch transaction
  hints:
    readOnly: false
  name: batch-execute-statement
- description: Get details about a SQL statement execution
  hints:
    readOnly: true
  name: describe-statement
- description: List SQL statement executions
  hints:
    openWorld: true
    readOnly: true
  name: list-statements
- description: Cancel a running SQL statement
  hints:
    destructive: true
  name: cancel-statement
- description: Retrieve results from a completed SQL statement
  hints:
    readOnly: true
  name: get-statement-result
- description: List databases in a Redshift cluster or workgroup
  hints:
    readOnly: true
  name: list-databases
- description: List schemas in a database
  hints:
    readOnly: true
  name: list-schemas
- description: List tables in a schema
  hints:
    readOnly: true
  name: list-tables
- description: Describe the columns of a table
  hints:
    readOnly: true
  name: describe-table
---
