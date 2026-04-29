---
categories: []
consumed_apis:
- dms
description: Workflow capability for database engineers and cloud architects to manage end-to-end database migrations using AWS Database Migration Service. Covers replication instance provisioning, source and target endpoint configuration, replication task management, migration monitoring, and schema conversion support.
layout: capability
name: Amazon DMS Database Migration Management
operations:
- description: List all replication instances
  method: GET
  name: describe-replication-instances
  path: /v1/replication-instances
- description: Create a new replication instance
  method: POST
  name: create-replication-instance
  path: /v1/replication-instances
- description: List all endpoints
  method: GET
  name: describe-endpoints
  path: /v1/endpoints
- description: Create a source or target endpoint
  method: POST
  name: create-endpoint
  path: /v1/endpoints
- description: List all replication tasks
  method: GET
  name: describe-replication-tasks
  path: /v1/tasks
- description: Create a new replication task
  method: POST
  name: create-replication-task
  path: /v1/tasks
- description: List registered SSL certificates
  method: GET
  name: describe-certificates
  path: /v1/certificates
personas: []
provider_name: Amazon DMS
provider_slug: amazon-dms
search_terms:
- create a new replication task to migrate data between source and target
- describe replication instances
- create a source or target database endpoint for migration
- start or resume a database migration replication task
- replication instances and network configuration
- create a new replication instance
- describe table statistics
- list all replication tasks
- list all dms replication instances used for database migration processing
- delete a dms replication instance
- amazon dms
- stop a running database migration replication task
- create a source or target endpoint
- create a new replication task
- describe certificates
- describe connections
- replication task lifecycle and monitoring
- describe endpoints
- Database Engineer
- list ssl certificates for encrypted database migration connections
- create endpoint
- describe event subscriptions
- database
- database migration
- aws
- source and target database endpoints
- list registered ssl certificates
- list per-table migration statistics for a replication task
- replication instances for migration processing
- create replication instance
- stop replication task
- create replication task
- source and target database endpoint management
- list sns event subscriptions for migration notifications
- list all endpoints
- cloud architect designing database migration strategy and infrastructure
- list replication tasks and their current migration status
- create a new dms replication instance to process migration tasks
- start replication task
- delete replication instance
- Cloud Architect
- describe replication tasks
- ssl certificates for encrypted migration
- list all source and target database endpoints configured for migration
- replication tasks for migration
- test connection
- test the connection between a replication instance and an endpoint
- list all replication instances
- end-to-end database migration lifecycle using aws dms
- database engineer managing migration projects and monitoring replication tasks
- migration
- data replication
- list connections between replication instances and endpoints
slug: database-migration-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon DMS Database Migration Management\n  description: >-\n    Workflow capability for database engineers and cloud architects to manage\n    end-to-end database migrations using AWS Database Migration Service. Covers\n    replication instance provisioning, source and target endpoint configuration,\n    replication task management, migration monitoring, and schema conversion support.\n  tags:\n    - Amazon DMS\n    - Database Migration\n    - Data Replication\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: dms\n      location: ./shared/dms-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: database-migration-api\n      description: Unified REST API for Amazon DMS database migration\
  \ workflows.\n      resources:\n        - path: /v1/replication-instances\n          name: replication-instances\n          description: Replication instances for migration processing\n          operations:\n            - method: GET\n              name: describe-replication-instances\n              description: List all replication instances\n              call: \"dms.describe-replication-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-replication-instance\n              description: Create a new replication instance\n              call: \"dms.create-replication-instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/endpoints\n          name: endpoints\n          description: Source and target database endpoints\n          operations:\n            - method: GET\n              name: describe-endpoints\n\
  \              description: List all endpoints\n              call: \"dms.describe-endpoints\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-endpoint\n              description: Create a source or target endpoint\n              call: \"dms.create-endpoint\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tasks\n          name: replication-tasks\n          description: Replication tasks for migration\n          operations:\n            - method: GET\n              name: describe-replication-tasks\n              description: List all replication tasks\n              call: \"dms.describe-replication-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-replication-task\n              description: Create\
  \ a new replication task\n              call: \"dms.create-replication-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificates\n          name: certificates\n          description: SSL certificates for encrypted migration\n          operations:\n            - method: GET\n              name: describe-certificates\n              description: List registered SSL certificates\n              call: \"dms.describe-certificates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: database-migration-mcp\n      transport: http\n      description: MCP server for AI-assisted database migration management.\n      tools:\n        - name: describe-replication-instances\n          description: List all DMS replication instances used for database migration processing\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"dms.describe-replication-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-replication-instance\n          description: Create a new DMS replication instance to process migration tasks\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.create-replication-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-replication-instance\n          description: Delete a DMS replication instance\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"dms.delete-replication-instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-endpoints\n          description: List all source and target database endpoints configured\
  \ for migration\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-endpoints\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-endpoint\n          description: Create a source or target database endpoint for migration\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.create-endpoint\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: test-connection\n          description: Test the connection between a replication instance and an endpoint\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.test-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-replication-tasks\n          description: List replication tasks and their current migration\
  \ status\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-replication-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-replication-task\n          description: Create a new replication task to migrate data between source and target\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.create-replication-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-replication-task\n          description: Start or resume a database migration replication task\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.start-replication-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: stop-replication-task\n          description: Stop a running database\
  \ migration replication task\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"dms.stop-replication-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-table-statistics\n          description: List per-table migration statistics for a replication task\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-table-statistics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-connections\n          description: List connections between replication instances and endpoints\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-certificates\n          description: List SSL certificates\
  \ for encrypted database migration connections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-certificates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-event-subscriptions\n          description: List SNS event subscriptions for migration notifications\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"dms.describe-event-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-dms/refs/heads/main/capabilities/database-migration-management.yaml
tags:
- Amazon DMS
- Database Migration
- Data Replication
- AWS
tools:
- description: List all DMS replication instances used for database migration processing
  hints:
    openWorld: true
    readOnly: true
  name: describe-replication-instances
- description: Create a new DMS replication instance to process migration tasks
  hints:
    destructive: false
    readOnly: false
  name: create-replication-instance
- description: Delete a DMS replication instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-replication-instance
- description: List all source and target database endpoints configured for migration
  hints:
    openWorld: true
    readOnly: true
  name: describe-endpoints
- description: Create a source or target database endpoint for migration
  hints:
    destructive: false
    readOnly: false
  name: create-endpoint
- description: Test the connection between a replication instance and an endpoint
  hints:
    destructive: false
    readOnly: false
  name: test-connection
- description: List replication tasks and their current migration status
  hints:
    openWorld: true
    readOnly: true
  name: describe-replication-tasks
- description: Create a new replication task to migrate data between source and target
  hints:
    destructive: false
    readOnly: false
  name: create-replication-task
- description: Start or resume a database migration replication task
  hints:
    destructive: false
    readOnly: false
  name: start-replication-task
- description: Stop a running database migration replication task
  hints:
    destructive: false
    readOnly: false
  name: stop-replication-task
- description: List per-table migration statistics for a replication task
  hints:
    openWorld: true
    readOnly: true
  name: describe-table-statistics
- description: List connections between replication instances and endpoints
  hints:
    openWorld: true
    readOnly: true
  name: describe-connections
- description: List SSL certificates for encrypted database migration connections
  hints:
    openWorld: true
    readOnly: true
  name: describe-certificates
- description: List SNS event subscriptions for migration notifications
  hints:
    openWorld: true
    readOnly: true
  name: describe-event-subscriptions
---
