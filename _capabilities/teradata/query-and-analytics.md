---
categories:
- analytics
consumed_apis:
- query-service
- querygrid-manager
description: Workflow capability for executing SQL queries and analytics against Teradata Vantage systems. Combines Query Service for SQL execution with QueryGrid for cross-system query monitoring. Used by data analysts and application developers.
layout: capability
name: Teradata Query and Analytics
operations:
- description: List available Vantage systems.
  method: GET
  name: list-query-systems
  path: /v1/systems
- description: Create a query session.
  method: POST
  name: create-session
  path: /v1/sessions
- description: Execute a SQL query.
  method: POST
  name: execute-query
  path: /v1/queries
personas: []
provider_name: Teradata
provider_slug: teradata
search_terms:
- get query status
- list querygrid queries
- sql
- execute sql queries and analytics.
- query sessions.
- administers querygrid systems, nodes, and software.
- execute a sql query against teradata vantage.
- list available vantage systems.
- create a new query session on a vantage system.
- enterprise
- execute query
- execute a sql query.
- available systems.
- list cross-system query summaries from querygrid.
- Data Analyst
- manage querygrid data fabric infrastructure.
- executes queries and analyzes data across vantage systems.
- Data Engineer
- sql queries.
- manages data fabric infrastructure and cross-system connectivity.
- query
- teradata
- Application Developer
- machine learning
- create a query session.
- list query systems
- create session
- analytics
- list available vantage systems for query execution.
- system and fabric configuration management.
- cloud
- data warehousing
- integrates applications with teradata via rest apis.
- get the status and results of a submitted query.
- health monitoring and issue detection.
- database
- data management
- Platform Administrator
- sql query execution and session management.
slug: query-and-analytics
tags:
- Teradata
- Query
- Analytics
- SQL
tools:
- description: List available Vantage systems for query execution.
  hints:
    readOnly: true
  name: list-query-systems
- description: Create a new query session on a Vantage system.
  hints:
    readOnly: false
  name: create-session
- description: Execute a SQL query against Teradata Vantage.
  hints:
    readOnly: false
  name: execute-query
- description: Get the status and results of a submitted query.
  hints:
    readOnly: true
  name: get-query-status
- description: List cross-system query summaries from QueryGrid.
  hints:
    readOnly: true
  name: list-querygrid-queries
---
