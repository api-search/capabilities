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
- available systems.
- executes queries and analyzes data across vantage systems.
- analytics
- sql queries.
- Data Engineer
- administers querygrid systems, nodes, and software.
- data management
- execute a sql query.
- health monitoring and issue detection.
- query sessions.
- manage querygrid data fabric infrastructure.
- manages data fabric infrastructure and cross-system connectivity.
- get query status
- list query systems
- execute a sql query against teradata vantage.
- enterprise
- database
- query
- list available vantage systems.
- machine learning
- execute sql queries and analytics.
- create session
- sql
- list available vantage systems for query execution.
- list cross-system query summaries from querygrid.
- integrates applications with teradata via rest apis.
- sql query execution and session management.
- Platform Administrator
- Application Developer
- list querygrid queries
- Data Analyst
- create a query session.
- system and fabric configuration management.
- data warehousing
- execute query
- teradata
- create a new query session on a vantage system.
- cloud
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
