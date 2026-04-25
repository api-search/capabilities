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
- create a new query session on a vantage system.
- Platform Administrator
- analytics
- manage querygrid data fabric infrastructure.
- database
- get query status
- create session
- enterprise
- query
- execute query
- executes queries and analyzes data across vantage systems.
- health monitoring and issue detection.
- machine learning
- list query systems
- cloud
- manages data fabric infrastructure and cross-system connectivity.
- teradata
- create a query session.
- sql query execution and session management.
- sql queries.
- execute sql queries and analytics.
- data management
- execute a sql query against teradata vantage.
- list available vantage systems.
- get the status and results of a submitted query.
- Data Analyst
- administers querygrid systems, nodes, and software.
- available systems.
- data warehousing
- query sessions.
- system and fabric configuration management.
- sql
- list available vantage systems for query execution.
- list querygrid queries
- Data Engineer
- integrates applications with teradata via rest apis.
- Application Developer
- list cross-system query summaries from querygrid.
- execute a sql query.
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
