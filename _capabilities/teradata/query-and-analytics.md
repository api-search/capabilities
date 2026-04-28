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
- data warehousing
- list available vantage systems for query execution.
- list cross-system query summaries from querygrid.
- Platform Administrator
- Data Analyst
- execute a sql query against teradata vantage.
- create a new query session on a vantage system.
- data management
- get the status and results of a submitted query.
- execute sql queries and analytics.
- database
- list querygrid queries
- analytics
- executes queries and analyzes data across vantage systems.
- available systems.
- execute a sql query.
- health monitoring and issue detection.
- list query systems
- enterprise
- list available vantage systems.
- administers querygrid systems, nodes, and software.
- integrates applications with teradata via rest apis.
- query
- Data Engineer
- Application Developer
- manage querygrid data fabric infrastructure.
- machine learning
- create a query session.
- execute query
- sql queries.
- teradata
- query sessions.
- sql
- get query status
- manages data fabric infrastructure and cross-system connectivity.
- sql query execution and session management.
- system and fabric configuration management.
- cloud
- create session
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
