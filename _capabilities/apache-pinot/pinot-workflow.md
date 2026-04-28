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
- manages pinot cluster, tables, and schemas
- list schemas
- list all tables in the pinot cluster
- execute sql query
- execute a sql query against pinot tables
- list all registered schemas
- query
- apache pinot
- list segments
- get table
- Data Analyst
- get a specific schema definition
- create table
- queries pinot for real-time analytics and dashboards
- low latency
- olap
- database
- Platform Engineer
- create a new pinot table
- real-time olap
- apache
- get the configuration of a specific table
- analytics
- open source
- query sql
- real-time
- get schema
- sql
- get cluster info
- list tables
- get pinot cluster status and information
- list all segments for a table
- distributed databases
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
