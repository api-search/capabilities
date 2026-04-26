---
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
- create a new pinot table
- sql
- analytics
- execute sql query
- database
- list all tables in the pinot cluster
- list all segments for a table
- queries pinot for real-time analytics and dashboards
- real-time olap
- query
- get table
- get cluster info
- list schemas
- apache
- list segments
- get pinot cluster status and information
- real-time
- get schema
- query sql
- list all registered schemas
- create table
- get a specific schema definition
- manages pinot cluster, tables, and schemas
- apache pinot
- list tables
- get the configuration of a specific table
- low latency
- distributed databases
- Platform Engineer
- olap
- execute a sql query against pinot tables
- Data Analyst
- open source
slug: pinot-workflow
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
