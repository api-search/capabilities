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
- enterprise
- sql
- get query status
- execute a sql query against teradata vantage.
- integrates applications with teradata via rest apis.
- execute sql queries and analytics.
- cloud
- machine learning
- health monitoring and issue detection.
- execute a sql query.
- list cross-system query summaries from querygrid.
- database
- list querygrid queries
- create a query session.
- get the status and results of a submitted query.
- Data Engineer
- query
- list available vantage systems.
- sql query execution and session management.
- create a new query session on a vantage system.
- Data Analyst
- manages data fabric infrastructure and cross-system connectivity.
- data management
- create session
- manage querygrid data fabric infrastructure.
- list query systems
- sql queries.
- executes queries and analyzes data across vantage systems.
- analytics
- Platform Administrator
- administers querygrid systems, nodes, and software.
- Application Developer
- query sessions.
- data warehousing
- system and fabric configuration management.
- execute query
- available systems.
- list available vantage systems for query execution.
- teradata
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
