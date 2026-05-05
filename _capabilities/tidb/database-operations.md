---
api_specs:
- filename: tidb-cloud-api-openapi.yml
  format: yaml
  label: tidb-cloud
  slug: tidb-cloud
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tidb/refs/heads/main/openapi/tidb-cloud-api-openapi.yml
categories: []
consumed_apis:
- tidb-cloud
- tidb-data-service
description: Unified capability for database administrators and developers to manage TiDB Cloud clusters, backups, and data imports alongside executing SQL queries via the Data Service API. Covers cluster lifecycle management, backup scheduling, and data access workflows.
layout: capability
name: TiDB Cloud Database Operations
operations:
- description: List all TiDB Cloud clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Get details for a specific cluster
  method: GET
  name: get-cluster
  path: /v1/clusters/{clusterId}
- description: List backups for a cluster
  method: GET
  name: list-backups
  path: /v1/clusters/{clusterId}/backups
- description: List data import tasks for a cluster
  method: GET
  name: list-imports
  path: /v1/clusters/{clusterId}/imports
- description: Execute a natural language query against a TiDB database
  method: POST
  name: chat2query
  path: /v1/query
personas: []
provider_name: tidb
provider_slug: tidb
search_terms:
- list backups for a cluster
- cloud
- create a manual backup for a tidb cloud cluster
- cluster management
- execute a natural language instruction against a tidb cloud database. the ai generates and runs sql automatically. ideal for ad-hoc analysis.
- data access
- get cluster
- tidb
- list all tidb cloud clusters
- query with natural language
- get details for a specific cluster
- data import tasks
- create backup
- chat2query
- database
- list all backups for a tidb cloud cluster
- list cluster backups
- get detailed configuration and status for a specific tidb cloud cluster
- tidb cloud cluster management
- cluster backups
- list clusters
- list backups
- ai-powered sql queries
- list imports
- individual cluster details
- distributed sql
- execute a natural language query against a tidb database
- list import tasks
- list all tidb cloud clusters across projects
- list data import tasks for a cluster
- list data import tasks for a tidb cloud cluster
slug: database-operations
source_filename: database-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: TiDB Cloud Database Operations\n  description: >-\n    Unified capability for database administrators and developers to manage\n    TiDB Cloud clusters, backups, and data imports alongside executing SQL\n    queries via the Data Service API. Covers cluster lifecycle management,\n    backup scheduling, and data access workflows.\n  tags:\n    - TiDB\n    - Cloud\n    - Database\n    - Cluster Management\n    - Data Access\n    - Distributed SQL\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TIDB_CLOUD_PUBLIC_KEY: TIDB_CLOUD_PUBLIC_KEY\n      TIDB_CLOUD_PRIVATE_KEY: TIDB_CLOUD_PRIVATE_KEY\n      TIDB_DATA_APP_API_KEY: TIDB_DATA_APP_API_KEY\n\ncapability:\n  consumes:\n    - import: tidb-cloud\n      location: ./shared/tidb-cloud-api.yaml\n    - import: tidb-data-service\n      location: ./shared/tidb-data-service.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ tidb-operations-api\n      description: >-\n        Unified REST API for TiDB Cloud cluster management and data service operations.\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: TiDB Cloud cluster management\n          operations:\n            - method: GET\n              name: list-clusters\n              description: List all TiDB Cloud clusters\n              call: \"tidb-cloud.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters/{clusterId}\n          name: cluster-detail\n          description: Individual cluster details\n          operations:\n            - method: GET\n              name: get-cluster\n              description: Get details for a specific cluster\n              call: \"tidb-cloud.get-cluster\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters/{clusterId}/backups\n          name: cluster-backups\n          description: Cluster backups\n          operations:\n            - method: GET\n              name: list-backups\n              description: List backups for a cluster\n              call: \"tidb-cloud.list-backups\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters/{clusterId}/imports\n          name: cluster-imports\n          description: Data import tasks\n          operations:\n            - method: GET\n              name: list-imports\n              description: List data import tasks for a cluster\n              call: \"tidb-cloud.list-imports\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n\n        - path: /v1/query\n          name: natural-language-query\n          description: AI-powered SQL queries\n          operations:\n            - method: POST\n              name: chat2query\n              description: Execute a natural language query against a TiDB database\n              call: \"tidb-data-service.chat2query\"\n              with:\n                cluster_id: \"rest.cluster_id\"\n                database: \"rest.database\"\n                instruction: \"rest.instruction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tidb-operations-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted TiDB Cloud database operations and data access.\n      tools:\n        - name: list-clusters\n          description: List all TiDB Cloud clusters across projects\n          hints:\n            readOnly: true\n         \
  \   openWorld: false\n          call: \"tidb-cloud.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cluster\n          description: Get detailed configuration and status for a specific TiDB Cloud cluster\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tidb-cloud.get-cluster\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cluster-backups\n          description: List all backups for a TiDB Cloud cluster\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tidb-cloud.list-backups\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-backup\n          description: Create a manual\
  \ backup for a TiDB Cloud cluster\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tidb-cloud.create-backup\"\n          with:\n            clusterId: \"tools.clusterId\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-import-tasks\n          description: List data import tasks for a TiDB Cloud cluster\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tidb-cloud.list-imports\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-with-natural-language\n          description: >-\n            Execute a natural language instruction against a TiDB Cloud database.\n            The AI generates and runs SQL automatically. Ideal for ad-hoc analysis.\n          hints:\n            readOnly:\
  \ true\n            openWorld: false\n          call: \"tidb-data-service.chat2query\"\n          with:\n            cluster_id: \"tools.cluster_id\"\n            database: \"tools.database\"\n            instruction: \"tools.instruction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tidb/refs/heads/main/capabilities/database-operations.yaml
tags:
- TiDB
- Cloud
- Database
- Cluster Management
- Data Access
- Distributed SQL
tools:
- description: List all TiDB Cloud clusters across projects
  hints:
    openWorld: false
    readOnly: true
  name: list-clusters
- description: Get detailed configuration and status for a specific TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: get-cluster
- description: List all backups for a TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-cluster-backups
- description: Create a manual backup for a TiDB Cloud cluster
  hints:
    idempotent: false
    readOnly: false
  name: create-backup
- description: List data import tasks for a TiDB Cloud cluster
  hints:
    openWorld: false
    readOnly: true
  name: list-import-tasks
- description: Execute a natural language instruction against a TiDB Cloud database. The AI generates and runs SQL automatically. Ideal for ad-hoc analysis.
  hints:
    openWorld: false
    readOnly: true
  name: query-with-natural-language
---
