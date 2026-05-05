---
api_specs:
- filename: sqlapi.yaml
  format: yaml
  label: snowflake-sql
  slug: snowflake-sql
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/sqlapi.yaml
- filename: task.yaml
  format: yaml
  label: snowflake-task
  slug: snowflake-task
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/task.yaml
- filename: stream.yaml
  format: yaml
  label: snowflake-stream
  slug: snowflake-stream
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/stream.yaml
- filename: pipe.yaml
  format: yaml
  label: snowflake-pipe
  slug: snowflake-pipe
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/pipe.yaml
- filename: stage.yaml
  format: yaml
  label: snowflake-stage
  slug: snowflake-stage
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/stage.yaml
- filename: function.yaml
  format: yaml
  label: snowflake-function
  slug: snowflake-function
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/function.yaml
- filename: procedure.yaml
  format: yaml
  label: snowflake-procedure
  slug: snowflake-procedure
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/procedure.yaml
- filename: user-defined-function.yaml
  format: yaml
  label: snowflake-udf
  slug: snowflake-udf
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/user-defined-function.yaml
- filename: result.yaml
  format: yaml
  label: snowflake-result
  slug: snowflake-result
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/result.yaml
categories:
- data-engineering
consumed_apis:
- snowflake-sql
- snowflake-task
- snowflake-stream
- snowflake-pipe
- snowflake-stage
- snowflake-function
- snowflake-procedure
- snowflake-udf
- snowflake-result
description: Unified workflow for building and managing data pipelines using SQL execution, tasks, streams, pipes, stages, and functions. Used by Data Engineers to orchestrate ETL/ELT workflows and continuous data ingestion.
layout: capability
name: Snowflake Data Engineering
operations:
- description: Submit a SQL statement
  method: POST
  name: submit-statement
  path: /v1/statements
- description: List tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Create a task
  method: POST
  name: create-task
  path: /v1/tasks
- description: List streams
  method: GET
  name: list-streams
  path: /v1/streams
- description: Create a stream
  method: POST
  name: create-stream
  path: /v1/streams
- description: List pipes
  method: GET
  name: list-pipes
  path: /v1/pipes
- description: Create a pipe
  method: POST
  name: create-pipe
  path: /v1/pipes
- description: List stages
  method: GET
  name: list-stages
  path: /v1/stages
