---
categories: []
consumed_apis: []
description: Workflow capability for real-time data analytics using Tinybird. Combines data ingestion, SQL transformation pipelines, and instant API publishing to support analytics engineers, data platform teams, and application developers building high-concurrency analytics APIs.
layout: capability
name: Tinybird Real-Time Analytics
operations:
- description: List all data sources available for analytics
  method: GET
  name: list-data-sources
  path: /v1/data-sources
- description: Create a new data source for analytics ingestion
  method: POST
  name: create-data-source
  path: /v1/data-sources
- description: Get statistics and schema for a data source
  method: GET
  name: get-data-source
  path: /v1/data-sources/{name}
- description: Drop a data source
  method: DELETE
  name: delete-data-source
  path: /v1/data-sources/{name}
- description: Ingest NDJSON events for real-time analytics
  method: POST
  name: ingest-events
  path: /v1/events
- description: List all data transformation pipes
  method: GET
  name: list-pipes
  path: /v1/pipes
- description: Create a new SQL transformation pipe
  method: POST
  name: create-pipe
  path: /v1/pipes
- description: Get pipe details and transformation nodes
  method: GET
  name: get-pipe
  path: /v1/pipes/{name}
- description: Delete a transformation pipe
  method: DELETE
  name: delete-pipe
  path: /v1/pipes/{name}
- description: Execute a SQL query for analytics exploration
  method: GET
  name: execute-sql-query
  path: /v1/query
- description: List all API tokens
  method: GET
  name: list-tokens
  path: /v1/tokens
- description: Create a new scoped API token
  method: POST
  name: create-token
  path: /v1/tokens
