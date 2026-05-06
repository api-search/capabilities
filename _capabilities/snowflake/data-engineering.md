---
categories:
- data-engineering
consumed_apis: []
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
- create a scheduled task
- cancel a running statement
- create a stored procedure
- list user defined functions
- cancel statement
- resume task
- create stage
- stream management
- submit sql
- create stream
- submit statement
- data pipelines
- snowflake
- suspend task
- create a pipe
- list tasks
- refresh a pipe
- create pipe
- list stages
- execute a task immediately
- list files in a stage
- create function
- list streams
- pipe management
- list data loading stages
- data engineering
- etl
- list stage files
- get statement status
- list data ingestion pipes
- create a task
- get status of a submitted statement
- sql
- stage management
- data sharing
- submit a sql statement
- list scheduled tasks
- create procedure
- create a cdc stream
- get query result
- list udfs
- data lakes
- database
- execute a function
- task management
- list change data capture streams
- refresh pipe
- execute function
- execute task
- get a query result
- create a pipe for continuous ingestion
- list functions
- call a stored procedure
- call procedure
- create a stream
- data warehousing
- submit a sql statement for execution
- create a stage
- create a function
- resume a suspended task
- list pipes
- create task
- sql statement execution
- list stored procedures
- suspend a running task
- list procedures
slug: data-engineering
source_filename: data-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowflake Data Engineering\n  description: Unified workflow for building and managing data pipelines using SQL execution, tasks, streams, pipes, stages,\n    and functions. Used by Data Engineers to orchestrate ETL/ELT workflows and continuous data ingestion.\n  tags:\n  - Snowflake\n  - Data Engineering\n  - ETL\n  - Data Pipelines\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n    SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snowflake-sql\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake SQL API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: statements\n      path: /api/v2/statements\n      description: SQL statement resources\n      operations:\n      - name: submit-statement\n        method: POST\n        description:\
  \ Submit a SQL statement for execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            statement: '{{tools.statement}}'\n            warehouse: '{{tools.warehouse}}'\n      - name: get-statement-status\n        method: GET\n        description: Get the status of a submitted statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-statement\n        method: POST\n        description: Cancel a running statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-task\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Task API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n   \
  \ resources:\n    - name: tasks\n      path: /api/v2/databases/{database}/schemas/{schema}/tasks\n      description: Task resources\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-task\n        method: POST\n        description: Create a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-task\n        method: GET\n        description: Fetch a task by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-task\n        method: DELETE\n        description: Delete a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: execute-task\n        method: POST\n        description: Execute a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-task\n        method: POST\n        description: Resume a suspended task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-task\n        method: POST\n        description: Suspend a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-stream\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Stream API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: streams\n      path: /api/v2/databases/{database}/schemas/{schema}/streams\n      description: Stream resources\n\
  \      operations:\n      - name: list-streams\n        method: GET\n        description: List streams\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-stream\n        method: POST\n        description: Create a stream\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-stream\n        method: GET\n        description: Fetch a stream by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-stream\n        method: DELETE\n        description: Delete a stream\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-pipe\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake\
  \ Pipe API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: pipes\n      path: /api/v2/databases/{database}/schemas/{schema}/pipes\n      description: Pipe resources\n      operations:\n      - name: list-pipes\n        method: GET\n        description: List pipes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pipe\n        method: POST\n        description: Create a pipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-pipe\n        method: GET\n        description: Fetch a pipe by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-pipe\n        method: DELETE\n        description: Delete a pipe\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-pipe\n        method: POST\n        description: Refresh a pipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-stage\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Stage API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: stages\n      path: /api/v2/databases/{database}/schemas/{schema}/stages\n      description: Stage resources\n      operations:\n      - name: list-stages\n        method: GET\n        description: List stages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-stage\n        method: POST\n        description: Create a stage\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-stage\n        method: GET\n        description: Fetch a stage by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-stage\n        method: DELETE\n        description: Delete a stage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-files\n        method: GET\n        description: List files in a stage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-function\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Function API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: functions\n\
  \      path: /api/v2/databases/{database}/schemas/{schema}/functions\n      description: Function resources\n      operations:\n      - name: list-functions\n        method: GET\n        description: List functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-function\n        method: POST\n        description: Create a function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-function\n        method: GET\n        description: Fetch a function by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-function\n        method: DELETE\n        description: Delete a function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: execute-function\n        method: POST\n        description: Execute a function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-procedure\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Procedure API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: procedures\n      path: /api/v2/databases/{database}/schemas/{schema}/procedures\n      description: Procedure resources\n      operations:\n      - name: list-procedures\n        method: GET\n        description: List procedures\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-procedure\n        method: POST\n        description: Create a procedure\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: fetch-procedure\n        method: GET\n        description: Fetch a procedure by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-procedure\n        method: DELETE\n        description: Delete a procedure\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: call-procedure\n        method: POST\n        description: Call a procedure\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-udf\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake User Defined Function API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: user-defined-functions\n\
  \      path: /api/v2/databases/{database}/schemas/{schema}/user-defined-functions\n      description: UDF resources\n      operations:\n      - name: list-udfs\n        method: GET\n        description: List user defined functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-udf\n        method: POST\n        description: Create a user defined function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-udf\n        method: GET\n        description: Fetch a UDF by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-udf\n        method: DELETE\n        description: Delete a UDF\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n  - type: http\n    namespace: snowflake-result\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Result API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: results\n      path: /api/v2/results\n      description: Result resources\n      operations:\n      - name: get-result\n        method: GET\n        description: Get a query result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: snowflake-data-eng-api\n    description: Unified REST API for Snowflake data pipeline management.\n    resources:\n    - path: /v1/statements\n      name: statements\n      description: SQL statement execution\n      operations:\n      - method: POST\n        name: submit-statement\n        description: Submit a SQL statement\n        call: snowflake-sql.submit-statement\n \
  \       inputParameters:\n        - name: statement\n          type: string\n          description: SQL statement to execute\n          required: true\n          mapping: $.body.statement\n        - name: warehouse\n          type: string\n          description: Warehouse used to execute the statement\n          required: false\n          mapping: $.body.warehouse\n        outputParameters:\n        - name: statementHandle\n          type: string\n          description: Handle identifying the submitted statement\n          mapping: $.statementHandle\n        - name: result\n          type: object\n          description: Raw statement submission payload\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Task management\n      operations:\n      - method: GET\n        name: list-tasks\n        description: List tasks\n        call: snowflake-task.list-tasks\n        inputParameters:\n        - name: database\n          type: string\n          description:\
  \ Database containing the tasks\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema containing the tasks\n          required: true\n          mapping: $.path.schema\n        outputParameters:\n        - name: tasks\n          type: array\n          description: Collection of tasks in the schema\n          mapping: $.\n      - method: POST\n        name: create-task\n        description: Create a task\n        call: snowflake-task.create-task\n        inputParameters:\n        - name: database\n          type: string\n          description: Database that will own the task\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema that will own the task\n          required: true\n          mapping: $.path.schema\n        - name: name\n          type: string\n          description: Task name\n          required: true\n \
  \         mapping: $.body.name\n        - name: definition\n          type: string\n          description: SQL body of the task\n          required: true\n          mapping: $.body.definition\n        outputParameters:\n        - name: task\n          type: object\n          description: Created task definition\n          mapping: $.\n    - path: /v1/streams\n      name: streams\n      description: Stream management\n      operations:\n      - method: GET\n        name: list-streams\n        description: List streams\n        call: snowflake-stream.list-streams\n        inputParameters:\n        - name: database\n          type: string\n          description: Database containing the streams\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema containing the streams\n          required: true\n          mapping: $.path.schema\n        outputParameters:\n        - name: streams\n          type: array\n\
  \          description: Collection of change data capture streams\n          mapping: $.\n      - method: POST\n        name: create-stream\n        description: Create a stream\n        call: snowflake-stream.create-stream\n        inputParameters:\n        - name: database\n          type: string\n          description: Database that will own the stream\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema that will own the stream\n          required: true\n          mapping: $.path.schema\n        - name: name\n          type: string\n          description: Stream name\n          required: true\n          mapping: $.body.name\n        - name: table_name\n          type: string\n          description: Source table tracked by the stream\n          required: true\n          mapping: $.body.table_name\n    - path: /v1/pipes\n      name: pipes\n      description: Pipe management\n      operations:\n  \
  \    - method: GET\n        name: list-pipes\n        description: List pipes\n        call: snowflake-pipe.list-pipes\n        inputParameters:\n        - name: database\n          type: string\n          description: Database containing the pipes\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema containing the pipes\n          required: true\n          mapping: $.path.schema\n        outputParameters:\n        - name: pipes\n          type: array\n          description: Collection of ingestion pipes\n          mapping: $.\n      - method: POST\n        name: create-pipe\n        description: Create a pipe\n        call: snowflake-pipe.create-pipe\n        inputParameters:\n        - name: database\n          type: string\n          description: Database that will own the pipe\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n        \
  \  description: Schema that will own the pipe\n          required: true\n          mapping: $.path.schema\n        - name: name\n          type: string\n          description: Pipe name\n          required: true\n          mapping: $.body.name\n        - name: copy_statement\n          type: string\n          description: COPY statement that defines the pipe\n          required: true\n          mapping: $.body.copy_statement\n    - path: /v1/stages\n      name: stages\n      description: Stage management\n      operations:\n      - method: GET\n        name: list-stages\n        description: List stages\n        call: snowflake-stage.list-stages\n        inputParameters:\n        - name: database\n          type: string\n          description: Database containing the stages\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema containing the stages\n          required: true\n          mapping: $.path.schema\n\
  \        outputParameters:\n        - name: stages\n          type: array\n          description: Collection of data loading stages\n          mapping: $.\n      - method: POST\n        name: create-stage\n        description: Create a stage\n        call: snowflake-stage.create-stage\n        inputParameters:\n        - name: database\n          type: string\n          description: Database that will own the stage\n          required: true\n          mapping: $.path.database\n        - name: schema\n          type: string\n          description: Schema that will own the stage\n          required: true\n          mapping: $.path.schema\n        - name: name\n          type: string\n          description: Stage name\n          required: true\n          mapping: $.body.name\n  - type: mcp\n    port: 9081\n    namespace: snowflake-data-eng-mcp\n    transport: http\n    description: MCP server (HTTP) for AI-assisted Snowflake data pipeline management.\n    tools:\n    - name: submit-sql\n\
  \      description: Submit a SQL statement for execution\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: snowflake-sql.submit-statement\n      inputParameters:\n      - name: statement\n        type: string\n        description: SQL statement to execute\n        required: true\n        mapping: $.body.statement\n      - name: warehouse\n        type: string\n        description: Warehouse used to execute the statement\n        required: false\n        mapping: $.body.warehouse\n      outputParameters:\n      - name: statementHandle\n        type: string\n        description: Handle identifying the submitted statement\n        mapping: $.statementHandle\n      - name: result\n        type: object\n        description: Raw statement submission payload\n        mapping: $.\n    - name: get-statement-status\n      description: Get status of a submitted statement\n      hints:\n        readOnly: true\n        destructive: false\n   \
  \     idempotent: true\n      call: snowflake-sql.get-statement-status\n      inputParameters:\n      - name: statementHandle\n        type: string\n        description: Handle of the statement to inspect\n        required: true\n        mapping: $.path.statementHandle\n      outputParameters:\n      - name: status\n        type: string\n        description: Current execution status\n        mapping: $.status\n      - name: result\n        type: object\n        description: Full status payload\n        mapping: $.\n    - name: cancel-statement\n      description: Cancel a running statement\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snowflake-sql.cancel-statement\n      inputParameters:\n      - name: statementHandle\n        type: string\n        description: Handle of the statement to cancel\n        required: true\n        mapping: $.path.statementHandle\n      outputParameters:\n      - name: result\n        type: object\n\
  \        description: Cancellation response\n        mapping: $.\n    - name: list-tasks\n      description: List scheduled tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-task.list-tasks\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the tasks\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the tasks\n        required: true\n        mapping: $.path.schema\n      outputParameters:\n      - name: tasks\n        type: array\n        description: Collection of tasks in the schema\n        mapping: $.\n    - name: create-task\n      description: Create a scheduled task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-task.create-task\n      inputParameters:\n      - name: database\n        type:\
  \ string\n        description: Database that will own the task\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema that will own the task\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Task name\n        required: true\n        mapping: $.body.name\n      - name: definition\n        type: string\n        description: SQL body of the task\n        required: true\n        mapping: $.body.definition\n    - name: execute-task\n      description: Execute a task immediately\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: snowflake-task.execute-task\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the task\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description:\
  \ Schema containing the task\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Task name to execute\n        required: true\n        mapping: $.path.name\n    - name: resume-task\n      description: Resume a suspended task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: snowflake-task.resume-task\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the task\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the task\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Task name to resume\n        required: true\n        mapping: $.path.name\n    - name: suspend-task\n      description: Suspend a running task\n      hints:\n        readOnly: false\n\
  \        destructive: true\n        idempotent: true\n      call: snowflake-task.suspend-task\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the task\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the task\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Task name to suspend\n        required: true\n        mapping: $.path.name\n    - name: list-streams\n      description: List change data capture streams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-stream.list-streams\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the streams\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n\
  \        description: Schema containing the streams\n        required: true\n        mapping: $.path.schema\n      outputParameters:\n      - name: streams\n        type: array\n        description: Collection of CDC streams\n        mapping: $.\n    - name: create-stream\n      description: Create a CDC stream\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-stream.create-stream\n      inputParameters:\n      - name: database\n        type: string\n        description: Database that will own the stream\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema that will own the stream\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Stream name\n        required: true\n        mapping: $.body.name\n      - name: table_name\n        type: string\n        description: Source table\
  \ tracked by the stream\n        required: true\n        mapping: $.body.table_name\n    - name: list-pipes\n      description: List data ingestion pipes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-pipe.list-pipes\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the pipes\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the pipes\n        required: true\n        mapping: $.path.schema\n      outputParameters:\n      - name: pipes\n        type: array\n        description: Collection of ingestion pipes\n        mapping: $.\n    - name: create-pipe\n      description: Create a pipe for continuous ingestion\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-pipe.create-pipe\n      inputParameters:\n \
  \     - name: database\n        type: string\n        description: Database that will own the pipe\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema that will own the pipe\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Pipe name\n        required: true\n        mapping: $.body.name\n      - name: copy_statement\n        type: string\n        description: COPY statement that defines the pipe\n        required: true\n        mapping: $.body.copy_statement\n    - name: refresh-pipe\n      description: Refresh a pipe\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: snowflake-pipe.refresh-pipe\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the pipe\n        required: true\n        mapping: $.path.database\n      - name:\
  \ schema\n        type: string\n        description: Schema containing the pipe\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Pipe name to refresh\n        required: true\n        mapping: $.path.name\n    - name: list-stages\n      description: List data loading stages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-stage.list-stages\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the stages\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the stages\n        required: true\n        mapping: $.path.schema\n      outputParameters:\n      - name: stages\n        type: array\n        description: Collection of data loading stages\n        mapping: $.\n    - name: create-stage\n      description:\
  \ Create a stage\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-stage.create-stage\n      inputParameters:\n      - name: database\n        type: string\n        description: Database that will own the stage\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema that will own the stage\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Stage name\n        required: true\n        mapping: $.body.name\n    - name: list-stage-files\n      description: List files in a stage\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-stage.list-files\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the stage\n        required: true\n        mapping: $.path.database\n\
  \      - name: schema\n        type: string\n        description: Schema containing the stage\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Stage name\n        required: true\n        mapping: $.path.name\n      outputParameters:\n      - name: files\n        type: array\n        description: Collection of files staged for loading\n        mapping: $.\n    - name: list-functions\n      description: List functions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-function.list-functions\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the functions\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the functions\n        required: true\n        mapping: $.path.schema\n      outputParameters:\n     \
  \ - name: functions\n        type: array\n        description: Collection of functions\n        mapping: $.\n    - name: create-function\n      description: Create a function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-function.create-function\n      inputParameters:\n      - name: database\n        type: string\n        description: Database that will own the function\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema that will own the function\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Function name\n        required: true\n        mapping: $.body.name\n    - name: execute-function\n      description: Execute a function\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: snowflake-function.execute-function\n\
  \      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the function\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n        description: Schema containing the function\n        required: true\n        mapping: $.path.schema\n      - name: name\n        type: string\n        description: Function name to execute\n        required: true\n        mapping: $.path.name\n    - name: list-procedures\n      description: List stored procedures\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: snowflake-procedure.list-procedures\n      inputParameters:\n      - name: database\n        type: string\n        description: Database containing the procedures\n        required: true\n        mapping: $.path.database\n      - name: schema\n        type: string\n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-engineering.yaml\n"
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
