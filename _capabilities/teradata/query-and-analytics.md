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
- available systems.
- analytics
- sql
- query sessions.
- execute a sql query against teradata vantage.
- manage querygrid data fabric infrastructure.
- create session
- list available vantage systems.
- create a new query session on a vantage system.
- cloud
- Application Developer
- list cross-system query summaries from querygrid.
- teradata
- list available vantage systems for query execution.
- executes queries and analyzes data across vantage systems.
- database
- Platform Administrator
- get query status
- create a query session.
- execute query
- execute sql queries and analytics.
- Data Analyst
- manages data fabric infrastructure and cross-system connectivity.
- machine learning
- list query systems
- enterprise
- get the status and results of a submitted query.
- sql query execution and session management.
- query
- Data Engineer
- health monitoring and issue detection.
- administers querygrid systems, nodes, and software.
- sql queries.
- integrates applications with teradata via rest apis.
- data warehousing
- data management
- system and fabric configuration management.
- list querygrid queries
- execute a sql query.
slug: query-and-analytics
source_filename: query-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Teradata Query and Analytics\n  description: >-\n    Workflow capability for executing SQL queries and analytics against Teradata\n    Vantage systems. Combines Query Service for SQL execution with QueryGrid for\n    cross-system query monitoring. Used by data analysts and application\n    developers.\n  tags:\n    - Teradata\n    - Query\n    - Analytics\n    - SQL\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      VANTAGE_USERNAME: VANTAGE_USERNAME\n      VANTAGE_PASSWORD: VANTAGE_PASSWORD\n      QUERYGRID_USERNAME: QUERYGRID_USERNAME\n      QUERYGRID_PASSWORD: QUERYGRID_PASSWORD\n\ncapability:\n  consumes:\n    - import: query-service\n      location: ./shared/query-service.yaml\n    - import: querygrid-manager\n      location: ./shared/querygrid-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: query-analytics-api\n      description: \"Unified\
  \ REST API for Teradata query and analytics.\"\n      resources:\n        - path: /v1/systems\n          name: systems\n          description: \"Available systems.\"\n          operations:\n            - method: GET\n              name: list-query-systems\n              description: \"List available Vantage systems.\"\n              call: \"query-service.list-systems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sessions\n          name: sessions\n          description: \"Query sessions.\"\n          operations:\n            - method: POST\n              name: create-session\n              description: \"Create a query session.\"\n              call: \"query-service.create-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: \"SQL queries.\"\n          operations:\n           \
  \ - method: POST\n              name: execute-query\n              description: \"Execute a SQL query.\"\n              call: \"query-service.execute-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: query-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SQL query execution.\"\n      tools:\n        - name: list-query-systems\n          description: \"List available Vantage systems for query execution.\"\n          hints:\n            readOnly: true\n          call: \"query-service.list-systems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-session\n          description: \"Create a new query session on a Vantage system.\"\n          hints:\n            readOnly: false\n          call: \"query-service.create-session\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: execute-query\n          description: \"Execute a SQL query against Teradata Vantage.\"\n          hints:\n            readOnly: false\n          call: \"query-service.execute-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-query-status\n          description: \"Get the status and results of a submitted query.\"\n          hints:\n            readOnly: true\n          call: \"query-service.get-query-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-querygrid-queries\n          description: \"List cross-system query summaries from QueryGrid.\"\n          hints:\n            readOnly: true\n          call: \"querygrid-manager.list-issues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/teradata/refs/heads/main/capabilities/query-and-analytics.yaml
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
