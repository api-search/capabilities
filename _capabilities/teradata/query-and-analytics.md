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
- Data Analyst
- create session
- database
- machine learning
- sql queries.
- manages data fabric infrastructure and cross-system connectivity.
- get query status
- data management
- enterprise
- executes queries and analyzes data across vantage systems.
- health monitoring and issue detection.
- teradata
- execute a sql query against teradata vantage.
- data warehousing
- integrates applications with teradata via rest apis.
- cloud
- execute sql queries and analytics.
- list available vantage systems.
- Data Engineer
- available systems.
- execute a sql query.
- list cross-system query summaries from querygrid.
- list query systems
- create a new query session on a vantage system.
- query
- create a query session.
- analytics
- query sessions.
- sql query execution and session management.
- sql
- list available vantage systems for query execution.
- administers querygrid systems, nodes, and software.
- system and fabric configuration management.
- Application Developer
- get the status and results of a submitted query.
- Platform Administrator
- manage querygrid data fabric infrastructure.
- execute query
- list querygrid queries
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
