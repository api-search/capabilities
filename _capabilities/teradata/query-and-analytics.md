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
- data management
- sql query execution and session management.
- sql
- system and fabric configuration management.
- manage querygrid data fabric infrastructure.
- sql queries.
- list query systems
- list available vantage systems.
- cloud
- execute query
- query sessions.
- list available vantage systems for query execution.
- analytics
- create a new query session on a vantage system.
- administers querygrid systems, nodes, and software.
- get the status and results of a submitted query.
- execute sql queries and analytics.
- executes queries and analyzes data across vantage systems.
- list cross-system query summaries from querygrid.
- teradata
- create a query session.
- list querygrid queries
- Platform Administrator
- create session
- machine learning
- Application Developer
- Data Engineer
- execute a sql query against teradata vantage.
- manages data fabric infrastructure and cross-system connectivity.
- health monitoring and issue detection.
- database
- available systems.
- get query status
- execute a sql query.
- data warehousing
- Data Analyst
- query
- enterprise
- integrates applications with teradata via rest apis.
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
