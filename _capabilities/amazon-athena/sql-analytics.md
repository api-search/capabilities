---
categories:
- analytics
consumed_apis: []
description: Workflow capability for running and managing SQL analytics queries with Amazon Athena including query execution, named queries, work groups, and data catalog management.
layout: capability
name: SQL Analytics Workflow
operations:
- description: Start a SQL query execution
  method: POST
  name: start-query-execution
  path: /v1/queries
- description: List query executions
  method: GET
  name: list-query-executions
  path: /v1/queries
- description: Create a named query
  method: POST
  name: create-named-query
  path: /v1/named-queries
- description: List named queries
  method: GET
  name: list-named-queries
  path: /v1/named-queries
personas: []
provider_name: Amazon Athena
provider_slug: amazon-athena
search_terms:
- create named query
- save a sql query as a named query for reuse in athena.
- list databases
- serverless
- list tables in an athena database to understand available data.
- analytics
- start a sql query execution
- start query execution
- download the results of a completed athena sql query.
- create a named query
- check the status of a running or completed athena query execution.
- list athena workgroups to understand available query isolation environments.
- sql query management
- run a sql query against s3 data using amazon athena for serverless analytics.
- list table metadata
- aws
- list databases in an athena data catalog to explore available schemas.
- list data catalogs
- list recent query executions in an athena workgroup.
- list named queries
- named query management
- amazon athena
- list work groups
- get query results
- list query executions
- list saved named queries available in an athena workgroup.
- sql
- get query execution
- list data catalogs registered with athena to discover available data sources.
slug: sql-analytics
source_filename: sql-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: SQL Analytics Workflow\n  description: Workflow capability for running and managing SQL analytics queries with Amazon Athena including query execution, named queries, work groups, and data catalog management.\n  tags:\n    - Amazon Athena\n    - SQL\n    - Analytics\n    - Serverless\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nimports:\n  - namespace: athena\n    from: shared/athena-api.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sql-analytics-rest\n      resources:\n        - path: /v1/queries\n          name: queries\n          description: SQL query management\n          operations:\n            - method: POST\n              name: start-query-execution\n              description: Start a SQL query execution\n              call: \"athena.start-query-execution\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \            - method: GET\n              name: list-query-executions\n              description: List query executions\n              call: \"athena.list-query-executions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/named-queries\n          name: named-queries\n          description: Named query management\n          operations:\n            - method: POST\n              name: create-named-query\n              description: Create a named query\n              call: \"athena.create-named-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-named-queries\n              description: List named queries\n              call: \"athena.list-named-queries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ sql-analytics-mcp\n      transport: http\n      tools:\n        - name: start-query-execution\n          description: Run a SQL query against S3 data using Amazon Athena for serverless analytics.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"athena.start-query-execution\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-query-execution\n          description: Check the status of a running or completed Athena query execution.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.get-query-execution\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-query-results\n          description: Download the results of a completed Athena SQL query.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.get-query-results\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-query-executions\n          description: List recent query executions in an Athena workgroup.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-query-executions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-named-query\n          description: Save a SQL query as a named query for reuse in Athena.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"athena.create-named-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-named-queries\n          description: List saved named queries available in an Athena workgroup.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-named-queries\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-work-groups\n          description: List Athena workgroups to understand available query isolation environments.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-work-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-data-catalogs\n          description: List data catalogs registered with Athena to discover available data sources.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-data-catalogs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-databases\n          description: List databases in an Athena data catalog to explore available schemas.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-databases\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-table-metadata\n          description: List tables in an Athena database to understand available data.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"athena.list-table-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\npersonas:\n  - name: Data Analyst\n    description: Runs SQL queries against S3 data using Athena for analytics and reporting.\n    tools:\n      - start-query-execution\n      - get-query-execution\n      - get-query-results\n      - list-query-executions\n      - create-named-query\n      - list-named-queries\n      - list-databases\n      - list-table-metadata\n\n  - name: Data Engineer\n    description: Manages Athena infrastructure including workgroups, data catalogs, and prepared statements.\n    tools:\n      - list-work-groups\n      - list-data-catalogs\n\
  \      - list-databases\n      - list-table-metadata\n      - list-named-queries\n      - list-query-executions\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-athena/refs/heads/main/capabilities/sql-analytics.yaml
tags:
- Amazon Athena
- SQL
- Analytics
- Serverless
- AWS
tools:
- description: Run a SQL query against S3 data using Amazon Athena for serverless analytics.
  hints:
    openWorld: false
    readOnly: false
  name: start-query-execution
- description: Check the status of a running or completed Athena query execution.
  hints:
    openWorld: true
    readOnly: true
  name: get-query-execution
- description: Download the results of a completed Athena SQL query.
  hints:
    openWorld: true
    readOnly: true
  name: get-query-results
- description: List recent query executions in an Athena workgroup.
  hints:
    openWorld: true
    readOnly: true
  name: list-query-executions
- description: Save a SQL query as a named query for reuse in Athena.
  hints:
    openWorld: false
    readOnly: false
  name: create-named-query
- description: List saved named queries available in an Athena workgroup.
  hints:
    openWorld: true
    readOnly: true
  name: list-named-queries
- description: List Athena workgroups to understand available query isolation environments.
  hints:
    openWorld: true
    readOnly: true
  name: list-work-groups
- description: List data catalogs registered with Athena to discover available data sources.
  hints:
    openWorld: true
    readOnly: true
  name: list-data-catalogs
- description: List databases in an Athena data catalog to explore available schemas.
  hints:
    openWorld: true
    readOnly: true
  name: list-databases
- description: List tables in an Athena database to understand available data.
  hints:
    openWorld: true
    readOnly: true
  name: list-table-metadata
---
