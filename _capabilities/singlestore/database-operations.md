---
categories: []
consumed_apis:
- singlestore-data
- singlestore-mgmt
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
- workspaces
- get details and connection information for a specific workspace
- execute select queries and return results as rows
- suspend a workspace
- list all workspace groups
- resume a suspended workspace
- provisioning
- list jobs
- cloud
- query database
- create workspace group
- create a new singlestore workspace group in a specified region
- analytics
- list workspace groups
- suspend a running workspace to pause billing during idle periods
- create a workspace
- query data
- list deployment regions
- execute sql statements
- manage workspace groups
- list available regions
- resume a workspace
- list all workspaces in the organization
- manage workspaces
- suspend workspace
- list all singlestore workspace groups in the organization
- provision a new singlestore workspace with specified compute size
- database
- create a workspace group
- list regions
- suspend a workspace to reduce costs
- resume workspace
- get workspace
- list available cloud regions for deploying singlestore workspaces
- query data with row results
- execute a sql ddl or dml statement against singlestore (create table, insert, update, delete)
- execute a select sql query against singlestore and return results
- list workspaces
- execute sql
- distributed sql
- resume a suspended workspace to restore database access
- list scheduled notebook automation jobs
- create workspace
- sql
- execute ddl or dml sql statements
slug: database-operations
source_filename: database-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SingleStore Database Operations\"\n  description: >-\n    Unified database operations workflow combining SQL execution via the\n    SingleStore Data API with workspace management via the Management API.\n    Used by data engineers, application developers, and DevOps teams to\n    manage database infrastructure and execute queries programmatically\n    without native database drivers.\n  tags:\n    - Database\n    - SQL\n    - Analytics\n    - Workspaces\n    - Provisioning\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SINGLESTORE_API_KEY: SINGLESTORE_API_KEY\n      SINGLESTORE_MANAGEMENT_API_KEY: SINGLESTORE_MANAGEMENT_API_KEY\n      SINGLESTORE_WORKSPACE_HOST: SINGLESTORE_WORKSPACE_HOST\n\ncapability:\n  consumes:\n    - import: singlestore-data\n      location: ./shared/data-api.yaml\n    - import: singlestore-mgmt\n      location: ./shared/management-api.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: database-operations-api\n      description: \"Unified REST API for SingleStore database and workspace management.\"\n      resources:\n        - path: /v1/sql/exec\n          name: sql-exec\n          description: Execute SQL statements\n          operations:\n            - method: POST\n              name: execute-sql\n              description: Execute DDL or DML SQL statements\n              call: \"singlestore-data.execute-sql\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sql/query\n          name: sql-query\n          description: Query data with row results\n          operations:\n            - method: POST\n              name: query-data\n              description: Execute SELECT queries and return results as rows\n              call: \"singlestore-data.query-rows\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/workspace-groups\n          name: workspace-groups\n          description: Manage workspace groups\n          operations:\n            - method: GET\n              name: list-workspace-groups\n              description: List all workspace groups\n              call: \"singlestore-mgmt.list-workspace-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace-group\n              description: Create a workspace group\n              call: \"singlestore-mgmt.create-workspace-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces\n          name: workspaces\n          description: Manage workspaces\n          operations:\n            - method: GET\n              name: list-workspaces\n              description: List workspaces\n              call: \"singlestore-mgmt.list-workspaces\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workspace\n              description: Create a workspace\n              call: \"singlestore-mgmt.create-workspace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspaceID}/suspend\n          name: workspace-suspend\n          description: Suspend a workspace\n          operations:\n            - method: POST\n              name: suspend-workspace\n              description: Suspend a workspace to reduce costs\n              call: \"singlestore-mgmt.suspend-workspace\"\n              with:\n                workspaceID: \"rest.workspaceID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workspaces/{workspaceID}/resume\n          name: workspace-resume\n          description:\
  \ Resume a workspace\n          operations:\n            - method: POST\n              name: resume-workspace\n              description: Resume a suspended workspace\n              call: \"singlestore-mgmt.resume-workspace\"\n              with:\n                workspaceID: \"rest.workspaceID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/regions\n          name: regions\n          description: List available regions\n          operations:\n            - method: GET\n              name: list-regions\n              description: List deployment regions\n              call: \"singlestore-mgmt.list-regions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: database-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SingleStore database operations and infrastructure management.\"\
  \n      tools:\n        - name: execute-sql\n          description: Execute a SQL DDL or DML statement against SingleStore (CREATE TABLE, INSERT, UPDATE, DELETE)\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"singlestore-data.execute-sql\"\n          with:\n            sql: \"tools.sql\"\n            database: \"tools.database\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-database\n          description: Execute a SELECT SQL query against SingleStore and return results\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"singlestore-data.query-rows\"\n          with:\n            sql: \"tools.sql\"\n            database: \"tools.database\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspace-groups\n          description: List all SingleStore workspace groups in the\
  \ organization\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"singlestore-mgmt.list-workspace-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace-group\n          description: Create a new SingleStore workspace group in a specified region\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"singlestore-mgmt.create-workspace-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workspaces\n          description: List all workspaces in the organization\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"singlestore-mgmt.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workspace\n          description: Provision a new SingleStore workspace\
  \ with specified compute size\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"singlestore-mgmt.create-workspace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workspace\n          description: Get details and connection information for a specific workspace\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"singlestore-mgmt.get-workspace\"\n          with:\n            workspaceID: \"tools.workspaceID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: suspend-workspace\n          description: Suspend a running workspace to pause billing during idle periods\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"singlestore-mgmt.suspend-workspace\"\n          with:\n            workspaceID: \"tools.workspaceID\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resume-workspace\n          description: Resume a suspended workspace to restore database access\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"singlestore-mgmt.resume-workspace\"\n          with:\n            workspaceID: \"tools.workspaceID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-regions\n          description: List available cloud regions for deploying SingleStore workspaces\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"singlestore-mgmt.list-regions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: List scheduled notebook automation jobs\n          hints:\n            readOnly: true\n      \
  \      openWorld: false\n          call: \"singlestore-mgmt.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
