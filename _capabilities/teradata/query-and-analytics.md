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
- machine learning
- sql
- analytics
- manages data fabric infrastructure and cross-system connectivity.
- database
- execute a sql query.
- create a new query session on a vantage system.
- sql query execution and session management.
- health monitoring and issue detection.
- query
- list query systems
- cloud
- list querygrid queries
- Data Engineer
- manage querygrid data fabric infrastructure.
- Platform Administrator
- execute query
- data management
- list available vantage systems.
- get the status and results of a submitted query.
- administers querygrid systems, nodes, and software.
- system and fabric configuration management.
- query sessions.
- teradata
- create session
- get query status
- data warehousing
- sql queries.
- enterprise
- execute a sql query against teradata vantage.
- available systems.
- executes queries and analyzes data across vantage systems.
- list available vantage systems for query execution.
- integrates applications with teradata via rest apis.
- Data Analyst
- execute sql queries and analytics.
- create a query session.
- Application Developer
- list cross-system query summaries from querygrid.
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
