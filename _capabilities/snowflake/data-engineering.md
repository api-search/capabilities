---
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
- list scheduled tasks
- etl
- suspend task
- create function
- get statement status
- cancel statement
- list user defined functions
- list udfs
- data warehousing
- submit a sql statement
- list change data capture streams
- task management
- list data ingestion pipes
- create a cdc stream
- create a function
- data lakes
- data sharing
- list data loading stages
- stream management
- create a pipe for continuous ingestion
- pipe management
- list pipes
- list stages
- submit statement
- create stream
- list streams
- create stage
- execute a task immediately
- refresh pipe
- call a stored procedure
- create pipe
- resume task
- create a stored procedure
- data pipelines
- sql
- list files in a stage
- get query result
- create task
- get status of a submitted statement
- refresh a pipe
- execute function
- call procedure
- stage management
- execute a function
- list stored procedures
- create procedure
- create a stream
- submit a sql statement for execution
- data engineering
- submit sql
- snowflake
- list procedures
- create a pipe
- execute task
- get a query result
- database
- suspend a running task
- create a stage
- list functions
- list tasks
- create a task
- cancel a running statement
- list stage files
- sql statement execution
- create a scheduled task
- resume a suspended task
slug: data-engineering
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Data Engineering\"\n  description: \"Unified workflow for building and managing data pipelines using SQL execution, tasks, streams, pipes, stages, and functions. Used by Data Engineers to orchestrate ETL/ELT workflows and continuous data ingestion.\"\n  tags:\n    - Snowflake\n    - Data Engineering\n    - ETL\n    - Data Pipelines\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-sql\n      location: ./shared/sqlapi.yaml\n    - import: snowflake-task\n      location: ./shared/task.yaml\n    - import: snowflake-stream\n      location: ./shared/stream.yaml\n    - import: snowflake-pipe\n      location: ./shared/pipe.yaml\n    - import: snowflake-stage\n      location: ./shared/stage.yaml\n    - import: snowflake-function\n\
  \      location: ./shared/function.yaml\n    - import: snowflake-procedure\n      location: ./shared/procedure.yaml\n    - import: snowflake-udf\n      location: ./shared/user-defined-function.yaml\n    - import: snowflake-result\n      location: ./shared/result.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: snowflake-data-eng-api\n      description: \"Unified REST API for Snowflake data pipeline management.\"\n      resources:\n        - path: /v1/statements\n          name: statements\n          description: \"SQL statement execution\"\n          operations:\n            - method: POST\n              name: submit-statement\n              description: \"Submit a SQL statement\"\n              call: \"snowflake-sql.submit-statement\"\n        - path: /v1/tasks\n          name: tasks\n          description: \"Task management\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List tasks\"\n         \
  \     call: \"snowflake-task.list-tasks\"\n            - method: POST\n              name: create-task\n              description: \"Create a task\"\n              call: \"snowflake-task.create-task\"\n        - path: /v1/streams\n          name: streams\n          description: \"Stream management\"\n          operations:\n            - method: GET\n              name: list-streams\n              description: \"List streams\"\n              call: \"snowflake-stream.list-streams\"\n            - method: POST\n              name: create-stream\n              description: \"Create a stream\"\n              call: \"snowflake-stream.create-stream\"\n        - path: /v1/pipes\n          name: pipes\n          description: \"Pipe management\"\n          operations:\n            - method: GET\n              name: list-pipes\n              description: \"List pipes\"\n              call: \"snowflake-pipe.list-pipes\"\n            - method: POST\n              name: create-pipe\n              description:\
  \ \"Create a pipe\"\n              call: \"snowflake-pipe.create-pipe\"\n        - path: /v1/stages\n          name: stages\n          description: \"Stage management\"\n          operations:\n            - method: GET\n              name: list-stages\n              description: \"List stages\"\n              call: \"snowflake-stage.list-stages\"\n            - method: POST\n              name: create-stage\n              description: \"Create a stage\"\n              call: \"snowflake-stage.create-stage\"\n\n    - type: mcp\n      port: 9081\n      namespace: snowflake-data-eng-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snowflake data pipeline management.\"\n      tools:\n        - name: submit-sql\n          description: \"Submit a SQL statement for execution\"\n          hints:\n            readOnly: false\n          call: \"snowflake-sql.submit-statement\"\n        - name: get-statement-status\n          description: \"Get status of a submitted statement\"\
  \n          hints:\n            readOnly: true\n          call: \"snowflake-sql.get-statement-status\"\n        - name: cancel-statement\n          description: \"Cancel a running statement\"\n          hints:\n            destructive: true\n          call: \"snowflake-sql.cancel-statement\"\n        - name: list-tasks\n          description: \"List scheduled tasks\"\n          hints:\n            readOnly: true\n          call: \"snowflake-task.list-tasks\"\n        - name: create-task\n          description: \"Create a scheduled task\"\n          hints:\n            readOnly: false\n          call: \"snowflake-task.create-task\"\n        - name: execute-task\n          description: \"Execute a task immediately\"\n          hints:\n            readOnly: false\n          call: \"snowflake-task.execute-task\"\n        - name: resume-task\n          description: \"Resume a suspended task\"\n          hints:\n            readOnly: false\n          call: \"snowflake-task.resume-task\"\n  \
  \      - name: suspend-task\n          description: \"Suspend a running task\"\n          hints:\n            readOnly: false\n          call: \"snowflake-task.suspend-task\"\n        - name: list-streams\n          description: \"List change data capture streams\"\n          hints:\n            readOnly: true\n          call: \"snowflake-stream.list-streams\"\n        - name: create-stream\n          description: \"Create a CDC stream\"\n          hints:\n            readOnly: false\n          call: \"snowflake-stream.create-stream\"\n        - name: list-pipes\n          description: \"List data ingestion pipes\"\n          hints:\n            readOnly: true\n          call: \"snowflake-pipe.list-pipes\"\n        - name: create-pipe\n          description: \"Create a pipe for continuous ingestion\"\n          hints:\n            readOnly: false\n          call: \"snowflake-pipe.create-pipe\"\n        - name: refresh-pipe\n          description: \"Refresh a pipe\"\n          hints:\n\
  \            readOnly: false\n          call: \"snowflake-pipe.refresh-pipe\"\n        - name: list-stages\n          description: \"List data loading stages\"\n          hints:\n            readOnly: true\n          call: \"snowflake-stage.list-stages\"\n        - name: create-stage\n          description: \"Create a stage\"\n          hints:\n            readOnly: false\n          call: \"snowflake-stage.create-stage\"\n        - name: list-stage-files\n          description: \"List files in a stage\"\n          hints:\n            readOnly: true\n          call: \"snowflake-stage.list-files\"\n        - name: list-functions\n          description: \"List functions\"\n          hints:\n            readOnly: true\n          call: \"snowflake-function.list-functions\"\n        - name: create-function\n          description: \"Create a function\"\n          hints:\n            readOnly: false\n          call: \"snowflake-function.create-function\"\n        - name: execute-function\n   \
  \       description: \"Execute a function\"\n          hints:\n            readOnly: false\n          call: \"snowflake-function.execute-function\"\n        - name: list-procedures\n          description: \"List stored procedures\"\n          hints:\n            readOnly: true\n          call: \"snowflake-procedure.list-procedures\"\n        - name: create-procedure\n          description: \"Create a stored procedure\"\n          hints:\n            readOnly: false\n          call: \"snowflake-procedure.create-procedure\"\n        - name: call-procedure\n          description: \"Call a stored procedure\"\n          hints:\n            readOnly: false\n          call: \"snowflake-procedure.call-procedure\"\n        - name: list-udfs\n          description: \"List user defined functions\"\n          hints:\n            readOnly: true\n          call: \"snowflake-udf.list-udfs\"\n        - name: get-query-result\n          description: \"Get a query result\"\n          hints:\n          \
  \  readOnly: true\n          call: \"snowflake-result.get-result\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-engineering.yaml