- description: Create a stage
  method: POST
  name: create-stage
  path: /v1/stages
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- create a pipe
- data warehousing
- data pipelines
- resume a suspended task
- create function
- list pipes
- sql statement execution
- create stream
- create a stage
- create task
- execute function
- list functions
- call a stored procedure
- list user defined functions
- data engineering
- create a stream
- get query result
- task management
- create pipe
- refresh a pipe
- list scheduled tasks
- list data ingestion pipes
- list files in a stage
- list stage files
- create a scheduled task
- list stages
- submit sql
- refresh pipe
- list change data capture streams
- cancel statement
- etl
- execute a function
- snowflake
- database
- list streams
- execute a task immediately
- list stored procedures
- suspend task
- stream management
- submit a sql statement for execution
- resume task
- submit a sql statement
- list udfs
- get a query result
- data lakes
- list data loading stages
- suspend a running task
- create procedure
- get status of a submitted statement
- create stage
- stage management
- cancel a running statement
- pipe management
- list procedures
- create a function
- data sharing
- create a cdc stream
- create a pipe for continuous ingestion
- submit statement
- execute task
- create a stored procedure
- get statement status
- sql
- create a task
- list tasks
- call procedure
slug: data-engineering
source_filename: data-engineering.yaml
source_heading: Capability Spec
source_yaml: "# Snowflake Data Engineering — Composed Capability\n# Composition: aggregates 9 shared Snowflake source capabilities (SQL API, tasks,\n# streams, pipes, stages, functions, procedures, UDFs, results) under a single\n# data-engineering domain facade.\n# Triple exposure: the same domain is surfaced through (1) a REST adapter for\n# conventional clients, (2) an MCP over HTTP server for remote AI agents, (3) an\n# MCP over stdio server for local IDE/agent clients, and (4) an Agent Skills\n# server for skill-aware agents. One capability, four consumer channels.\n# Aligned with Naftiko Framework v1.0.0-alpha1 spec patterns from the\n# Use Cases guide (#1 AI integration, #2 Rightsize AI context,\n# #8 Capability-first context engineering).\nnaftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Data Engineering\"\n  description: \"Unified workflow for building and managing data pipelines using SQL execution, tasks, streams, pipes, stages, and functions. Used by Data Engineers to\
  \ orchestrate ETL/ELT workflows and continuous data ingestion.\"\n  tags:\n    - Snowflake\n    - Data Engineering\n    - ETL\n    - Data Pipelines\n  created: \"2026-04-18\"\n  modified: \"2026-04-23\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-sql\n      location: ./shared/sqlapi.yaml\n    - import: snowflake-task\n      location: ./shared/task.yaml\n    - import: snowflake-stream\n      location: ./shared/stream.yaml\n    - import: snowflake-pipe\n      location: ./shared/pipe.yaml\n    - import: snowflake-stage\n      location: ./shared/stage.yaml\n    - import: snowflake-function\n      location: ./shared/function.yaml\n    - import: snowflake-procedure\n      location: ./shared/procedure.yaml\n    - import: snowflake-udf\n      location: ./shared/user-defined-function.yaml\n    - import: snowflake-result\n      location: ./shared/result.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8081\n      namespace: snowflake-data-eng-api\n      description: \"Unified REST API for Snowflake data pipeline management.\"\n      resources:\n        - path: /v1/statements\n          name: statements\n          description: \"SQL statement execution\"\n          operations:\n            - method: POST\n              name: submit-statement\n              description: \"Submit a SQL statement\"\n              call: \"snowflake-sql.submit-statement\"\n              inputParameters:\n                - name: statement\n                  type: string\n                  description: \"SQL statement to execute\"\n                  required: true\n                  mapping: \"$.body.statement\"\n                - name: warehouse\n                  type: string\n                  description: \"Warehouse used to execute the statement\"\n                  required: false\n                  mapping: \"$.body.warehouse\"\n              outputParameters:\n\
  \                - name: statementHandle\n                  type: string\n                  description: \"Handle identifying the submitted statement\"\n                  mapping: \"$.statementHandle\"\n                - name: result\n                  type: object\n                  description: \"Raw statement submission payload\"\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          description: \"Task management\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List tasks\"\n              call: \"snowflake-task.list-tasks\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database containing the tasks\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema containing\
  \ the tasks\"\n                  required: true\n                  mapping: \"$.path.schema\"\n              outputParameters:\n                - name: tasks\n                  type: array\n                  description: \"Collection of tasks in the schema\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-task\n              description: \"Create a task\"\n              call: \"snowflake-task.create-task\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database that will own the task\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema that will own the task\"\n                  required: true\n                  mapping: \"$.path.schema\"\n                - name: name\n                  type: string\n                  description:\
  \ \"Task name\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: definition\n                  type: string\n                  description: \"SQL body of the task\"\n                  required: true\n                  mapping: \"$.body.definition\"\n              outputParameters:\n                - name: task\n                  type: object\n                  description: \"Created task definition\"\n                  mapping: \"$.\"\n        - path: /v1/streams\n          name: streams\n          description: \"Stream management\"\n          operations:\n            - method: GET\n              name: list-streams\n              description: \"List streams\"\n              call: \"snowflake-stream.list-streams\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database containing the streams\"\n                  required: true\n                  mapping:\
  \ \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema containing the streams\"\n                  required: true\n                  mapping: \"$.path.schema\"\n              outputParameters:\n                - name: streams\n                  type: array\n                  description: \"Collection of change data capture streams\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-stream\n              description: \"Create a stream\"\n              call: \"snowflake-stream.create-stream\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database that will own the stream\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema that will own the stream\"\n       \
  \           required: true\n                  mapping: \"$.path.schema\"\n                - name: name\n                  type: string\n                  description: \"Stream name\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: table_name\n                  type: string\n                  description: \"Source table tracked by the stream\"\n                  required: true\n                  mapping: \"$.body.table_name\"\n        - path: /v1/pipes\n          name: pipes\n          description: \"Pipe management\"\n          operations:\n            - method: GET\n              name: list-pipes\n              description: \"List pipes\"\n              call: \"snowflake-pipe.list-pipes\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database containing the pipes\"\n                  required: true\n                  mapping: \"$.path.database\"\n\
  \                - name: schema\n                  type: string\n                  description: \"Schema containing the pipes\"\n                  required: true\n                  mapping: \"$.path.schema\"\n              outputParameters:\n                - name: pipes\n                  type: array\n                  description: \"Collection of ingestion pipes\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-pipe\n              description: \"Create a pipe\"\n              call: \"snowflake-pipe.create-pipe\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database that will own the pipe\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema that will own the pipe\"\n                  required: true\n                  mapping:\
  \ \"$.path.schema\"\n                - name: name\n                  type: string\n                  description: \"Pipe name\"\n                  required: true\n                  mapping: \"$.body.name\"\n                - name: copy_statement\n                  type: string\n                  description: \"COPY statement that defines the pipe\"\n                  required: true\n                  mapping: \"$.body.copy_statement\"\n        - path: /v1/stages\n          name: stages\n          description: \"Stage management\"\n          operations:\n            - method: GET\n              name: list-stages\n              description: \"List stages\"\n              call: \"snowflake-stage.list-stages\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database containing the stages\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n   \
  \               type: string\n                  description: \"Schema containing the stages\"\n                  required: true\n                  mapping: \"$.path.schema\"\n              outputParameters:\n                - name: stages\n                  type: array\n                  description: \"Collection of data loading stages\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-stage\n              description: \"Create a stage\"\n              call: \"snowflake-stage.create-stage\"\n              inputParameters:\n                - name: database\n                  type: string\n                  description: \"Database that will own the stage\"\n                  required: true\n                  mapping: \"$.path.database\"\n                - name: schema\n                  type: string\n                  description: \"Schema that will own the stage\"\n                  required: true\n                  mapping: \"$.path.schema\"\n\
  \                - name: name\n                  type: string\n                  description: \"Stage name\"\n                  required: true\n                  mapping: \"$.body.name\"\n\n    - type: mcp\n      port: 9081\n      namespace: snowflake-data-eng-mcp\n      transport: http\n      description: \"MCP server (HTTP) for AI-assisted Snowflake data pipeline management.\"\n      tools:\n        - name: submit-sql\n          description: \"Submit a SQL statement for execution\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"snowflake-sql.submit-statement\"\n          inputParameters:\n            - name: statement\n              type: string\n              description: \"SQL statement to execute\"\n              required: true\n              mapping: \"$.body.statement\"\n            - name: warehouse\n              type: string\n              description: \"Warehouse used to execute the statement\"\n\
  \              required: false\n              mapping: \"$.body.warehouse\"\n          outputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle identifying the submitted statement\"\n              mapping: \"$.statementHandle\"\n            - name: result\n              type: object\n              description: \"Raw statement submission payload\"\n              mapping: \"$.\"\n        - name: get-statement-status\n          description: \"Get status of a submitted statement\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-sql.get-statement-status\"\n          inputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle of the statement to inspect\"\n              required: true\n              mapping: \"$.path.statementHandle\"\n          outputParameters:\n            - name:\
  \ status\n              type: string\n              description: \"Current execution status\"\n              mapping: \"$.status\"\n            - name: result\n              type: object\n              description: \"Full status payload\"\n              mapping: \"$.\"\n        - name: cancel-statement\n          description: \"Cancel a running statement\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-sql.cancel-statement\"\n          inputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle of the statement to cancel\"\n              required: true\n              mapping: \"$.path.statementHandle\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Cancellation response\"\n              mapping: \"$.\"\n        - name: list-tasks\n          description: \"List scheduled tasks\"\
  \n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-task.list-tasks\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the tasks\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the tasks\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: tasks\n              type: array\n              description: \"Collection of tasks in the schema\"\n              mapping: \"$.\"\n        - name: create-task\n          description: \"Create a scheduled task\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-task.create-task\"\n          inputParameters:\n\
  \            - name: database\n              type: string\n              description: \"Database that will own the task\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the task\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Task name\"\n              required: true\n              mapping: \"$.body.name\"\n            - name: definition\n              type: string\n              description: \"SQL body of the task\"\n              required: true\n              mapping: \"$.body.definition\"\n        - name: execute-task\n          description: \"Execute a task immediately\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"snowflake-task.execute-task\"\n          inputParameters:\n\
  \            - name: database\n              type: string\n              description: \"Database containing the task\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the task\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Task name to execute\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: resume-task\n          description: \"Resume a suspended task\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"snowflake-task.resume-task\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the task\"\n              required: true\n              mapping: \"$.path.database\"\
  \n            - name: schema\n              type: string\n              description: \"Schema containing the task\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Task name to resume\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: suspend-task\n          description: \"Suspend a running task\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snowflake-task.suspend-task\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the task\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the task\"\n              required: true\n              mapping: \"$.path.schema\"\
  \n            - name: name\n              type: string\n              description: \"Task name to suspend\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-streams\n          description: \"List change data capture streams\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-stream.list-streams\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the streams\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the streams\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: streams\n              type: array\n              description: \"Collection of CDC streams\"\n             \
  \ mapping: \"$.\"\n        - name: create-stream\n          description: \"Create a CDC stream\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-stream.create-stream\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database that will own the stream\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the stream\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Stream name\"\n              required: true\n              mapping: \"$.body.name\"\n            - name: table_name\n              type: string\n              description: \"Source table tracked by the stream\"\n              required: true\n\
  \              mapping: \"$.body.table_name\"\n        - name: list-pipes\n          description: \"List data ingestion pipes\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-pipe.list-pipes\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the pipes\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the pipes\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: pipes\n              type: array\n              description: \"Collection of ingestion pipes\"\n              mapping: \"$.\"\n        - name: create-pipe\n          description: \"Create a pipe for continuous ingestion\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-pipe.create-pipe\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database that will own the pipe\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the pipe\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Pipe name\"\n              required: true\n              mapping: \"$.body.name\"\n            - name: copy_statement\n              type: string\n              description: \"COPY statement that defines the pipe\"\n              required: true\n              mapping: \"$.body.copy_statement\"\n        - name: refresh-pipe\n          description: \"Refresh a pipe\"\n          hints:\n\
  \            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"snowflake-pipe.refresh-pipe\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the pipe\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the pipe\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Pipe name to refresh\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-stages\n          description: \"List data loading stages\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-stage.list-stages\"\n          inputParameters:\n      \
  \      - name: database\n              type: string\n              description: \"Database containing the stages\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the stages\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: stages\n              type: array\n              description: \"Collection of data loading stages\"\n              mapping: \"$.\"\n        - name: create-stage\n          description: \"Create a stage\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-stage.create-stage\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database that will own the stage\"\n              required: true\n              mapping: \"\
  $.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the stage\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Stage name\"\n              required: true\n              mapping: \"$.body.name\"\n        - name: list-stage-files\n          description: \"List files in a stage\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-stage.list-files\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the stage\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the stage\"\n              required: true\n              mapping:\
  \ \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Stage name\"\n              required: true\n              mapping: \"$.path.name\"\n          outputParameters:\n            - name: files\n              type: array\n              description: \"Collection of files staged for loading\"\n              mapping: \"$.\"\n        - name: list-functions\n          description: \"List functions\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-function.list-functions\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the functions\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the functions\"\n              required: true\n            \
  \  mapping: \"$.path.schema\"\n          outputParameters:\n            - name: functions\n              type: array\n              description: \"Collection of functions\"\n              mapping: \"$.\"\n        - name: create-function\n          description: \"Create a function\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-function.create-function\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database that will own the function\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the function\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Function name\"\n              required: true\n\
  \              mapping: \"$.body.name\"\n        - name: execute-function\n          description: \"Execute a function\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-function.execute-function\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the function\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the function\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Function name to execute\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-procedures\n          description: \"List stored procedures\"\n          hints:\n           \
  \ readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-procedure.list-procedures\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the procedures\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the procedures\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: procedures\n              type: array\n              description: \"Collection of stored procedures\"\n              mapping: \"$.\"\n        - name: create-procedure\n          description: \"Create a stored procedure\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snowflake-procedure.create-procedure\"\n   \
  \       inputParameters:\n            - name: database\n              type: string\n              description: \"Database that will own the procedure\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema that will own the procedure\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Procedure name\"\n              required: true\n              mapping: \"$.body.name\"\n        - name: call-procedure\n          description: \"Call a stored procedure\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"snowflake-procedure.call-procedure\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the procedure\"\n     \
  \         required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing the procedure\"\n              required: true\n              mapping: \"$.path.schema\"\n            - name: name\n              type: string\n              description: \"Procedure name to call\"\n              required: true\n              mapping: \"$.path.name\"\n        - name: list-udfs\n          description: \"List user defined functions\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-udf.list-udfs\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"Database containing the UDFs\"\n              required: true\n              mapping: \"$.path.database\"\n            - name: schema\n              type: string\n              description: \"Schema containing\
  \ the UDFs\"\n              required: true\n              mapping: \"$.path.schema\"\n          outputParameters:\n            - name: udfs\n              type: array\n              description: \"Collection of user defined functions\"\n              mapping: \"$.\"\n        - name: get-query-result\n          description: \"Get a query result\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-result.get-result\"\n          inputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle of the statement whose result is fetched\"\n              required: true\n              mapping: \"$.path.statementHandle\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Full query result payload\"\n              mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: snowflake-data-eng-mcp-stdio\n\
  \      transport: stdio\n      description: \"MCP server (stdio) for local IDE and agent clients managing Snowflake data pipelines.\"\n      tools:\n        - name: submit-sql\n          description: \"Submit a SQL statement for execution\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"snowflake-sql.submit-statement\"\n          inputParameters:\n            - name: statement\n              type: string\n              description: \"SQL statement to execute\"\n              required: true\n              mapping: \"$.body.statement\"\n            - name: warehouse\n              type: string\n              description: \"Warehouse used to execute the statement\"\n              required: false\n              mapping: \"$.body.warehouse\"\n          outputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle identifying the submitted statement\"\n \
  \             mapping: \"$.statementHandle\"\n            - name: result\n              type: object\n              description: \"Raw statement submission payload\"\n              mapping: \"$.\"\n        - name: get-statement-status\n          description: \"Get status of a submitted statement\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-sql.get-statement-status\"\n          inputParameters:\n            - name: statementHandle\n              type: string\n              description: \"Handle of the statement to inspect\"\n              required: true\n              mapping: \"$.path.statementHandle\"\n          outputParameters:\n            - name: status\n              type: string\n              description: \"Current execution status\"\n              mapping: \"$.status\"\n        - name: list-tasks\n          description: \"List scheduled tasks\"\n          hints:\n            readOnly:\
  \ true\n            destructive: false\n            idempotent: true\n          call: \"snowflake-task.list-tasks\"\n          inputParameters:\n            - name: database\n              type: string\n              description: \"D\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-engineering.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-engineering.yaml
