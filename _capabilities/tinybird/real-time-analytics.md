---
api_specs:
- filename: tinybird-openapi.yml
  format: yaml
  label: tinybird
  slug: tinybird
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tinybird/refs/heads/main/openapi/tinybird-openapi.yml
categories: []
consumed_apis:
- tinybird
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
- background job monitoring
- delete data source
- monitor background jobs and import status
- manage analytics data sources
- drop a data source
- list pipes
- execute sql query
- create token
- list jobs
- sql transformation pipelines
- create a new sql transformation pipe
- get schema and row statistics for a specific tinybird data source
- get data source
- analytics
- data
- list all data transformation pipes
- list data sources
- create pipe
- list all tinybird authentication tokens with their scopes
- ingest events
- ad-hoc sql analytics queries
- delete pipe
- streaming
- create a new scoped api token
- data platform
- individual pipe management
- create data source
- get pipe details and transformation nodes
- delete a transformation pipe
- list all tinybird data sources in the workspace for analytics exploration
- stream ndjson events into a tinybird data source for real-time ingestion
- run an ad-hoc sql query against tinybird data sources for analytics exploration
- list tokens
- list all api tokens
- inspect the sql nodes and configuration of a tinybird transformation pipe
- get pipe
- authentication token management
- real-time
- individual data source management
- get statistics and schema for a data source
- list all data sources available for analytics
- monitor tinybird background jobs including imports and schema changes
- execute a sql query for analytics exploration
- sql
- create a new tinybird api token with specific scope permissions
- stream events into analytics data sources
- drop a tinybird data source and all its stored data permanently
- list all sql transformation pipes and published api endpoints in tinybird
- ingest ndjson events for real-time analytics
- create a new data source for analytics ingestion
slug: real-time-analytics
source_filename: real-time-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tinybird Real-Time Analytics\"\n  description: >-\n    Workflow capability for real-time data analytics using Tinybird. Combines data\n    ingestion, SQL transformation pipelines, and instant API publishing to support\n    analytics engineers, data platform teams, and application developers building\n    high-concurrency analytics APIs.\n  tags:\n    - Analytics\n    - Real-Time\n    - Data Platform\n    - Streaming\n    - SQL\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TINYBIRD_TOKEN: TINYBIRD_TOKEN\n\ncapability:\n  consumes:\n    - import: tinybird\n      location: ./shared/tinybird.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tinybird-analytics-api\n      description: \"Unified REST API for Tinybird real-time analytics workflows.\"\n      resources:\n        - path: /v1/data-sources\n          name: data-sources\n          description: \"\
  Manage analytics data sources\"\n          operations:\n            - method: GET\n              name: list-data-sources\n              description: \"List all data sources available for analytics\"\n              call: \"tinybird.list-data-sources\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-data-source\n              description: \"Create a new data source for analytics ingestion\"\n              call: \"tinybird.create-data-source\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-sources/{name}\n          name: data-source\n          description: \"Individual data source management\"\n          operations:\n            - method: GET\n              name: get-data-source\n              description: \"Get statistics and schema for a data source\"\n              call: \"tinybird.get-data-source\"\n\
  \              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-data-source\n              description: \"Drop a data source\"\n              call: \"tinybird.delete-data-source\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Stream events into analytics data sources\"\n          operations:\n            - method: POST\n              name: ingest-events\n              description: \"Ingest NDJSON events for real-time analytics\"\n              call: \"tinybird.ingest-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipes\n          name: pipes\n          description: \"\
  SQL transformation pipelines\"\n          operations:\n            - method: GET\n              name: list-pipes\n              description: \"List all data transformation pipes\"\n              call: \"tinybird.list-pipes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-pipe\n              description: \"Create a new SQL transformation pipe\"\n              call: \"tinybird.create-pipe\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipes/{name}\n          name: pipe\n          description: \"Individual pipe management\"\n          operations:\n            - method: GET\n              name: get-pipe\n              description: \"Get pipe details and transformation nodes\"\n              call: \"tinybird.get-pipe\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-pipe\n              description: \"Delete a transformation pipe\"\n              call: \"tinybird.delete-pipe\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query\n          name: query\n          description: \"Ad-hoc SQL analytics queries\"\n          operations:\n            - method: GET\n              name: execute-sql-query\n              description: \"Execute a SQL query for analytics exploration\"\n              call: \"tinybird.execute-sql-query\"\n              with:\n                q: \"rest.q\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tokens\n          name: tokens\n          description: \"Authentication\
  \ token management\"\n          operations:\n            - method: GET\n              name: list-tokens\n              description: \"List all API tokens\"\n              call: \"tinybird.list-tokens\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-token\n              description: \"Create a new scoped API token\"\n              call: \"tinybird.create-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Background job monitoring\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"Monitor background jobs and import status\"\n              call: \"tinybird.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n     \
  \ port: 9090\n      namespace: tinybird-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted real-time analytics with Tinybird.\"\n      tools:\n        - name: list-data-sources\n          description: \"List all Tinybird data sources in the workspace for analytics exploration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tinybird.list-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-data-source\n          description: \"Get schema and row statistics for a specific Tinybird data source\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tinybird.get-data-source\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-events\n          description: \"Stream NDJSON events into a Tinybird\
  \ data source for real-time ingestion\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"tinybird.ingest-events\"\n          with:\n            name: \"tools.name\"\n            events_payload: \"tools.events_payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipes\n          description: \"List all SQL transformation pipes and published API endpoints in Tinybird\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tinybird.list-pipes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pipe\n          description: \"Inspect the SQL nodes and configuration of a Tinybird transformation pipe\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tinybird.get-pipe\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: execute-sql-query\n          description: \"Run an ad-hoc SQL query against Tinybird data sources for analytics exploration\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tinybird.execute-sql-query\"\n          with:\n            q: \"tools.q\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tokens\n          description: \"List all Tinybird authentication tokens with their scopes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tinybird.list-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-token\n          description: \"Create a new Tinybird API token with specific scope permissions\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"tinybird.create-token\"\n          with:\n            token_name: \"tools.token_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"Monitor Tinybird background jobs including imports and schema changes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tinybird.list-jobs\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-data-source\n          description: \"Drop a Tinybird data source and all its stored data permanently\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tinybird.delete-data-source\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
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
