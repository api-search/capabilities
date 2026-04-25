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
- sql
- list all registered schemas
- execute sql query
- real-time olap
- get the configuration of a specific table
- apache pinot
- get table
- get a specific schema definition
- open source
- distributed databases
- database
- manages pinot cluster, tables, and schemas
- get cluster info
- apache
- Platform Engineer
- query
- list all tables in the pinot cluster
- olap
- Data Analyst
- query sql
- list all segments for a table
- get pinot cluster status and information
- queries pinot for real-time analytics and dashboards
- get schema
- low latency
- list segments
- analytics
- list schemas
- create table
- execute a sql query against pinot tables
- real-time
- list tables
- create a new pinot table
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