tags:
- Snowflake
- Data Engineering
- ETL
- Data Pipelines
tools:
- description: Submit a SQL statement for execution
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: submit-sql
- description: Get status of a submitted statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-statement-status
- description: Cancel a running statement
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-statement
- description: List scheduled tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Create a scheduled task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-task
- description: Execute a task immediately
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: execute-task
- description: Resume a suspended task
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-task
- description: Suspend a running task
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: suspend-task
- description: List change data capture streams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-streams
- description: Create a CDC stream
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-stream
- description: List data ingestion pipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-pipes
- description: Create a pipe for continuous ingestion
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-pipe
- description: Refresh a pipe
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: refresh-pipe
- description: List data loading stages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-stages
- description: Create a stage
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-stage
- description: List files in a stage
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-stage-files
- description: List functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-functions
- description: Create a function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-function
- description: Execute a function
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-function
- description: List stored procedures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-procedures
- description: Create a stored procedure
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-procedure
- description: Call a stored procedure
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: call-procedure
- description: List user defined functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-udfs
- description: Get a query result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-query-result
- description: Submit a SQL statement for execution
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: submit-sql
- description: Get status of a submitted statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-statement-status
- description: List scheduled tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-tasks
- description: List change data capture streams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-streams
- description: List data ingestion pipes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-pipes
- description: List data loading stages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-stages
- description: Get a query result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-query-result
---
