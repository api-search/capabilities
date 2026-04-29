---
categories:
- analytics
consumed_apis:
- redshift
- redshift-data
description: Workflow capability for managing Amazon Redshift clusters and executing SQL queries for data analytics.
layout: capability
name: Amazon Redshift Data Warehouse Workflow
operations: []
personas: []
provider_name: AWS Redshift
provider_slug: aws-redshift
search_terms:
- list_sql_statements
- data warehouse
- create a snapshot of a redshift cluster
- delete_cluster
- big data
- get_sql_result
- create_snapshot
- cloud database
- cancel a running sql statement
- execute a sql statement against a redshift cluster
- cancel_sql_statement
- get the result of a sql statement execution
- create a new amazon redshift cluster
- sql
- delete a redshift cluster
- create_cluster
- list_clusters
- analytics
- execute_sql
- list all redshift clusters in the account
- list recent sql statement executions
slug: data-warehouse-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon Redshift Data Warehouse Workflow\n  description: Workflow capability for managing Amazon Redshift clusters and executing SQL queries for data analytics.\n  tags:\n    - Analytics\n    - Data Warehouse\n    - SQL\n    - Cloud Database\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n    - import: redshift\n      location: ./shared/redshift.yaml\n    - import: redshift-data\n      location: ./shared/redshift-data.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-api\n      resources:\n        - label: Create Cluster\n          method: POST\n          path: /clusters\n        - label: List Clusters\n          method: GET\n          path: /clusters\n        - label: Delete Cluster\n          method: DELETE\n\
  \          path: /clusters/{id}\n        - label: Create Snapshot\n          method: POST\n          path: /snapshots\n        - label: Execute SQL\n          method: POST\n          path: /sql/execute\n        - label: Get SQL Result\n          method: GET\n          path: /sql/results/{id}\n        - label: List SQL Statements\n          method: GET\n          path: /sql/statements\n        - label: Cancel SQL Statement\n          method: DELETE\n          path: /sql/statements/{id}\n    - type: mcp\n      port: 9090\n      namespace: workflow-mcp\n      transport: http\n      tools:\n        - name: create_cluster\n          description: Create a new Amazon Redshift cluster\n        - name: list_clusters\n          description: List all Redshift clusters in the account\n        - name: delete_cluster\n          description: Delete a Redshift cluster\n        - name: create_snapshot\n          description: Create a snapshot of a Redshift cluster\n        - name: execute_sql\n       \
  \   description: Execute a SQL statement against a Redshift cluster\n        - name: get_sql_result\n          description: Get the result of a SQL statement execution\n        - name: list_sql_statements\n          description: List recent SQL statement executions\n        - name: cancel_sql_statement\n          description: Cancel a running SQL statement\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-redshift/refs/heads/main/capabilities/data-warehouse-workflow.yaml
tags:
- Analytics
- Data Warehouse
- SQL
- Cloud Database
tools:
- description: Create a new Amazon Redshift cluster
  hints: {}
  name: create_cluster
- description: List all Redshift clusters in the account
  hints: {}
  name: list_clusters
- description: Delete a Redshift cluster
  hints: {}
  name: delete_cluster
- description: Create a snapshot of a Redshift cluster
  hints: {}
  name: create_snapshot
- description: Execute a SQL statement against a Redshift cluster
  hints: {}
  name: execute_sql
- description: Get the result of a SQL statement execution
  hints: {}
  name: get_sql_result
- description: List recent SQL statement executions
  hints: {}
  name: list_sql_statements
- description: Cancel a running SQL statement
  hints: {}
  name: cancel_sql_statement
---