tags:
- Snowflake
- Data Engineering
- ETL
- Data Pipelines
tools:
- description: Submit a SQL statement for execution
  hints:
    readOnly: false
  name: submit-sql
- description: Get status of a submitted statement
  hints:
    readOnly: true
  name: get-statement-status
- description: Cancel a running statement
  hints:
    destructive: true
  name: cancel-statement
- description: List scheduled tasks
  hints:
    readOnly: true
  name: list-tasks
- description: Create a scheduled task
  hints:
    readOnly: false
  name: create-task
- description: Execute a task immediately
  hints:
    readOnly: false
  name: execute-task
- description: Resume a suspended task
  hints:
    readOnly: false
  name: resume-task
- description: Suspend a running task
  hints:
    readOnly: false
  name: suspend-task
- description: List change data capture streams
  hints:
    readOnly: true
  name: list-streams
- description: Create a CDC stream
  hints:
    readOnly: false
  name: create-stream
- description: List data ingestion pipes
  hints:
    readOnly: true
  name: list-pipes
- description: Create a pipe for continuous ingestion
  hints:
    readOnly: false
  name: create-pipe
- description: Refresh a pipe
  hints:
    readOnly: false
  name: refresh-pipe
- description: List data loading stages
  hints:
    readOnly: true
  name: list-stages
- description: Create a stage
  hints:
    readOnly: false
  name: create-stage
- description: List files in a stage
  hints:
    readOnly: true
  name: list-stage-files
- description: List functions
  hints:
    readOnly: true
  name: list-functions
- description: Create a function
  hints:
    readOnly: false
  name: create-function
- description: Execute a function
  hints:
    readOnly: false
  name: execute-function
- description: List stored procedures
  hints:
    readOnly: true
  name: list-procedures
- description: Create a stored procedure
  hints:
    readOnly: false
  name: create-procedure
- description: Call a stored procedure
  hints:
    readOnly: false
  name: call-procedure
- description: List user defined functions
  hints:
    readOnly: true
  name: list-udfs
- description: Get a query result
  hints:
    readOnly: true
  name: get-query-result
---
