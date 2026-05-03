---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Hudi Lakehouse Management
operations: []
personas: []
provider_name: Apache Hudi
provider_slug: apache-hudi
search_terms:
- lakehouse
- big data
- incremental processing
- apache
- acid
- open source
- data lake
slug: hudi-lakehouse-management
source_filename: hudi-lakehouse-management.yaml
source_heading: Capability Spec
source_yaml: "name: Apache Hudi Lakehouse Management\ndescription: Workflow capability for managing Apache Hudi data lake tables with ACID transactions, incremental queries, and timeline operations\npersona: Data Engineer\nworkflow:\n  - step: create-table\n    name: Create Hudi Table\n    description: Initialize a new Hudi table with record key and partition configuration\n    capability: hudi-timeline\n    operation: createTable\n    server:\n      rest: http://localhost:9090\n      mcp: http://localhost:9090\n\n  - step: get-timeline\n    name: Inspect Timeline\n    description: View completed commits and operations on the Hudi timeline\n    capability: hudi-timeline\n    operation: getTimeline\n    server:\n      rest: http://localhost:9090\n      mcp: http://localhost:9090\n\n  - step: get-commit\n    name: Get Commit Details\n    description: Inspect write statistics for a specific commit\n    capability: hudi-timeline\n    operation: getCommitMetadata\n    server:\n      rest: http://localhost:9090\n\
  \      mcp: http://localhost:9090\n\n  - step: run-cleaning\n    name: Clean Old Files\n    description: Remove old file versions to reclaim storage space\n    capability: hudi-timeline\n    operation: runCleaning\n    server:\n      rest: http://localhost:9090\n      mcp: http://localhost:9090\n\ntools:\n  - name: getTimeline\n    description: Get all timeline instants for a Hudi table\n    server:\n      rest:\n        baseUrl: http://localhost:9090\n        path: /v1/hoodie/timeline/{tableName}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getTimeline\n        method: POST\n\n  - name: getCommitMetadata\n    description: Get write statistics for a specific Hudi commit\n    server:\n      rest:\n        baseUrl: http://localhost:9090\n        path: /v1/hoodie/timeline/{tableName}/commits/{commitTime}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getCommitMetadata\n        method: POST\n\n\
  \  - name: createTable\n    description: Create a new Apache Hudi table\n    server:\n      rest:\n        baseUrl: http://localhost:9090\n        path: /v1/hoodie/table\n        method: POST\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/createTable\n        method: POST\n\n  - name: getTable\n    description: Get configuration and metadata for a Hudi table\n    server:\n      rest:\n        baseUrl: http://localhost:9090\n        path: /v1/hoodie/table/{tableName}\n        method: GET\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/getTable\n        method: POST\n\n  - name: runCleaning\n    description: Trigger cleaning to remove old Hudi file versions\n    server:\n      rest:\n        baseUrl: http://localhost:9090\n        path: /v1/hoodie/table/{tableName}/clean\n        method: POST\n      mcp:\n        baseUrl: http://localhost:9090\n        path: /tools/runCleaning\n        method: POST\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-hudi/refs/heads/main/capabilities/hudi-lakehouse-management.yaml
tags: []
tools: []
---
