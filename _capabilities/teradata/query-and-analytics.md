---
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
- list cross-system query summaries from querygrid.
- execute sql queries and analytics.
- manage querygrid data fabric infrastructure.
- create session
- data warehousing
- Platform Administrator
- teradata
- list querygrid queries
- database
- sql
- analytics
- enterprise
- list query systems
- data management
- system and fabric configuration management.
- create a new query session on a vantage system.
- health monitoring and issue detection.
- list available vantage systems.
- machine learning
- list available vantage systems for query execution.
- Data Analyst
- executes queries and analyzes data across vantage systems.
- sql query execution and session management.
- execute a sql query.
- execute query
- Data Engineer
- available systems.
- create a query session.
- manages data fabric infrastructure and cross-system connectivity.
- Application Developer
- cloud
- query sessions.
- query
- get query status
- integrates applications with teradata via rest apis.
- sql queries.
- administers querygrid systems, nodes, and software.
- execute a sql query against teradata vantage.
- get the status and results of a submitted query.
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
