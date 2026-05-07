---
categories:
- analytics
consumed_apis: []
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
- analytics
- execute sql queries and analytics.
- create session
- sql queries.
- manages data fabric infrastructure and cross-system connectivity.
- Data Analyst
- list available vantage systems.
- query sessions.
- query
- Application Developer
- data management
- execute a sql query.
- list available vantage systems for query execution.
- health monitoring and issue detection.
- machine learning
- sql
- execute a sql query against teradata vantage.
- manage querygrid data fabric infrastructure.
- administers querygrid systems, nodes, and software.
- list cross-system query summaries from querygrid.
- executes queries and analyzes data across vantage systems.
- enterprise
- list querygrid queries
- sql query execution and session management.
- execute query
- database
- cloud
- get query status
- available systems.
- Platform Administrator
- Data Engineer
- data warehousing
- create a query session.
- get the status and results of a submitted query.
- teradata
- system and fabric configuration management.
- list query systems
- integrates applications with teradata via rest apis.
- create a new query session on a vantage system.
slug: query-and-analytics
source_filename: query-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Teradata Query and Analytics\n  description: Workflow capability for executing SQL queries and analytics against Teradata Vantage systems. Combines Query\n    Service for SQL execution with QueryGrid for cross-system query monitoring. Used by data analysts and application developers.\n  tags:\n  - Teradata\n  - Query\n  - Analytics\n  - SQL\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VANTAGE_USERNAME: VANTAGE_USERNAME\n    VANTAGE_PASSWORD: VANTAGE_PASSWORD\n    QUERYGRID_USERNAME: QUERYGRID_USERNAME\n    QUERYGRID_PASSWORD: QUERYGRID_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: query-service\n    baseUri: https://vantage.teradata.com/api/query/v1\n    description: Teradata Query Service REST API.\n    authentication:\n      type: basic\n      username: '{{VANTAGE_USERNAME}}'\n      password: '{{VANTAGE_PASSWORD}}'\n    resources:\n    - name: systems\n      path: /systems\n\
  \      description: Available Vantage systems.\n      operations:\n      - name: list-systems\n        method: GET\n        description: List available Vantage systems.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /sessions\n      description: Query sessions.\n      operations:\n      - name: create-session\n        method: POST\n        description: Create a new query session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-session\n        method: GET\n        description: Get session details.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n      - name: delete-session\n        method: DELETE\n        description: Close a query session.\n        inputParameters:\n        - name: sessionId\n          in: path\n          type: string\n          required: true\n          description: Session identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queries\n      path: /queries\n      description: SQL query execution.\n      operations:\n      - name: execute-query\n        method: POST\n        description: Execute a SQL query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-query-status\n        method: GET\n        description: Get query status and results.\n        inputParameters:\n        - name: queryId\n          in: path\n          type: string\n          required: true\n          description: Query identifier.\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: querygrid-manager\n    baseUri: https://querygrid.teradata.com/api/v1\n    description: QueryGrid Manager REST API for data fabric administration.\n    authentication:\n      type: basic\n      username: '{{QUERYGRID_USERNAME}}'\n      password: '{{QUERYGRID_PASSWORD}}'\n    resources:\n    - name: monitoring\n      path: /\n      description: Monitoring and status endpoints.\n      operations:\n      - name: get-api-info\n        method: GET\n        description: Retrieve API version and status information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-issues\n        method: GET\n        description: Retrieve all current issues.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n        \
  \  required: true\n          description: Issues endpoint path.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /config\n      description: Configuration management endpoints.\n      operations:\n      - name: list-data-centers\n        method: GET\n        description: Retrieve all configured data centers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-data-center\n        method: POST\n        description: Create a new data center configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-systems\n        method: GET\n        description: Retrieve all configured systems.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-system\n        method: POST\n        description: Register a new system.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-bridges\n        method: GET\n        description: Retrieve all configured bridges.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-connectors\n        method: GET\n        description: Retrieve all configured connectors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-links\n        method: GET\n        description: Retrieve all configured links.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-fabrics\n        method: GET\n \
  \       description: Retrieve all configured fabrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-networks\n        method: GET\n        description: Retrieve all configured networks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations\n      path: /operations\n      description: Operational management endpoints.\n      operations:\n      - name: run-diagnostic-check\n        method: POST\n        description: Execute a diagnostic check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: auto-install-nodes\n        method: POST\n        description: Trigger automated node installation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: query-analytics-api\n    description: Unified REST API for Teradata query and analytics.\n    resources:\n    - path: /v1/systems\n      name: systems\n      description: Available systems.\n      operations:\n      - method: GET\n        name: list-query-systems\n        description: List available Vantage systems.\n        call: query-service.list-systems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sessions\n      name: sessions\n      description: Query sessions.\n      operations:\n      - method: POST\n        name: create-session\n        description: Create a query session.\n        call: query-service.create-session\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries\n      name: queries\n      description: SQL queries.\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute\
  \ a SQL query.\n        call: query-service.execute-query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: query-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted SQL query execution.\n    tools:\n    - name: list-query-systems\n      description: List available Vantage systems for query execution.\n      hints:\n        readOnly: true\n      call: query-service.list-systems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-session\n      description: Create a new query session on a Vantage system.\n      hints:\n        readOnly: false\n      call: query-service.create-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-query\n      description: Execute a SQL query against Teradata Vantage.\n      hints:\n        readOnly: false\n      call: query-service.execute-query\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-query-status\n      description: Get the status and results of a submitted query.\n      hints:\n        readOnly: true\n      call: query-service.get-query-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-querygrid-queries\n      description: List cross-system query summaries from QueryGrid.\n      hints:\n        readOnly: true\n      call: querygrid-manager.list-issues\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
