---
categories: []
consumed_apis: []
description: Unified database operations workflow combining SQL execution via the SingleStore Data API with workspace management via the Management API. Used by data engineers, application developers, and DevOps teams to manage database infrastructure and execute queries programmatically without native database drivers.
layout: capability
name: SingleStore Database Operations
operations:
- description: Execute DDL or DML SQL statements
  method: POST
  name: execute-sql
  path: /v1/sql/exec
- description: Execute SELECT queries and return results as rows
  method: POST
  name: query-data
  path: /v1/sql/query
- description: List all workspace groups
  method: GET
  name: list-workspace-groups
  path: /v1/workspace-groups
- description: Create a workspace group
  method: POST
  name: create-workspace-group
  path: /v1/workspace-groups
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create a workspace
  method: POST
  name: create-workspace
  path: /v1/workspaces
- description: Suspend a workspace to reduce costs
  method: POST
  name: suspend-workspace
  path: /v1/workspaces/{workspaceID}/suspend
- description: Resume a suspended workspace
  method: POST
  name: resume-workspace
  path: /v1/workspaces/{workspaceID}/resume
- description: List deployment regions
  method: GET
  name: list-regions
  path: /v1/regions
personas: []
provider_name: SingleStore
provider_slug: singlestore
search_terms:
- analytics
- list all workspace groups
- list workspaces
- suspend a running workspace to pause billing during idle periods
- manage workspaces
- suspend workspace
- list regions
- provision a new singlestore workspace with specified compute size
- create a workspace
- query database
- suspend a workspace
- resume a suspended workspace to restore database access
- execute sql
- query data with row results
- query data
- list available cloud regions for deploying singlestore workspaces
- execute ddl or dml sql statements
- execute a select sql query against singlestore and return results
- create workspace
- distributed sql
- list available regions
- provisioning
- sql
- execute sql statements
- create a workspace group
- list all singlestore workspace groups in the organization
- manage workspace groups
- create a new singlestore workspace group in a specified region
- list deployment regions
- suspend a workspace to reduce costs
- database
- get details and connection information for a specific workspace
- cloud
- list jobs
- execute select queries and return results as rows
- execute a sql ddl or dml statement against singlestore (create table, insert, update, delete)
- resume workspace
- create workspace group
- list workspace groups
- resume a workspace
- workspaces
- list scheduled notebook automation jobs
- list all workspaces in the organization
- get workspace
- resume a suspended workspace
slug: database-operations
source_filename: database-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SingleStore Database Operations\n  description: Unified database operations workflow combining SQL execution via the SingleStore Data API with workspace management\n    via the Management API. Used by data engineers, application developers, and DevOps teams to manage database infrastructure\n    and execute queries programmatically without native database drivers.\n  tags:\n  - Database\n  - SQL\n  - Analytics\n  - Workspaces\n  - Provisioning\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SINGLESTORE_API_KEY: SINGLESTORE_API_KEY\n    SINGLESTORE_MANAGEMENT_API_KEY: SINGLESTORE_MANAGEMENT_API_KEY\n    SINGLESTORE_WORKSPACE_HOST: SINGLESTORE_WORKSPACE_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: singlestore-data\n    baseUri: https://{{SINGLESTORE_WORKSPACE_HOST}}\n    description: SingleStore Data API for SQL execution over HTTP\n    authentication:\n      type: bearer\n   \
  \   token: '{{SINGLESTORE_API_KEY}}'\n    resources:\n    - name: exec\n      path: /api/v2/exec\n      description: Execute DDL and DML SQL statements\n      operations:\n      - name: execute-sql\n        method: POST\n        description: Execute a SQL statement (DDL, DML, or non-SELECT statements)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sql: '{{tools.sql}}'\n            database: '{{tools.database}}'\n            args: '{{tools.args}}'\n    - name: query-rows\n      path: /api/v2/query/rows\n      description: Execute SELECT statements returning JSON rows\n      operations:\n      - name: query-rows\n        method: POST\n        description: Execute a SQL query and return results as named JSON rows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \    body:\n          type: json\n          data:\n            sql: '{{tools.sql}}'\n            database: '{{tools.database}}'\n            args: '{{tools.args}}'\n    - name: query-tuples\n      path: /api/v2/query/tuples\n      description: Execute SELECT statements returning JSON tuples\n      operations:\n      - name: query-tuples\n        method: POST\n        description: Execute a SQL query and return results as compact JSON tuples\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sql: '{{tools.sql}}'\n            database: '{{tools.database}}'\n            args: '{{tools.args}}'\n    - name: ping\n      path: /api/v2/ping\n      description: Health check for the Data API\n      operations:\n      - name: ping\n        method: GET\n        description: Ping the Data API to verify connectivity\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: singlestore-mgmt\n    baseUri: https://api.singlestore.com/v1\n    description: SingleStore Management API for workspace and infrastructure management\n    authentication:\n      type: bearer\n      token: '{{SINGLESTORE_MANAGEMENT_API_KEY}}'\n    resources:\n    - name: workspace-groups\n      path: /workspaceGroups\n      description: Manage workspace groups\n      operations:\n      - name: list-workspace-groups\n        method: GET\n        description: List all workspace groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace-group\n        method: POST\n        description: Create a new workspace group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n       \
  \   data:\n            name: '{{tools.name}}'\n            regionID: '{{tools.regionID}}'\n            adminPassword: '{{tools.adminPassword}}'\n    - name: workspace-group\n      path: /workspaceGroups/{workspaceGroupID}\n      description: Manage a specific workspace group\n      operations:\n      - name: get-workspace-group\n        method: GET\n        description: Get a workspace group\n        inputParameters:\n        - name: workspaceGroupID\n          in: path\n          type: string\n          required: true\n          description: The workspace group identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminate-workspace-group\n        method: DELETE\n        description: Terminate a workspace group\n        inputParameters:\n        - name: workspaceGroupID\n          in: path\n          type: string\n          required: true\n          description: The workspace group identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces within workspace groups\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: List workspaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-workspace\n        method: POST\n        description: Create a new workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            workspaceGroupID: '{{tools.workspaceGroupID}}'\n            size: '{{tools.size}}'\n    - name: workspace\n      path: /workspaces/{workspaceID}\n      description: Manage a specific workspace\n  \
  \    operations:\n      - name: get-workspace\n        method: GET\n        description: Get a workspace\n        inputParameters:\n        - name: workspaceID\n          in: path\n          type: string\n          required: true\n          description: The workspace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-workspace\n        method: PATCH\n        description: Suspend a workspace to stop billing\n        inputParameters:\n        - name: workspaceID\n          in: path\n          type: string\n          required: true\n          description: The workspace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            suspended: true\n      - name: resume-workspace\n        method: PATCH\n        description: Resume a suspended\
  \ workspace\n        inputParameters:\n        - name: workspaceID\n          in: path\n          type: string\n          required: true\n          description: The workspace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            suspended: false\n      - name: terminate-workspace\n        method: DELETE\n        description: Terminate and delete a workspace\n        inputParameters:\n        - name: workspaceID\n          in: path\n          type: string\n          required: true\n          description: The workspace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: regions\n      path: /regions\n      description: List available deployment regions\n      operations:\n      - name: list-regions\n        method: GET\n        description: List\
  \ available regions for workspace deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Manage scheduled notebook jobs\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List scheduled jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Create a new scheduled job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            notebookPath: '{{tools.notebookPath}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: database-operations-api\n    description: Unified REST API for SingleStore database\
  \ and workspace management.\n    resources:\n    - path: /v1/sql/exec\n      name: sql-exec\n      description: Execute SQL statements\n      operations:\n      - method: POST\n        name: execute-sql\n        description: Execute DDL or DML SQL statements\n        call: singlestore-data.execute-sql\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sql/query\n      name: sql-query\n      description: Query data with row results\n      operations:\n      - method: POST\n        name: query-data\n        description: Execute SELECT queries and return results as rows\n        call: singlestore-data.query-rows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspace-groups\n      name: workspace-groups\n      description: Manage workspace groups\n      operations:\n      - method: GET\n        name: list-workspace-groups\n        description: List all workspace groups\n        call: singlestore-mgmt.list-workspace-groups\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workspace-group\n        description: Create a workspace group\n        call: singlestore-mgmt.create-workspace-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List workspaces\n        call: singlestore-mgmt.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workspace\n        description: Create a workspace\n        call: singlestore-mgmt.create-workspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspaceID}/suspend\n      name: workspace-suspend\n      description: Suspend a workspace\n      operations:\n      - method:\
  \ POST\n        name: suspend-workspace\n        description: Suspend a workspace to reduce costs\n        call: singlestore-mgmt.suspend-workspace\n        with:\n          workspaceID: rest.workspaceID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces/{workspaceID}/resume\n      name: workspace-resume\n      description: Resume a workspace\n      operations:\n      - method: POST\n        name: resume-workspace\n        description: Resume a suspended workspace\n        call: singlestore-mgmt.resume-workspace\n        with:\n          workspaceID: rest.workspaceID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/regions\n      name: regions\n      description: List available regions\n      operations:\n      - method: GET\n        name: list-regions\n        description: List deployment regions\n        call: singlestore-mgmt.list-regions\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: database-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted SingleStore database operations and infrastructure management.\n    tools:\n    - name: execute-sql\n      description: Execute a SQL DDL or DML statement against SingleStore (CREATE TABLE, INSERT, UPDATE, DELETE)\n      hints:\n        readOnly: false\n        destructive: false\n      call: singlestore-data.execute-sql\n      with:\n        sql: tools.sql\n        database: tools.database\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-database\n      description: Execute a SELECT SQL query against SingleStore and return results\n      hints:\n        readOnly: true\n        openWorld: true\n      call: singlestore-data.query-rows\n      with:\n        sql: tools.sql\n        database: tools.database\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspace-groups\n\
  \      description: List all SingleStore workspace groups in the organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: singlestore-mgmt.list-workspace-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace-group\n      description: Create a new SingleStore workspace group in a specified region\n      hints:\n        readOnly: false\n        destructive: false\n      call: singlestore-mgmt.create-workspace-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all workspaces in the organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: singlestore-mgmt.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workspace\n      description: Provision a new SingleStore workspace with specified compute size\n      hints:\n        readOnly: false\n       \
  \ destructive: false\n      call: singlestore-mgmt.create-workspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workspace\n      description: Get details and connection information for a specific workspace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: singlestore-mgmt.get-workspace\n      with:\n        workspaceID: tools.workspaceID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: suspend-workspace\n      description: Suspend a running workspace to pause billing during idle periods\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: singlestore-mgmt.suspend-workspace\n      with:\n        workspaceID: tools.workspaceID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-workspace\n      description: Resume a suspended workspace to restore database access\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: singlestore-mgmt.resume-workspace\n      with:\n        workspaceID: tools.workspaceID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-regions\n      description: List available cloud regions for deploying SingleStore workspaces\n      hints:\n        readOnly: true\n        openWorld: false\n      call: singlestore-mgmt.list-regions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List scheduled notebook automation jobs\n      hints:\n        readOnly: true\n        openWorld: false\n      call: singlestore-mgmt.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/singlestore/refs/heads/main/capabilities/database-operations.yaml
