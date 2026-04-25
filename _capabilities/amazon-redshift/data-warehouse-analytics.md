---
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
- analytics
- describe statement
- describe table
- data lake
- list databases in a redshift cluster or workgroup
- batch execute statement
- sql statement execution
- get details about a sql statement execution
- list tables in a schema
- execute multiple sql statements in a batch transaction
- cancel statement
- describe the columns of a table
- big data
- list schemas in a database
- machine learning
- list schemas
- serverless
- table metadata
- get statement result
- sql
- list tables
- list sql statement executions
- database metadata
- data warehouse
- execute a sql statement asynchronously against redshift
- list sql statements
- etl
- list statements
- execute a sql statement
- execute statement
- aws
- retrieve results from a completed sql statement
- cancel a running sql statement
- list databases
- cloud
- amazon
slug: data-warehouse-analytics
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