- description: Monitor background jobs and import status
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Tinybird
provider_slug: tinybird
search_terms:
- inspect the sql nodes and configuration of a tinybird transformation pipe
- analytics
- delete data source
- list pipes
- create token
- streaming
- create a new tinybird api token with specific scope permissions
- create data source
- stream events into analytics data sources
- individual pipe management
- execute sql query
- drop a tinybird data source and all its stored data permanently
- list tokens
- drop a data source
- authentication token management
- ingest ndjson events for real-time analytics
- sql transformation pipelines
- data platform
- list all data transformation pipes
- get pipe details and transformation nodes
- delete pipe
- manage analytics data sources
- sql
- list all tinybird authentication tokens with their scopes
- monitor background jobs and import status
- get data source
- delete a transformation pipe
- list all api tokens
- ad-hoc sql analytics queries
- background job monitoring
- monitor tinybird background jobs including imports and schema changes
- ingest events
- create a new sql transformation pipe
- execute a sql query for analytics exploration
- get schema and row statistics for a specific tinybird data source
- get pipe
- list jobs
- stream ndjson events into a tinybird data source for real-time ingestion
- individual data source management
- create a new scoped api token
- run an ad-hoc sql query against tinybird data sources for analytics exploration
- list all data sources available for analytics
- data
- create pipe
- list data sources
- real-time
- list all sql transformation pipes and published api endpoints in tinybird
- create a new data source for analytics ingestion
- list all tinybird data sources in the workspace for analytics exploration
- get statistics and schema for a data source
slug: real-time-analytics
source_filename: real-time-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tinybird Real-Time Analytics\n  description: Workflow capability for real-time data analytics using Tinybird. Combines data ingestion, SQL transformation\n    pipelines, and instant API publishing to support analytics engineers, data platform teams, and application developers\n    building high-concurrency analytics APIs.\n  tags:\n  - Analytics\n  - Real-Time\n  - Data Platform\n  - Streaming\n  - SQL\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TINYBIRD_TOKEN: TINYBIRD_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tinybird\n    baseUri: https://api.tinybird.co\n    description: Tinybird real-time data platform REST API\n    authentication:\n      type: bearer\n      token: '{{TINYBIRD_TOKEN}}'\n    resources:\n    - name: data-sources\n      path: /v0/datasources\n      description: Manage Tinybird data sources\n      operations:\n      - name: list-data-sources\n      \
  \  method: GET\n        description: List all accessible data sources in the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-data-source\n        method: POST\n        description: Create, append, or replace a data source\n        inputParameters:\n        - name: mode\n          in: query\n          type: string\n          required: false\n          description: 'Operation mode: create, append, or replace'\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Name of the data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-source\n      path: /v0/datasources/{name}\n      description: Manage a specific data source\n      operations:\n      - name: get-data-source\n        method: GET\n        description: Retrieve\
  \ information and statistics for a specific data source\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-data-source\n        method: DELETE\n        description: Drop an entire data source and all its data\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Name of the data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: truncate-data-source\n        method: POST\n        description: Remove all data from a data source\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n\
  \          description: Name of the data source to truncate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /v0/events\n      description: Ingest NDJSON events into data sources\n      operations:\n      - name: ingest-events\n        method: POST\n        description: Ingest NDJSON events via HTTP POST\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Target data source name\n        - name: wait\n          in: query\n          type: boolean\n          required: false\n          description: Wait for ingestion to complete\n        body:\n          type: text\n          data: '{{tools.events_payload}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipes\n      path: /v0/pipes\n      description:\
  \ Manage Tinybird transformation pipes\n      operations:\n      - name: list-pipes\n        method: GET\n        description: List all pipes in the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pipe\n        method: POST\n        description: Create a new SQL transformation pipe\n        body:\n          type: json\n          data:\n            name: '{{tools.pipe_name}}'\n            description: '{{tools.pipe_description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipe\n      path: /v0/pipes/{name}\n      description: Manage a specific pipe\n      operations:\n      - name: get-pipe\n        method: GET\n        description: Retrieve details about a specific pipe\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required:\
  \ true\n          description: Pipe name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-pipe\n        method: DELETE\n        description: Delete a pipe and all its nodes\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Pipe name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /v0/sql\n      description: Execute SQL queries against Tinybird data\n      operations:\n      - name: execute-sql-query\n        method: GET\n        description: Execute a SQL query against Tinybird data\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SQL query string\n        - name: format\n          in: query\n     \
  \     type: string\n          required: false\n          description: 'Output format: JSON, CSV, NDJSON, Parquet'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /v0/tokens\n      description: Manage Tinybird authentication tokens\n      operations:\n      - name: list-tokens\n        method: GET\n        description: Retrieve all workspace static tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-token\n        method: POST\n        description: Create a new token with specified scopes\n        body:\n          type: json\n          data:\n            name: '{{tools.token_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /v0/jobs\n      description: Track Tinybird\
  \ background jobs\n      operations:\n      - name: list-jobs\n        method: GET\n        description: Retrieve job history from the past 48 hours or last 100 jobs\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: done, error, working, waiting'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tinybird-analytics-api\n    description: Unified REST API for Tinybird real-time analytics workflows.\n    resources:\n    - path: /v1/data-sources\n      name: data-sources\n      description: Manage analytics data sources\n      operations:\n      - method: GET\n        name: list-data-sources\n        description: List all data sources available for analytics\n        call: tinybird.list-data-sources\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: POST\n        name: create-data-source\n        description: Create a new data source for analytics ingestion\n        call: tinybird.create-data-source\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-sources/{name}\n      name: data-source\n      description: Individual data source management\n      operations:\n      - method: GET\n        name: get-data-source\n        description: Get statistics and schema for a data source\n        call: tinybird.get-data-source\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-data-source\n        description: Drop a data source\n        call: tinybird.delete-data-source\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description:\
  \ Stream events into analytics data sources\n      operations:\n      - method: POST\n        name: ingest-events\n        description: Ingest NDJSON events for real-time analytics\n        call: tinybird.ingest-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes\n      name: pipes\n      description: SQL transformation pipelines\n      operations:\n      - method: GET\n        name: list-pipes\n        description: List all data transformation pipes\n        call: tinybird.list-pipes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-pipe\n        description: Create a new SQL transformation pipe\n        call: tinybird.create-pipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipes/{name}\n      name: pipe\n      description: Individual pipe management\n      operations:\n      - method: GET\n        name: get-pipe\n     \
  \   description: Get pipe details and transformation nodes\n        call: tinybird.get-pipe\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-pipe\n        description: Delete a transformation pipe\n        call: tinybird.delete-pipe\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: Ad-hoc SQL analytics queries\n      operations:\n      - method: GET\n        name: execute-sql-query\n        description: Execute a SQL query for analytics exploration\n        call: tinybird.execute-sql-query\n        with:\n          q: rest.q\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tokens\n      name: tokens\n      description: Authentication token management\n      operations:\n      -\
  \ method: GET\n        name: list-tokens\n        description: List all API tokens\n        call: tinybird.list-tokens\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-token\n        description: Create a new scoped API token\n        call: tinybird.create-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Background job monitoring\n      operations:\n      - method: GET\n        name: list-jobs\n        description: Monitor background jobs and import status\n        call: tinybird.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tinybird-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted real-time analytics with Tinybird.\n    tools:\n    - name: list-data-sources\n      description: List all Tinybird data sources in the\
  \ workspace for analytics exploration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tinybird.list-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-source\n      description: Get schema and row statistics for a specific Tinybird data source\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tinybird.get-data-source\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ingest-events\n      description: Stream NDJSON events into a Tinybird data source for real-time ingestion\n      hints:\n        readOnly: false\n        destructive: false\n      call: tinybird.ingest-events\n      with:\n        name: tools.name\n        events_payload: tools.events_payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipes\n      description: List all SQL transformation pipes and published\
  \ API endpoints in Tinybird\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tinybird.list-pipes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipe\n      description: Inspect the SQL nodes and configuration of a Tinybird transformation pipe\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tinybird.get-pipe\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-sql-query\n      description: Run an ad-hoc SQL query against Tinybird data sources for analytics exploration\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tinybird.execute-sql-query\n      with:\n        q: tools.q\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tokens\n      description: List all Tinybird authentication tokens with their scopes\n      hints:\n      \
  \  readOnly: true\n        openWorld: true\n      call: tinybird.list-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-token\n      description: Create a new Tinybird API token with specific scope permissions\n      hints:\n        readOnly: false\n        destructive: false\n      call: tinybird.create-token\n      with:\n        token_name: tools.token_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: Monitor Tinybird background jobs including imports and schema changes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tinybird.list-jobs\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-data-source\n      description: Drop a Tinybird data source and all its stored data permanently\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n\
  \      call: tinybird.delete-data-source\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tinybird/refs/heads/main/capabilities/real-time-analytics.yaml
tags:
- Analytics
- Real-Time
- Data Platform
- Streaming
- SQL
tools:
- description: List all Tinybird data sources in the workspace for analytics exploration
  hints:
    openWorld: true
    readOnly: true
  name: list-data-sources
- description: Get schema and row statistics for a specific Tinybird data source
  hints:
    openWorld: false
    readOnly: true
  name: get-data-source
- description: Stream NDJSON events into a Tinybird data source for real-time ingestion
  hints:
    destructive: false
    readOnly: false
  name: ingest-events
- description: List all SQL transformation pipes and published API endpoints in Tinybird
  hints:
    openWorld: true
    readOnly: true
  name: list-pipes
- description: Inspect the SQL nodes and configuration of a Tinybird transformation pipe
  hints:
    openWorld: false
    readOnly: true
  name: get-pipe
- description: Run an ad-hoc SQL query against Tinybird data sources for analytics exploration
  hints:
    openWorld: true
    readOnly: true
  name: execute-sql-query
- description: List all Tinybird authentication tokens with their scopes
  hints:
    openWorld: true
    readOnly: true
  name: list-tokens
- description: Create a new Tinybird API token with specific scope permissions
  hints:
    destructive: false
    readOnly: false
  name: create-token
- description: Monitor Tinybird background jobs including imports and schema changes
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Drop a Tinybird data source and all its stored data permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-data-source
---