tags:
- Database
- SQL
- Analytics
- Workspaces
- Provisioning
tools:
- description: Execute a SQL DDL or DML statement against SingleStore (CREATE TABLE, INSERT, UPDATE, DELETE)
  hints:
    destructive: false
    readOnly: false
  name: execute-sql
- description: Execute a SELECT SQL query against SingleStore and return results
  hints:
    openWorld: true
    readOnly: true
  name: query-database
- description: List all SingleStore workspace groups in the organization
  hints:
    openWorld: false
    readOnly: true
  name: list-workspace-groups
- description: Create a new SingleStore workspace group in a specified region
  hints:
    destructive: false
    readOnly: false
  name: create-workspace-group
- description: List all workspaces in the organization
  hints:
    openWorld: false
    readOnly: true
  name: list-workspaces
- description: Provision a new SingleStore workspace with specified compute size
  hints:
    destructive: false
    readOnly: false
  name: create-workspace
- description: Get details and connection information for a specific workspace
  hints:
    openWorld: false
    readOnly: true
  name: get-workspace
- description: Suspend a running workspace to pause billing during idle periods
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-workspace
- description: Resume a suspended workspace to restore database access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-workspace
- description: List available cloud regions for deploying SingleStore workspaces
  hints:
    openWorld: false
    readOnly: true
  name: list-regions
- description: List scheduled notebook automation jobs
  hints:
    openWorld: false
    readOnly: true
  name: list-jobs
---
