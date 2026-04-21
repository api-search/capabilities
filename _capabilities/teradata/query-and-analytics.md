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
- get query status
- cloud
- database
- get the status and results of a submitted query.
- manages data fabric infrastructure and cross-system connectivity.
- administers querygrid systems, nodes, and software.
- machine learning
- system and fabric configuration management.
- create session
- manage querygrid data fabric infrastructure.
- available systems.
- list query systems
- teradata
- enterprise
- Application Developer
- data management
- list querygrid queries
- create a query session.
- execute a sql query.
- execute a sql query against teradata vantage.
- execute sql queries and analytics.
- Platform Administrator
- create a new query session on a vantage system.
- execute query
- list available vantage systems for query execution.
- list cross-system query summaries from querygrid.
- Data Analyst
- executes queries and analyzes data across vantage systems.
- integrates applications with teradata via rest apis.
- Data Engineer
- list available vantage systems.
- sql query execution and session management.
- health monitoring and issue detection.
- sql queries.
- data warehousing
- analytics
- query sessions.
- query
- sql
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
