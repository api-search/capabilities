---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Hive Data Querying
operations: []
personas: []
provider_name: Apache Hive
provider_slug: apache-hive
search_terms:
- apache
- etl
- open source
- hadoop
- sql
- data warehouse
- big data
slug: hive-data-querying
source_filename: hive-data-querying.yaml
source_heading: Capability Spec
source_yaml: "name: Apache Hive Data Querying\ndescription: Workflow capability for querying and managing data warehouse tables using Apache Hive WebHCat\npersona: Data Analyst\nworkflow:\n  - step: list-databases\n    name: List Databases\n    description: Discover available databases in the Hive metastore\n    capability: hive-webhcat\n    operation: listDatabases\n    server:\n      rest: http://localhost:50111/templeton/v1\n      mcp: http://localhost:9090\n\n  - step: list-tables\n    name: List Tables\n    description: List tables in a target database\n    capability: hive-webhcat\n    operation: listTables\n    server:\n      rest: http://localhost:50111/templeton/v1\n      mcp: http://localhost:9090\n\n  - step: get-table\n    name: Get Table Schema\n    description: Retrieve column definitions and metadata for a table\n    capability: hive-webhcat\n    operation: getTable\n    server:\n      rest: http://localhost:50111/templeton/v1\n      mcp: http://localhost:9090\n\n  - step:\
  \ submit-query\n    name: Submit HiveQL Query\n    description: Execute a HiveQL query as an asynchronous job\n    capability: hive-webhcat\n    operation: submitHiveJob\n    server:\n      rest: http://localhost:50111/templeton/v1\n      mcp: http://localhost:9090\n\ntools:\n  - name: listDatabases\n    description: List all databases in the Hive metastore\n    server:\n      rest:\n        baseUrl: http://localhost:50111/templeton/v1\n        path: /ddl/database\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listDatabases\n        method: POST\n\n  - name: listTables\n    description: List tables in a Hive database\n    server:\n      rest:\n        baseUrl: http://localhost:50111/templeton/v1\n        path: /ddl/database/{dbName}/table\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/listTables\n        method: POST\n\n  - name: getTable\n    description: Get schema and metadata for a Hive\
  \ table\n    server:\n      rest:\n        baseUrl: http://localhost:50111/templeton/v1\n        path: /ddl/database/{dbName}/table/{tableName}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getTable\n        method: POST\n\n  - name: submitHiveJob\n    description: Submit a HiveQL query as an asynchronous job\n    server:\n      rest:\n        baseUrl: http://localhost:50111/templeton/v1\n        path: /hive\n        method: POST\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/submitHiveJob\n        method: POST\n\n  - name: getJobStatus\n    description: Get the status and result of a submitted Hive job\n    server:\n      rest:\n        baseUrl: http://localhost:50111/templeton/v1\n        path: /jobs/{jobId}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getJobStatus\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-hive/refs/heads/main/capabilities/hive-data-querying.yaml
tags: []
tools: []
---
